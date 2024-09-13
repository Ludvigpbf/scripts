# Create a New Script and Make it Executable

This script automates the creation of a new script file, makes it executable, and adds a shebang line to it. It can either use a user-provided directory or default to the Desktop directory.

## Prerequisites

- Unix-based system (Linux, macOS) or Windows with a compatible shell environment.
- `xdg-user-dir` command available (optional, for better Desktop directory detection on Unix-based systems).

## Usage

### <ins>_Method 1_</ins>: Provide Script Name and Folder Path

```bash
./create-script.sh <script-name> <scripts-folder-path>
```

Replace `<script-name>` with the desired name for your new script and `<scripts-folder-path>` with the path to the folder where you want to create the script.

### <ins>_Method 2_</ins>: Provide Only Script Name (Defaults to Desktop)

```bash
./create-script.sh <script-name>
```

Replace `<script-name>` with the desired name for your new script. The script will be created on the Desktop.

### <ins>_Method 3_</ins>: Using the Script from PATH

1. Add the Script to PATH:
   - Move the script to a directory that is included in your system's PATH. For example, you can move it to `/usr/local/bin` on Unix-based systems or a directory in your PATH on Windows.

```bash
mv create-script.sh /usr/local/bin/new-script
chmod +x /usr/local/bin/new-script
```

On Windows, you can add the script to a directory in your PATH and rename it to `new-script.bat` if necessary.

2. Run the Script:
   - You can now run the script from anywhere using the following command:

```bash
new-script <script-name> [scripts-folder-path]
```

Replace `<script-name>` with the desired name for your new script and `[scripts-folder-path]` with the optional path to the folder where you want to create the script.

## Script Details

1. Check if script name is provided:
   - If no script name is provided, the script exits with a usage message.
2. Set the scripts folder path:
   - If a folder path is provided, it uses that path.
   - If no folder path is provided, it attempts to use the Desktop directory:
     - On Unix-based systems, it uses xdg-user-dir DESKTOP if available.
     - Defaults to $HOME/Desktop if xdg-user-dir is not available.
3. Create a new script file in the scripts folder:
   - Uses the touch command to create a new script file.
4. Make the new script executable:
   - Uses the chmod +x command to make the script executable.
5. Add a shebang line to the new script:
   - Adds #!/bin/bash as the first line of the script.
6. Print a success message:
   - Prints a message indicating that the new script has been created and its location.

### Example

#### Creating a Script in a Specified Folder

```bash
./create-script.sh my-script.sh /path/to/scripts
```

This will create a new script named `my-script.sh` in the `/path/to/scripts` directory.

#### Creating a Script on the Desktop

```bash
./create-script.sh my-script.sh
```

This will create a new script named `my-script.sh` on the Desktop.

#### Running the Script from PATH
```bash
new-script my-script.sh /path/to/scripts
```
This will create a new script named ``my-script.sh`` in the ``/path/to/scripts`` directory.

## Notes

- Ensure you have the necessary permissions to create files in the specified directory.
- The script assumes a Unix-based environment for default paths and commands. Adjustments may be needed for other environments.

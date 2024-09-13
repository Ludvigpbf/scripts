# Create a new React project with Vite and a repo on your github

This script automates the creation of a new private GitHub repository and sets up a React project using a specified template or Vite.

## Prerequisites

- GitHub CLI (gh) installed and authenticated.
- Node.js and npm installed

## Usage

### <ins>_Method 1:_</ins> Direct Script Execution

```bash
./script.sh <project-name>
```

Replace `<project-name>` with the desired name for your new project.

### <ins>_Method 2:_</ins> Using the Script from PATH

1. Add the Script to PATH:
   - Move the script to a directory that is included in your system's PATH. For example, you can move it to /usr/local/bin on Unix-based systems or a directory in your PATH on Windows.

```bash
mv script.sh /usr/local/bin/new-react
chmod +x /usr/local/bin/new-react
```

On Windows, you can add the script to a directory in your PATH and rename it to `new-react.bat` if necessary.

2. Run the Script:
   - You can now run the script from anywhere using the following command:

```bash
new-react <project-name>
```

## Script Details

1. Check if a project name is provided:
   - If no project name is provided, the script exits with a usage message.
2. Set GitHub username and access token:
   - Replace yourUsername and your_github_access_token with your actual GitHub username and personal access token.
3. Authenticate with GitHub:
   - Uses the provided token to authenticate with GitHub.
4. Create a new private repository on GitHub:
   - Creates a new private repository with the provided project name.
5. Create a new directory for the project and navigate into it:
   - Creates a directory with the project name and navigates into it.
6. Project Setup Options:
   - V.1 <ins>*(Default)*</ins>: Clone a specified template repository and remove its ``.git`` folder.
   - V.2: Clone your own template repository and remove its ``.git`` folder (uncomment to use).
   - V.3: Create a new React project using Vite (uncomment to use).
     
7. Initialize a new git repository and set the remote origin:
    * Initializes a new git repository and sets the remote origin to the newly created GitHub repository.
8. Install project dependencies using npm:
    * Installs the project dependencies.
9. Add ``node_modules`` to ``.gitignore``:
    * Adds ``node_modules`` to the ``.gitignore`` file.
10. Stage all files and make the initial commit:
    * Stages all files and makes the initial commit.
11. Rename the default branch to ``main`` and push to the remote repository:
    * Renames the default branch to ``main`` and pushes the initial commit to the remote repository.
12. Print a success message:
    * Prints a message indicating that the new private repository has been set up.

## Example
```bash
./script.sh my-new-project
```
or
```bash
new-react my-new-project
```
This will create a new private repository named my-new-project, set up the project using the specified template or Vite, and push the initial commit to GitHub.
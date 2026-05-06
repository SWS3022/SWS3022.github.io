# Install Tools

This lesson prepares the tools needed for local development. For students new to software development, the important idea is this: tools are part of the system you build with. If the tools are not installed correctly, the application may fail before your own code runs.

## Required Tools

| Tool | Used for |
| --- | --- |
| Python 3.10 or newer | Running Flask and backend scripts |
| Node.js 20 LTS or newer | Running React development tools |
| Git | Downloading and tracking project code |
| Visual Studio Code | Editing code and using the terminal |
| A modern browser | Testing the application |

Python 3.8 can build this tutorial website, but students should use Python 3.10 or newer for the course project when possible.

## What These Tools Do

| Tool | What to remember |
| --- | --- |
| Python | Runs the Flask backend code. |
| `pip` | Installs Python packages such as Flask. |
| Node.js | Runs JavaScript tools outside the browser. |
| `npm` | Installs frontend packages such as React. |
| Git | Tracks project history and lets you compare changes. |
| Browser DevTools | Shows console errors, network requests, and responses. |

You do not need to master every tool before starting. You do need to know which tool is responsible for which kind of failure.

## Check Versions

Open a terminal and run:

```bash
python --version
node --version
npm --version
git --version
```

You should see version numbers rather than command-not-found errors.

## Example Output

Your exact versions may differ, but the output should look similar:

```text
Python 3.11.8
v20.14.0
10.7.0
git version 2.43.0
```

If one command fails, fix that tool before continuing. A broken setup causes confusing errors later.

## Terminal Basics

The terminal runs commands in a current folder. Many errors happen because the command is correct but the terminal is in the wrong folder.

Use these commands often:

| Command | Meaning |
| --- | --- |
| `pwd` | Show the current folder on macOS/Linux. |
| `Get-Location` | Show the current folder in PowerShell. |
| `ls` | List files on macOS/Linux. |
| `Get-ChildItem` | List files in PowerShell. |
| `cd folder-name` | Move into a folder. |

## Recommended Folder Layout

Create one folder for the course:

```text
sws3022-workspace/
  finsight-risk-dashboard/
```

Avoid spaces and non-English characters in the folder path. This reduces setup problems across Windows, macOS, and Linux.

## Manual Setup Check

Create the project folder and move into it:

```bash
mkdir sws3022-workspace
cd sws3022-workspace
mkdir finsight-risk-dashboard
cd finsight-risk-dashboard
```

Then confirm your current location:

```bash
pwd
```

On Windows PowerShell, use:

```powershell
Get-Location
```

## Development Mindset

When something fails, read the error from top to bottom and identify:

- The command that failed.
- The file or package mentioned.
- The first error message, not only the last line.

Debugging is not a side activity. It is part of building software.

## Common Setup Problems

| Symptom | Likely cause |
| --- | --- |
| `python` is not recognized | Python is not installed or not on PATH. |
| `npm` is not recognized | Node.js is not installed correctly. |
| `pip install` fails | Network, proxy, or virtual environment issue. |
| `npm install` fails | Wrong folder or package download issue. |
| PowerShell blocks activation | Script execution policy needs adjustment. |

Record the exact error message before asking for help. Screenshots are useful, but copied terminal text is usually better.

## Checkpoint

You are ready for the next lesson when:

- `python --version` works.
- `node --version` works.
- `npm --version` works.
- `git --version` works.
- Your course folder is named `finsight-risk-dashboard`.

## Review Questions

1. Why do we need both Python and Node.js?
2. What does `npm` install?
3. Why can running a command in the wrong folder cause an error?
4. Which tool would you inspect first if an API request returns `500`?

# Install Tools

This lesson prepares the tools needed for local development. Install the tools before running the starter project.

## Required Tools

| Tool | Used for |
| --- | --- |
| Python 3.10 or newer | Running Flask and backend scripts |
| Node.js 20 LTS or newer | Running React development tools |
| Git | Downloading and tracking project code |
| Visual Studio Code | Editing code and using the terminal |
| A modern browser | Testing the application |

Python 3.8 can build this tutorial website, but students should use Python 3.10 or newer for the course project when possible.

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

## Recommended Folder Layout

Create one folder for the course:

```text
sws3022-workspace/
  finsight-risk-dashboard/
```

Avoid spaces and non-English characters in the folder path. This reduces setup problems across Windows, macOS, and Linux.

## Development Mindset

When something fails, read the error from top to bottom and identify:

- The command that failed.
- The file or package mentioned.
- The first error message, not only the last line.

Debugging is not a side activity. It is part of building software.

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

On Windows PowerShell, you can also use:

```powershell
Get-Location
```

## Checkpoint

You are ready for the next lesson when all four version commands work:

```bash
python --version
node --version
npm --version
git --version
```

Also confirm that your course folder is named `finsight-risk-dashboard`.

## Review Questions

1. Why do we need both Python and Node.js?
2. What does `npm` install?
3. Why should a project folder path be simple?

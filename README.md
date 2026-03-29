# Lambda Function Deploy
For AWS Lambdas. A fast CI/CD tool for uploading, invoking, and logging lambdas - without having to wait on or go through GitHub Actions. Intended for rapid/incremental iteration where commits would not be useful.
<img width="1170" height="445" alt="screenshot" src="screenshot.png" />

## Installation
- Put the fndeploy file somewhere permanent. The file is a Bash shell script but **leave it without any extension** (ex: `"C:\Users\scale\Files\Dev\fndeploy\fndeploy"`)
- Add the fndeploy file to path by running this in a Bash terminal (substituting your path - be careful to use POSIX format here): `echo 'export PATH="$PATH:/c/Users/scale/Files/Dev/fndeploy"' >> ~/.bashrc`
- Reload your terminal: `source ~/.bashrc`

## Running
- Navigate to the folder of your lambda (ex: `cd "C:\Users\scale\Files\Dev\quickops\lambda\migrateDb"`)
- Run `fndeploy`, with optional flags (ex: `fndeploy -u` if you want to upload only and skip invocation)

## Arguments
| Flag | Description |
|------|------------|
| `-h`, `--help` | Help - prints out all available flags |
| `-u`, `--upload-only` | Upload only |
| `-i`, `--invoke-only` | Invoke only |

## Code Notes
- It gets the `FUNCTION_NAME` from the name of the parent folder
- It uses `awk` for all the colouring and also for removing some useless verbosity (such as the time being printed twice every line)

# Licence
This repo is licensed with AGPL3.0, a copyleft license.  
This licence ensures that this remains open source regardless of modifications or through being provided via a SaaS.  
Additionally, the software is provided "as is" with no warranty, and the authors or contributors are not liable for any damages arising from its use.  
All details are in the LICENSE file.
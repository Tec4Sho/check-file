# check-file-action

Use to check workspace (sh, cpp, c, h, mk, Makefile) files for errors and also locate any filename an display its content or search for a text (string) match located within all files.

- Search starts from github workspace or root directory on file types listed here for matches.


## Parameters:

- **filename :**  File name to search for in workspace directories. 

## Optional:

- **dirname :**  Your workspace directory name use only when needed.

- **rootdir :**  Search starts from root directory only when needed. true or false.

- **content :**  Display file & directory contents for filename found. true or false.

- **include :**  Check all #include <name> for errors in C/C++ filename. true or false.

- Support for wildcards is limited or untested if a filename is found multiple times in different directories all will be scanned. Or use dirname to add directory of files exact location to search.
- **Regex:** *.sh, *.cpp, *.h, *.c Makefile

Adding a name that is not a actual file check-file-action will then proceed with checking files for any **TEXT STRING MATCHES** of the provided information.

Any filename not listed for error checking if found will display file location and file contents if true.

Any filename or files found will be scanned for errors if they are of file types listed below only.
- .c
- .h
- .cpp
- .sh
- .mk
- Makefile

## Default report.
**Found in github action runner workflow logs.**

Check your (check-file-action) step output.

## Workflow actions.
**Steps usage example:**


    - name: Check File
      if: inputs.check-file != ''
      uses: Tec4Sho/check-file-action@master
      with:
        filename: ${{ inputs.check-file }}
        dirname: workspace
        rootdir: false
        content: true
        include: true
      continue-on-error: true


- Action runs using either cppcheck, shellcheck packages and checkmake linux development tools at their default debug settings.


- You can add a checkmake.ini file found above to your repo root directory to apply rules for checking Makefile types.

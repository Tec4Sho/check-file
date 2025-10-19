# check-file-action

Use to check workspace (mk, sh, cpp, c, h,) files for errors and also locate any filename an Show its content or search for a text (string) match located within all files. Search will start with the file types listed here first in build environment for matches.


Parameters :

• filename:  -- Add file name to search for in workspace build. 

Optional :

• dirname:  -- Add your workspace directory name only when needed.

• rootdir:  -- Add to search starting from root directory only when needed. Values are true or false.

• content:  -- Show all content in file & directory for filename found. Values are true or false.

Adding a name that is not a actual file check-file-action will then proceed with checking files for any TEXT STRING MATCHES of the provided information.

Any filename not listed for error checking if found will display file location and file contents.

Any filename or files found will be scanned for errors if they are of file types listed below only.
- .c
- .h
- .cpp
- .sh
- .mk
- Makefile

# Default report is found in workflow logs. Within (check-file-action) step.

Workflow actions steps usage example:


    - name: Check File
      if: inputs.check-file != ''
      uses: Tec4Sho/check-file-action@master
      with:
        filename: ${{ inputs.check-file }}
        dirname: workspace
        rootdir: false
        content: true
      continue-on-error: true


Action runs using either cppcheck, shellcheck packages and checkmake linux development tools at their default debug settings.

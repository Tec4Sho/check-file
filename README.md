# check-file-action
Use to check build (mk, sh, cpp, c, h,) files for errors and also locate any file containing a text (string) match.

Parameters:

filename: - Add file name to search for in workspace build. 

Optional:

dirname: - Add your workspace directory name only if needed.

rootdir: - true or false, add to search starting from root directory only if needed.

publish: - Add branch to publish report only if needed.

Adding a name that is not a actual file check-file-action will then proceed with checking files for any TEXT STRING MATCHES of the provided information.

Any file or files found will be scanned for errors if they are file types listed.
.c
.h
.cpp
.sh
.mk
Makefile

Action runs using cppcheck shellcheck and remake linux packages.

# myscripts
Scripts made to make life easy.

### Installation
> **Note:**
> - For the sake of simplicity and abstraction, extensions are not used instead shebang (#!) is preferred.
> - The directory containing scripts should be added to `PATH` environment to avoid using full path when executing the scripts.
> - Most of the dependencies should be already present on most systems but can be downloaded if needed using appropriate package manager like `pip` for python and `cpan` for perl.

***Unix based systems like linux or macos:***
Users can simply download scripts and make them executable using `chmod +x` to run.

***Windows:***
> Unix shell scripts like bash scripts aren't compatible with windows.

Users need to either add the proper extension, e.g. `.pl` for perl scripts, as windows doesn't support shebang functionality or execute the scripts by passing the script as argument to the appropriate interpreter.


## run
A script to to compile and run C/C++/Java/Python/Perl programs, compile and view Latex and HTML files. This script can be attached to a short key in an editor (like Vim) to run different types of files in an abstract way.

## remapLaptopKeyBoard
A script to remap a shortcircuited keyboard key to an unused keycode.

## addReqFile
Create requirements file for python projects that don't maintain it. pip freeze can be used to create requirements.txt file when packages are already installed, but to install packages use this script to create requirements file first.

## getbook
A script to search and download books using various query options like isbn or author. Simple to use while providing multiple options to modify default behaviour as per requirement.

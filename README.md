# Buildtool
## A simple wrapper script to manage the use of autotools

This script aims to complete the following:
- Shorten the commands required to simple ones, such as "./buildtool build"
- Be easily modifiable to add more commands
- Be very lightweight (94 lines of shell last time I checked)
- Remove unnecessary files during all but debug builds to keep the root directory clean

The actual script is called "buildtool", but I've provided an example project which should be fully set up. A simple "hello world" program is stored in "src/".

### Usage examples
- To build the project, do "./buildtool build". This will create an executable at "build/main". This command runs autotools, then configures and makes the program.
- To build debug builds, do "./buildtool debug1" or "./buildtool debug2" for less or more intermediary files left behind. By default the files created by autotools are removed, so this will let you see them.
- To build the project but stop and ask for confirmation at each stage, use "./buildtool slowbuild".
- To build a distribution release of the project, use "./buildtool build dist". This will create a tarball instead of a binary in "build/". The user should extract this, then simply run the standard "./configure && make && make install" to build their own copy.

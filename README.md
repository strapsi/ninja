```text
   _____   ____ ___  ________ 
  /     \ |    |   \/  _____/ 
 /  \ /  \|    |   /   \  ___ 
/    Y    \    |  /\    \_\  \
\____|__  /______/  \______  /
        \/                 \/

a command line tool to make the daily work easier
```

# Table of Contents

- [Commands](#commands)
    * [build](#build)
    * [commit](#commit)
    * [hash](#hash)
    * [log](#log)
    * [proxy](#proxy)
    * [run](#run)

# Commands
this is what mug can do for you
### build
runs a build command depending on the project type of the current working directory

supported project types:
- angular
  - `--profile, -p <profile>` angular build profile, e.g. `prod`
  - `--npm, -n` use npm build script instead of `ng build`
- npm
- gradle
  - `--gradle, -g` use native gradle script instead of gradlew
  - `--ignore-tests, -i` do not run tests
- go
  - `--target, -t <target>` build target, `linux` or `windows`
### commit
make a git commit with the be/beng specific commit tags. 

for this command to work the branch name has to be in a specific format:

`<type>-<jira-id>-cool-new-feature`

following types can be used:
- `feature, f`	
- `refactor, r`	
- `intern, i`	
- `style, s`	
- `bugfix, b`	
- `test, t`


`--add` add all changed files before the commit

`--type <type>` override the commit type that is derived from the branch name
### hash
prints out a sha512 hash of the given input string
### log
print out logs different types of logs, default is `git log`

- git
  - `--file-names, -n` print the file names of the changed files
  - `--limit, -l <n>` limit the output by n lines
- docker
  - `--docker, -d <fuzzy-name>` prints the docker log for the given container name, the name can be fuzzy
  - `--follow, -f` follow the log output
  - `--limit, -l <n>` limit the output by n lines
  
### proxy
### run
runs a "run" command depending on the project type of the current working directory, e.g. `ng serve` or `go run`

supported project types:
- angular
  - `--npm, -n` use npm build script instead of `ng build`
- npm
- gradle
  - `--gradle, -g` use native gradle script instead of gradlew
  - `--profile, -p <profile>` spring profile, add the param `-Pprofile` to the run command 
- go

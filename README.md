## Build this plugin locally: 
_gradlew buildPlugin_


## OpenInTerminal plugin
This is plugin for Intellij IDEA IDE. It's provide ability to open terminal with current file location by corresponding action in context menu (in editor and project view). 
You can also choose to open terminal in module directory instead of just parent directory of file. 

## Configuration
Before usage please set command and options for terminal app in plugin settings. 

#### Linux:

* Terminal command: _gnome-terminal_
* Options: _--working-directory_

#### Windows:

* Terminal command: _cmd /C start cmd.exe /K_
* Options: _cd /D_

#### Windows (Git Bash):

 * Create a link for _C:\Program Files\Git\git-bash.exe_ in _C:\WINDOWS\system32_ using the name _git-bash_
 * Create file _run-git-bash.cmd_ in _C:\WINDOWS\system32_ containing the single command: _cmd /C start git-bash --cd=%1_
 
 In a plugin settings: 
  - Terminal command: _run-git-bash.cmd_
  - Options: _leave this field empty_
    


#### Windows (with babun or cygwin):

 * Terminal command: _C:\<USER-DIRECTORY>\.babun\cygwin\bin\mintty.exe_
 * Options: _-i /Cygwin-Terminal.ico  C:\<USER-DIRECTORY>\.babun\cygwin\bin\bash.exe  -l -c "cd \"$0\" ; exec bash"_
  
#### Mac OS:

* Terminal command: _open -a Terminal_

If you are a Mac OS X user, please make sure that options mentioned in [following post on StackOverflow](http://stackoverflow.com/a/7054045) are enabled.

For all above configurations directory path will be added at the end of full command. For example full command which will be executed on above Linux configuration will be following: _gnome-terminal_ _--working-directory_ _"path_to_file_or_directory"_. 

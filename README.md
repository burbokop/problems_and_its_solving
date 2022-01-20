# problems_and_its_solving
This repo contains list of problems and tips how to solve them.


## Running postgresql server:

### issue 0: `EOF` error on query
Check port: `sudo netstat -plnt | grep "postgres"`

### issue 1: `password authentication failed for user` error
Run `ALTER USER user_name WITH PASSWORD 'new_password';` in `psql` shell:

### issue 2: How to setup sublime text hotkeys like in qt-creator
Go: Preferences -> Key Bindings<br/>
Copy the following text to `User` file.
```
[
	{ "keys": ["ctrl+space"], "command": "auto_complete" },
	{ "keys": ["ctrl+space"], "command": "replace_completion_with_auto_complete", "context":
		[
			{ "key": "last_command", "operator": "equal", "operand": "insert_best_completion" },
			{ "key": "auto_complete_visible", "operator": "equal", "operand": false },
			{ "key": "setting.tab_completion", "operator": "equal", "operand": true }
		]
	},
	//{ "keys": ["alt+shift+up"], "command": "select_lines", "args": {"forward": false} },
	//{ "keys": ["alt+shift+down"], "command": "select_lines", "args": {"forward": true} },
	{"keys": ["ctrl+i"], "command": "reindent", "args": {"single_line": false} },
	{ "keys": ["ctrl+r"], "command": "build", "args": {"select": true} }
]
```

### issue 3: Running conan from cmake
1. Create conanfile in folder with cmake
2. Add to cmake:
```
#conan section
message("Running conan...")
execute_process(COMMAND conan install --build=missing ${CMAKE_CURRENT_LIST_DIR} WORKING_DIRECTORY ${CMAKE_BINARY_DIR})
include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()
#conan section end
```

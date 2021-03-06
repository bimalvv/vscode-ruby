# Ruby Language and Debugging Support for Visual Studio Code

[![Join the chat at https://gitter.im/rebornix/vscode-ruby](https://badges.gitter.im/rebornix/vscode-ruby.svg)](https://gitter.im/rebornix/vscode-ruby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![Build Status](https://travis-ci.org/rebornix/vscode-ruby.svg?branch=master)](https://travis-ci.org/rebornix/vscode-ruby) [![Build status](https://ci.appveyor.com/api/projects/status/s4sv1fwpjeqmgnhd?svg=true)](https://ci.appveyor.com/project/rebornix/vscode-ruby)


This extension provides rich Ruby language and debugging support for Visual Studio Code. Fully tested against *inx/Windows and Ruby 1.9.3 to 2.2.0.
It's still in progress ( [GitHub](https://github.com/rebornix/vscode-ruby.git) ), please expect frequent updates with breaking changes before 1.0. If you are interested in this project, feel free to

* Subscribe to our [mailing list](http://eepurl.com/bTBAfv), get notified when we release new features or fix bugs.
* File GitHub [issues](https://github.com/rebornix/vscode-ruby/issues/new) anytime you ran into unexpected situations/bugs.
* Fork [our project](https://github.com/rebornix/vscode-ruby), hack it around and send us PRs!

## Install
### Install Extension
Press `F1`, type `ext install ruby`.

### Install Ruby Dependencies
In this extension, we implement [ruby debug ide protocol](http://debug-commons.rubyforge.org/protocol-spec.html) to allow VS Code to communicate with ruby debug, it requires `ruby-debug-ide` to be installed on your machine. This is also how RubyMine/NetBeans does by default.

- If you are using JRuby or Ruby v1.8.x (`jruby`, `ruby_18`, `mingw_18`)
  * `gem install ruby-debug-ide`, the latest version is `0.6.0`. Make sure `ruby-debug-base` is installed together with ruby-debug-ide`.
- If you are using Ruby v1.9.x (`ruby_19`, `mingw_19`)
  * `gem install ruby-debug-ide`, the latest version is `0.6.0`. Make sure `ruby-debug-base19x` is installed together with `ruby-debug-ide`.
- If you are using Ruby v2.0.x
  * `gem install ruby-debug-ide -v 0.4.32` or higher versions
  * `gem install debase -v 0.2.1` or higher versions

### Add VS Code config to your project
Go to the debugger view of VS Code and hit the gear icon. Choose Ruby or Ruby Debugger from the prompt window, then you'll get the sample launch config in `.vscode/launch.json`

```
{
	"version": "0.2.0",
	"configurations": [
		{
			"name": "Debug Local File",
			"type": "Ruby",
			"request": "launch",
			"program": "${workspaceRoot}/main.rb"
		},
		{
			"name": "Rails server",
			"type": "Ruby",
			"request": "launch",
			"cwd": "${workspaceRoot}",
			"program": "${workspaceRoot}/bin/rails",
			"args": ["server"]
		},
		{
			"name": "Listen for rdebug-ide",
			"type": "Ruby",
			"request": "attach",
			"cwd": "${workspaceRoot}",
			"remoteHost": "127.0.0.1",
			"remotePort": "1234",
			"remoteWorkspaceRoot": "${workspaceRoot}"
		}
	]
}
```

## Detailed instruction of debugging Ruby Scripts/Rails/etc
Read following instructions about how to debug ruby/rails/etc locally or remotely
- [Debug Ruby Scripts](https://github.com/rebornix/vscode-ruby/wiki/2.-Debug-ruby-scripts)
- [Debug Rails App](https://github.com/rebornix/vscode-ruby/wiki/3.-Debug-Rails-App)
- [Attach to process](https://github.com/rebornix/vscode-ruby/wiki/4.-Attach-to-process)

## Features

- Ruby scripts debugging
  * Line breakpoints (add, delete, disable, enable)
  * Step over, step in, step out, continue, pause
  * Multiple, parallel threads
  * Call stack
  * Scope variables
  * Debug console
  * Watch window
  * Variables evaluate/inspect
  * Stop on entry
  * Breaking on uncaught exceptions and errors
  * Attach requests
- Ruby remote debug
- Rails

## TODO
- Ruby scripts debugging
  * Conditional breakpoints
- Unit/Integration tests debugging
  * RSpec
  * Cucumber
  * Shoulda
  * Test::Unit
- Rack
- Rake
- Gem
- IRB console
- IntelliSense and autocomplete
- Linting

## Main contributors

- [@rebornix](https://github.com/rebornix)
- [@HookyQR](https://github.com/HookyQR)

## License

This extension is [licensed under the MIT License](LICENSE.txt).

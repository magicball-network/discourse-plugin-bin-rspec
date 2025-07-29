# Discourse plugin bin/rspec

This repository provides a script to execute RSpec from within the a Discourse plugin's own directory. 
The `bin/rspec` script will execute Discourse's [bin/rspec]([url](https://github.com/discourse/discourse/blob/main/bin/rspec)) script but it will correct the paths so that only the plugin's tests are executed.

## Installation

Just drop the script in `bin/rspec` and you can execute it from the plugin's directory

Execute all tests in the `spec` directory:

```
elmuerte@devstation:~/discourse/plugins/discourse-example$ ./bin/rspec
```

Execute a specific test case:

```
elmuerte@devstation:~/discourse/plugins/discourse-example$ ./bin/rspec path/to/a_spec.rb:37:87
```

## Ruby LSP

When this `bin/rspec` script is executed via [Ruby LSP RSpec](https://github.com/st0012/ruby-lsp-rspec) (version 0.1.27 or later) it adds some additional corrections so that the correct feedback to ruby-lsp is given.

With this script you will be able to use the plugin's directory as a project root, in for example VS Code, and still have the full functionality offered by ruby-lsp and ruby-lsp-rspec:

- Executing all tests, or an individual test
- Test debugging
- Testing with coverage reporting

Ruby LSP RSpec will automatically use the `bin/rspec` when it finds it in the project root, no additional configuration is needed.

# VS code python setup

## Handy VS code tidbits for python

### Setup

- code-runner
- python

## Set default code-runner output to python3

By default code-runner will execute 'python'. I use python3 so to defeat that
you need to change the code-runner setup. Search settings for 
`code-runner.executorMap`. Change this to `python3` if using a distro
that uses python2 by default, or if `python` means python2 rather than 3, al a Ubuntu.

This **does not** respect virtualenv's.

Below will fix that.

### Run code-runner in terminal

To use virtualenv's you can alter the `code-runner.runInTerminal` to `true`.
This will run in the terminal and if you have setup virtualenv's it will be 
run within that. 

### Set virtualenvwrapper location

Set virtualenv location via `python.venvPath`. If using `virtualenvwrapper` this
could be something like `~/.virtualenvs`.

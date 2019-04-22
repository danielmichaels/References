# Boostnote Vim

Boostnote is pretty awesome and comes with built in vim support. As a vim power user I struggle unmapping my mind from 'jk' when escaping modes.

Happily, typing the following inside the dev tools console will remap Boostnote's default codeMirror Esc to 'jk'.

```shell
CodeMirror.Vim.map('jk', '<Esc>', 'insert')
```

Vim!

# iPython 6.5 Vim Keybindings

**Taken from [SO](https://stackoverflow.com/questions/38443907/how-does-one-set-specific-vim-bindings-in-ipython-5-0-0/38810821#38810821) user [jellycola](https://stackoverflow.com/users/2340015/jellycola)**


According to the IPython docs, you can specify Keyboard Shortcuts in a startup configuration script.

Instead of rebinding jk to ESC, I'm making a unicode "j" (u'j') followed by a unicode "k" (u'k') inside of VimInsertMode() a shortcut for a prompt_toolkit event that switches to navigation mode.

I created a `.ipython/profile_default/startup/keybindings.py` with the following code:

```python
from IPython import get_ipython
from prompt_toolkit.enums import DEFAULT_BUFFER
from prompt_toolkit.filters import HasFocus, ViInsertMode
from prompt_toolkit.key_binding.vi_state import InputMode


ip = get_ipython()

def switch_to_navigation_mode(event):
    vi_state = event.cli.vi_state
    vi_state.reset(InputMode.NAVIGATION)

if getattr(ip, 'pt_cli'):
    registry = ip.pt_cli.application.key_bindings_registry
    registry.add_binding(u'j',u'k',
                         filter=(HasFocus(DEFAULT_BUFFER)
                                 & ViInsertMode()))(switch_to_navigation_mode)

```

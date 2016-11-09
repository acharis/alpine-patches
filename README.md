My Alpine/Re-Alpine Patches
===========================

I wanted the embedded editor in my email client to have emacs keybindings.

These patches implement support for the following keys:
 - Ctrl+Del -> delete forward word (kill-word)
 - Ctrl+Backarrow -> delete backward word (backward-kill-word)
 - Ctrl+Up -> move to beginning of paragraph (backward-paragraph)
 - Ctrl+Down -> move to end of paragraph (forward-paragraph)
 - Alt+B -> move backward word (backward-word)
 - Alt+D -> delete forward word  (kill-word)
 - Alt+F -> move forward word (forward-word)

It removes the binding of Ctrl+U to yank and changes the binding of Ctrl+Y to yank instead of move backward page.

Tested on Arch Linux (running kernel 4.8.2 if you think that matters) in XTerm(327).

To get XTerm to transmit Ctrl+Backarrow to alpine/re-alpine I put the following in my .Xresources:

```
  XTerm*VT100.translations: #override \n\
   Ctrl ~Alt ~Shift <Key>BackSpace: string("\033[5;8~")
```

I release these files under WTFPL.

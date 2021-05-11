# Modal Mapping

In the last chapter we talked about how to map keys in Vim. We used the map command
which made the keys work in normal mode. If you played around a bit before moving on
to this chapter, you may have noticed that the mappings also took effect in visual mode.

You can be more specific about when you want mappings to apply by using nmap, vmap,
and imap. These tell Vim to only use the mapping in normal, visual, or
insert mode respectively.

Run this command:

```vim
:nmap \ dd
```

Now put your cursor in your text file, make sure you're in normal mode, and press \.
Vim will delete the current line.

Now enter visual mode and try pressing \. Nothing will happen, because we told
Vim to only use that mapping in normal mode (and \ doesn't do anything by default).

Run this command:

```vim
:vmap \ U
```
Enter visual mode and select some text, then press \. Vim will convert the text
to uppercase!

Try the \ key a few times in normal and visual modes and notice that it now does 
something completely different depending on which mode you're in.



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

## Muscle Memory

At first the idea of mapping the same key to do different things depending on which
mode you're in may sound like a terrible idea. Why would you want to have to stop and
think which mode you're in before pressing the key? Wouldn't that negate any time you
save from the mapping itself?

In practice it turns out that this isn't really a problem. Once you start using Vim
often you won't be thinking about the individual keys you're typing any more.
You'll think: "delete a line" and not "press dd". Your fingers and brain will
learn your mappings and the keys themselves will become subconscious.

## Insert Mode

Now that we've covered how to map keys in normal and visual mode, let's move on to insert mode.
Run this command:

```vim
:imap <c-d> dd
```
You might think that this would let you press Ctrl+d whenever you're in insert mode to delete
the current line. This would be handy because you wouldn't need to go back into normal
mode to cut out lines.

The problem is that Vim is doing exactly what we told it to. We said:
"when I press &lt;c-d&gt; I want you to do what pressing d and d would normally do".
Well, normally when you're in insert mode and press the d key twice, you get
two ds in a row!

To make this mapping do what we intended we need to be very explicit.
Run this command to change the mapping:

```vim
:imap <c-d> <esc>dd
```

Created by José Vitor based on https://learnvimscriptthehardway.stevelosh.com/

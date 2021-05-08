# Basic Mapping

If there's one feature of Vimscript that will let you bend Vim to your will more than any other, it's the ability to map keys. Mapping keys lets you tell Vim:

When I press this key, I want you to do this stuff instead of whatever you would normally do.

We're going to start off by mapping keys in normal mode. We'll talk about how to map keys in insert and other modes in the next chapter.

Type a few lines of text into a file, then run:

```vim
:map - x
```

Put your cursor somewhere in the text and press -. Notice how Vim deleted the character under the cursor, just like if you had pressed x.

We already have a key for "delete the character under the cursor", so let's change that mapping to something slightly more useful. Run this command:

```vim
:map - dd
```

Now put your cursor on a line somewhere and press - again. This time Vim deletes the entire line, because that's what dd does.

## Special Characters

You can use &lt;keyname&gt; to tell Vim about special keys. Try running this command:

```vim
:map <space> viw
```

Put your cursor on a word in your text and press the space bar. Vim will visually select the word.

You can also map modifier keys like Ctrl and Alt. Run this:

```vim
:map <c-d> dd
```

Now pressing Ctrl+d on your keyboard will run dd.


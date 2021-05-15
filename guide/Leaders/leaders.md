# Leaders

We've learned how to map keys in a way that won't make us want to tear our hair out later,
but you might have noticed one more problem.

Every time we do something like :nnoremap &lt;space&gt; dd we've overwritten what &lt;space&gt; normally
does. What if we need that key later?

There are a bunch of keys that you don't normally need in your day-to-day Vim usage. -, H, L, 
&lt;space&gt;, &lt;cr&gt;, and &lt;bs&gt; do things that you almost never need (in normal mode, of course). 
Depending on how you work you may find others that you never use.

Those are safe to map, but that only gives us six keys to work with. What happened
to Vim's legendary customizability?

## Mapping Key Sequences

Unlike Emacs, Vim makes it easy to map more than just single keys. Run these commands:

```vim
:nnoremap -d dd
:nnoremap -c ddO
```

Try them out by typing -d and -c (quickly) in normal mode. The first creates a custom mapping to 
delete a line, while the second "clears" a line and puts you into insert mode.

This means you can pick a key that you don't care about (like -) as a "prefix" key and create mappings
on top of it. It means you'll have to type an extra key to activate the mappings, but one extra
keystroke can easily be absorbed into muscle memory.

If you think this might be a good idea, you're right, and it turns out that Vim already has mechanisms
for this "prefix" key!



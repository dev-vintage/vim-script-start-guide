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

## Leader 

Vim calls this "prefix" key the "leader". You can set your leader key to whatever you like. 
Run this command:

```vim
:let mapleader = "-"
```

You can replace - with any key you like. I personally like , even though it shadows a useful 
function, because it's very easy to type.

When you're creating new mappings you can use <leader> to mean "whatever I have my leader key setto".
Run this command:

```vim
:nnoremap <leader>d dd
```

Now try it out by pressing your leader key and then d. Vim will delete the current line.

Why bother with setting &lt;leader&gt; at all, though? Why not just include your "prefix" key directly 
in your mapping commands? There are three good reasons.

First of all, you may decide you need the normal function of your leader later on down the road.
Defining it in one place makes it easy to change later.

Second, when someone else is looking at your ~/.vimrc file they'll immediately know what you mean
when you say &lt;leader&gt;. They can simply copy your mapping into their own ~/.vimrc if they like it
even if they use a different leader.

Finally, many Vim plugins create mappings that start with &lt;leader&gt;. If you've already got it set 
up they'll work properly and will feel familiar right out of the box.



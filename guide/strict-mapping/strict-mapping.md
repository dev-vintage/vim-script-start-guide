## Strict Mapping

Get ready, because things are about to get a little wild.

So far we've used map, nmap, vmap, and imap to create key mappings that
will save time. These work, but they have a downside. Run the following commands:

```vim
:nmap - dd
:nmap \ -
```

Now try pressing \ (in normal mode). What happens?

When you press \ Vim sees the mapping and says "I should run - instead". But we've 
already mapped - to do something else! Vim sees that and says "oh, now I need to run dd", and so it deletes the current line.

When you map keys with these commands Vim will take other mappings into account. 
This may sound like a good thing at first but in reality it's pure evil. Let's talk
about why, but first remove those mappings by running the following commands:

```vim
:nunmap -
:nunmap \
```

## Recursion

Run this command:

```vim
:nmap dd O<esc>jddk
```

At first glance it might look like this would map dd to:

Open a new line above this one.
Exit insert mode.
Move back down.
Delete the current line.
Move up to the blank line just created.
Effectively this should "clear the current line". Try it.

Vim will seem to freeze when you press dd. If you press &lt;c-c&gt; you'll get Vim back, 
but there will be a ton of empty lines in your file! What happened?

This mapping is actually recursive! When you press dd, Vim says:

dd is mapped, so perform the mapping.
Open a line.
Exit insert mode.
Move down a line.
dd is mapped, so perform the mapping.
Open a line.
Exit insert mode.
Move down a line.
dd is mapped, so perform the mapping, and so on.
This mapping can never finish running! Go ahead and remove this
terrible thing with the following command:

```vim
:nunmap dd
```

## Side Effects

One downside of the *map commands is the danger of recursing. Another is that their behavior can change if you install a plugin that maps keys they depend on.

When you install a new Vim plugin there's a good chance that you won't use and memorize every mapping it creates. Even if you do, you'd have to go back and look through your ~/.vimrc file to make sure none of your custom mappings use a key that the plugin has mapped.

This would make installing plugins tedious and error-prone. There must be a better way.




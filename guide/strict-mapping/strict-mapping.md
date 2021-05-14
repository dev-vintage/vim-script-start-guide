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



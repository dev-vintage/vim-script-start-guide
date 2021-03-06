# Echoing Messages

The first pieces of Vimscript we'll look at are the echo and echom commands.

You can read their full documentation by running **:help echo** and **:help** echom in Vim. As you go through this book you should try to read the **:help** for every new command you encounter to learn more about them.

Try out echo by running the following command:

```vim
:echo "Hello, world!"
```

You should see Hello, world! appear at the bottom of the window.

## Persistent Echoing

Now try out **echom** by running the following command.
```vim
:echom "Hello again, world!"
```

You should see Hello again, world! appear at the bottom of the window.

To see the difference between these two commands, run the following:

```vim
:messages
```

You should see a list of messages. Hello, world! will not be in this list, but Hello again, world! will be in it.

When you're writing more complicated Vimscript later in this book you may find yourself wanting to "print some output" to help you debug problems. Plain old :echo will print output, but it will often disappear by the time your script is done. Using :echom will save the output and let you run :messages to view it later.

## Comments

Before moving on, let's look at how to add comments. When you write Vimscript code (in your ~/.vimrc file or any other one) you can add comments with the " character, like this:

```vim
" Make space more useful
nnoremap <space> za
```

This doesn't always work (that's one of those ugly corners of Vimscript), but in most cases it does. Later we'll talk about when it won't (and why that happens).

Let a star please!!

Created by José Vitor based on https://learnvimscriptthehardway.stevelosh.com/

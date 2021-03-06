# Setting Options

Vim has many options you can set to change how it behaves.

There are two main kinds of options: boolean options (either "on" or "off") and options that take a value.

### Boolean Options

Run the following command:
```vim
:set number
```
Line numbers should appear on the left side of the window if they weren't there already. Now run this:
```vim
:set nonumber
```
The line numbers should disappear. number is a boolean option: it can be off or on. You turn it "on" by running :set number and "off" with :set nonumber.

All boolean options work this way. :set name turns the option on and :set noname turns it off.

### Toggling Boolean Options

You can also "toggle" boolean options to set them to the opposite of whatever they are now. Run this:
```vim
:set number!
```
The line numbers should reappear. Now run it again:
```vim
:set number!
```
They should disappear once more. Adding a ! (exclamation point or "bang") to a boolean option toggles it.

### Checking Options

You can ask Vim what an option is currently set to by using a ?. Run these commands and watch what happens after each:
```vim
:set number
:set number?
:set nonumber
:set number?
```

Notice how the first :set number? command displayed number while the second displayed nonumber.

### Options with Values

Some options take a value instead of just being off or on. Run the following commands and watch what happens after each:

```vim
:set number
:set numberwidth=10
:set numberwidth=4
:set numberwidth?
```

The numberwidth option changes how wide the column containing line numbers will be. You can change non-boolean options with :set &lt;name&gt;=&lt;value&gt;, and check them the usual way (:set &lt;name&gt;?).

Try checking what a few other common options are set to:

```vim
:set wrap?
:set shiftround?
:set matchtime?
```

### Setting Multiple Options at Once

Finally, you can specify more than one option in the same :set command to save on some typing. Try running this:

```vim
:set numberwidth=2
:set nonumber
:set number numberwidth=6
```

Notice how both options were set and took effect in the last command.

Created by Jos?? Vitor based on https://learnvimscriptthehardway.stevelosh.com/
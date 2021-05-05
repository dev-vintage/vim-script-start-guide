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




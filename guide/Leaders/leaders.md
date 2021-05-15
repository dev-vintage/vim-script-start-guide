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



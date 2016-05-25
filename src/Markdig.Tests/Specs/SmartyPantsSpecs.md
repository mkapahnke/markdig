# Extensions

Adds support for smarty pants:

## SmartyPants Quotes
 
Converts the following character to smarty pants:

```````````````````````````````` example
This is a "text"
.
<p>This is a &ldquo;text&rdquo;</p>
````````````````````````````````

```````````````````````````````` example
This is a 'text'
.
<p>This is a &lsquo;text&rsquo;</p>
````````````````````````````````

```````````````````````````````` example
This is a <<text>>
.
<p>This is a &laquo;text&raquo;</p>
````````````````````````````````

Unbalanced quotes are not changed:

```````````````````````````````` example
This is a "text
.
<p>This is a &quot;text</p>
````````````````````````````````

```````````````````````````````` example
This is a 'text
.
<p>This is a 'text</p>
````````````````````````````````

```````````````````````````````` example
This is a <<text
.
<p>This is a &lt;&lt;text</p>
````````````````````````````````

Unbalanced quotes inside other quotes are not changed:

```````````````````````````````` example
This is a "text 'with" a another text'
.
<p>This is a &ldquo;text 'with&rdquo; a another text'</p>
````````````````````````````````

```````````````````````````````` example
This is a 'text <<with' a another text>>
.
<p>This is a &lsquo;text &lt;&lt;with&rsquo; a another text&gt;&gt;</p>
````````````````````````````````

```````````````````````````````` example
This is a <<text 'with>> a another text'
.
<p>This is a &laquo;text 'with&raquo; a another text'</p>
````````````````````````````````

Quotes requires to have the same rules than emphasis `_` regarding left/right frankling rules:

```````````````````````````````` example
It's not quotes'
.
<p>It's not quotes'</p>
````````````````````````````````

```````````````````````````````` example
They are ' not matching quotes '
.
<p>They are ' not matching quotes '</p>
````````````````````````````````

```````````````````````````````` example
They are' not matching 'quotes
.
<p>They are' not matching 'quotes</p>
````````````````````````````````

Double quotes using ``` `` ``` are working if they match another `''` pair, and there is no other double quotes on the line (otherwise they would be parsed as a code span):

```````````````````````````````` example
This is ``a double quote''
.
<p>This is &ldquo;a double quote&rdquo;</p>
````````````````````````````````

```````````````````````````````` example
This is ``a code span''`` 
.
<p>This is <code>a code span''</code></p>
````````````````````````````````

An emphasis starting inside left/right quotes will span over the right quote:

```````````````````````````````` example
This is "a *text" with an emphasis*
.
<p>This is &ldquo;a <em>text&rdquo; with an emphasis</em></p>
````````````````````````````````

## SmartyPants Separators

```````````````````````````````` example
This is a -- text
.
<p>This is a &ndash; text</p>
````````````````````````````````

```````````````````````````````` example
This is a --- text
.
<p>This is a &mdash; text</p>
````````````````````````````````

```````````````````````````````` example
This is a en ellipsis...
.
<p>This is a en ellipsis&hellip;</p>
````````````````````````````````
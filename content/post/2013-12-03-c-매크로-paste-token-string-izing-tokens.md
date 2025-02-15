---
title: 'C 매크로: Paste Token, String-izing Tokens'
author: openmicrolab
type: post
date: 2013-12-03T00:02:14+00:00
url: /c-매크로-paste-token-string-izing-tokens/
dsq_thread_id:
  - "2210552693"
categories:
  - Development
  - Tip
tags:
  - C 매크로
  - Paste Token
  - String-izing Tokens

---
### Pasting Tokens

Each argument passed to a macro is a token, and sometimes it might be expedient to paste arguments together to form a new token. This could come in handy if you have a complicated structure and you&#8217;d like to debug your program by printing out different fields. Instead of writing out the whole structure each time, you might use a macro to pass in the field of the structure to print.

To paste tokens in a macro, use ## between the two things to paste together.

For instance

<pre><strong>#define BUILD_FIELD(field) my_struct.inner_struct.union_a.##field
</strong></pre>

Now, when used with a particular field name, it will expand to something like

<pre><strong>my_struct.inner_struct.union_a.field1
</strong></pre>

The tokens are literally pasted together.

### String-izing Tokens

Another potentially useful macro option is to turn a token into a string containing the literal text of the token. This might be useful for printing out the token. The syntax is simple&#8211;simply prefix the token with a pound sign (#).

<pre><strong>#define PRINT_TOKEN(token) printf(#token " is %d", token)
</strong></pre>

For instance, PRINT_TOKEN(foo) would expand to

<pre><strong>printf("&lt;foo&gt;" " is %d" &lt;foo&gt;)
</strong></pre>

(Note that in C, string literals next to each other are concatenated, so something like &#8220;token&#8221; &#8221; is &#8221; &#8221; this &#8221; will effectively become &#8220;token is this&#8221;. This can be useful for formatting printf statements.)

For instance, you might use it to print the value of an expression as well as the expression itself (for debugging purposes).

<pre><strong>PRINT_TOKEN(x + y);
</strong></pre>

출처: <a href="http://www.cprogramming.com/tutorial/cpreprocessor.html " target="_blank">http://www.cprogramming.com/tutorial/cpreprocessor.html </a>
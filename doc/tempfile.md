

# Module tempfile #
* [Data Types](#types)
* [Function Index](#index)
* [Function Details](#functions)

Copyright (c) 2014 Finexkap, 2016 BotsUnit

Erlang module for managing temporary files

__Behaviours:__ [`gen_server`](gen_server.md).

__Authors:__ Gregoire Lejeune ([`gl@finexkap.com`](mailto:gl@finexkap.com)), Grégoire Lejeune ([`gregoire.lejeune@botsunit.com`](mailto:gregoire.lejeune@botsunit.com)).

<a name="types"></a>

## Data Types ##




### <a name="type-tmpname_option">tmpname_option()</a> ###


<pre><code>
tmpname_option() = {ext, string()} | {path, string()}
</code></pre>




### <a name="type-tmpname_options">tmpname_options()</a> ###


<pre><code>
tmpname_options() = [<a href="#type-tmpname_option">tmpname_option()</a>]
</code></pre>

<a name="index"></a>

## Function Index ##


<table width="100%" border="1" cellspacing="0" cellpadding="2" summary="function index"><tr><td valign="top"><a href="#name-1">name/1</a></td><td>Equivalent to <a href="#name-2"><tt>name(Prefix, [])</tt></a>.</td></tr><tr><td valign="top"><a href="#name-2">name/2</a></td><td> 
Get a temporary file name.</td></tr></table>


<a name="functions"></a>

## Function Details ##

<a name="name-1"></a>

### name/1 ###

`name(Prefix) -> any()`

Equivalent to [`name(Prefix, [])`](#name-2).

<a name="name-2"></a>

### name/2 ###

<pre><code>
name(Prefix::string(), Options::<a href="#type-tmpname_options">tmpname_options()</a>) -&gt; string()
</code></pre>
<br />


Get a temporary file name

Options:

* `ext` : temp file extension (default: `.tmp`)
* `path` : temp file path (default: `ostemp:dir()`)

Examples:

```erlang

 1> tempfile:name("prefix_").
 "/tmp/prefix_ZL7YmS5HRQodKpOfEAaO.tmp"
 2> tempfile:name("prefix_", [{ext, "toto"}]).
 "/tmp/prefix_RbmrP0wsde4NNwhBzzer.toto"
 3> tempfile:name("prefix_", [{ext, ".toto"}]).
 "/tmp/prefix_0OSbH34VQlLbVtbSHFtj.toto"
 4> tempfile:name("prefix_", [{ext, ".toto"}, {path, "."}]).
 "./prefix_Sa7BFnEzS6h862jmXQdy.toto"
```


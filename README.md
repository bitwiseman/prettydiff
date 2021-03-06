Try it online at [http://prettydiff.com/](http://prettydiff.com/).

![Pretty Diff logo](http://prettydiff.com/images/pdlogoxs.svg) Pretty Diff
===

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/prettydiff/prettydiff?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![npm version](https://badge.fury.io/js/prettydiff.svg)](http://badge.fury.io/js/prettydiff)
[![Dependency Status](https://david-dm.org/prettydiff/prettydiff.svg)](https://david-dm.org/prettydiff/prettydiff)

[![NPM stats](https://nodei.co/npm/prettydiff.svg?downloadRank=true&downloads=true)](https://www.npmjs.org/package/prettydiff)

Summary
---

Language aware code comparison tool for several web based languages. It also beautifies, minifies, and a few other things.

Benefits - see [overview page](http://prettydiff.com/overview.xhtml) for more details
---

* [React JSX format support](http://prettydiff.com/guide/react_jsx.xhtml)
* LESS, SCSS (Sass), and CSS support
* Separate support for XML and HTML
* [Recursive command line directory diff](http://prettydiff.com/guide/diffcli.xhtml)
* [JavaScript scope in colors](http://prettydiff.com/guide/jshtml.xhtml)
* [Supports presets for popular styleguides](http://prettydiff.com/guide/styleguide.xhtml)
* [Markup beautification with optional opt out](http://prettydiff.com/guide/tag_ignore.xhtml)
* [JavaScript auto correction](http://prettydiff.com/guide/jscorrect.xhtml)
* [Supports a ton of options](http://prettydiff.com/documentation.php#function_properties)

Run with Node.js / io.js / CommonJS / RequireJS
---

Node.js and io.js support is provided by api/node-local.js.  This file can execute in the following modes:

* auto - Determine if the resource is text, a file, or a directory and process as such (except that directories are processed with the subdirectory option)
* screen - code input is on the command line and output is to the command line
* filescreen - code input is in a file and the output is to the command line
* file - the input and the output reside in files
* directory - everything in a directory is processed into a specified output directory except ".", "..", and subdirectories
* subdirectory - process the entire directory tree

**Execute in the context of a NodeJS application**

First install the prettydiff package locally

    npm install prettydiff

Add this code to your application

    var prettydiff = require("prettydiff"),
        args       = {
            source: "asdf",
            diff  : "asdd",
            lang  : "text"
        },
        output     = prettydiff.api(args);

**Execute from the command line**

First install the prettydiff package globally

    npm install prettydiff -g

Run in windows

    prettydiff source:"c:\myDirectory" readmethod:"subdirectory" diff:"c:\myOtherDirectory"

Run in Linux and OSX

    prettydiff source:"myDirectory" mode:"beautify" readmethod:"subdirectory" output:"path/to/outputDirectory"
    
To see a *man* page provide no arguments or these: help, man, manual

    prettydiff
    prettydiff help
    prettydiff man

To see only the version number supply only *v* or *version* as an argument:

    prettydiff v
    prettydiff version

Run in a web browser with api/dom.js
---

Please feel free to use prettydiff.com.xhtml file to supplement dom.js.  Otherwise, dom.js requires supplemental assistance to map DOM nodes from an HTML source.  dom.js is fault tolerant so nodes mapped to the supplied prettydiff.com.xhtml don't need to be supported from custom HTML.

To run Pretty Diff using dom.js include the following two script tags and bind the pd.recycle() function to the executing event.  Please refer to prettydiff.com.xhtml for an HTML example and documentation.xhtml for option and execution information.

    <script type="application/javascript" src="prettydiff.js"></script>
    <script type="application/javascript" src="api/dom.js"></script>

Run on Windows command line with WSH
---

Create a WSH script file using XML syntax and with a file extension of
"WSF".  This file must have a tag for each supported argument, must be
capable of reading from a file, and retrieving dependencies.

http://prettydiff.com/api/prettydiff.wsf

Pretty Diff would be executed using the following on CLI:

    cscript prettydiff.wsf
    cscript prettydiff.wsf /source:"myFile.xml" /mode:"beautify"

Execute with vanilla JS
---

    var args   = {
            source: "asdf",
            diff  : "asdd",
            lang  : "text"
        },
        output = prettydiff(args);

License:
---

 @source: http://prettydiff.com/prettydiff.js

 @documentation - English: http://prettydiff.com/documentation.php

 @licstart  The following is the entire license notice for Pretty Diff.
 
 This code may not be used or redistributed unless the following
 conditions are met:

 * Prettydiff created by Austin Cheney originally on 3 Mar 2009.
 http://prettydiff.com/
 * The use of diffview.js and prettydiff.js must contain the following
 copyright:
 Copyright (c) 2007, Snowtide Informatics Systems, Inc.
 All rights reserved.
  - Redistributions of source code must retain the above copyright
 notice, this list of conditions and the following disclaimer.
  - Redistributions in binary form must reproduce the above copyright
 notice, this list of conditions and the following disclaimer in the
 documentation and/or other materials provided with the
 distribution.
  - Neither the name of the Snowtide Informatics Systems nor the
 names of its contributors may be used to endorse or promote products
 derived from this software without specific prior written
 permission.
  - used as diffview function
  http://prettydiff.com/lib/diffview.js
 * CodeMirror
 Copyright (C) 2013 by Marijn Haverbeke marijnh@gmail.com and others
 http://codemirror.com - MIT License
 * The code mentioned above has significantly expanded documentation in
 each of the respective function's external JS file as linked from the
 documentation page:
 http://prettydiff.com/documentation.php
 * In addition to the previously stated requirements any use of any
 component, aside from directly using the full files in their entirety,
 must restate the license mentioned at the top of each concerned file.

 If each and all these conditions are met use, extension, alteration,
 and redistribution of Pretty Diff and its required assets is unlimited
 and free without author permission.

 @licend  The above is the entire license notice for Pretty Diff.

Acknowledgements
---
 
 * Harry Whitfield - http://g6auc.me.uk/
  - JS Pretty QA
  - JS Pretty widget
 * Andreas Greuel - https://plus.google.com/105958105635636993368/posts
  - diffview.js QA
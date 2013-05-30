
jQuery Schedule
===============

(Scheduled/Deferred Actions for jQuery)

Abstract
--------

jQuery Schedule is a [jQuery](http://jquery.com/) plugin for
performing scheduled/deferred actions on DOM elements.

Synopsis
--------

    <div id="button">TEST BUTTON</div>
    <div id="test"></div>

    <script type="text/javascript">
       $(document).ready(
       function(){
           $('#button').click(function () {
               $(this).css("color", "blue").schedule(2000, function (x) {
                   $(this).css("color", "red");
                   $("#test").html("test: x = " + x);
               }, 42);
           });
       });
    </script>

API
---

    ctx = $.schedule({
        id:      null,         /* unique identifier of high-level schedule */
        time:    1000,         /* time in milliseconds after which the task is run */
        repeat:  false,        /* whether schedule should be automatically repeated */
        protect: false,        /* whether schedule should be protected from double scheduling */
        obj:     null,         /* function context object ("this") */
        func:    function(){}, /* function to call */
        args:    []            /* function arguments to pass */
    })
    
    ctx = $.schedule([time [, repeat], ]{{ obj, methodname } | func}[, arg, ...])
    
    $.reschedule(ctx)
    
    $.cancel(ctx)
    
    ctx = $([...]).schedule([...])

Building jQuery Schedule
------------------------

You can pick the jQuery plugin in file "jquery.schedule.js" as is for use,
but for linting and minifying it yourself you need Node.js ("node") and
its Node.js Package Manager ("npm") globally installed.

    # approach 1: use convenient Makefile (author preference)
    $ make

    # approach 2: use Grunt locally (contributor recommendation)
    $ npm install
    $ node_modules/grunt-cli/bin/grunt

    # approach 3: install and use Grunt globally (contributor alternative)
    $ npm install -g grunt-cli
    $ npm install
    $ grunt

License
-------

Copyright (c) 2007-2013 Ralf S. Engelschall (http://engelschall.com/)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


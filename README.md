Summary
---------
Debugging javascript can be tedious due to the lack of integration between the code editor and the browsers' debugging tools. JsDebuggr aims to make it a tad easier by allowing Sublime Text to mark breakpoints for the web browser debugging tools.  

The way JsDebuggr works is by inserting the `debugger;` statement at each breakpoint when the document is saved. If the web browser's dev tools window is opened, this keyword acts as a breakpoint, giving the user an opportunity to review variable values, the call stack, etc.

![ScreenShot](https://raw.github.com/rDr4g0n/JsDebuggr/master/screen1.png)

The benefits of a plugin to do this over entering debugger statements manually are minor, but all add up:
* Adding the debugger statement is done in 2 clicks or with a keyboard shortcut rather than typing it out
* Debugger statements are marked in the gutter with a dot like a breakpoint in an IDE
* Breakpoints can be removed all at once with a single commend, so cleaning up or disabling all the debug statements after a long and messy debug session is quick and easy
* When adding breakpoints in your browser dev tool, if you add or remove a line from the js then refresh the page, all the breakpoints will be off by a line. Using the debugger statement, all the breakpoints are always exactly where you place them
* It's more complex (or not possible at all) to debug injected or eval'd code with dev tools. That's not a problem with the debugger statement


Installation
------------
Clone the repo to your Sublime Text `Packages folder`. Something like this should work: `C:\Users\User\AppData\Roaming\Sublime Text 2\Packages\JsDebuggr\`


Settings
--------
JsDebuggr has only one settings for now. They can be found in the `JsDebuggr.sublime-settings` file.  

* `file_type_list` is an array of file extensions that should be enabled for scanning and tracking. The default value is `["html", "htm", "js"]`.


Key Bindings
------------
The default key bindings are as follows:

* `ctrl + f10` - add or remove breakpoint

Additionally, the right click menu allows for:

* clear all


Future Features
-----
This is a complete rewrite which is much cleaner but actually removed a number of features. These features should be showing up pretty soon:

* enable / disable of breakpoints
* conditional breakpoints
* scan document for existing `debugger;` statements and convert them to breakpoints
* save and load of breakpoint sets

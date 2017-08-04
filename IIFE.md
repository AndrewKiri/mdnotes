Immediately-invoked function expressions may be written in a number of different ways. A common convention is to enclose the function expression (and optionally its invocation operator) with the grouping operator,i.e. in parentheses, to explicitly tell the parser to expect an expression. Otherwise, in most situations, when the parser encounters the function keyword, it treats it as a function declaration (statement), and not as a function expression.

    (function () { /* ... */ })();
    (function () { /* ... */ }());

In contexts where an expression is expected, wrapping in parentheses is not necessary:

    var f = function () { /* ... */ }();
    true && function () { /* ... */ }();
    0, function () { /* ... */ }();

Passing variables into the scope is done as follows:

    (function(a, b) { /* ... */ })("hello", "world");

An initial parenthesis is one case where the automatic semicolon insertion (ASI) in JavaScript can cause problems; the expression is instead interpreted as a call to the last term on the preceding line. In some styles that omit optional semicolons, the semicolon is placed in front of the parenthesis, and is known as a defensive semicolon. For example:

    a = b + c
    ;(function () {
      // code
    })();

…to avoid being parsed as `c()`
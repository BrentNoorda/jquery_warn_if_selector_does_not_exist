jquery\_warn\_if\_selector\_does\_not\_exist
======================================

Alter jQuery `$` to log errors when selector is not found.

Why?
--------------------------------------------------------------

jQuery's default behavior if the 'selector' in `$('selector')` doesn't match anything is to quietly do nothing. But I don't like that because very rarely do I write a selector and expect it not to match anything. Almost always, if a selector is not found it means I have a bug or at least a typo, and so I would rather jQuery tell me so.

How:
------------------------------------------------------------------------------

This code overrides the `$('selector')` logic so that if the selector is not found a `console.error()` statement (or `alert()` if `console.error` is not supported such as in IE) is called to warn you so.

I recommended using this code only in a DEBUG-like situation, such as when developing locally or trying to find a bug. If you want a `$('selector')` call to NOT show an error (i.e. you want the default NOP behavior) then on those calls use `jQuery('selector')` instead of `$('selector')`.

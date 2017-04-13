---
title: Variables
taxonomy:
    category: docs
---

The following list of variables is not unique to Custom System Messages. They are native variables available in ExpressionEngine's <a href="https://docs.expressionengine.com/latest/cp/design/system/index.html">System Message Templates</a>.

``{meta_refresh}``
Renders the meta refresh tag for your HTML head

``{heading}``
Message header

``{content}``
Message details, usually a sentence of text or possibly an unordered list of error messages.

``{link}``
Link to return to the previous page.

``{action}``
will return the ACT ID which you can use it in your templates to show messages specific to the action the user performed. This will usually be found in your URL as ``?ACT=[id]``.

``{error}``
Boolean: If the action is an error message or not. Use this in conditionals to change the behavior of your error template. By default, ExpressionEngine uses the same ACT ID for success or error messages, only internally does it know which message to display (e.g. what the ``{content}`` variable is set to).

``{referrer}``
The URL prior to the error message.

Custom System Messages also provides aliases for each each variable that are parsed early, thus they can be used in conditional statements and other template tags. Each variable above has an alias prefixed with ``csm:``. For example ``{content}`` is also available with ``{csm:content}``. If you are having trouble with the original variables, try the aliases.

Even though the ``{action}`` and ``{error}`` variables are available, you may want to use entirely different templates for each ACT and on their success or error results instead of conditionals. You can do this by selecting which template each action in the drop down is assigned to, there is also an "(On Error)" version for each action.

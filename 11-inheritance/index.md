# CSS exercise 11: Inheritance

Let's do some research on what we commonly refer to as *inheritance* in CSS.

Try to answer the following questions:

- What do we mean by *CSS inheritance*? What does it affect?
- Which properties have values that are inherited by default?
- What is the difference between the `currentColor` and `inherit` keywords when used with colour values?
- What do the `revert`, `initial`, and `unset` keyword values do?
- Are there any dangers or unintended side-effects when using `inherit` as a value? What about the `revert`, `initial` and `unset` properties?
- What are the possibilities with using an ancestor or universal selector, combined with the `inherit` value?

  ## CSS inheritance:
CSS stands for Cascading Style Sheets, and that first word cascading is incredibly important to understand — the way that the cascade behaves is key to understanding CSS.

At some point, you will be working on a project and you will find that the CSS you thought should be applied to an element is not working. Usually the problem is that you have created two rules which could potentially apply to the same element. The cascade, and the closely-related concept of specificity, are mechanisms that control which rule applies when there is such a conflict. Which rule is styling your element may not be the one you expect, so you need to understand how these mechanisms work.

Also significant here is the concept of inheritance, which means that some CSS properties by default inherit values set on the current element's parent element, and some don't. This can also cause some behavior that you might not expect.

Let's start by taking a quick look at the key things we are dealing with, then we'll look at each in turn and see how they interact with each other and your CSS. This can seem like a set of tricky concepts to understand. As you get more practice writing CSS, however, the way it works will become more obvious to you.

##  currentColor` and `inherit`:

The currentcolor keyword represents the value of an element's color property. This lets you use the color value on properties that do not receive it by default.

If currentcolor is used as the value of the color property, it instead takes its value from the inherited value of the color property.

## revert, initial, and unset keyword values:
The revert CSS keyword reverts the cascaded value of the property from its current value to the value the property would have had if no changes had been made by the current style origin to the current element. Thus, it resets the property to its inherited value if it inherits from its parent or to the default value established by the user agent's stylesheet (or by user styles, if any exist). It can be applied to any CSS property, including the CSS shorthand all.

This removes from the cascade all of the styles that have been overridden until the style being rolled back to is reached.

If used by a site's own styles (the author origin), revert rolls back the property's cascaded value to the user's custom style, if one exists; otherwise, it rolls the style back to the user agent's default style.
If used in a user's custom stylesheet, or if the style was applied by the user (the user origin), revert rolls back the cascaded value to the user agent's default style.
If used within the user agent's default styles, this keyword is functionally equivalent to unset.
The revert keyword works exactly the same as unset in many cases. The only difference is for properties that have values set by the browser or by custom stylesheets created by users (set on the browser side).

Revert will not affect rules applied to children of an element you reset (but will remove effects of a parent rule on a child). So if you have a color: green for all sections and all: revert on a specific section the color of the section will be black. But if you have a rule to make all paragraphs red then all paragraphs will still be red in all sections.

The initial CSS keyword applies the initial (or default) value of a property to an element. This initial value is set by the browser. It can be applied to any CSS property. This includes the CSS shorthand all, with which initial can be used to restore all CSS properties to their initial state.

##

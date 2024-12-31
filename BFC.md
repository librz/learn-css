## concept

BFC: Block Formatting Context

As the name suggests, it provides context(environment) for how block level elements are formatted.

Another interpretation is that BFC is a part of the visual CSS rendering of a web page that creates an **independent** layout environment for block-level boxes. You can think of it as mini-layout inside your page, where everything is contained within its own rules.

When you create an empty html file, the `html` tag creates a default BFC. But sometimes you want to escape from the default BFC and create your own BFC. Flexbox is a common example, you want create a context so that children elements under it are formatted using flex layout.

## usages

BFC has 3 main usages:

1. contain internal floats (the famous height collapse problem)
2. exclude external floats
3. supress margin collapse

## ways to create BFC

 - `display: flow-root`: most modern and generic way
 - `display: flex` or `display: inline-flex`
 - `display: grid` or `display: inline-grid`
 - `display: inline-block`
 - Floats (elements where `float` isn't `none`)
 - Overflow (eleements where `overflow` has a value other than `visible` or `clip`)
 - Absolute positioned elements (elements where `position` is `absolute` or `fixed`)

## Doc

For detials see: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_display/Block_formatting_context


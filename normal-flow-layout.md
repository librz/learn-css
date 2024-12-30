## Concept

Normal flow layout is nothing new.

The original goal of the web is to establish a publish platform and webpages were treated as digital documents.

What's needed in order to layout a document? Well, you have blocks like headings, paragraphs and lists, you want to control width/height of images, you'd like to embed link inside a paragraph, etc.

Normal flow layout is the default layout to handle basic formatting requirement. It separates elements into 2 categories:

1. block-level elements
2. inline-level elements

The difference is whether an element tolerates other elements so that both can live in the same *line*.

## block-level elements

by default, the following tags are block-level elements:

- text
- specialized tags: `article`, `aside`, `form`, `main`, `header, footer`, `table`, `form`, `h1, ..., h6`, `p`, `nav`, `ul, ol, li`, `blockquote`, `pre`
- generic tags: `div`, `section`

You can set the width/height of block level elements.

## inline-level elements

by default, the following tags are inline-level elements:

- specialized tags: `a`, `abbr`, `img`, `video`, `code`, `input, select, textarea`, `label`, `quote`
- generic tags: `span`

Setting width/height of an inline element is invalid. Both the width and height of the element is decided by its content. However, you can use `display: inline-block` to set the width/height while keeping the element as an inline element.

## display

You can specify whether an element is block-level or inline-level.

To set an element as block level elements, you can:

- `display: block`
- `display: flex`
- `display: grid`

To set an element as inline level elements, you can:

- `display: inline`
- `display: inline-block`: set as inline element, but allow setting width/height as if it's block level.
- `display: inline-flex`: set as inline element, but allow setting layout of its content as if it's flexbox. (such as using `align-items` and `justify-content`)
- `display: inline-grid`: set as inline element, but allow setting layout of its content as if it's grid.
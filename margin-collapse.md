## test of comprehension

1. true or false: if two boxes are adjacent but not siblings(children of same container), their margins won't collapse
2. true or false: margin collapse can happen either in horizontal or vertical direction
3. what are the types of margin collapse?
4. what are the ways to prevent margin collapse?

if u can confidently answer the above questions -> you are good -> skip the rest of this article.

if not, read on.

## doc

[Mastering Margin Collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)

## answers

### True or False: if two boxes are adjacent but not siblings(children of same container), their margins won't collapse

False. They don't have to be siblings. e.g.

```html
<div>
    <div style="margin-bottom: 50px">box1</div>
    <div>
        <div style="margin-top: 50px">box2</div>
    </div>
</div>
```

In this example, whitespace between box1 and box2 is 50px instead of 100px

### True or False: margin collapse can happen either in horizontal or vertical direction

False. margin collapse *only* happens in *vertical* direction. e.g.

```html
<div>
  <span style="margin-right: 50px">left</span>
  <span style="margin-left: 50px">right</span>
</div>
```

In this example, horizontal whitespace between left span and right span is 100px instead of 50px

### what are the types of margin collapse?

3 types:

#### Adjacent elements

When two block-level elements are adjacent, their vertical margins collapse into a single margin. The size of the collapsed margin is the largest of the two margins.

This is the most common scenario.

#### Nested elements

If a parent and its first or last child have vertical margins, these margins can also collapse. e.g.

```html
<div>
    <div>box1</div>
    <div style="margin-top: 50px">
        <div style="margin-top: 100px"></div>
    </div>
    <div>box2</div>
</div>
```

In this example, the whitespace between box1 and box2 is 100px instead of 150px

#### Empty blocks

If a block has no content, its top and bottom margins will collapse. e.g.

```html
<div>
  <div>box1</div>
  <div style="margin-top: 100px; margin-bottom: 50px"></div>
  <div>box2</div>
</div>
```

In this example, the whitespace between box1 and box2 is 100px instead of 150px

### what are the ways to prevent margin collapse?

#### *something with height* in between

it could be a border:

```html
<div>
  <div style="margin-bottom: 50px">box1</div>
  <div style="border: 1px solid black">
      <div style="margin-top: 50px">box2</div>
  </div>
</div>
```

or padding:

```html
<div>
  <div style="margin-bottom: 50px">box1</div>
  <div style="padding-top: 1px">
      <div style="margin-top: 50px">box2</div>
  </div>
</div>
```

or inline content:

```html
<div >
  <div style="margin-bottom: 50px">box1</div>
  <div>
      Aha!
      <div style="margin-top: 50px">box2</div>
  </div>
</div>
```

#### BFC(Block Formatting Context)

BFC in itself is a big topic, I won't go into details here. 

There're many ways to create BFC. Below is an example of using `display: flex` to create one:

```html
<div style="display: flex; flex-direction: column;">
  <div style="margin-bottom: 50px">box1</div>
  <div style="margin-top: 50px">box2</div>
</div>
```

In this example, the whitespace between box1 and box2 is 100px instead of 50px.

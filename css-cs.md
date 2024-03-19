# CSS Cheat Sheet

## Selectors
- `*` - Universal selector (selects all elements)
- `element` - Type selector (selects all elements of the given type)
- `.class` - Class selector (selects all elements with the given class)
- `#id` - ID selector (selects the element with the given ID)
- `selector1, selector2` - Group selector (selects all elements matching either selector)
- `selector1 selector2` - Descendant selector (selects elements that are descendants of the first selector)
- `selector1 > selector2` - Child selector (selects elements that are direct children of the first selector)
- `selector1 + selector2` - Adjacent sibling selector (selects elements that are next siblings of the first selector)
- `selector1 ~ selector2` - General sibling selector (selects elements that are siblings of the first selector)

## Box Model
- `margin` - Clears an area around an element (outside the border)
- `padding` - Clears an area around the content (inside the border)
- `border` - Defines the border around an element
- `width` - Sets the width of an element
- `height` - Sets the height of an element

## Typography
- `font-family` - Specifies the font family for text
- `font-size` - Specifies the font size of text
- `font-weight` - Specifies the font weight of text
- `line-height` - Specifies the line height of text
- `text-align` - Specifies the horizontal alignment of text
- `text-decoration` - Adds decoration to text (e.g., underline, overline, line-through)
- `color` - Sets the color of text

## Backgrounds
- `background-color` - Sets the background color of an element
- `background-image` - Sets the background image of an element
- `background-repeat` - Specifies how a background image should be repeated
- `background-position` - Specifies the position of a background image
- `background-size` - Specifies the size of a background image

## Layout
- `display` - Specifies the display behavior of an element (block, inline, flex, grid, etc.)
- `position` - Specifies the positioning method of an element (static, relative, absolute, fixed, sticky)
- `float` - Specifies how an element should float (left or right)
- `clear` - Specifies which sides of an element should not allow floating elements
- `overflow` - Specifies how to handle content that overflows its container

## Flexbox
- `display: flex` - Creates a flex container
- `flex-direction` - Specifies the direction of the flex items
- `justify-content` - Aligns flex items along the main axis
- `align-items` - Aligns flex items along the cross axis
- `flex-wrap` - Specifies whether flex items should wrap or not
- `flex-grow` - Specifies how much a flex item should grow relative to the other items
- `flex-shrink` - Specifies how much a flex item should shrink relative to the other items
- `flex-basis` - Specifies the initial length of a flex item

## CSS Grid
- `display: grid` - Creates a grid container
- `grid-template-columns` - Defines the columns of the grid
- `grid-template-rows` - Defines the rows of the grid
- `grid-gap` - Specifies the gap between grid items
- `grid-column` - Specifies the column(s) where an item should start and end
- `grid-row` - Specifies the row(s) where an item should start and end
- `justify-items` - Aligns grid items along the inline (row) axis
- `align-items` - Aligns grid items along the block (column) axis

## Transitions and Animations
- `transition` - Applies a transition effect when changing CSS properties
- `transform` - Applies 2D or 3D transformations to an element
- `animation` - Applies an animation to an element
- `@keyframes` - Specifies the animation code

## Miscellaneous
- `cursor` - Specifies the mouse cursor to be displayed when hovering over an element
- `opacity` - Sets the transparency level of an element
- `z-index` - Specifies the stack order of an element
- `box-shadow` - Adds a shadow effect to an element
- `filter` - Applies graphical effects like blur, grayscale, or sepia
- `list-style` - Specifies the style of list items
- `outline` - Specifies the outline of an element

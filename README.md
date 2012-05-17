# jQuery xeyes

This is a simple jQuery plugin that is meant to emulate the classic xeyes program. While it doesn't have many native uses, some very creative people managed to incorporate it into their pojects. If you have any questions or need help using this script, contact [@felix_mc](http://twitter.com/#!/felix_mc).

## Examples
- http://fiddle.jshell.net/felixmc/f4MnQ/show/light/
- http://fiddle.jshell.net/felixmc/xafhf/show/light/
- http://fiddle.jshell.net/felixmc/YggeK/show/light/ image via [VampireJaku](http://vampirejaku.deviantart.com/)

- http://birondesign.com/Portfolio/ via [@birondesign](http://twitter.com/#!/birondesign)
- http://sheepfilms.co.uk/interact/eyes.htm via [sheepfilms.co.uk](http://sheepfilms.co.uk/)

## Basic Usage

The plugin modifies two block level elements, the `eyeball` and the `iris` by using some basic trig to calculate the position of the `iris` based on the curren position of the cursor.

You'll need at least two block-level elements to serve as the `eyeball` and the `iris` respectively:

```html
<div class="eyeball">
    <div class="iris"></div>
</div>
```

Some basic css is required for things like dimensions in order for the plugin to work. Defining backgrounds is also a good idea, so you can actually see the plugin work:

```css
.eyeball {
    width: 110px;
    height: 150px;
    background: #fff;
}
 
.iris {
    width: 25px;
    height: 25px;
    background: #000;
}
```

Finally, to initialize the plugin, simply call the js function on the `iris` element:

```js
$('.iris').xeyes();
```

The plugin will automatically assume that its immidiate parent will be used as the `eyeball` element. The `eyeball` class was only required for the styling.

Using the basic code above, you should get something like this: http://fiddle.jshell.net/felixmc/YKKuY/show/light/

## Advanced Options

*All* of the following are optional. You can use them to further customize this plugin.

 - **padding:** space between the `iris` and the `eyeball`. Only `px` values allowed! Default value is `0px`

 - **radius:** the path the `iris` will move inside the `eyeball`. Can be string value `"natural"` or `"circular"`. With `natural` the `iris` follows the shape of the `eyeball` in either an elliptical or circular path, while `"circular"` will force the `iris` to use a perfectly circular path using the shortest radius of the `eyeball`. Default is `"natural"`

 - **position:** position of the `iris` when the page loads prior to moving the cursor. Can be one of the following string values: `"center"`, `"topLeft"`, `"top"`, `"topRight"`, `"right"`, `"bottomRight"`, `"bottom"`, `"bottomLeft"`. Can also be an object in the following format: `{x: 'value', y: 'value'}` where value is a pixel value. Default value is `"center"`

 - **onHover:** behavior of the `iris` when the cursor enters the `eyeball`. Can be string value `"follow"` or `"nofollow"`. Using `"follow"` makes the `iris` move with the cursor, while `"nofollow"` ignores the cursor while on the `eyeball`. Default value is `"follow"`

 - **trigger:** DOM object(s) to trigger eye movement when the cursor moves over them. Can be a jQuery selector or DOM object. Default value is `window`
 
 - **triggerOut:** position the iris to return to when the cursor is no longer on the `trigger` element. Accepts same values as `position` option. If not specified, the iris will not move when the cursor is no longer on the `trigger` element
 
 - **triggerOutSpeed:** speed in milliseconds for the iris to return to the position specified in `triggerOut` when the mouse leaves the `trigger` element. Default value is `1000` 

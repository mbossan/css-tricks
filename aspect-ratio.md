Maintain aspect-ratio in a Pure CSS Responsive design:

Apply and maintain an aspect-ratio on a dom element using css only. 


<a href="https://codepen.io/mbossan/pen/yPJqwE" target="_blank">https://codepen.io/mbossan/pen/yPJqwE</a>
```
.container{
  position: relative;
}
.container::before{
  display: block;
  width: 100%;
  padding-top: 56.25%; //16:9 -> 9/16 * 100 = 56.25
  content: '';
}
.container > .content{
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
```

```
@mixin aspect-ratio($width, $height) {
  position: relative;
  &:before {
    display: block;
    width: 100%;
    padding-top: ($height / $width) * 100%;
    content: '';
  }
  > .content {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
  }
}
```

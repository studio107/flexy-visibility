[![Build Status](https://travis-ci.org/studio107/flexy-visibility.svg?branch=master)](https://travis-ci.org/studio107/flexy-visibility)

# flexy-visibility-media

```scss
@include assert-equal(flexy-visibility-media(medium, false), (min-width: 769px));
@include assert-equal(flexy-visibility-media(medium, true), (max-width: 991px, min-width: 769px));
```

# flexy-visibility-next-media

Return next media query from breakpoint map

```scss
@include assert-equal(flexy-visibility-next-media(medium), (min-width: 769px, max-width: 991px));
@include assert-equal(flexy-visibility-next-media(large), (min-width: 992px, max-width: 1199px));
```

# mixin: flexy-hide

Only current breakpoint

```scss
.foo {
  @include flexy-hide(small, true);
}

// Output

@media only screen and (max-width: 768px) and (min-width: 0) {
  .foo {
    display: none;
  }
}
```

Current breakpoint and up

```scss
.foo {
  @include flexy-hide(small, false);
}

// Output

@media only screen and (min-width: 0) {
  .foo {
    display: none;
  }
}
```

# mixin: flexy-show

Hide for current breakpoint only

```scss
.foo {
  @include flexy-show(small, true);
}

// Output

.foo {
  display: none;
}

@media only screen and (max-width: 768px) and (min-width: 0) {
  .foo {
    display: block;
  }
}
```

Hide for current breakpoint and up

```scss
.foo {
  @include flexy-show(medium, false);
}

// Output

.foo {
  display: none;
}

@media only screen and (min-width: 769px) {
  .foo {
    display: block;
  }
}
```

# classes

```html
<div class="b-hide b-hide_large_up"></div>

<div class="b-show b-show_large_up"></div>
<div class="b-visible b-visible_large_up"></div>
```

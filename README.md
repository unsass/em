# Em

[![Version](https://flat.badgen.net/npm/v/@unsass/em)](https://www.npmjs.com/package/@unsass/em)
[![Downloads](https://flat.badgen.net/npm/dt/@unsass/em)](https://www.npmjs.com/package/@unsass/em)
[![License](https://flat.badgen.net/npm/license/@unsass/em)](https://www.npmjs.com/package/@unsass/em)

## Introduction

Sass functions and mixins to use em units.

## Installing

```shell
npm install @unsass/em
```

## Usage

```scss
@use "@unsass/em";

.foo {
    font-size: em.convert(16px, 16px);
}
```

## API

### Sass functions

| Function              | Description                |
|-----------------------|----------------------------|
| `convert($values...)` | Convert `px` unit to `em`. |

#### Convert with `em.convert()`

The following Sass...

```scss
@use "@unsass/em";

.foo {
    font-size: em.convert(16px, 16px); // Single value.
    margin: em.convert(20px 30px, 16px); // Multiple values.
    border: em.convert(1px solid darkcyan, 16px); // Multiple mixed values.
    box-shadow: em.convert(0 0 10px 5px rgba(darkcyan, 0.75), inset 0 0 10px 5px rgba(darkcyan, 0.75), 16px); // Comma-separated values.
}
```

...will produce the following CSS...

```css
.foo {
    font-size: 1em;
    margin: 1.25em 1.875em;
    border: 0.0625em solid darkcyan;
    box-shadow: 0 0 0.625em 0.3125em rgba(0, 139, 139, 0.75), inset 0 0 0.625em 0.3125em rgba(0, 139, 139, 0.75);
}
```

### Sass mixins

| Mixin                                                  | Description                                                                        |
|--------------------------------------------------------|------------------------------------------------------------------------------------|
| `declaration($property, $value, $context, $important)` | Sets declaration with conversion of `px` unit to `em`, with optional `!important`. |

#### Convert declaration with `em.declaration()`

The following Sass...

```scss
@use "@unsass/em";

.foo {
    @include em.declaration(font-size, 16px, 16px); // Single value.
    @include em.declaration(margin, 20px 30px, 16px); // Multiple values.
    @include em.declaration(border, 1px solid darkcyan, 16px); // Multiple mixed values.
    @include em.declaration(box-shadow, 0 0 10px 5px rgba(darkcyan, 0.75), inset 0 0 10px 5px rgba(darkcyan, 0.75), 16px); // Comma-separated values.
}
```

...will produce the following CSS...

```css
.foo {
    font-size: 1em;
    margin: 1.25em 1.875em;
    border: 0.0625em solid darkcyan;
    box-shadow: 0 0 0.625em 0.3125em rgba(0, 139, 139, 0.75), inset 0 0 0.625em 0.3125em rgba(0, 139, 139, 0.75);
}
```

# Create Web Design With Sass ([Template](https://www.os-templates.com/website-templates/template-demos/free-psd-templates/composition/))

## how to instal
follow instruction in [sass-lang.com/install](https://sass-lang.com/install)

## how to compile:
```sh
sass --watch input-sass-dir:output-css-dir --style expanded
```

## course 4: (media queries with all methods)
### how to use it:
```
p {
	@media (min-width: 992px) {
		color: #080;
	}
	@media (min-width: 1200px) {
		color: #080;
	}
}
```

### method 1: (variable)
```
$minSmall: 768px;
```

```
p {
	@media (min-width: $minSmall) {
		color: #080;
	}
}
```

### method 2: (interpolation)
```
$minSmall: "screen (min-width: 992px)";
```
```
p {
	@media #{$minSmall} {
		color: #080;
	}
}
```

### method 3: (mixins)
```
@mixin minSmall {
	@media (min-width: 992px) {
		@content;
	}
}
```
```
p {
	@include minSmall {
		color: #080;
	}
}
```

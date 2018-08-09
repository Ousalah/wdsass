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

## course 26: (advanced sass tricks part 1)
### mixin: opacity, ofen used propertie
see ``_mixins.css``

### color calculation
```
.elment {
	color: green + red;
}
```
```
.elment {
	color: #080 + #ff0;
}
```

## course 27: (advanced sass tricks part 2)
### nested css properties
```
.elment {
	.child {
		font: {
			weight: bold;
			size: 20px
			family: Ariale;
		}
		border: {
			right: 1px solid #ccc;
			left: 1px solid #ddd;
		}
		padding {
			right: 10px;
			left: 10px;
		}
	}
}
```

### extend
#### normal extend (if you will use it in html file) => ``a lot of groupped elements``
in `` .scss`` file
```
.error {
	color: green;
	font-weight: bold;
}

.element {
	@extend .error;
	font-size: 20px;
}
```

in `` .css`` file
```
.error, .element {
	color: green;
	font-weight: bold;
}

.element {
	font-size: 20px;
}
```

#### placeholder extend (if you will NOT use it in html file) => ``no groupped elements``
in `` .scss`` file
```
%error {
	color: green;
	font-weight: bold;
}

.element {
	@extend %error;
	font-size: 20px;
}
```

in `` .css`` file
```
.element {
	color: green;
	font-weight: bold;
}

.element {
	font-size: 20px;
}
```
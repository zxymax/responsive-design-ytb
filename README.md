### Sass, BEM & Responsive Design

#### Compiling Sass with VsCode extensions
- `Live Sass Compiler` author: Glenn Marks

> `command shift p`  setting Sass VsCode settings.json
```json
"liveSassCompile.settings.formats": [
      {
        "format": "compressed",
        "extensionName": ".css",
        "savePath": "/dist",
        "savePathReplacementPairs": null
      }
    ],
```

- `Live Server` author: Ritwick Dey

#### Import the compiled Css file into the index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive-Design</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Koulen&family=Open+Sans:wght@300&family=Public+Sans:wght@300;400&family=Righteous&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="/dist/style.css" />
</head>
<body>
</body>
</html>
```

### Sass variables and Css custom properties

> scss style folder

- style.scss  //style entry file

```scss
@forward 'globals';
@forward 'layout';
```
> folders

- /scss/globals/ folder

- /scss/layouts/ folder

- /scss/utils/ folder

> Define Font family

- /utils/_fonts.scss

```scss
$font: 'Open Sans', sans-serif;
```

- /utils/_index.scss

```scss
@forward 'fonts';
```

> import utils fonts use fonts

```scss
// globals/_boilerplate.scss
@use '../utils' as u;
body {
  font-family: u.$font;
}
```

> Define variables :root

```scss
// globals/_colors.scss
:root {
  --background-color: hsl(0, 0%, 11%);
  --text-color: hsl(0, 0%, 100%);
}
```

- /globals/_index.scss

```scss
@forward 'colors';
```

> use variables colors

```scss
// /globals/_boilerplate.scss
body {
  background-color: var(--background-color);
  color: var(--text-color);
}
```



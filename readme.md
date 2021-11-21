# @chiarapassaro/color-palettes-range
![Color Palette](https://raw.githubusercontent.com/ChiaraPassaro/color-palettes-range/master/screen/screen141.jpg)

# Are you bored with classic color palettes?
Now you can generate more than three or five colors palette:
take a Complementary Palette or a Random Dominant Palette, and you can decide how many colors you want!

In this versions: 
From Es5 to Es6
Bug fix convert from Hex Color

V2.0.0

##Install
```
$ npm init
$ npm install @chiarapassaro/color-palettes-range
```

##Usage
```
var ColorPalettesRange = require("@chiarapassaro/color-palettes-range/src/js");
```

## Functionality

### Create Hsl color:<br/>
```
var baseColor = new ColorPalettesRange.Hsl(
    {
        hue, 
        saturation, 
        brightness
    }
);
```

##### Props: <br/>
Hue degree (1-360)<br/>
Saturation (1-100)<br/>
Brightness (1-100)<br/>

##### Methods:
```
baseColor.getHue() -> number
baseColor.getSaturation() -> number
baseColor.getBrightness() -> number
baseColor.setHue(number)
baseColor.setSaturation(number)
baseColor.setBrightness(number)
baseColor.printHsl() -> string hsl(hue, saturation% , brightness%)
baseColor.printRgb() -> string rgb(value, value , value)
baseColor.printHex() -> string #RRGGBB

```

### Create palettes:<br/>
```
var palettes = new ColorPalettesRange.SetColorPalette(baseColor)
```
##### Arguments: <br/>
Base Color  [obj Hsl]

##### Methods:

### Base Color
```
palettes.getBasecolor() -> obj Hsl()
updateColorPalette(newColor)
```
### Triadic:<br/>
#### Create Triadic scheme:<br/>
```
palettes.triad()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```
#### Get palettes Triadic
```
palettes.getTriad()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Complementary palettes:<br/>
```
palettes.complementar(
    {
        numColor, 
        stepDegree
    }
);
```
##### Props:<br/>
Color number - even <br/>
Step degree between colors<br/>
Max degree numColor*step = 140<br/>
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```
#### Get palettes complementary colors
```
palettes.getComplementar()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Split complementary palettes:<br/>
```
palettes.splitComplementar()
```
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get palettes Split complementary colors
```
palettes.splitComplementar()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Analogous palettes:<br/>
```
palettes.analogous(
    {
        typeScheme, 
        numColor, 
        stepDegree
    }
);
```
##### Props:<br/>
Scheme Type: 'allArch', 'cold', 'warm'<br/>
Colors number - even<br/>
Step degree between colors<br/>
Max degree numColor*step = 60<br/>
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```
#### Get analogous colors
```
palettes.getAnalogous()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create tetradic palettes:<br/>
```
palettes.tetradic()
```
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Tradic Colors
```
palettes.getTetradic()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Square palettes:<br/>
```
palettes.square()
```
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Square colors
```
palettes.getSquare()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```

### Create Monochrome palettes:<br/>
```
palettes.mono (
    {
        numColor, 
        stepDegree, 
        typeScheme
    }
)'
```
##### Props:<br/>
Colors number - even<br/>
Step degree between colors<br/>
Max degree numColor*step = 100<br/>
Scheme type = saturation / brightness
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Monochrome colors
```
palettes.getMono()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Random with Dominat Color palettes
```
palettes.randomDominant(
    {
        numColor, 
        percDominant
    }
);
```
##### Props:<br/>
Colors number - even (1-360)<br/>
Color Dominant Percentage (1-100)<br/>
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Random Dominant colors
```
palettes.getRandomDominant()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


## Conversion Utilities
### Convert Hsl color:<br/>
```
var color = new ColorPalettesRange.HslConvert(
    {
        hue, 
        saturation, 
        brightness
    }
)
```

##### Props: <br/>
hue (1-360)<br/>
saturation (1-100)<br/>
brightness (1-100)<br/>

##### Methods:
```
color.getRgb() -> [Obj] new Rgb(r, g, b)
color.getRed() -> number
color.getGreen() -> number
color.getBlue() -> number
color.getHex() -> [Obj] new Hex(#RRGGBB)
```

### Convert Rgb color:<br/>
```
var color = new ColorPalettesRange.RgbConvert(
    {
        red, 
        green,
        blue
    }
);
```

##### Props: <br/>
red (1-255)<br/>
green (1-255)<br/>
blue (1-255)<br/>

##### Methods:
```
color.getHsl() -> [Obj] new Hsl({hue, saturation, brightness})
color.getHue() -> number
color.getSaturation() -> number
color.getBrightness() -> number
color.getHex() -> [Obj] new Hex(#RRGGBB)
```

### Convert Hex color:<br/>
```
var color = new ColorPalettesRange.HexConvert(#RRGGBB)
```

##### Arguments: <br/>
hex (#RRGGBB)<br/>

##### Methods:
```
color.getRgb() -> [Obj] new Rgb(r, g, b)
color.getRed() -> number
color.getGreen() -> number
color.getBlue() -> number
color.getHsl() -> [Obj] new Hsl({hue, saturation, brightness})
color.getHue() -> number
color.getSaturation() -> number
color.getBrightness() -> number
```

### Create Rgb color:<br/>
```
var color = new ColorPalettesRange.Rgb(
    {
        red, 
        green, 
        blue
    }
);
```

##### Props: <br/>
Red (1-255)<br/>
Green (1-255)<br/>
Blue (1-255)<br/>

##### Methods:
```
color.getRed() -> number
color.getGreen() -> number
color.getBlue() -> number
color.printHsl() -> string rgb(r, g , b)
color.setRed(number)
color.setBlue(number)
color.setGreen(number)

```

### Create Hex color:<br/>
```
var color = new ColorPalettesRange.Hex(#RRGGBB)
```

##### Arguments: <br/>
\#RRGGBB

##### Methods:
```
color.printHex() -> string #RRGGBB
color.setHex(#RRGGBB)
```


#Example with ChartJs Wheels
![Color Palette](https://raw.githubusercontent.com/ChiaraPassaro/color-palettes-range/master/screen/screenExample.png)
# @chiarapassaro/color-palettes-range
![Color Palette](https://raw.githubusercontent.com/ChiaraPassaro/color-palettes-range/master/screen/screen141.jpg)

# Are you bored with classic color palettes?
Now you can generate more than three or five colors palette:
take a Complementary Palette or a Random Dominant Palette, and you can decide how many colors you want!

V2.0.0

##Install
```
$ npm init
$ npm install @chiarapassaro/color-palettes-range
```

##Usage
```
var ColorPalettesRange = require("@chiarapassaro/color-palettes-range/src/js");
```

## Functionality

### Create Hsl color:<br/>
```
var baseColor = new ColorPalettesRange.Hsl(
    {
        hue, 
        saturation, 
        brightness
    }
);
```

##### Props: <br/>
Hue degree (1-360)<br/>
Saturation (1-100)<br/>
Brightness (1-100)<br/>

##### Methods:
```
baseColor.getHue() -> number
baseColor.getSaturation() -> number
baseColor.getBrightness() -> number
baseColor.setHue(number)
baseColor.setSaturation(number)
baseColor.setBrightness(number)
baseColor.printHsl() -> string hsl(hue, saturation% , brightness%)
baseColor.printRgb() -> string rgb(value, value , value)
baseColor.printHex() -> string #RRGGBB

```

### Create palettes:<br/>
```
var palettes = new ColorPalettesRange.SetColorPalette(baseColor)
```
##### Arguments: <br/>
Base Color  [obj Hsl]

##### Methods:

### Base Color
```
palettes.getBasecolor() -> obj Hsl()
updateColorPalette(newColor)
```
### Triadic:<br/>
#### Create Triadic scheme:<br/>
```
palettes.triad()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```
#### Get palettes Triadic
```
palettes.getTriad()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Complementary palettes:<br/>
```
palettes.complementar(
    {
        numColor, 
        stepDegree
    }
);
```
##### Props:<br/>
Color number - even <br/>
Step degree between colors<br/>
Max degree numColor*step = 140<br/>
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```
#### Get palettes complementary colors
```
palettes.getComplementar()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Split complementary palettes:<br/>
```
palettes.splitComplementar()
```
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get palettes Split complementary colors
```
palettes.splitComplementar()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Analogous palettes:<br/>
```
palettes.analogous(
    {
        typeScheme, 
        numColor, 
        stepDegree
    }
);
```
##### Props:<br/>
Scheme Type: 'allArch', 'cold', 'warm'<br/>
Colors number - even<br/>
Step degree between colors<br/>
Max degree numColor*step = 60<br/>
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```
#### Get analogous colors
```
palettes.getAnalogous()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create tetradic palettes:<br/>
```
palettes.tetradic()
```
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Tradic Colors
```
palettes.getTetradic()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Square palettes:<br/>
```
palettes.square()
```
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Square colors
```
palettes.getSquare()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```

### Create Monochrome palettes:<br/>
```
palettes.mono (
    {
        numColor, 
        stepDegree, 
        typeScheme
    }
)'
```
##### Props:<br/>
Colors number - even<br/>
Step degree between colors<br/>
Max degree numColor*step = 100<br/>
Scheme type = saturation / brightness
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Monochrome colors
```
palettes.getMono()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


### Create Random with Dominat Color palettes
```
palettes.randomDominant(
    {
        numColor, 
        percDominant
    }
);
```
##### Props:<br/>
Colors number - even (1-360)<br/>
Color Dominant Percentage (1-100)<br/>
##### Return:
```
Array [obj Hsl(), obj Hsl()]
```
#### Get Random Dominant colors
```
palettes.getRandomDominant()
```
##### Return:
```
Array [obj Hsl(), obj Hsl(), ...]
```


## Conversion Utilities
### Convert Hsl color:<br/>
```
var color = new ColorPalettesRange.HslConvert(
    {
        hue, 
        saturation, 
        brightness
    }
)
```

##### Props: <br/>
hue (1-360)<br/>
saturation (1-100)<br/>
brightness (1-100)<br/>

##### Methods:
```
color.getRgb() -> [Obj] new Rgb(r, g, b)
color.getRed() -> number
color.getGreen() -> number
color.getBlue() -> number
color.getHex() -> [Obj] new Hex(#RRGGBB)
```

### Convert Rgb color:<br/>
```
var color = new ColorPalettesRange.RgbConvert(
    {
        red, 
        green,
        blue
    }
);
```

##### Props: <br/>
red (1-255)<br/>
green (1-255)<br/>
blue (1-255)<br/>

##### Methods:
```
color.getHsl() -> [Obj] new Hsl({hue, saturation, brightness})
color.getHue() -> number
color.getSaturation() -> number
color.getBrightness() -> number
color.getHex() -> [Obj] new Hex(#RRGGBB)
```

### Convert Hex color:<br/>
```
var color = new ColorPalettesRange.HexConvert(#RRGGBB)
```

##### Arguments: <br/>
hex (#RRGGBB)<br/>

##### Methods:
```
color.getRgb() -> [Obj] new Rgb(r, g, b)
color.getRed() -> number
color.getGreen() -> number
color.getBlue() -> number
color.getHsl() -> [Obj] new Hsl({hue, saturation, brightness})
color.getHue() -> number
color.getSaturation() -> number
color.getBrightness() -> number
```

### Create Rgb color:<br/>
```
var color = new ColorPalettesRange.Rgb(
    {
        red, 
        green, 
        blue
    }
);
```

##### Props: <br/>
Red (1-255)<br/>
Green (1-255)<br/>
Blue (1-255)<br/>

##### Methods:
```
color.getRed() -> number
color.getGreen() -> number
color.getBlue() -> number
color.printHsl() -> string rgb(r, g , b)
color.setRed(number)
color.setBlue(number)
color.setGreen(number)

```

### Create Hex color:<br/>
```
var color = new ColorPalettesRange.Hex(#RRGGBB)
```

##### Arguments: <br/>
\#RRGGBB

##### Methods:
```
color.printHex() -> string #RRGGBB
color.setHex(#RRGGBB)
```


#Example with ChartJs Wheels
![Color Palette](https://raw.githubusercontent.com/ChiaraPassaro/color-palettes-range/master/screen/screenExample.png)

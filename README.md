#Note
This project is a fork from the excellent work of https://github.com/The5heepDev/iron-grid

The motivation to realize this fork has been to generate the grid system through css exclusively, the original project uses javascript to generate its responsiveness

This project are heavy inspired in Bootstrap Grid System and use only CSS and media queries to give you a responsiveness capabilities. In the Future this project will be recoded based on Bootstrap Grid Syntax

#Demo
[Plunker](https://plnkr.co/edit/sBg2hZ)

## Styling

The following custom properties are available for styling:

| Custom property          | Description            | Default |
| ------------------------ | ---------------------- | ------- |
| `--iron-container-width` | Width of the Container | `90%`   |
| `--iron-responsive-container-element-style` | Permit to override grid style element | `null`   |
 
## Grid System 

Our standard grid has 12 columns. No matter the size of the browser, each of these columns will always have an equal width.

![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/1-desktop.png)

To get a feel of how the grid is used in HTML. Take a look at this code below which will produce a similar result as the one above.

```html
<iron-responsive-container>

    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>
    <div class="m1 example blue">.m1</div>

    <div class="m8 example red">.m8</div>
    <div class="m4 example red">.m4</div>

    <div class="m4 example purple">.m4</div>
    <div class="m4 example purple">.m4</div>
    <div class="m4 example purple">.m4</div>

    <div class="m6 example green">.m6</div>
    <div class="m6 example green">.m6</div>

</iron-responsive-container>
```

### Offsets

To offset, simply add `offset-m*` to the class where `m` signifies the screen class-prefix (s = small, m = medium, l = large) and the number after is the number of columns you want to offset by.

![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/4-desktop.png)

```html
<iron-responsive-container>
    
    <div class="m4 example blue">.m4</div>
    <div class="m4 offset-m4 example blue">.m4 .offset-m4</div>
    
    <div class="m3 offset-m3 example red">.m3 .offset-m3</div>
    <div class="m3 offset-m3 example red">.m3 .offset-m3</div>
    
    <div class="m6 offset-m3 example purple">.m6 .offset-m3</div>
    
</iron-responsive-container>

<iron-responsive-container>
    <div class="xs6 s4 example blue"> xs6 s4 </div>
    <div class="xs6 s4 example blue"> xs6 s4 </div>
    <div class="xs6 offset-xs3 s4 offset-s0 example purple">xs6 offset-xs3 s4 offset-s0</div>
</iron-responsive-container>

```

### Nesting & Orders
You can nested a elements inside other elements if you want it, only need add a container with max with and flex display 

You can change the normal element's order of appearance on the screen. To do this, simply add `order-s1` to the class where `s` signifies the screen class-prefix (s = small, m = medium, l = large) and the number is the appearance order (from 1 to 12). The default element order is 6, so the page will load in order of number (ie. order-s1 order-s2 order-s3 etc.)

![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/5-desktop.png)

```html
<iron-responsive-container>
    <div class="s9 example blue">
        Level 1: .s9
        <div style="display:flex;width:100%">
            <div class="xs8 s6 example purple">
                Level 2: .xs8 .s6
            </div>
            <div class="xs4 s6 example purple">
                Level 2: .xs4 .s6
            </div>
        </div>
    </div>
</iron-responsive-container>

<iron-responsive-container>
    <div class="m9 order-m3 example blue">.m9 .order-m3</div>
    <div class="m3 order-m1 example red">.m3 .order-m1</div>
</iron-responsive-container>
```

### Creating Responsive Layouts

Above we showed you how to layout elements using our grid system. Now we'll show you how to design your layouts so that they look great on all screen sizes.

| . | Mobile Devices &lt;= 480px | Mobile Devices &lt;= 960px | Tablet Devices &lt;= 1280px | Desktop Devices &lt;= 1600px | Desktop Devices &gt; 1600px |
|-----------------------|----------------------------|----------------------------|----------------------------|-----------------------------|-----------------------------|
| **Class Prefix**      | .xs                        | .s                         | .m                         | .l                          | .xl                         |
| **Number of Columns** | 12                         | 12                         | 12                         | 12                          | 12                          |

### Adding Responsiveness

In the previous examples, we only defined the size for medium screens using `m12`.  But we can use whataver class prefix enunced upward and this clasess make your site responsive easy


![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/2-desktop.png)

```html
<iron-responsive-container>
    <!-- Stack the columns on mobile by making one full-width and the other half-width -->
    
    <div class="xs12 m8 example blue">.xs12 .m8</div>
    <div class="xs6  m4 example blue">.xs6 .m4</div>
    

    <!-- Columns start at 50% wide on mobile and bump up to 33.3% wide on desktop -->
    
    <div class="xs6 m4 example red">.xs6 .m4</div>
    <div class="xs6 m4 example red">.xs6 .m4</div>
    <div class="xs6 m4 example red">.xs6 .m4</div>
    

    <!-- Columns are always 50% wide, on mobile and desktop -->
    
    <div class="xs6 example purple">.xs6</div>
    <div class="xs6 example purple">.xs6</div>
    
</iron-responsive-container>

<iron-responsive-container>			
    <div class="xs12 s6 m8 example blue">.xs12 .s6 .m8</div>
    <div class="xs6 m4 example blue">.xs6 .m4</div>
    
    <div class="xs6 s4 example red">.xs6 .s4</div>
    <div class="xs6 s4 example red">.xs6 .s4</div>

    <div class="xs6 s4 example purple">.xs6 .s4</div>
</iron-responsive-container>
```

### Responsiveness Example

| Desktop  | Mobile       |              
| -------- | ------------ |
|![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/1-desktop.png) | ![Mobile-1](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/1-mobile.png) |
|                                                                                                        | ![Mobile-1](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/11-mobile.png) |
|![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/2-desktop.png) | ![Mobile-1](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/2-mobile.png) |
|![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/3-desktop.png) | ![Mobile-1](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/3-mobile.png) |
|![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/4-desktop.png) | ![Mobile-1](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/4-mobile.png) |
|![Desktop](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/5-desktop.png) | ![Mobile-1](https://raw.githubusercontent.com/jmtt89/iron-responsive-container/master/img/5-mobile.png) |

### Licensing

iron-responsive-container is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of the License, or (at your option) any later version.

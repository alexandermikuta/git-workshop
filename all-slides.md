<!-- section 0 -->

# markdeck {#markdeck .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

collaborative slide editing made easy

![](fab%20fa-markdown)
![](fab%20fa-docker)
![](fab%20fa-html5)
![](fab%20fa-css3)
![](fab%20fa-js-square)

`<small>`{=html} arne\@hilmann.de • 2020`</small>`{=html}

[![](fab%20fa-github)](https://github.com/arnehilmann/markdeck)
[![](fab%20fa-docker)](https://hub.docker.com/r/arne/markdeck-pandoc/)
[![](fas%20fa-envelope)](email:arne@hilmann.de)

<!-- section 1 -->

# features {#features .light-on-dark rx="1" bgcss="sea-gradient"}

converts markdown to complex`</br>`{=html} HTML5 slides

should run on all \*nix platforms,`</br>`{=html} windows`<small>`{=html}?`</small>`{=html} and MacOS

<!-- section 2 -->

# features, contd. {#features-contd. rx="0" ry="1"}

cool
• graphical
• easy
• robust
• collaborative
• adaptable

<!-- section 3 -->

# cool looking {#cool-looking .light-on-dark bg="white;assets/img/paperclip.gif" rx="-1" ry="0"}

leverages battle-proven`</br>`{=html}HTML5 presentation frameworks:

revealjs • impressjs

<!-- section 4 -->

# graphical

content as markdown`</br>`{=html}
`<small>`{=html}
incl unicode ♥
emojis 😎
font-awesome
![](fas%20fa-desktop)
`</small>`{=html}

images as asciiart`</br>`{=html}
`<small>`{=html}charts, diagrams, graphs, math, ...`</small>`{=html}

<!-- section 5 -->

# easy {#easy rx="0" ry="-1"}

completely text-based`</br>`{=html}
`<small>`{=html}use your preferred editor/IDE`</small>`{=html}

auto-reload
►
fast feedback

<!-- section 6 -->

# robust

modify and present your slides`<br/>`{=html} *without* `<br/>`{=html}internet uplink

[![](fas%20fa-wifi%20fa-stack-1x)
![](fas%20fa-slash%20fa-stack-1x)]{.fa-stack .fa-1x}

<!-- section 7 -->

# collaborative {#collaborative rx="1" ry="0"}

presentation-as-code

use your normal version control system

<!-- section 8 -->

# adaptable

you can always fall back to`</br>`{=html}plain HTML/CSS

<!-- section 9 -->

# code, highlighted

``` {.java}
public class Example {
    public static final void main(String[] args) {
        // foo
        System.out.println("Hello World");
    }
}
```

<!-- section 10 -->

# asciiart (ditaa) {#asciiart-ditaa .ltr rx="0" ry="1"}

``` {.nohighlight style="width: 40%; height: 100%; font-size: 40%;"}
+-----------------------------+
| Node A                      |
|                             |
| +----------+   +----------+ |
| |          |   |          | |
| | Frontend |   | Foo      | |
| |          |   |          | |
| |          |   | {s}      | |
| +-----+----+   +----------+ |
|       ^                     |
|       |                     |
|       \-service-\           |
|                 |           |
+-----------------|-----------+
                  |
+-----------------|-----------+
| Node B          |           |
|       /---------/           |
|       |                     |
|       v                     |
| +-----+----+   +=---------+ |
| |          |   |          | |
| | Frontend |   | Bar      | |
| |          |   |          | |
| |          |   | {s}      | |
| +----------+   +----------+ |
+-----------------------------+
```

►

``` {.render_ditaa args="--transparent --scale 1 --font 'Raleway'"}
+-----------------------------+
| Node A                      |
|                             |
| +----------+   +----------+ |
| |          |   |          | |
| | Frontend |   | Foo      | |
| |          |   |          | |
| |          |   | {s}      | |
| +-----+----+   +----------+ |
|       ^                     |
|       |                     |
|       \-service-\           |
|                 |           |
+-----------------|-----------+
                  |
+-----------------|-----------+
| Node B          |           |
|       /---------/           |
|       |                     |
|       v                     |
| +-----+----+   +=---------+ |
| |          |   |          | |
| | Frontend |   | Bar      | |
| |          |   |          | |
| |          |   | {s}      | |
| +----------+   +----------+ |
+-----------------------------+
```

<!-- section 11 -->

# asciiart (a2s) {#asciiart-a2s .ltr}

``` {.nohighlight style="width: 40%;"}
#--------------------.
|[0]                 |
| .---# .---# #---.  |
| |[1]| |[1]| |[1]|  |
| #---' #---' '---#  |
|   ^     ^     ^    |
#---+-----+-----+----#
|   |     |     |    |
|   a     2 sketch   |
'--------------------#

[0]: {"fill": "#933"}
[1]: {"fill": "#bbb","a2s:delref":true,"a2s:type":"storage"}
```

►

``` {.render_a2s}
#--------------------.
|[0]                 |
| .---# .---# #---.  |
| |[1]| |[1]| |[1]|  |
| #---' #---' '---#  |
|   ^     ^     ^    |
#---+-----+-----+----#
|   |     |     |    |
|   a     2 sketch   |
'--------------------#

[0]: {"fill": "#933","a2s:delref":true}
[1]: {"fill": "#bbb","a2s:delref":true,"a2s:type":"storage"}
```

<!-- section 12 -->

# asciiart (sketchy) {#asciiart-sketchy .ltr}

``` {.nohighlight style="width: 45%;"}
#=----------------------------#
|[0]                          |
| Node                        |
|                             |
| #----------#   #----------# |
| |          |   |[1]       | |
| | front    |   | foo      | |
| |          |   |          | |
| |  ^       |   |          | |
| |  |       |   |          | |
| #--|-------#   #----------# |
|    |                ^       |
|    |                |       |
|    '-- service    --'       |
|                             |
#-----------------------------#
[0]: {"fill":"#fff","fillStyle":"solid","a2s:delref":true}
[1]: {"fill":"#eee","fillStyle":"solid","a2s:delref":true}
```

►

``` {.render_a2sketch}

#-----------------------------#
|[0]                          |
| Node                        |
|                             |
| #----------#   #----------# |
| |          |   |[1]       | |
| |front     |   | foo      | |
| |          |   |          | |
| |  ^       |   |          | |
| |  |       |   |          | |
| #--|-------#   #----------# |
|    |                ^       |
|    |                |       |
|    '-- service    --'       |
|                             |
#-----------------------------#
[0]: {"fill":"#fff","fillStyle":"solid","a2s:delref":true}
[1]: {"fill":"#eee","fillStyle":"solid","a2s:delref":true}
```

<!-- section 13 -->

# asciiart (svgbob) {#asciiart-svgbob .ltr rx="-1" ry="0"}

``` {.nohighlight style="width: 40%; height: 100%;"}
        P *
           \
            \
       v0    \       v3
         *----\-----*
        /      v X   \
       /        o     \
      /                \
  v1 *------------------* v2
```

►

``` {.render_svgbob args="--scale 10 --font-family Raleway --font-size 24"}
        P *
           \
            \
       v0    \       v3
         *----\-----*
        /      v X   \
       /        o     \
      /                \
  v1 *------------------* v2
```

<!-- section 14 -->

# asciiart (mermaid) {#asciiart-mermaid .ltr}

``` {.nohighlight style="width: 40%; height: 100%; font-size: 40%;"}
graph LR
   a --> b & c--> d
```

►

``` {.render_mermaid args="-w 400" style="font-size: 100%;"}
graph LR
   a --> b & c--> d
```

<!-- section 15 -->

# asciiart (plantuml) {#asciiart-plantuml .ltr}

``` {.nohighlight style="width: 40%; font-size: 60%;"}
@startuml
Bob->Alice : hello
Alice->Bob : oh, you again...
Bob->Alice : ??
@enduml
```

►

``` {.render_plantuml args="-Sbackgroundcolor=transparent -SdefaultFontSize=24 -SdefaultFontName=Raleway"}
@startuml
Bob->Alice : hello
Alice->Bob : oh, you again...
Bob->Alice : ??
@enduml
```

<!-- section 16 -->

# asciiart (graphviz) {#asciiart-graphviz .ltr}

``` {.nohighlight style="width: 50%; font-size: 60%;"}
digraph G {
    bgcolor=transparent;
    node [style=filled,color=white];

    a -> b -> c;
    a -> c;
    b -> d;
}
```

►

``` {.render_dot args="-Nfontname=Raleway"}
digraph G {
    bgcolor=transparent;
    node [style=filled,color=white];

    a -> b -> c;
    a -> c;
    b -> d;
}
```

<!-- section 17 -->

# charts (vega-lite) {#charts-vega-lite .ltr rx="0" ry="-1"}

``` {.json style="width: 50%; font-size: 30%;"}
{
    "$schema": "https://vega.github.io/schema/vega-lite/v2.0.json",
    "data": {
        "values": [
            {"a": "A","b": 28}, {"a": "B","b": 55}, {"a": "C","b": 43},
            {"a": "D","b": 91}, {"a": "E","b": 81}, {"a": "F","b": 53},
            {"a": "G","b": 19}, {"a": "H","b": 87}, {"a": "I","b": 52}
        ]
    },
    "width": 600,
    "height": 300,
    "mark": "area",
    "encoding": {
        "x": {"field": "a", "type": "ordinal"},
        "y": {"field": "b", "type": "quantitative", "scale": {"domain": [0, 100]}}
    }
}
```

►

``` {.render_vegalite}
{
    "$schema": "https://vega.github.io/schema/vega-lite/v2.0.json",
    "data": {
        "values": [
            {"a": "A","b": 28}, {"a": "B","b": 55}, {"a": "C","b": 43},
            {"a": "D","b": 91}, {"a": "E","b": 81}, {"a": "F","b": 53},
            {"a": "G","b": 19}, {"a": "H","b": 87}, {"a": "I","b": 52}
        ]
    },
    "width": 250,
    "height": 300,
    "mark": "area",
    "encoding": {
        "x": {"field": "a", "type": "ordinal"},
        "y": {"field": "b", "type": "quantitative", "scale": {"domain": [0, 100]}}
    },
    "config": {
        "axis": {
            "labelFont": "Raleway",
            "labelFontSize": 18,
            "titleFont": "Raleway",
            "titleFontSize": 24,
            "titleAngle": 0
        },
        "axisX": {
            "labelAngle": 0
        }
    }
}
```

<!-- section 18 -->

# math equations

``` {.nohighlight style="width: 100%; font-size: 70%;"}
$a^2 + b^2 = c^2$
```

$a^2 + b^2 = c^2$

 

``` {.nohighlight style="width: 100%; font-size: 70%;"}
$$e = \mathop
    {\lim }\limits_{n \to \infty }
    \left( {1 + \frac{1}{n}} \right)^n$$
```

$$
e = \mathop
    {\lim }\limits_{n \to \infty }
    \left( {1 + \frac{1}{n}} \right)^n
$$

<!-- section 19 -->

# terminal session (asciinema) {#terminal-session-asciinema rx="0" ry="-1" rz="0" bg="#121314"}

`<asciinema-player src="./assets/test.json"
poster="npt:0:21"
idle-time-limit=1
speed=2
rows=18
font-size="medium"

>`{=html} `</asciinema-player>`{=html}

<!-- section 20 -->

# Thank You!

[pandoc](http://pandoc.org)
•
[reveal.js](http://lab.hakim.se/reveal-js/#/)
•
[impress.js](https://github.com/impress/impress.js)
`</br>`{=html}

[plantuml](http://plantuml.com)
•
[ditaamini](https://github.com/pepijnve/ditaa.git)
•
[graphviz](http://www.graphviz.org)
•
[svgbob](https://ivanceras.github.io/svgbob-editor/)
•
[asciinema](https://github.com/asciinema/asciinema-player)
`</br>`{=html}

[decktape](https://github.com/astefanutti/decktape)
•
[vega-lite](https://vega.github.io/vega-lite/)
•
[math-jax](https://www.mathjax.org)
•
[font awesome](https://fontawesome.com/)
`</br>`{=html}

🙃

<!-- section 21 -->

#  {#section .flush-right bg="White;themes/example/img/wordcloud.svg" rx="1" ry="0"}

[`https://github.com/arnehilmann/markdeck`{.render_qr}](https://github.com/arnehilmann/markdeck)

<!-- section 22 -->

# markdeck {#markdeck-3 .light-on-dark skipon="impress" bgcss="sea-gradient"}

collaborative slide editing made easy

![](fab%20fa-markdown)
![](fab%20fa-docker)
![](fab%20fa-html5)
![](fab%20fa-css3)
![](fab%20fa-js-square)
`<img src="assets/img/buddy-egyptian.svg" style="height:120px; vertical-align:middle; box-shadow:none;"/>`{=html}

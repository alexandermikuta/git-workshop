---
title: Github-Workshop
# variant: reveal
# variant: impress
# pdf: github-workshop.pdf
# standalone: github-workshop.html
# highlight_style: grayscale
highlight_style: github-gist
asciinema: true
themes: mytheme
# themes: mono

# slideNumber: true
# autoSlide: 5000
# controls: true
# controlsTutorial: true
# controlsLayout: edges
# pdf_size: 1189x841
# pdf_size: 1024x768
---

# Git Workshop {bgcss=sea-gradient x=0 y=0 rz=-.1 .light-on-dark}

the distributed source control

<img src="assets/git.png style="vertical-align:middle; box-shadow:none;"/>

<small> Alexander Mikuta • 2022</small>

# features {rx=1 bgcss=sea-gradient .light-on-dark}

converts markdown to complex</br> HTML5 slides

should run on all \*nix platforms,</br> windows<small>?</small> and MacOS

# features, contd. {rx=0 ry=1}

cool
• graphical
• easy
• robust
• collaborative
• adaptable

# cool looking {bg=white;assets/img/paperclip.gif .light-on-dark rx=-1 ry=0}

leverages battle-proven</br>HTML5 presentation frameworks:

revealjs • impressjs

# graphical

content as markdown</br>
<small>
incl unicode ♥
emojis 😎
font-awesome
![](fas fa-desktop)
</small>

images as asciiart</br>
<small>charts, diagrams, graphs, math, …</small>

# easy {rx=0 ry=-1}

completely text-based</br>
<small>use your preferred editor/IDE</small>

auto-reload
►
fast feedback

# robust

modify and present your slides<br/> _without_ <br/>internet uplink

[
![](fas fa-wifi fa-stack-1x)
![](fas fa-slash fa-stack-1x)
]{.fa-stack .fa-1x}

# collaborative {rx=1 ry=0}

presentation-as-code

use your normal version control system

# asciiart (ditaa) {.ltr rx=0 ry=1}

```{.nohighlight style="width: 40%; height: 100%; font-size: 40%;"}
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

```{.render_ditaa args="--transparent --scale 1 --font 'Raleway'"}

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

# asciiart (a2s) {.ltr}

```{.nohighlight style="width: 40%;"}
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

```render_a2s
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

# asciiart (sketchy) {.ltr}

```{.nohighlight style="width: 45%;"}
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

```render_a2sketch


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

# asciiart (svgbob) {.ltr rx=-1 ry=0}

```{.nohighlight style="width: 40%; height: 100%;"}
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

```{.render_svgbob args="--scale 10 --font-family Raleway --font-size 24"}

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

# asciiart (mermaid) {.ltr}

```{.nohighlight style="width: 40%; height: 100%; font-size: 40%;"}
graph LR
   a --> b & c--> d
```

►

```{.render_mermaid args="-w 400" style="font-size: 100%;"}
graph LR
   a --> b & c--> d
```

# asciiart (plantuml) {.ltr}

```{.nohighlight style="width: 40%; font-size: 60%;"}
@startuml
Bob->Alice : hello
Alice->Bob : oh, you again...
Bob->Alice : ??
@enduml
```

►

```{.render_plantuml args="-Sbackgroundcolor=transparent -SdefaultFontSize=24 -SdefaultFontName=Raleway"}
@startuml
Bob->Alice : hello
Alice->Bob : oh, you again...
Bob->Alice : ??
@enduml
```

# asciiart (graphviz) {.ltr}

```{.nohighlight style="width: 50%; font-size: 60%;"}
digraph G {
    bgcolor=transparent;
    node [style=filled,color=white];

    a -> b -> c;
    a -> c;
    b -> d;
}
```

►

```{.render_dot args="-Nfontname=Raleway"}
digraph G {
    bgcolor=transparent;
    node [style=filled,color=white];

    a -> b -> c;
    a -> c;
    b -> d;
}
```

# charts (vega-lite) {.ltr rx=0 ry=-1}

```{.json style="width: 50%; font-size: 30%;"}
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

```render_vegalite
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

# {bg=White;themes/mytheme/img/wordcloud.svg .flush-right rx=1 ry=0}

[`https://github.com/arnehilmann/markdeck`{.render_qr}](https://github.com/arnehilmann/markdeck)

# markdeck {.skip skipon="reveal" scale=5 x=1.8}

# {.skip skipon="reveal" scale=1 .flush-right rx=0 ry=.25}

impress.js-variant

# markdeck {x=3 y=-2.5 z=3000 rotate-y=60 scale=2 skipon="reveal"}

collaborative slide editing made easy

![](fab fa-markdown)
![](fab fa-docker)
![](fab fa-html5)
![](fab fa-css3)
![](fab fa-js-square)

# {x=0 y=0 scale=2 skipon="reveal" id=overview}

# markdeck {skipon="impress" bgcss=sea-gradient .light-on-dark}

collaborative slide editing made easy

![](fab fa-markdown)
![](fab fa-docker)
![](fab fa-html5)
![](fab fa-css3)
![](fab fa-js-square)

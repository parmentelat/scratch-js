---
jupytext:
  cell_metadata_filter: all,-hidden,-heading_collapsed
  formats: md:myst
  notebook_metadata_filter: all,-language_info,-toc,-jupytext.text_representation.jupytext_version,-jupytext.text_representation.format_version
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Javascript (Node.js)
  language: javascript
  name: javascript
---

<div class="licence">
<span>Licence CC BY-NC-ND</span>
</div>

+++

Hey folks

```{code-cell}
"use strict";
```

```{code-cell}
console.log(`Hello world`)
```

```{code-cell}
print = console.log
```

```{code-cell}
print("hello world")
```

```{code-cell}
10 * 200
```

```{code-cell}
// it's best to declare a variable only once
let whom = "world";
```

```{code-cell}
whom = "world";
print(`hello ${whom}`)
```

```{code-cell}
function fact(n){
    if (n<=1)
        return 1
    return n*fact(n-1);
}
```

```{code-cell}
fact(123)
```

```{code-cell}
[1,2,3].forEach(x => print(x))
```

```{code-cell}
// c'est comme de faire
[1,2,3].forEach(function(x) {print(x);})
```

### figures

+++

from [issue # 186](https://github.com/n-riesco/ijavascript/issues/186) on the ijavascript git repo, I tried these 2 snippets as is; I could not get the second one to fly at all despite having `npm install`'ed corresponding package

```{code-cell}
Plotly = require("ijavascript-plotly");
Plotly([{y: [10, 30, 20]}], {title: "Plotly from IJavascript"})
```

```{code-cell}
var Plot = require('plotly-notebook-js');
var NotebookPlot = Plot.createPlot().constructor;
NotebookPlot.prototype._toHtml = NotebookPlot.prototype.render;
Plot.createPlot([{ x: [1,2,3], y: [3,4,5] }], { title: 'Plotly in Jupyter!' });
```

### Visualizing JS objects

```{code-cell}
$$.json({a: {b:1}})
```

```{code-cell}
my_funny_variable = 10;
```

```{code-cell}
my_funny_variable
```

### back to graphics

```{code-cell}
var fs = require('fs');
var d3 = require('d3');
var jsdom = require('jsdom');
var { JSDOM } = jsdom;

var document = new JSDOM("<html><body></body></html>");
var svg = d3.select(document.window.document.body).append("svg");

svg.append("rect")
    .attr("width", 80)
    .attr("height", 80)
    .style("fill", "orange");

$$.svg("<svg>" + svg.html() + "</svg>");
```

# padding

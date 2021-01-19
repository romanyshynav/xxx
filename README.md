#### [How to work with file ](#user-content-how-to-work-with-file)
#### [How to work online ](#user-content-how-to-work-online)
#### [How to install local GraphViz ](#user-content-how-to-install-local-graphviz)
#### [How to use terminal ](#user-content-how-to-use-terminal)
#### [How to use GVEdit? ](#user-content-how-to-use-GVEdit?)
#### [Graph structure ](#user-content-graph-structure)
#### [How to work with code ](#user-content-how-to-work-with-code)

## How to work with file?
 Create and save a `".dot"-file`. It can be edited using:
   - Notepad
   - local GUI,
   - copy the code from the `".dot"-file` to the online editor
 [GraphVizOnline](https://dreampuf.github.io/GraphvizOnline/), provide codding, then copy back 
 and save <b> (best solution) </b>.

## How to work online?
   For convenience, it is better to use an online editor -
[GraphVizOnline](https://dreampuf.github.io/GraphvizOnline/).	
It only displays the chart on the result screen, but does not save it to a file. So after work
you need to copy the code to a file on your computer with the extension`".dot"`. And then convert this 
file in the desired output format(`png, pdf, svg, ...`) using the local GUI or the terminal (CMD).

## How to install local GraphViz?
For <b>Windows</b> (32, 64) - 7, 8, 10 you need to download and install the local program `GVEdit` -
[Download GVEdit](https://www.softsalad.ru/software/razrabotka-po/instrumenty/graphviz).  
On <b> other operating systems </b> GraphViz does not work . Therefore it is necessary to work through 
the terminal. You need to install a terminal from the site -
[Download Terminal](https://graphviz.org/download/).

## How to use terminal?
You do not need to install it for <b> Windows </b>. To do this, we use the program `GVEdit`.
For <b> other operating systems </b> you need to install a terminal from the site -
[Download Terminal](https://graphviz.org/download/).  
See the version.
```
dot -v
```
You need to go to the directory with `.dot-файлами`:
```
cd path_to_folder
```
Now you can now convert `".dot "-files` to any format from the specified directory:
```
dot -Tpng -oOutput.png Input.dot
dot -Tpdf -oOutput.pdf Input.dot
dot -Tjpg -oOutput.jpg Input.dot
dot -Tjpeg -oOutput.jpg Input.dot
dot -Tsvg -oOutput.svg Input.dot
```

## How to use GVEdit?
1. `File -> Open -> path_to_file`  
Open the desired `.dot-file` and edit it. There will be two windows. One to edit
code, the second with its visual representation.
2. `Graph -> Settings -> we use "Layout Engine - dot", choose desired format"Output File Type", 
path to save "Output File Name" -> OK`  
Convert `.dot-file` to any format.
 
 ## Graph structure
- **Block-1: Variables**, where variables are listed. <b> Variables </b> are our blocks in between 
arrows will be drawn. Here is their name, relations, style. For correct display it is required
make sure that the names of the variables are not repeated. For identical variable names we add in
end character `" _ "`. That way we will know that they are <b> unique </b>.
- **Block-2: Relations like "Service -> Topic (SNS) -> Event"**, where we display separately
<b> each service </b>. These blocks are marked in gray. Each block is a separate area of visibility.
Here are the relationships between the blocks inside service(`Service -> Topic -> Event`), 
styles for arrows and background color blocks.
- **Block-3: Relations like "Event -> Services"** displays the <b>relationship between all services</b>
 (`Event -> Service`). Styles for these arrows (relations) are also listed here.

## How to work with code?
Style-attribute for the node or arrow applies to the <b> scope </b> in which it is specified,
and <b> nested </b> scopes. For example, for a node:   
`node [xlabel = "SQS", shape = "oval", color = "chartreuse4", fillcolor = "chartreuse1"]` -
 settings for the entire scope.  
So that the nodes that follow it do not inherit the style-attribute `xlabel= "SQS"`, write below the code:  
`node [xlabel = ""]` - we redefine it with an empty symbol.  
Other attributes will be inherited. If they do not suit us - just redefine them.  
For more details, check this documentation:
[Tutorial](https://rich-iannone.github.io/DiagrammeR/graphviz_and_mermaid.html#colors)

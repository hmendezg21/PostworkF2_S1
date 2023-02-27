An h1 header
============

Paragraphs are separated by a blank line.

2nd paragraph. *Italic*, **bold**, and `monospace`. Itemized lists
look like:

* this one
* that one
* the other one

Note that --- not considering the asterisk --- the actual text
content starts at 4-columns in.

> Block quotes are
> written like so.
>
> They can span multiple paragraphs,
> if you like.

Use 3 dashes for an em-dash. Use 2 dashes for ranges (ex., "it's all
in chapters 12--14"). Three dots ... will be converted to an ellipsis.
Unicode is supported. ☺



An h2 header
------------

Here's a numbered list:

1. first item
2. second item
3. third item

Note again how the actual text starts at 4 columns in (4 characters
from the left side). Here's a code sample:

    # Let me re-iterate ...
    for i in 1 .. 10 { do-something(i) }

As you probably guessed, indented 4 spaces. By the way, instead of
indenting the block, you can use delimited blocks, if you like:

~~~
define foobar() {
    print "Welcome to flavor country!";
}
~~~

(which makes copying & pasting easier). You can optionally mark the
delimited block for Pandoc to syntax highlight it:

~~~python
import time
# Quick, count to ten!
for i in range(10):
    # (but not *too* quick)
    time.sleep(0.5)
    print(i)
~~~



### An h3 header ###

Now a nested list:

1. First, get these ingredients:

    * carrots
    * celery
    * lentils

2. Boil some water.

3. Dump everything in the pot and follow
   this algorithm:

       find wooden spoon
       uncover pot
       stir
       cover pot
       balance wooden spoon precariously on pot handle
       wait 10 minutes
       goto first step (or shut off burner when done)

   Do not bump wooden spoon or it will fall.

Notice again how text always lines up on 4-space indents (including
that last line which continues item 3 above).

Here's a link to [a website](http://foo.bar), to a [local
doc](local-doc.html), and to a [section heading in the current
doc](#an-h2-header). Here's a footnote [^1].

[^1]: Some footnote text.

Tables can look like this:

Name           Size  Material      Color
------------- -----  ------------  ------------
<br>
All Business      9  leather       brown
Roundabout       10  hemp canvas   natural
Cinderella       11  glass         transparent

Table: Shoes sizes, materials, and colors.

(The above is the caption for the table.) Pandoc also supports
multi-line tables:

--------  -----------------------
Keyword   Text
--------  -----------------------
red       Sunsets, apples, and
other red or reddish
things.

green     Leaves, grass, frogs
and other things it's
not easy being.
--------  -----------------------

A horizontal rule follows.

***

<table style  = "width:100%; border: 1px solid black; "   >
  <tr style=" border: 1px solid black; background-color: #f1f1c1;">
    <th>Algorithm</th>
    <th>Parameters</th>
    <th>Update formula</th> 
  </tr>
  <tr >
        <td>
<b>SGD </b>       
        </td>
                <td>
<b>  \begin{align}
    \eta & = 0.01
      \end{align} </b>       
        </td>
          <td>
\begin{align}
   \beta_{t+1} & = \beta_{t} -  \eta v_t   \\
v_t & =  g_t
\end{align}
        </td>
    </tr>   
        <tr>
        <td>
<b>Momentum   </b>       
        </td>        
            <td>
<b>
    \begin{align}
    \eta & = 0.01\\
    \rho & = 0.0
      \end{align}               
                </b>       
        </td>
          <td>
\begin{align}
   \beta_{t+1} & = \beta_{t} -  \eta v_t   \\
v_t & = \rho v_{t-1} + (1-\rho) g_t
\end{align}
        </td>
    </tr> 
     <tr>
        <td>
<b>AdaGrad </b>        
        </td>
                 <td>
<b>\begin{align}
    \eta & = 0.01\\
    \epsilon & = 10^{-7}
      \end{align}</b>       
        </td>
          <td>
\begin{align}
   \beta_{t+1} &= \beta_{t} - \eta \frac{1}{\sqrt{s_t + \epsilon}}g_t  \\
s_t &=  s_{t-1} + g_t^2
\end{align}
        </td>
    </tr>
            <tr>
        <td>
<b>RMSProp </b>        
        </td>
                 <td>
<b>\begin{align}
    \eta & = 0.001\\
    \rho & = 0.9\\
    \epsilon & = 10^{-8}
      \end{align}</b>       
        </td>
          <td>
\begin{align}
   \beta_{t+1} &= \beta_{t} - \eta \frac{1}{\sqrt{s_t + \epsilon}}g_t  \\
s_t &= \rho s_{t-1} + (1-\rho)g_t^2
\end{align}
        </td>
    </tr>
    <tr>
        <td>
<b> Adam     </b>     
        </td>
         <td>
<b>\begin{align}
    \eta & = 0.001\\
    \rho_1 & = 0.9\\
    \rho_2 & = 0.999\\
    \epsilon & = 10^{-8}
      \end{align} </b>       
        </td>
          <td>
\begin{align}
   \beta_{t+1} &= \beta_{t} -  \eta\frac{1 }{\sqrt{\hat{s}_t  + \epsilon}}\hat{v}_t \\
    \hat{v}_t & = \frac{v_t}{ 1- \rho^t_1}\\
     \hat{s}_t & = \frac{s_t}{ 1- \rho^t_2}\\
v_t & = \rho_1 v_{t-1} + (1-\rho_1)g_t\\
s_t &= \rho_2 s_{t-1} + (1-\rho_2)g_t^2              
\end{align}
        </td>
    </tr>
        <tr>
        <td>
<b> Nadam     </b>     
        </td>
             <td>
<b>\begin{align}
     \eta & = 0.002\\
    \rho_1 & = 0.9\\
    \rho_2 & = 0.999\\
    \epsilon & = 10^{-7}
      \end{align} </b>       
        </td>
          <td>
\begin{align}
   \beta_{t+1} &= \beta_{t} -  \eta\frac{1}{\sqrt{\hat{s}_t  + \epsilon}}\tilde{v}_t  \\
    \tilde{v}_t & = \rho_1  \hat{v}_{t-1} + \frac{1-\rho_1}{1-\rho^t_1}g_t\\
    \hat{v}_t & = \frac{v_t}{ 1- \rho^t_1}\\
     \hat{s}_t & = \frac{s_t}{ 1- \rho^t_2}\\
v_t & = \rho_1 v_{t-1} + (1-\rho_1)g_t\\
s_t &= \rho_2 s_{t-1} + (1-\rho_2)g_t^2              
\end{align}
        </td>
    </tr>
    <tr>
        <td>
<b> AMSGrad    </b>     
        </td>
         <td>
<b>\begin{align}
     \eta & = 0.001\\
    \rho_1 & = 0.9\\
    \rho_2 & = 0.999\\
    \epsilon & = 10^{-7}
      \end{align}  </b>       
        </td>
          <td>
\begin{align}
   \beta_{t+1} &= \beta_{t} -  \eta\frac{{v}_t }{\sqrt{\hat{s}_t  + \epsilon}} \\
     \hat{s}_t & = \max\{\hat{s}_{t-1},s_t\}\\
v_t & = \rho_1 v_{t-1} + (1-\rho_1)g_t\\
s_t &= \rho_2 s_{t-1} + (1-\rho_2)g_t^2              
\end{align}
        </td>
    </tr>
</table> 




Here's a definition list:

apples
: Good for making applesauce.

oranges
: Citrus!

tomatoes
: There's no "e" in tomatoe.

Again, text is indented 4 spaces. (Put a blank line between each
term and  its definition to spread things out more.)

Here's a "line block" (note how whitespace is honored):

| Line one
|   Line too
| Line tree

and images can be specified like so:

![example image](example-image.jpg "An exemplary image")

Inline math equation: $\omega = d\phi / dt$. Display
math should get its own line like so:     

$$I = \int \rho R^{2} dV$$

And note that you can backslash-escape any punctuation characters
which you wish to be displayed literally, ex.: \`foo\`, \*bar\*, etc.

Editor.md
Open source online Markdown editor.

        yc=448 - RADIUS;
        while(!kbhit())
        {
            setcolor(RED);
            xl= RADIUS * cos(angle * RADS);
            yl= RADIUS * sin(angle * RADS);
            circle(xc,yc,RADIUS);
            circle(xc+100,yc,RADIUS);
            setcolor(BLUE);
            line(xc+xl,yc+yl,xc+xl+100,yc+yl);
            line(xc-xl,yc-yl,xc-xl+100,yc-yl);
            delay(10);
            setcolor(BLACK);
            circle(xc,yc,RADIUS);
            circle(xc+100,yc,RADIUS);
            line(xc+xl,yc+yl,xc+xl+100,yc+yl);
            line(xc-xl,yc-yl,xc-xl+100,yc-yl);
            angle +=1;
            xc+=2 *M_PI * RADIUS /360;
            if(xc-RADIUS>getmaxx())
                xc= -RADIUS-100;
            
        }
    }
    main()
    {
        int gr_drive = DETECT, gr_mode;
        initgraph(&gr_drive,& gr_mode,"");
        line(0,450, getmaxx(),450);
        line(0,451,getmaxx(),451);
        banhxelua();
        getch();
        closegraph();
        
    }
    


 #include <winbgim.h>
 int main(){
     initwindow(700,500);
     setbkcolor(0);
    cleardevice();
    setcolor(11);
    int x=getmaxx();
    int y=getmaxy();
    rectangle(5,5,x-5,y-5);
    floodfill(1,1,11);
    setcolor(12);
    circle(350,250,200);
    circle(350,250,150);
    setfillstyle(1,9);
    floodfill(350,250,12);
    setfillstyle(1,12);
   floodfill(160,250,12);
   setcolor(12);
   setlinestyle(1,2,50);
   line(250,130,450,350);
   line(250,350,450,130);
    while(!kbhit()) delay(1);
    return 0;    
 }


#include<graphics.h>
#include<math.h>
#define FCT 0.7071067
#define RADS 0.017453293
#define RADIUS 21
void banhxelua()
{
    double angle = 0 ,xc = 100, yc, xl, yl;
    yc = 448 - RADIUS;
    while (!kbhit())
    {
        setcolor(13);
        xl = RADIUS * cos(angle * RADS);
        yl = RADIUS * sin(angle * RADS);
        circle(xc, yc, RADIUS);
        circle(xc + 100, yc, RADIUS);
        setcolor(RED);
        line(xc + xl, yc + yl, xc + xl + 100, yc + yl);
        line(xc - xl, yc - yl, xc - xl - 100, yc - yl);
        delay(10);
        setcolor(BLACK);
        circle(xc, yc, RADIUS);
        circle(xc + 100, yc, RADIUS);
        line(xc + xl, yc + yl, xc + xl + 100, yc + yl);
        line(xc - xl, yc - yl, xc - xl - 100, yc - yl);
        angle += 1;
        xc += 2 * M_PI * RADIUS / 360;
        if (xc-RADIUS >getmaxx())
            xc = - RADIUS - 100;
    }
}
main()
{
    int gr_drive = DETECT, gr_mode;
    initgraph(&gr_drive, &gr_mode, "");
    line(0,450,getmaxx(),450);
    line(0,451,getmaxx(),451);
    banhxelua();
    getch();
    closegraph();
}


#include<graphics.h>
#include<math.h>
#define FCT 0.7071067
#define RADS 0.017453293
#define RADIUS 21
void banhxelua()
{
    double angle =0,xc=100,yc,xl,yl;
    yc=448 - RADIUS;
    while(!kbhit())
    {
        setcolor(RED);
        xl= RADIUS * cos(angle * RADS);
        yl= RADIUS * sin(angle * RADS);
        circle(xc,yc,RADIUS);
        circle(xc+100,yc,RADIUS);
        setcolor(BLUE);
        line(xc+xl,yc+yl,xc+xl+100,yc+yl);
        line(xc-xl,yc-yl,xc-xl+100,yc-yl);
        delay(10);
        setcolor(BLACK);
        circle(xc,yc,RADIUS);
        circle(xc+100,yc,RADIUS);
        line(xc+xl,yc+yl,xc+xl+100,yc+yl);
        line(xc-xl,yc-yl,xc-xl+100,yc-yl);
        angle +=1;
        xc+=2 *M_PI * RADIUS /360;
        if(xc-RADIUS>getmaxx())
            xc= -RADIUS-100;
    }
}
main()
{
    int gr_drive = DETECT, gr_mode;
    initgraph(&gr_drive,& gr_mode,"");
    line(0,450, getmaxx(),450);
    line(0,451,getmaxx(),451);
    banhxelua();
    getch();
    closegraph();
}
Example
<link rel="stylesheet" href="editormd/css/editormd.css" />
<div id="test-editor">
    <textarea style="display:none;">### Editor.md

**Editor.md**: The open source embeddable online markdown editor, based on CodeMirror & jQuery & Marked.
    </textarea>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<script src="editormd/editormd.min.js"></script>
<script type="text/javascript">
    $(function() {
        var editor = editormd("test-editor", {
            // width  : "100%",
            // height : "100%",
            path   : "editormd/lib/"
        });
    });
</script>Copy
More Examples >>

Features
Support Standard Markdown / CommonMark and GFM(GitHub Flavored Markdown);
Full-featured: Real-time Preview, Image (cross-domain) upload, Preformatted text/Code blocks/Tables insert, Code fold, Search replace, Read only, Themes, Multi-languages, L18n, HTML entities, Code syntax highlighting...;
Markdown Extras : Support ToC (Table of Contents), Emoji, Task lists, @Links...;
Support TeX (LaTeX expressions, Based on KaTeX), Flowchart and Sequence Diagram of Markdown extended syntax;
Support identification, interpretation, fliter of the HTML tags;
Support AMD/CMD (Require.js & Sea.js) Module Loader, and Custom/define editor plugins;
Compatible with all major browsers (IE8+), compatible Zepto.js and iPad;
Support Custom theme styles;
Download & install
Latest version: v1.5.0，Update: 2015-06-09



 


Or NPM install:

npm install editor.md



Or Bower install:

bower install editor.md




Change logs:

CHANGES

Dependents
Projects :

CodeMirror
marked
jQuery
FontAwesome
github-markdown.css
KaTeX
Rephael.js
prettify.js
flowchart.js
sequence-diagram.js
Prefixes.scss

Development tools :

Visual Studio Code
Sass/Scss
Gulp.js
License
Editor.md follows the MIT License, Anyone can freely use.





Fork me on Github :







Users

 Contact Us: editor.md@ipandao.com


Editor.md
Copyright © 2015-2019 Editor.md, MIT license.

Design & Develop By: Pandao      

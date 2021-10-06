![](https://i0.wp.com/s1.uphinh.org/2021/10/06/imagef923d61af5bc03fe.png)

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

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/image719618c016ea84fe.png)

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

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/image9ef0f6ff859c0fb6.png)

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

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/imagef170882e9e995152.png)

    #include <graphics.h>
    #include <math.h>
    float t = 0.0;
    float x, y;
    void vebanhxe()
    {
    	int x1,  y1, x2, y2;
    	circle(int(x), int(y), 20);
    	x1= int(x - 20 * cos(t));
    	y1= int(y - 20 * sin(t));
    	x2= int(x + 20 * cos(t));
    	y2= int(y + 20 * sin(t));
    	line(x1, y1, x2, y2);
    }
    main()
    {
    	int gd = DETECT, gm ;
    	initgraph(&gd, &gm, "");
    	line(0, 321, getmaxx(), 321);
    	x = 100;
    	y = 300;
    	while (!kbhit())
    	{
    		setcolor(7);
    		vebanhxe();
    		delay(10);
    		setcolor(2);
    		vebanhxe();
    		t += 0.05;
    		x += 1 ;
    		if (x > getmaxx() + 20)
    			x = 0;
    	}
    	getch();
    	closegraph();
    }

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/Animation.gif)

    #include<graphics.h>
    #include<conio.h>
    using namespace std;
    main()
    {
    	initwindow(1000,1000);
    	setbkcolor(15);
    	int x=500,y=100;
    	char key;
    	setcolor(14);
    	setfillstyle(1,14);
    	while(1)
    	{
    		while(y<=400)
    		{
    			circle(x,y,100);
    			floodfill(x,y,14);
    			y+=5;
    			delay(50);
    			cleardevice();		
    		}
    		while(y>=200)
    		{	
    		circle(x,y,100);
    		floodfill(x,y,14);
    		y-=5;
    		delay(50);
    		cleardevice();
    		}
    		if(kbhit()){
                key = getch();
                if(key == 27)
    			{
                    break;
                }
    	 }
    	}
    	getch();
    }
    

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/imageb4a66013cc330b45.png)

    #include<winbgim.h>
    int main(int argc, char *argv[])
    {
    	initwindow(600,600);
    	setbkcolor(0);
    	cleardevice();
    	setcolor(15);
        
       
    	setfillstyle(1,4);
    	circle(300,300,100);
        floodfill(300,300,15);
        
    	while(!kbhit()) delay(1);
    	return 0;
    }

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/imagef6bf1172a7ce05e1.png)

    #include <winbgim.h> 
    #include <stdlib.h>
    #include <time.h> 
    #include <stdio.h>
    
    int main(int argc, char *argv[])
    {
    	initwindow(500, 500);			
    	setbkcolor(0);					
    	cleardevice();
    	int x = getmaxx()/2;
    	int y = getmaxy()/2;
    	int r = 0;
    	int i;
    	for(i=1;i<=300;i++)
    	{
    		//delay(10);
    		setcolor(i/10);
    		circle(x,y,i);
    	}
    		getch();	
    	
    	return 0;
    }
    	
![](https://i0.wp.com/s1.uphinh.org/2021/10/06/imagef24de60df54b00a5.png)

    #include <winbgim.h> 
    int main(int argc, char *argv[])
    {
    	
    	initwindow(800,800);			
    	setbkcolor(0);				
       	cleardevice();
    	setcolor(15);
    	setfillstyle(1,14);
    	circle(400,400,200);
    	floodfill(300,300,15);	
    	
    	/*int x,y;
    	for(x=0;x<=800;x=x+50)
    	{
    		line(0,x,800,x);
    		line(x,800,x,0);
    	
    	}*/
    	
    	setcolor(15);
    	ellipse(350,300,0,360,25,50);
    	ellipse(450,300,0,360,25,50);
    	setfillstyle(1,0);	
    	floodfill(350,300,15);
    	floodfill(450,300,15);
    	setcolor(4);
    	setlinestyle(1,1,7);
    	floodfill(450,300,15);	
    	ellipse(400,450,180,0,100,100);
    
    		
    	while(!kbhit()) delay(1);		
    	return 0;
    }

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/image0e8d7ce312f5aacc.png)

    #include <winbgim.h> 
    #include <stdlib.h>
    #include <time.h>
    
    int main(int argc, char *argv[])
    {
    	initwindow(800, 600);			
    	setbkcolor(0);					
    	cleardevice();
    	setcolor(15);
    	
    	int x, y;
    	x = y = 400;
    	int r = 70;
    	
    
    	setcolor(15);
    	int m = 30;
    	x = getmaxx();
    	y = getmaxy();
    	//ve truc
    	moveto(m,m);
    	linerel(0, y-2*m);
    	linerel(x-2*m, 0);
    //ve so 0
    //	outtextxy(m,y-2*m+m+5,"O");
    	//chu x va y
    //	outtextxy(x-2*m+m,y-2*m+m,"x");
    //	outtextxy(m+5,m,"y");
    	//ve mui ten
    	moveto(m,m);
    	linerel(-5,5);
    	moveto(m,m);
    	linerel(5,5);
    	moveto(x-2*m+m,y-2*m+m);
    	linerel(-5,-5);
    moveto(x-2*m+m,y-2*m+m);
    	linerel(-5,5);
    	//ve tru ngau nhien
    	srand(time(NULL));
    	int i = 0;
    	int x1, y1;
    	while(i++ < 10){
    		int a = rand()%(x-m)+2*m;
    		x1 = y1 = a;
    		if(a < y-m)
    			rectangle(x1, y1, x1+10, y-m);
    	}
    	
    	
    	
    	while(!kbhit()) delay(1);		
    	return 0;
    }


![](https://i0.wp.com/s1.uphinh.org/2021/10/06/imageabea5a91b6c8d45a.png)

    #include <winbgim.h> 
    typedef struct dinh
    {
    	int x,y;
    };
    dinh a,b,c,d;
    
    dinh tinhtien(dinh p,int tr_x,int tr_y)
    {
    	dinh tam;
    	tam.x=p.x+ tr_x;
    	tam.y=p.y+ tr_y;
    	return tam;
    	
    }
    
    int main(int argc, char *argv[])
    {
    	// now, you can run project
    	initwindow(700, 700);			// init window graphics
    	setbkcolor(0);					// set background
       	cleardevice();
    	setcolor(15);					// set text color
    	//
    	a.x=100;a.y=500;
    	settextstyle(0,0,2);
    	outtextxy(a.x-10,a.y+20,"A");
    	b.x=200;b.y=300;
    	outtextxy(b.x-10,b.y-20,"B");
    	
    	int tr_x=300, tr_y=-100;
    	d=tinhtien(a, tr_x, tr_y);
    	outtextxy(d.x-10,d.y+20,"D");
    	c=tinhtien(b,tr_x, tr_y);
    	outtextxy(c.x-10,c.y-20,"C");
    	//
    	moveto(a.x,a.y);
    	lineto(b.x,b.y);
    	lineto(c.x,c.y);
    	lineto(d.x,d.y);
    	lineto(a.x,a.y);
    	
    	
    	while(!kbhit()) delay(1);		// pause screen	
    	return 0;
    }
    

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
    

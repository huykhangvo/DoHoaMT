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
    

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/imageef92f868a5b2b1a3.png)

    #include <winbgim.h> 
    
    int main(int argc, char *argv[])
    {
    	// now, you can run project
    	initwindow(300, 300);			// init window graphics
    	setbkcolor(0);					// set background
       	cleardevice();
    	setcolor(15);					// set text color
    	
    	int maxx = getmaxx();
    	int maxy = getmaxy();
    //ve ban co
    	for(int x = 0; x <= 800; x+=100){
    		line(x, 0, x, 800);
    		line(0, x, 800, x);
    	}
    //to ban co
    	setfillstyle(1, 15);
    	int stt = 1;
    	for(int x = 50; x <= 800; x+=100){
    		if(stt++%2 != 0)
    			for(int y = 50; y <= 800; y+=200)
    				floodfill(x, y, 15);
    		else
    			for(int y = 150; y <= 800; y+=200)
    				floodfill(x, y, 15);
    	}
    	
    	while(!kbhit()) delay(1);		// pause screen	
    	return 0;
    }

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/3.gif)

    #include <graphics.h>
    #include <math.h>
    float t = 0.0;
    float x, y;
    void vebanhxe(){
    int x1, y1, x2, y2;
    circle(int(x), int(y), 50);
    x1 = int(x - 50 * cos(t));
    y1 = int(y - 50 * sin(t));
    x2 = int(x + 50 * cos(t));
    y2 = int(y + 50 * sin(t));
    line(x1, y1, x2, y2);
    }
    main(){
    int gd = DETECT, gm;
    initgraph(&gd, &gm, "");
    
    x = 100;
    y = 300;
    while( !kbhit()){
    setcolor(4);
    vebanhxe();
    delay(1);
    setcolor(0);//mau nen
    vebanhxe();
    t += 0.05;
    x += 1;
    if (x > getmaxx() + 50)
    x = 0;
    }
    getch();
    closegraph();
    }

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/4.gif)

    #include <graphics.h>
    #include <conio.h>
    #include <math.h>
    #define RADS 0.017453293
    #define CIRCLE 200
    #define M_PI 3.14159265358979323846
    #include <time.h>
    #include <iostream> 
    #include <windows.h>
    
    using namespace std;
    double xc, yc;
    int gio, phut, giay;
    struct time {
        int tm_sec;         /* bi?u di?n giây, t? 0 t?i 59  */
        int tm_min;         /* bi?u di?n phút, t? 0 t?i 59  */
        int tm_hour;        /* bi?u di?n gi?, t? 0 t?i 23   */
        int tm_mday;        /* bi?u di?n ngày c?a tháng, t? 1 t?i 31  */
        int tm_mon;         /* bi?u di?n tháng, t? 0 t?i 11      */
        int tm_year;        /* bi?u di?n nam, b?t d?u t? 1900    */
        int tm_wday;        /* ngày trong tu?n, t? 0 t?i 6       */
        int tm_yday;        /* ngày trong nam, t? 0 t?i 365      */
        int tm_isdst;       /* bi?u di?n Daylight Saving Time    */
     };
    void ve_kim_gio(int color)
    {
      double angle;
    
      setcolor(color);
      angle = ((double)360 * gio / 12 + (double)phut / 2 - 90.0) * RADS;
      moveto(xc - 20.0 * cos(angle), yc - 20.0 * sin(angle));
      lineto(xc - 10.0 * cos(angle + M_PI / 2), yc - 10.0 * sin(angle + M_PI/2));
      lineto(xc + 110.0 * cos(angle), yc + 110.0 * sin(angle));
      lineto(xc + 10.0 * cos(angle + M_PI / 2), yc + 10.0 * sin(angle + M_PI/2));
      lineto(xc - 20.0 * cos(angle), yc - 20.0 * sin(angle));
    }
    
    void ve_kim_phut(int color)
    {
      double angle;
    
      setcolor(color);
      angle = ((double)360 * phut / 60 + (double)giay / 10 - 90.0) * RADS;
      moveto(xc - 30.0 * cos(angle), yc - 30.0 * sin(angle));
      lineto(xc - 8.0 * cos(angle + M_PI / 2), yc - 8.0 * sin(angle + M_PI/2));
      lineto(xc + 140.0 * cos(angle), yc + 140.0 * sin(angle));
      lineto(xc + 8.0 * cos(angle + M_PI / 2), yc + 8.0 * sin(angle + M_PI/2));
      lineto(xc - 30.0 * cos(angle), yc - 30.0 * sin(angle));
    }
    
    void ve_kim_giay(int color)
    {
      double angle;
    
      setcolor(color);
      angle = (/*(double)*/360 * (giay - 3) / 60) * RADS;
    //  moveto(xc - 40.0 * cos(angle), yc - 40.0 * sin(angle));
    //  lineto(xc + 150.0 * cos(angle), yc + 150.0 * sin(angle));
    	line(xc -40 * cos(angle),yc - 40 *sin(angle),xc + 150 *cos(angle),yc + 150*sin(angle));
      setfillstyle(SOLID_FILL, color);
      fillellipse(xc, yc, 3, 3);
    }
    void ve_mat_dong_ho()
    {
      int i, j;
    
      setcolor(YELLOW);
      circle(xc, yc, CIRCLE);
      setlinestyle(SOLID_LINE, 0, 3);
      for (i=0; i<12; i++)
        if (i%3 == 0)
        {
          line(xc + (CIRCLE - 2) * sin(RADS * (30 * i - 1)), yc + (CIRCLE - 2) * cos(RADS * (30 * i - 1)),
               xc + (CIRCLE - 24) * sin(RADS * (30 * i - 1)), yc + (CIRCLE - 24) * cos(RADS * (30 * i - 1)));
          line(xc + (CIRCLE - 2) * sin(RADS * (30 * i + 1)), yc + (CIRCLE - 2) * cos(RADS * (30 * i + 1)),
               xc + (CIRCLE - 24) * sin(RADS * (30 * i + 1)), yc + (CIRCLE - 24) * cos(RADS * (30 * i + 1)));
        }
        else
          line(xc + (CIRCLE - 2) * sin(RADS * (30 * i)), yc + (CIRCLE - 2) * cos(RADS * (30 * i)),
               xc + (CIRCLE - 24) * sin(RADS * (30 * i)), yc + (CIRCLE - 24) * cos(RADS * (30 * i)));
    }
    void run(){
    	struct time timep;
    	ve_mat_dong_ho();	  
    	  gio = timep.tm_hour;
    	  phut = timep.tm_min;
    	  giay = timep.tm_sec;
    	  setlinestyle(SOLID_LINE, 0, 0);
      do {
        ve_kim_gio(YELLOW);
        ve_kim_phut(GREEN);
        ve_kim_giay(RED);
        delay(0);
        //sound(1000);
        delay(0);
        //nosound();
        ve_kim_giay(BLACK);
        ve_kim_phut(BLACK);
        ve_kim_gio(BLACK);
        giay++;
        if (giay >= 60)
        {
          giay %= 60;
          phut++;
          if (phut >= 60)
          {
            phut %= 60;
            gio++;
            if (gio >= 12)
              gio %= 12;
          }
        }
      } while (!kbhit());
    }
    main(){
    	initwindow(700,700);
    	int x,y,r;
    	xc = getmaxx() / 2;
      	yc = getmaxy() / 2;
    	
    	 run();
    	
    	
    	getch();
    } 

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/5.gif)

    	
     #include<winbgim.h>
    	int main(){
    	initwindow(700,700);
    	cleardevice();
    	setbkcolor(0);
    	setcolor(14);
    	setfillstyle(1,14);
    
    	int x=0;
    	int y=0;
    	while(!kbhit()){
    	while(y<=getmaxy()-100 && !kbhit()){
    	cleardevice();
    	rectangle(x,y,x+100,y+100);
    	floodfill(x+10,y+10,14);
    	y+=10;
    	delay(20);
    	}
    	while(x<=getmaxx()-100 && !kbhit()){
    	cleardevice();
    	rectangle(x,y,x+100,y+100);
    	floodfill(x+10,y+10,14);
    	x+=10;
    	delay(20);
    	}
    	while(y>=0 && !kbhit()){
    	cleardevice();
    	rectangle(x,y,x+100,y+100);
    	floodfill(x+10,y+10,14);
    	y-=10;
    	delay(20);
    	}
    	while(x>=0 && !kbhit()){
    	cleardevice();
    	rectangle(x,y,x+100,y+100);
    	floodfill(x+10,y+10,14);
    	x-=10;
    	delay(20);
    	}
    	}
    	
    	while(kbhit()) delay(1);
    	return(0);
    } 
    

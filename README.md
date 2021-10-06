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

![](https://i0.wp.com/s1.uphinh.org/2021/10/06/image55f99047c8238c06.png)

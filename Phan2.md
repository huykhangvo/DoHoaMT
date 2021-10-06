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

![]()

			# IO_API
			Version: 0.0.1

Ever wanted to build an application that was not only easily portible,
but wasn't excessivly bulky with tons of functionality you don't want?
One that can actually port to any platform you could imagion.  Well
IO_API aims to satisify those needs by abstracting IO in a way that
helps you build your application in isolation, then port by fleshing
out the API's function prototypes.  Or use any IO_API_ implimentation
built by another.  It's designed to be minimal and only concern itself
with platform specific functionality so that you can easily layer other
libraries ontop which don't require IO specific tasks directly.

::Instilation::
Copy IO_API.h and IO_API.c into your project and either make or use a
file that impliments the IO_API.h's function prototypes.  See IO_API.h
for details.

EXAMPLE:
```c
//In pure main.c

#include "IO_API/IO_API.h"
#include <time.h>
#include <stdio.h>



struct Texture texture;
clock_t c;

void start() {
	cWidth = 1024;
	cHeight = 768;
	
	getTexture("test.png", &texture);

	c = clock();
}

void end() {
	free(texture.data);
}

void appLoop() {
	static int x = 0;

	drawTexture(&texture, 64, 64);

	double duration = (clock() - c) / (double)CLOCKS_PER_SEC;

	char str[100] = { 0 };
	int ms = duration * CLOCKS_PER_SEC;
	_itoa(ms, str, 10);
	printf("ms of time till last frame ");  //May be inaccurate not sure yet.
	printf(str);
	printf("\r\n");

	c = clock();
}
```

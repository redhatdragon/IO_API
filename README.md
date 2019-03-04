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
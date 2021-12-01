# cmake-packaging-example
took me a long time to figure it out, anyway here it is

THE FILES:
mylib:

  in: these are the files that are used as templates to generate config.cmake and .pc files
  
  mylib.cpp: the source code for the library
  
  mylib.h: the public header
  
  CMakeLists.txt: makes the library and adds an install command
  
main:

  main.cpp: the main source code that needs a function from mylib
  
  CMakeLists.txt: finds the mylib package and links it with the maine executable
  

TO RUN:

1. go to mylib, make a build directory, then run "cmake .." from inside of it
2. run "make install" This puts mylib into your default program installation directory (C:\Program Files (x86) for windows)
3. The previous command also prints out ADD THIS TO YOUR PATH: some/path. Copy that path, it will be needed later.
4. go to main, make a build directory, then run "cmake .." and "make" inside of it. 
5. Now, if you run "./main", it might work. But, there is a large chance it doesn't because your environment variables arent set to check inside mylib. Therefore, you must append that path you copied earlier into your PATH environment variable. On Windows, either use the GUI to permenantly add it, or run inside CMD "set PATH=%PATH%;path/you/copied/earlier" to add it only for that CMD terminal while it is open. Now, if you run main.exe or ./main, it should work and print "hello world" followed by "7".

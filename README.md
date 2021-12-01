# cmake-packaging-example
took me a long time to figure it out, anyway here it is

TO RUN:

1. go to mylib, make a build directory, then run "cmake .." from inside of it
2. run "make install" This puts mylib into your default program installation directory (C:\Program Files (x86) for windows)
3. The previous command also prints out ADD THIS TO YOUR PATH: some/path. Copy that path, it will be needed later.
4. go to main, make a build directory, then run "cmake .." and "make" inside of it. 
5. Now, if you run "./main", it might work. But, there is a large chance it doesn't because your environment variables arent set to check inside mylib. Therefore, you must append that path you copied earlier into your PATH environment variable. On Windows, either use the GUI to permenantly add it, or run inside CMD "set PATH=%PATH%;path/you/copied/earlier". Now, if you run main.exe or ./main, it should work and print "hello world" followed by "7".

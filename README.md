# Delve Framework Build Example

This repository shows how to include and use the Delve Framework in another Zig project using Zig's package manager.

Currently targets Zig 0.12.0

## Build and run
To build and run natively:
```
zig build run
```
## Building for web
To build for web, use the -Dtarget=wasm32-emscripten build argument:
```
zig build run -Dtarget=wasm32-emscripten
```

This will 
- build the web application
- launch a local web server (using emrun.py)
- Open it using your default browser. 

Documentation for emrun.py: https://emscripten.org/docs/compiling/Running-html-files-with-emrun.html

### Run web application without python

The built application has no dependencies, and can be served through any http server. This includes bare-metal hosts with no operating-system: useful for creating web-config pages for embedded systems.

e.g. using one of the http-oneliners: https://gist.github.com/willurd/5720255
```
busybox httpd -f zig-out/web/ -p 8000
```
And then open it in your browser: http://localhost:8000/delve-framework-example.html

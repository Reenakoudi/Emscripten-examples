# Emscripten

The core Emscripten SDK (emsdk) driver is a Python script. You can get it for the first time with

# Get the emsdk repo
git clone https://github.com/juj/emsdk.git

# Enter that directory
cd emsdk

Run the following emsdk commands to get the latest tools from GitHub and set them as active:

# Fetch the latest registry of available tools.
./emsdk update

# Download and install the latest SDK tools.
./emsdk install latest

# Make the "latest" SDK "active" for the current user. (writes ~/.emscripten file)
./emsdk activate latest

# Activate PATH and other environment variables in the current terminal
source ./emsdk_env.sh

NOTE: On Windows, run emsdk instead of ./emsdk, and emsdk_env.bat instead of source ./emsdk_env.sh

If you change the location of the SDK (e.g. take it to another computer on an USB), re-run the ./emsdk activate latest and source ./emsdk_env.sh commands.

Navigate with the command prompt to the SDK root directory for your target SDK.
for example <emsdk root directory>/emscripten/1.20.0/.
  
 emsdk/emscripten/1.38.9
 
 # Verifying Emscripten
 $ ./emcc -v
 
 # Running Emscripten  
 You can now compile your first C/C++ file to JavaScript.
 Specify the C/C++ file after emcc 
 
 $ ./emcc tests/hello_world.c
 
 You should see two files generated by that command: a.out.js and a.out.wasm.
 
 a.out.wasm -> WebAssembly file containing the compiled code
 a.out.js   -> JavaScript file containing the runtime support to load and execute it
 
 You can run them using node.js:
 $ node a.out.js
 
 This prints “hello, world!” to the console, as expected.







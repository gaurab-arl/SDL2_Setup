🔹 Step 0: Download SDL2 for MinGW
1️⃣ Go to: https://github.com/libsdl-org/SDL/releases/

2️⃣ Find and Download:
Download SDL2-devel-2.x.x-mingw.zip (not the .tar.gz version)

🔹 Step 1: Extract and Organize Files

1️⃣ Extract the ZIP file
Right-click the downloaded file → Select Extract All…
Choose Desktop as the destination (or decument for easy asscess)

2️⃣ Inside x86_64-w64-mingw32, you'll see three main folders:

bin
include
lib


Copy files in this order:
🔹 Step 2: First, from the bin folder:

Copy SDL2.dll
Create a new folder in your Documents called "MyGames" (or any name you prefer)
Paste SDL2.dll there (this is where you'll create your game projects)


🔹 Step 3: From the include folder:

Go into the SDL2 folder inside it
Copy ALL header files (.h files)
Navigate to C:\Program Files (x86)\Dev-Cpp\MinGW64\include
Create a new folder named SDL2 here
Paste all the header files into this new SDL2 folder

🔹 Step 4: From the lib folder:

Copy all .a files
Navigate to C:\Program Files (x86)\Dev-Cpp\MinGW64\lib
Paste all the .a files here

4️⃣ Click OK and exit.

🔹 Step 7: you need to link the SDL2 library: add linker

Before compiling, we need to link SDL2:

1️⃣ Go to Tools → Compiler Options
In the "Linker" box, add: -lmingw32 -lSDL2main -lSDL2

🔹 Step 6: Create and Run a Test Program

1️⃣ Create a New Source File

Open Dev-C++
Go to File → Project → Name it 
Save it inside your game project folder ( i.e "MyGame" )

2️⃣ We need to add the linker to project for use in project

Project → Project Options → Parameters
In "Linker" add: -lmingw32 -lSDL2main -lSDL2

2️⃣ Paste this test code:
#include <SDL2/SDL.h>
#include <stdio.h>

int main(int argc, char* argv[]) {
    if (SDL_Init(SDL_INIT_VIDEO) != 0) {
        printf("SDL_Init Error: %s\n", SDL_GetError());
        return 1;
    }

    SDL_Quit();
    return 0;
}

3️⃣ Save the file (test.c)
4️⃣ Compile and Run! (F9 to build)

🔹 Troubleshooting Common Errors
❌ "SDL2.h not found" → Check if headers are copied to the correct folder
❌ "Undefined reference to SDL" → Ensure you added the linker flags
❌ "Program crashes on launch" → Make sure SDL2.dll is in the project folder
❌ "Using C++ can show error" → Use C language 

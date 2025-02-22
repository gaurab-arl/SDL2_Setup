SDL2 Setup Guide for Dev-C++
Step 0: Download SDL2

Visit SDL2 Releases
Download SDL2-devel-2.x.x-mingw.zip (not the .tar.gz version)

Step 1: Extract Files

Right-click downloaded file → Extract All
Choose Desktop or Documents for easy access
Locate x86_64-w64-mingw32 folder with these subdirectories:

bin
include
lib



Step 2: Copy SDL2.dll

From bin folder:

Copy SDL2.dll


Create folder in Documents called "MyGames"
Paste SDL2.dll there

Step 3: Copy Header Files

From include/SDL2 folder:

Copy ALL .h files


Navigate to C:\Program Files (x86)\Dev-Cpp\MinGW64\include
Create new folder named SDL2
Paste all header files there

Step 4: Copy Library Files

From lib folder:

Copy all .a files


Navigate to C:\Program Files (x86)\Dev-Cpp\MinGW64\lib
Paste all .a files

Step 5: Link SDL2 Library

Go to Tools → Compiler Options
In "Linker" box, add:

Copy-lmingw32 -lSDL2main -lSDL2
Step 6: Create Test Program

Create New Project:

File → Project
Choose Console Application
Name your project
Save in your "MyGames" folder


Add Linker to Project:

Project → Project Options → Parameters
In "Linker" tab, add:



Copy-lmingw32 -lSDL2main -lSDL2

Test Code:

cCopy#include <SDL2/SDL.h>
#include <stdio.h>

int main(int argc, char* argv[]) {
    if (SDL_Init(SDL_INIT_VIDEO) != 0) {
        printf("SDL_Init Error: %s\n", SDL_GetError());
        return 1;
    }
    SDL_Quit();
    return 0;
}

Save as test.c and compile (F9)

Troubleshooting

SDL2.h not found: Check header files in include folder
Undefined reference to SDL: Verify linker flags
Program crashes: Check SDL2.dll location
C++ errors: Use C language instead

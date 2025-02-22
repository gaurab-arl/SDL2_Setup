### SDL2 Setup Guide for Dev-C++

#### Step 0: Download SDL2
1. Visit [SDL2 Releases](https://github.com/libsdl-org/SDL/releases/)
2. Download **SDL2-devel-2.x.x-mingw.zip** (not the .tar.gz version)

#### Step 1: Extract Files
1. Right-click the downloaded file → **Extract All**
2. Choose **Desktop** or **Documents** for easy access
3. Locate **x86_64-w64-mingw32** folder with these subdirectories:
   - **bin**
   - **include**
   - **lib**

#### Step 2: Copy SDL2.dll
1. From **bin** folder:
   - Copy **SDL2.dll**
2. Create a folder in **Documents** called **"MyGames"**
3. Paste **SDL2.dll** there

#### Step 3: Copy Header Files
1. From **include/SDL2** folder:
   - Copy **ALL** `.h` files
2. Navigate to `C:\Program Files (x86)\Dev-Cpp\MinGW64\include`
3. Create a new folder named **SDL2**
4. Paste all header files there

#### Step 4: Copy Library Files
1. From **lib** folder:
   - Copy **all** `.a` files
2. Navigate to `C:\Program Files (x86)\Dev-Cpp\MinGW64\lib`
3. Paste all `.a` files

#### Step 5: Link SDL2 Library
1. Go to **Tools → Compiler Options**
2. In the **"Linker"** box, add:
   ```
   -lmingw32 -lSDL2main -lSDL2
   ```

#### Step 6: Create Test Program
1. **Create New Project:**
   - **File → Project**
   - Choose **Console Application**
   - Name your project
   - Save in your **"MyGames"** folder

2. **Add Linker to Project:**
   - **Project → Project Options → Parameters**
   - In **"Linker"** tab, add:
     ```
     -lmingw32 -lSDL2main -lSDL2
     ```

3. **Test Code:**
   ```c
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
   ```
4. Save as **test.c** and **compile (F9)**

### Troubleshooting
- **SDL2.h not found**: Check header files in the `include` folder
- **Undefined reference to SDL**: Verify linker flags
- **Program crashes**: Check **SDL2.dll** location
- **C++ errors**: Use **C language** instead


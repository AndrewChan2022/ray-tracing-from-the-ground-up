# build for windows mingw

changes:

    1. Window/Window.hpp add define before include
        #define SDL_MAIN_HANDLED
        #include <SDL2/SDL.h>
    2. Window/Window-THREAD.cpp add include
        #include <cstdio>
    3. download SDL mingw version to external/SDL2
        https://www.matsson.com/prog/sdl2-mingw-w64-tutorial.php
        download SDL2-devel-2.30.3-mingw.zip
        copy x86_64-w64-mingw32 to external/SDL2
    4. make file
        LINKS = -lSDL2 -lpthread -pthread -std=c++11
        =>
        LINKS = -lSDL2 -lpthread -pthread -std=c++11 -lmingw32 -lSDL2main
        LIBPATH = -L"external/SDL2/lib"
        INCLUDES = -I"external/SDL2/include"


        $(CC) $^ $(FLAGS) $(LINKS) -o $@
        =>
        $(CC) $^ $(LIBPATH) $(INCLUDES) $(FLAGS) $(LINKS) -o $@

build:

    1. mingw terminal: gitbash or other mingw terminal
    2. make -j12
    3. cd build
    4. ./RTX.out
    5. change World.cpp include file to change different scene  #include "../build/XXX.hpp"
    

-----------------------------

# Ray-Tracing-from-the-Ground-Up
software from the book Ray Tracing from the Ground Up by Kevin Suffern

currently in chapter 25.

Mirror Reflection

![alt_text](https://github.com/hadryans/Ray-Tracing-from-the-Ground-Up/blob/master/build/images/Mirror%20Reflection.png)

Area Lights

![alt_text](https://github.com/hadryans/Ray-Tracing-from-the-Ground-Up/blob/master/build/images/Area%20Lights.png)

Ambient Occlusion (Regular Sampler: 1x, 4x, 16x, 256x)

![alt_text](https://github.com/hadryans/Ray-Tracing-from-the-Ground-Up/blob/master/build/images/Ambient%20Occlusion.png)

Shadow

![alt_text](https://github.com/hadryans/Ray-Tracing-from-the-Ground-Up/blob/master/build/images/Shadows.png)


Glossy Material

![alt_text](https://github.com/hadryans/Ray-Tracing-from-the-Ground-Up/blob/master/build/images/Specular%20Highlight.png)


Grid

![alt text](https://github.com/hadryans/Ray-Tracing-from-the-Ground-Up/blob/master/build/images/1000%20spheres%20grid.png)

 1 - Design and Programming  : complete
 
 2 - Essential Mathematics   : complete
 
 3 - Bare-Bones Ray Tracing  : complete
 
 4 - Antialiasing            : complete
 
 5 - Sampling Techniques     : complete
 
 6 - Disk Samples            : complete
 
 7 - Hemisphere Samples      : complete
 
 8 - Perpective Viewing      : complete
 
 9 - Viewing System          : complete

10 - Depth of Field          : complete

11 - Nonlinear Projection    : --------

12 - Stereoscopy             : --------

13 - Theretical Fundations   : complete

14 - Lights and Materials    : complete

15 - Specular Reflection     : complete

16 - Shadows                 : complete

17 - Ambient Occlusion       : complete

18 - Area Lights             : 70%

19 - Ray-Object Intersections: 70%

20 - Affine Transformations  : --------

21 - Transforming Objects    : --------

22 - Regular Grids           : complete

23 - Triangle Meshes         : DISCONTINUED

24 - Mirror Reflection       : complete

25 - Glossy Reflection       : --------

26 - Global Illumination     : --------

27 - Simple Transparency     : --------

28 - Realistc Transparency   : --------

29 - Texture Mapping         : --------

30 - Procedural Textures     : --------

31 - Noise-Based Textures    : --------

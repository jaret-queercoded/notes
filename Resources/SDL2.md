---
title: SDL2
date: 2022-01-11
---

# SDL2
  
Simple DirectMedia Layer 2.0 ([[SDL2]]) is a cross-platform development library designed to provide low level access to audio, keyboard, mouse, joystick, and graphics hardware via [[OpenGL]] and Direct3D.

## Tips
I have written some helper functions that I find useful for using [[SDL2]] in [[C]]

This function can be used to check return code of a SDL functions and give you the error and exit if something broke

```c
void check_sdl_code(int code) {  
 if(code < 0) {  
 fprintf(stderr, "SDL encountered an error: %s", SDL_GetError());  
        exit(EXIT_FAILURE);  
    }  
}
```

This function checks any pointer that SDL gives you and if it is bad exit and if it is good gives it back to you

```c
void* check_sdl_ptr(void *ptr) {  
 if(ptr == NULL) {  
 fprintf(stderr, "SDL gave you a null ptr: %s", SDL_GetError());  
        exit(EXIT_FAILURE);  
    }  
 return ptr;  
}
```
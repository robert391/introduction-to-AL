1. For this project, I looked at the lecture about the introduction to assembly language.
2. Some challenges were using the nano text editor because it was different from using the regular text editor.
3. assembly code:
   section  .text
   global _start    ;must be declared for using gcc

_start:             ;tell linker entry point
   mov eax, SYS_WRITE
   mov ebx, STDOUT
   mov ecx, msg1
   mov edx, len1
   int 0x80

   mov eax, SYS_WRITE
   mov ebx, STDOUT
   mov ecx, msg2
   mov edx, len2
   int 0x80

   mov eax, SYS_WRITE
   mov ebx, STDOUT
   mov ecx, msg3
   mov edx, len3
   int 0x80

   mov eax,SYS_EXIT    ;system call number (sys_exit)
   int 0x80            ;call kernel

section  .data
msg1 db 'I came,',0xA,0xD
len1 equ $ - msg1

msg2 db 'I saw,', 0xA,0xD
len2 equ $ - msg2

msg3 db 'I conquered.'
len3 equ $- msg3

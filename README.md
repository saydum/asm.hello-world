```asm
SECTION .data
msg     db "Hello World!",0xa
len     equ $ - msg
SECTION .text
global _start
_start:
        mov eax, 4
        mov ebx, 1
        mov ecx, msg
        mov edx, len
        int 0x80
        mov eax, 1
        mov ebx, 0
        int 0x80
```

```bash
sudo apt install nasm

nasm -f elf app.asm

ld -m elf_i386 app.o -o run

./run
Hello World!
```

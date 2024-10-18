# Estudo de comandos NASM

<p align="center">
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSSKcN91zGCwjNYxg_W3Ar0zp-TOxJ4ni-eoQ&s" width=200 heigth=200 >
</p>

## Primeiros comandos

* Programa hello world

```Assembly
global_start

    section .text
    _start:
        mov rax,1          ;prepara o sistema para fazer a escrta de um texto
        mov rdi, 1         ;prepara a saida do texto na tela
        mov rsi,mensagem   ;imprimir a mensagem na tela
        mov rdx,13         ;quantidade de caracteres
        syscall            ;chama o sistema para preparar a saida
        mov rax, 60        ;chamada para a saida do sistema
        xor rdi,rdi        ;execultar a saida do sistema
        syscall            ;invocar o sistema operacional para fechar

        section .data
        mensagem:db 'hello,world',10    ;O valor 10 representa quebra de linha

```
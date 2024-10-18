# Estudo de comandos NASM

<p align="center">
<img src="https://play-lh.googleusercontent.com/UWg9QLQCg6iwyD9njae1csEUBZR34llgIYR2crZI1dvcdNDFq2HX65WmEfnGh8Qcv34=w240-h480" width=100 height=100>
</p>

## primeiros comandos

* Programa Hello world

```Assembly
global _start

    section .text
    _start:     
        mov rax,1               ;Prepara o sistema para fazer uma escrita de um texo
        mov rdi,1               ;Preparar a saida do texto na tela
        mov rsi,mensagem        ;exibir a mensagem na tela
        mov rdx,13              ;Quantidade de caracteres que vai utilizar
        syscall                 ;Chama o sistema para preparar a saida
        mov rax,60              ;chamada para a saida do sistema
        xor rdi,rdi             ;executar a saida do sistema
        syscall                 ;invocar o sistema operacional para fechar

    section .data
    mensagem: db 'Hello, word!' ,10      ;O valor 10 representa a quebra de linha

```
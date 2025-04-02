# Linux

## Comandos Úteis

### Recortar vídeos
``` bash
ffmpeg -ss 00:01:00 -to 00:02:00 -i input.mp4 -c copy output.mp4

# Formato da hora -> hh:mm:ss
# -ss             -> Horário do início
# -to             -> Horário do fim (considerando o inicio real do arquivo)
# -c              -> Copy - Recorte via copia de stream (muito rápido)
```

### Converter image .webp em .png

``` bash
ffmpeg -i input_file.webp output_file.png
```

### Achar arquivos grandes

``` bash
du -h 2>/dev/null | egrep -v "\./.+/" | sort -h | tail -n 10
```

### Achar e apagar diretórios pelo nome

``` shell
#!/bin/bash

# Define o diretorio base para iniciar a busca
BASE_DIR="."

# Encontra e remove todos os diretorios com o nome "venv"
find "$BASE_DIR" -type d -name "venv" -exec rm -rf {} +

echo "Todos os diretorios 'venv' foram removidos"
```

### Achar e apagar arquivos pelo nome

``` shell
#!/bin/bash

# Define o diretorio base para iniciar a busca
BASE_DIR="."

# Encontra e remove todos os diretorios com o nome "venv"
find "$BASE_DIR" -type f -name ".DS_Store" -exec rm -rf {} +

echo "Todos os arquivos '.DS_Store' foram removidos"
```

### Acertar Tmux p/ carregar ~/.bashrc

Editar o arquivo `~/.tmux.conf`

``` bash
set -g default-terminal "xterm-256color"
set-option -g default-command bash
```

---

## Preparação de Ambiente

### 6 Apps Linux que nunca deixei de usar by Diolinux

<https://www.youtube.com/watch?v=19YqeX4PBS0>

1. darktable
1. Authy
1. Bitwarden
1. flameshot
1. WinFF
1. Blanket (white noise)
1. Davinci Resolve (editor de video) <- profissional



**Verificar:**

<https://www.youtube.com/watch?v=nY4G5f8uJW0>

* Apostrophe (markdown)
* NewsFlash (feed rss)
* GnomePhotos
* Newton Mail
* Streamio (gestor de mídia)
* Sweet Home 3D (opensource)
* Akira UI Design (criar interface)
* Alacritty (terminal acelerado por GPU)
* BricsCad (nao é free)
* Fondo (wall papers)
* Lightworks (editor de video - nao e free, tem versao gratis)


### Inport Nerd Fonts

<https://www.nerdfonts.com/font-downloads>

``` bash
sudo mkdir -p /usr/share/truetype/myfonts; \
cd /usr/share/truetype/myfonts && \
sudo curl -O https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/RobotoMono/Regular/complete/Roboto%20Mono%20Nerd%20Font%20Complete.ttf && \
sudo curl -O https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/UbuntuMono/Regular/complete/Ubuntu%20Mono%20Nerd%20Font%20Complete.ttf && \
sudo curl -O https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/VictorMono/Light/complete/Victor%20Mono%20Light%20Nerd%20Font%20Complete.ttf && \
sudo curl -O https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/VictorMono/Regular/complete/Victor%20Mono%20Regular%20Nerd%20Font%20Complete.ttf && \
sudo fc-cache -f -v

# cd /path/to/local-fonts/
# sudo cp *.ttf /usr/share/fonts/truetype/ && sudo fc-cache -f -v
# sudo -k
```

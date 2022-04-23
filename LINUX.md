# Linux

## 6 Apps Linux que nunca deixei de usar by Diolinux

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
* 


## rich

Fabulous command line toolbox for fancy output.
<https://github.com/Textualize/rich-cli>

``` bash
pip install rich-cli

rich README.md -m --pager
```

## ritchie-cli
``` bash
rit create formula
rit build formula
rit build formula --watch
rit publish repo
rit set credential
rit list credential
```
**Main files:**
* `config.json` <== Input Values
* `src/main.*`  <== Value Extractor
* `src/pkg/formula.*` <== Run

## Inport Nerd Fonts

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

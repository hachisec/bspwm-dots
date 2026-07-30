#!/bin/sh

# Inicia o gerenciador de atalhos em segundo plano
sxhkd &

# --------------------------------------------------------
# MONITORES E WORKSPACES
# --------------------------------------------------------
# Define 5 áreas de trabalho numéricas
bspc monitor -d 1 2 3 4 5

# --------------------------------------------------------
# APARÊNCIA (Gaps e Bordas)
# --------------------------------------------------------
bspc config border_width         2
bspc config window_gap          12
bspc config split_ratio          0.50
bspc config borderless_monocle   true
bspc config gapless_monocle      true

# Cores das bordas (Estilo Nord)
bspc config normal_border_color  "#4c566a"
bspc config active_border_color  "#81a1c1"
bspc config focused_border_color "#5e81ac"
bspc config presel_feedback_color "#bf616a"

# --------------------------------------------------------
# REGRAS DE JANELAS (Window Rules)
# --------------------------------------------------------
# Força programas específicos a abrirem flutuando
bspc rule -a Gimp state=floating follow=on
bspc rule -a mpv state=floating
bspc rule -a "VirtualBox Manager" state=floating

# --------------------------------------------------------
# AUTOSTART (Aplicativos que iniciam com o sistema)
# --------------------------------------------------------
# Remova o "#" da frente das linhas abaixo quando instalar esses programas:
# feh --bg-fill ~/Imagens/wallpaper.jpg &  # Papel de parede
# picom -b &                               # Transparência e sombras
# polybar main &                           # Barra de status superior

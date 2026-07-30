# --------------------------------------------------------
# APLICATIVOS
# --------------------------------------------------------
# Abrir o terminal (Alacritty)
super + Return
	alacritty

# Abrir um menu de aplicativos (requer 'dmenu' ou 'rofi' instalado)
super + space
	dmenu_run

# --------------------------------------------------------
# CONTROLE DE JANELAS
# --------------------------------------------------------
# Fechar a janela atual
super + w
	bspc node -c

# Forçar o encerramento da janela atual
super + shift + w
	bspc node -k

# Alternar entre layout lado-a-lado (tiled) e flutuante (floating)
super + s
	bspc node -t {tiled,floating}

# Alternar para tela cheia (fullscreen)
super + f
	bspc node -t \~fullscreen

# --------------------------------------------------------
# NAVEGAÇÃO
# --------------------------------------------------------
# Mudar o foco entre as janelas usando as setas do teclado
super + {Left,Down,Up,Right}
	bspc node -f {west,south,north,east}

# Mover a janela atual usando as setas do teclado
super + shift + {Left,Down,Up,Right}
	bspc node -m {west,south,north,east}

# Alternar entre as áreas de trabalho (Workspaces de 1 a 5)
super + {1-5}
	bspc desktop -f '^{1-5}'

# Mover a janela atual para outra área de trabalho
super + shift + {1-5}
	bspc node -d '^{1-5}'

# --------------------------------------------------------
# SISTEMA
# --------------------------------------------------------
# Recarregar as configurações do bspwm e sxhkd sem sair do sistema
super + Escape
	pkill -USR1 -x sxhkd; bspc wm -r

# Sair do BSPWM (Voltar para a tela de login/terminal)
super + alt + Escape
	bspc quit

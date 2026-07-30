cat << 'EOF' > ~/.config/polybar/config.ini
[colors]
background = #2e3440
background-alt = #3b4252
foreground = #eceff4
primary = #88c0d0
secondary = #81a1c1
alert = #bf616a
disabled = #4c566a

[bar/main]
width = 100%
height = 24pt
radius = 0

background = ${colors.background}
foreground = ${colors.foreground}

line-size = 2pt

border-size = 4pt
border-color = #00000000

padding-left = 1
padding-right = 1

module-margin = 1

separator = |
separator-foreground = ${colors.disabled}

font-0 = monospace;2

modules-left = bspwm xwindow
modules-right = cpu memory wlan eth date

cursor-click = pointer
cursor-scroll = ns-resize

enable-ipc = true

[module/bspwm]
type = internal/bspwm

label-active = %name%
label-active-background = ${colors.background-alt}
label-active-underline= ${colors.primary}
label-active-padding = 1

label-occupied = %name%
label-occupied-padding = 1

label-urgent = %name%
label-urgent-background = ${colors.alert}
label-urgent-padding = 1

label-empty = %name%
label-empty-foreground = ${colors.disabled}
label-empty-padding = 1

[module/xwindow]
type = internal/xwindow
label = %title:0:30:...%

[module/cpu]
type = internal/cpu
interval = 2
format-prefix = "CPU "
format-prefix-foreground = ${colors.primary}
label = %percentage:2%%

[module/memory]
type = internal/memory
interval = 2
format-prefix = "RAM "
format-prefix-foreground = ${colors.primary}
label = %used_percentage%%

[module/date]
type = internal/date
interval = 1

date = %H:%M
date-alt = %d-%m-%Y %H:%M:%S

label = %date%
label-foreground = ${colors.primary}

[settings]
screenchange-reload = true
pseudo-transparency = true
EOF

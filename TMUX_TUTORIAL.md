# TMUX Tutorial

Esta configuración de tmux vive en `tmux/.tmux.conf` y se instala con **GNU Stow**.

## Instalación

Desde la raíz de este repositorio:

```bash
stow -t "$HOME" tmux
```

Eso crea este symlink:

```bash
~/.tmux.conf -> ~/dotfiles/tmux/.tmux.conf
```

## Plugin manager

La configuración usa **TPM**:

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Después, dentro de tmux:

- `Ctrl+Space` + `I` instala plugins
- `Ctrl+Space` + `U` actualiza plugins
- `Ctrl+Space` + `Alt+u` limpia plugins no usados

## Prefix

El prefix configurado es:

```text
Ctrl + Space
```

No se usa el default `Ctrl+b`.

## Navegación entre paneles

Con prefix:

- `Ctrl+Space` + `h` → izquierda
- `Ctrl+Space` + `j` → abajo
- `Ctrl+Space` + `k` → arriba
- `Ctrl+Space` + `l` → derecha

Sin prefix:

- `Alt + ←/→/↑/↓` → mover foco entre paneles

## Navegación entre ventanas

Sin prefix:

- `Shift + ←` → ventana anterior
- `Shift + →` → ventana siguiente
- `Alt + Shift + h` → ventana anterior
- `Alt + Shift + l` → ventana siguiente

## Dividir paneles

Con prefix:

- `Ctrl+Space` + `"` → split vertical
- `Ctrl+Space` + `%` → split horizontal

Los nuevos paneles abren en el mismo directorio actual.

## Copy mode

La configuración usa estilo **vi** en copy mode.

- `v` inicia selección
- `Ctrl+v` activa selección rectangular
- `y` copia y sale

## Plugins activos

- `tmux-plugins/tpm`
- `tmux-plugins/tmux-sensible`
- `christoomey/vim-tmux-navigator`
- `tmux-plugins/tmux-yank`

## Tema

El tema actual es **Gruvbox**, configurado inline en `tmux/.tmux.conf`.

## Recargar configuración

Si ya tienes una sesión tmux abierta:

```bash
tmux source-file ~/.tmux.conf
```

## Verificación rápida

Puedes validar que tmux tomó esta configuración con:

```bash
tmux show-options -gv prefix
tmux show-options -gv mouse
```

El resultado esperado incluye:

- `C-Space`
- `on`

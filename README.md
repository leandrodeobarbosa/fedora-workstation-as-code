# fedora-workstation-as-code

> Ambiente de trabalho Linux reprodutível e automatizado baseado em Fedora + Sway (Wayland), com foco em produtividade, leveza e consistência.

Esse repositório reúne meus dotfiles para um setup pessoal de workstation no **Fedora Linux**, utilizando **Sway** como window manager, além de configurações para **Waybar**, **Swaylock**, scripts auxiliares e outros ajustes que melhoram a experiência de uso no dia a dia.

O projeto foi criado para automatizar a configuração do ambiente local e aplicar princípios de **DevOps** ao workstation setup, tratando a máquina do desenvolvedor como código.

---

## 📸🤯 Demonstração do Workflow
Demonstração do ambiente em uso, alternando entre janelas, atalhos de produtividade e integração com terminal e ferramentas gráficas.

![Demo do workflow](media/demo.gif)
---

## Objetivos do projeto
- Automatizar a configuração de um ambiente Linux pessoal
- Reduzir o esforço de setup manual
- Manter um ambiente leve e produtivo com Sway
- Organizar preferências e scripts em um repositório versionado
- Aplicar uma abordagem de **Workstation as Code**

#### Esse projeto cobre:
- configuração do Sway
- configuração da Waybar
- scripts personalizados para o fluxo de trabalho
- instalação automatizada de dependências e ajustes base
- organização de wallpapers e assets locais

#### Esse repositório **não** inclui, no momento:
- provisionamento de ferramentas DevOps como `kubectl` ou `terraform`
- integração com cloud providers
- gerenciamento avançado de dotfiles com ferramentas como `chezmoi` ou `dotbot`

---

## Pré-requisitos
Esse setup foi testado no **Fedora Workstation 42**.

### Dependências básicas

- `git`
- `curl`
- `wget`
- `unzip`
- `python3`
- `xdg-user-dirs`

---

## 📂 Estrutura do Repositório

```
dotfiles/
├── sway/                  → Configurações do Sway
│   └── scripts/           → Scripts personalizados (ex: screenshot)
├── waybar/                → Configurações do Waybar e scripts
│   └── scripts/           → Scripts personalizados
├── media/
│   └── demo-workflow.mp4
│   └── qrcode-pix.jpg
├── wallpapers/            → Imagens de fundo (default.jpg)
├── install.sh             → Script principal de instalação
```

---

## 🚀 Instalação

Clone o repositório e execute o script de instalação:

```bash
$ git clone https://github.com/leandrodeobarbosa/fedora-workstation-as-code ~/fedora-workstation-as-code
$ cd ~/fedora-workstation-as-code
$ chmod +x install.sh sway/scripts/screenshot.sh waybar/scripts/cups-tray.sh waybar/scripts/updates-counter.sh
$ ./install.sh
```

---

## O que o script faz?
1. Valida se o sistema operacional é Fedora;
2. Instala os pacotes essenciais do ambiente gráfico e utilitários;
3. Cria os links simbólicos das configurações para Sway, Waybar e scripts;
4. Copia o wallpaper padrão para o diretório de imagens do usuário;
5. Instala a fonte FiraCode Nerd Font;
6. Limpa arquivos temporários ao final da execução.

---

## Ferramentas instaladas

- Window Manager: Sway
- Status Bar: Waybar
- Screen Lock: Swaylock
- Captura de tela: Grim, Slurp, Swappy
- Terminal: Alacritty
- Editor: Vim
- Clipboard (Wayland): wl-clipboard

---

## Personalização

### Tema escuro para GTK

Para forçar o tema escuro nos aplicativos GTK:

```bash
gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'
```

### Ajuste de resolução (wlr-randr)

Configure a resolução do monitor manualmente:

```bash
wlr-randr --output HDMI-A-3 --mode 1920x1080@144
```

Para descobrir o nome da sua saída:
`swaymsg -t get_outputs`

Mais informações em: [man sway](https://man.archlinux.org/man/sway.1) | [Wiki oficial](https://github.com/swaywm/sway/wiki)

---

## Solução de problemas

### Sway não inicia no login?
Verifique se o Sway está disponível como sessão no seu gerenciador de login.

### Waybar não aparece ou falha?
Reinicie o Sway (`Mod+Shift+c`) ou revise a configuração em:
```bash
~/.config/waybar/config.jsonc
```

---

## Roadmap
- Modularizar melhor o script de instalação
- Adicionar suporte opcional a Flatpak
- Avaliar um gerenciador de dotfiles dedicado no futuro
- Incluir configuração de editor voltada ao meu fluxo de desenvolvimento
---

## Autor
Desenvolvido por Leandro de O Barbosa como parte de uma jornada contínua em DevOps, com foco em automação, produtividade e ambientes Linux bem organizados.
🔗 [Portfólio técnico](https://leandrodeobarbosa.dev)
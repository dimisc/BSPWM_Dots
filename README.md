# BSPWM_Dots
Dotfiles for BSPWM

*** INSTRUCTIONS: ***

## 1)  Minimal Arch Install (Grub, Pipewire, NetworkManager. Packages: git)

## 2)  Install yay
        git clone https://aur.archlinux.org/yay.git
        cd yay
        makepkg -si
        cd ~

## 3)  Clone the BSPWM_Dots repo

## 4)  Install AUR & Pacman packages (optional: extra)
        cd BSPWM_Dots/1. Packages/
        sudo pacman -S $(cat PacmanPackages.txt)
        yay -S $(cat AURPackages.txt)
        yay -S $(cat ExtraPackages.txt)
        sudo pacman -U transmission-gtk-3.00-6-x86_64.pkg.tar.zst
        cd ~

## 6)  Generate the User folders
        LC_ALL=C.UTF-8 xdg-user-dirs-update --force

## 7)  Copy #2 Home configs in home folder
        cp -R BSPWM_Dots/2. Home Config Files/* /home/user/.config/

## 8)  Copy #3 Fonts
        sudo cp -R BSPWM_Dots/3. User Share Fonts/* /usr/share/fonts/
        sudo fc-cache -fv

## 9)  Copy #4 Themes
        sudo cp -R BSPWM_Dots/4. User Share Themes/* /usr/share/themes/

## 10)  Copy #5 Custom Scripts
        sudo cp -R BSPWM_Dots/5. User Local Bin/* /usr/local/bin/

## 11) Copy #6 ETC configurations
        sudo cp -R BSPWM_Dots/6. ETC/* /etc/

## 12) Install Oh-my-zsh
        sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

## 13) Copy #7 Home Hidden Files
        cp -R BSPWM_Dots/7. Home Hidden Files/* /home/user/

        ** Check to see if files have copied with ls -la If not then copy one by one **

## 14) Copy #8 Root config files
        sudo cp -R BSPWM_Dots/8. Root/Config/* /home/root/.config/

## 15) Copy #9 Pictures (needed for wallpaper & screen lock)
        cp -R BSPWM_Dots/9. Pictures/* /home/user/Pictures/

## 16) Post install:
        rm -rf /home/user/yay
        rm -rf /home/user/BSPWM_Dots
        sudo chown -R user:user /home/user

        sudo systemctl enable bluetooth
        
        * While in a GUI Environment *
        betterlockscreen -u /home/user/Pictures/Wallpapers/Lock.jpg

## 17) Install a Login Manager (SDDM or ly for minimal)
        sudo pacman -S ly
        sudo systemctl enable ly

Reboot

You should have a fully working BSPWM installation.

## IMPORTANT KEYBINDS (see .config/bspwm/sxhkdrc):
        super + d                 Launches Rofi
        super + q                 Quits
        super + x                 Shutdown Menu
        super + enter             Alacritty
        super + Shift + f         Thunar
        super + Shift + w         Firefox
        super + Shift + t         Geany

## Optional:
    killall xsettingsd
    gsettings set org.gnome.desktop.interface gtk-theme Qogir-dark
    gsettings set org.gnome.desktop.interface icon-theme Papirus

Reboot

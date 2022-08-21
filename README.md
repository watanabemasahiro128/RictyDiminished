# Ricty Diminished

## How to generate Nerd Fonts and Patched Fonts

```sh
mkdir ricty_diminished
cd ricty_diminished
curl -OL https://rictyfonts.github.io/files/ricty_diminished-4.1.1.tar.gz
tar -zxvf ricty_diminished-4.1.1.tar.gz
cd ..
brew install fontforge
git clone https://github.com/ryanoasis/nerd-fonts.git
fontforge -script ./nerd-fonts/font-patcher ./ricty_diminished/RictyDiminishedDiscord-Regular.ttf --powerline --powerlineextra
fontforge -script ./nerd-fonts/font-patcher ./ricty_diminished/RictyDiminishedDiscord-Bold.ttf --powerline --powerlineextra
mv *.ttf ./ricty_diminished/
cd ricty_diminished
mv "Ricty Diminished Discord Regular Nerd Font.ttf" RictyDiminishedDiscord-Regular.ttf
mv "Ricty Diminished Discord Bold Nerd Font.ttf" RictyDiminishedDiscord-Bold.ttf
cp RictyDiminishedDiscord-Regular.ttf RictyDiminishedDiscord-Regular-Patched.ttf
cp RictyDiminishedDiscord-Bold.ttf RictyDiminishedDiscord-Bold-Patched.ttf
cp RictyDiminishedDiscord-NerdFont-Regular.ttf RictyDiminishedDiscord-NerdFont-Regular-Patched.ttf
cp RictyDiminishedDiscord-NerdFont-Bold.ttf RictyDiminishedDiscord-NerdFont-Bold-Patched.ttf
find *-Patched.ttf | xargs -I {} fontforge -lang ff -script patch {}
```

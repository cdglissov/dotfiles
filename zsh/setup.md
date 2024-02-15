# Steps

* Ubuntu, if windows use wsl, wsl --set-default-version 2
* Install windows terminal and follow the required steps
- sudo apt update
- sudo apt upgrade -y
- sudo apt install build-essential -y
- sudo apt install zsh -y
- sudo apt install wget git -y
- sudo apt install screenfetch -y
- sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

* Follow setup guide, nano ~/.zshrc then change ZSH_THEME="powerlevel10k/powerlevel10k"
- git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
## 安装ZSH
```bash
apt install zsh
```
## 切换到ZSH
```bash
chsh -s $(which zsh)
```
## 安装oh-my-zsh
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
## 安装主题
```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```
## 安装插件
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```
## 安装字体
- 安装字体管理工具
```bash
apt-get install -y fontconfig
```
- 下载字体文件
```bash
wget -P /tmp https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/FiraMono/Regular/FiraMonoNerdFont-Regular.otf
```
- 将字体复制到系统字体目录
```bash
mkdir -p /usr/share/fonts/opentype/nerd-fonts
mv /tmp/FiraMonoNerdFont-Regular.otf /usr/share/fonts/opentype/nerd-fonts/
chmod 644 /usr/share/fonts/opentype/nerd-fonts/*
```
- 更新字体缓存
```bash
fc-cache -fv
```
## 克隆备份仓库并部署配置
```sh
git clone https://github.com/mfblog/oh-my-zsh-backup.git
if [ -d "oh-my-zsh-backup" ]; then
    cp oh-my-zsh-backup/.p10k.zsh /root/
    cp oh-my-zsh-backup/.zshrc /root/
    mkdir -p /root/.oh-my-zsh/custom
    cp -r oh-my-zsh-backup/oh-my-zsh-custom/* /root/.oh-my-zsh/custom/
    echo "配置文件部署完成"
else
    echo "错误：备份仓库克隆失败"
    exit 1
fi
```


# Ubuntu .dotfile

```sh
            .-/+oossssoo+/-.               igmr@DellOptiPlex7050 
        `:+ssssssssssssssssss+:`           --------------------- 
      -+ssssssssssssssssssyyssss+-         OS: Ubuntu 22.04.4 LTS x86_64 
    .ossssssssssssssssssdMMMNysssso.       Host: OptiPlex 7050 
   /ssssssssssshdmmNNmmyNMMMMhssssss/      Kernel: 6.5.0-21-generic 
  +ssssssssshmydMMMMMMMNddddyssssssss+     Uptime: 55 mins 
 /sssssssshNMMMyhhyyyyhmNMMMNhssssssss/    Packages: 1644 (dpkg), 9 (snap) 
.ssssssssdMMMNhsssssssssshNMMMdssssssss.   Shell: bash 5.1.16 
+sssshhhyNMMNyssssssssssssyNMMMysssssss+   Terminal: /dev/pts/0 
ossyNMMMNyMMhsssssssssssssshmmmhssssssso   CPU: Intel i7-6700 (8) @ 4.000GHz 
ossyNMMMNyMMhsssssssssssssshmmmhssssssso   GPU: Intel HD Graphics 530 
+sssshhhyNMMNyssssssssssssyNMMMysssssss+   Memory: 844MiB / 15846MiB 
.ssssssssdMMMNhsssssssssshNMMMdssssssss.
 /sssssssshNMMMyhhyyyyhdNMMMNhssssssss/                            
  +sssssssssdmydMMMMMMMMddddyssssssss+                             
   /ssssssssssshdmNNNNmyNMMMMhssssss/
    .ossssssssssssssssssdMMMNysssso.
      -+sssssssssssssssssyyyssss+-
        `:+ssssssssssssssssss+:`
            .-/+oossssoo+/-.
```

## Instalación de paquetes

```sh
sudo apt install curl -y
bash <(curl -s https://raw.githubusercontent.com/igmr/shell-ubuntu/main/installers.sh)
```

## Crear carpeta

```sh
bash <(curl -s https://raw.githubusercontent.com/igmr/shell-ubuntu/main/folder.sh)
```

## Descargar configuración de .zshrc para Ubuntu

```sh
bash <(curl -s https://raw.githubusercontent.com/igmr/shell-ubuntu/main/.zshrc-pull.sh)
source ~/.zshrc
```

## Descargar configuración de .hyper.js para Ubuntu

```sh
bash <(curl -s https://raw.githubusercontent.com/igmr/shell-ubuntu/main/.hyper-pull.sh)
```

## Configuración de git

```sh
# =============================================================================
# Descargar configuración de git
# =============================================================================
bash <(curl -s https://raw.githubusercontent.com/igmr/shell-ubuntu/main/git.sh)
# =============================================================================
# Generar clave ssh
# =============================================================================
ssh-keygen -t rsa -b 4096 -C "igmrivan@gmail.com"
# =============================================================================
# Mostrar ssh public
# =============================================================================
cat ~/.ssh/id_rsa.pub
```

## Configuración de MySQL

```sh
# =============================================================================
# Install MySQL
# =============================================================================
sudo apt install -y mysql-client mysql-server mysql-common
# =============================================================================
# Iniciar servicio de MySQL
# =============================================================================
sudo systemctl start mysql
# =============================================================================
# Habilitar MySQL al iniciar sesión
# =============================================================================
sudo systemctl enable mysql
# =============================================================================
# Establecer contraseña de MySQL
# =============================================================================
sudo mysql --user="root" --execute="ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'MySQL94.';"
# =============================================================================
# Configurar mysql in firewall
# =============================================================================
sudo ufw allow 3306
```

## PHP 8.1

```sh
sudo apt install -y php8.1 libapache2-mod-php8.1 php8.1-pgsql php8.1-sqlite3 php8.1-interbase php8.1-odbc php8.1-sybase php8.1-mysql php8.1-common php8.1-cli php8.1-common php8.1-cli php8.1-opcache php8.1-readline php8.1-mbstring php-pear php8.1-intl php8.1-dom php8.1-curl php8.1-cgi php-json
```

## PHP 8.2

```sh
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install php8.2 -y
sudo apt install -y php8.2-cli php8.2-common php8.2-fpm php8.2-mysql php8.2-zip php8.2-gd php8.2-mbstring php8.2-curl php8.2-xml php8.2-bcmath
```

## Composer 2.7.4

```sh
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"

sudo mv composer.phar /usr/local/bin/composer
```

## Composer 2.7.6

```sh
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"

sudo mv composer.phar /usr/local/bin/composer
```

## Configuración de Zsh && OhMyZsh

```sh
# =============================================================================
# Instalación de zsh 
# =============================================================================
sudo apt install zsh
# =============================================================================
# Cambiar bash por zsh
# =============================================================================
chsh -s $(which zsh)
# =============================================================================
# Instalación de OhMyZsh
# =============================================================================
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
# =============================================================================
# Instalación de plugin
# =============================================================================
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-completions
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
# =============================================================================
# Tema default
# =============================================================================
robbyrussell
```

## Configuración de NodeJS

```sh
# =============================================================================
# Instalación de nvm
# =============================================================================
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
# =============================================================================
# Recargar configuración de nvm
# =============================================================================
source ~/.zshrc
# =============================================================================
# Instalación de ultima versión de Node JS
# =============================================================================
nvm install node
```
## FTP

```sh
# =============================================================================
# Instalación de servidor FTP
# =============================================================================
sudo apt install -y vsftpd
# =============================================================================
# Editar archivo de configuracion /etc/vsftpd.conf
# =============================================================================
sudo nano /etc/vsftpd.conf
# =============================================================================
# Descomentar linea: # write_enable=YES
# =============================================================================
# Uncomment this to enable any form of FTP write command.
write_enable=YES
# =============================================================================
# Reiniciar servicio vsftpd
# =============================================================================
sudo systemctl restart vsftpd
# =============================================================================
# Habilitar inicio de servicio vsftp
# =============================================================================
sudo systemctl enable vsftpd
```

Este é um projeto de exemplo usado em posts do blog [Mind Share](http://fabiolnm.blogspot.com).

# Preparação do Projeto

Caso esteja usando Ubuntu, execute o comando abaixo para configuração automática do ambiente.

```
source App-Contatos-Rails/setup-project
```

Caso esteja usando outro sistema operacional, é necessário modificar o passo de instalação onde é usado o apt-get.

## Pré-requisitos automatizados com script setup-project
* O script inicia com a instalação de bibliotecas requeridas pelo Ruby (é neecssário digitar a senha de root para rodar o apt-get install):

```
sudo apt-get install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-0 libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion nodejs
```

* Na raiz do projeto, existe um arquivo .rvmrc, um script que é executado automaticamente ao entrar no diretório do projeto.
* Este script contém o seguinte comando:

```
rvm use 1.9.2@ambiente_app_contatos
```

* Este comando serve para carregar o ambiente "ambiente_app_contatos", baseado no Ruby 1.9.2.
* Desta forma, o carregamento automático via .rvmrc dispensa o desenvolvedor de carregar o ambiente manualmente no terminal.

* Caso o RVM não esteja instalado, o script setup-project efetua a instalação:

```
cd $HOME
bash < <(curl -s https://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer)
source $HOME/.bashrc
```
* Em seguida, o Ruby 1.9.2 é instalado:

```
rvm install ruby-1.9.2-p290
```

* E o ambiente_app_contatos é criado:

```
rvm --create 1.9.2-p290@ambiente_app_contatos
```

* Ao entrar no diretório do projeto, o ambiente é carregado, como pose ser confirmado pela mensagem no terminal:

```
Using /home/ep/.rvm/gems/ruby-1.9.2-p290 with gemset ambiente_app_contatos
```

* Por fim, a instalação das dependências do projeto ocorre com o comando:

```
bundle install
```

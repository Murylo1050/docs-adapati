<h1>Instalação asdf, nodejs e PHP</h1>

Referência da documentação original pode ser encontrada [aqui!](https://asdf-vm.com/pt-br/guide/introduction.html)
<h2>Download asdf</h2>
<p>Baixe o repositório oficial contendo o asdf</p>
<pre>git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.14.1</pre>

<h2>Adicionando ao seu shell</h2>

<h3>Bash</h3>

<p>Para bash será necessário adicionar essa linha ao seu arquivo ~/.bashrc: </p>
<pre>. "$HOME/.asdf/asdf.sh" </pre>

<p>O auto completar deve ser manualmente configurado, adicionando essa linha ao seu arquivo .bashrc</p>
<pre>. "$HOME/.asdf/completions/asdf.bash"</pre>

<h3>Fish</h3>

<p>Para fish será necessário adicionar essa linha ao seu arquivo ~/.config/fish/config.fish: </p>
<pre>source ~/.asdf/asdf.fish</pre>

<p>O auto completar deve ser configurado manualmente através do seguinte comando:</p>
<pre>mkdir -p ~/.config/fish/completions; and ln -s ~/.asdf/completions/asdf.fish ~/.config/fish/completions</pre>

<h3>ZSH</h3>

<p>Adicione a seguinte linha ao seu ~/.zshrc: </p>
<pre>. "$HOME/.asdf/asdf.sh" </pre>

<p>OU utilize um framework para ZSH, como asdf para oh-my-zsh que irá adicionar o script e o auto completar.

O auto completar pode ser configurado ou pelo plugin do asdf para framework para ZSH, ou através da adição das seguintes linhas ao seu .zshrc:</p>
<pre># append completions to fpath
fpath=(${ASDF_DIR}/completions $fpath)
# initialise completions with ZSH's compinit
autoload -Uz compinit && compinit</pre>
* Se você está utilizando uma configuração compinit customizada, garanta que compinit esteja abaixo chamada asdf.sh
* Se você está utilizando uma configuração compinit customizada com um framework para ZSH, garanta que compinit esteja abaixo da chamada do framework.
Aviso

Se você está utilizando um framework para ZSH, o plugin do asdf pode precisar ser atualizado para utilização adequada do novo auto completar do ZSH através do fpath. O plugin do asdf para o oh-my-zsh ainda não foi atualizado, veja: [ohmyzsh/ohmyzsh#8837.](ohmyzsh/ohmyzsh#8837)

<h2>Instalando plugin do nodejs</h2>

<pre>asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git</pre>

<h2>Instalando versões do node</h2>
Agora temos o plugin para o Node.js, nós podemos instalar uma versão desta ferramenta.

Podemos ver quais versões tão disponíveis através do comando <strong>asdf list all nodejs</strong>, ou uma lista específica de versões com <strong>asdf list all nodejs 14</strong>

Vamos instalar somente a última versão disponível, utilizando a tag latest:

<pre>asdf install nodejs latest</pre>

<h2>Definindo uma versão</h2>
asdf executa uma verificação das versões das ferramentas a serem utilizadas através do arquivo <strong>.tool-versions</strong> presente desde diretório atual, até o diretório $HOME. A varredura ocorre no momento em que você executa uma ferramenta que o asdf gerencia.

<h3>Versões globais</h3>
Os padrões globais são gerenciados em <strong>$HOME/.tool-versions</strong>. Defina uma versão global através do comando:

<pre>asdf global nodejs latest</pre>

<h3>Versões locais</h3>
A versão local só precisar ser definida caso queira utilizar uma versão diferente da global.

Versões locais são definidas no arquivo <strong>$PWD/.tool-versions</strong> (seu diretório atual). Geralmente, será um repositório Git para um projeto. Quando estiver no diretório desejado, execute:
<pre>asdf local nodejs versão-que-precisar</pre>
<br/><br/><br/><br/>
<h2>Instalando dependências do PHP</h2>
<pre>sudo apt install -y autoconf bison re2c pkg-config libxml2-dev libsqlite3-dev zlib1g-dev libcurl4-openssl-dev libgd-dev libonig-dev libpq-dev libzip-dev build-essential libssl-dev libreadline-dev</pre>
<h2>Instalando plugin do PHP</h2>

<pre>asdf plugin-add php https://github.com/asdf-community/asdf-php.git</pre>

<h2>Instalando versões do PHP</h2>
Agora temos o plugin para o PHP, nós podemos instalar uma versão desta ferramenta.

Podemos ver quais versões tão disponíveis através do comando <strong>asdf list all php</strong>, ou uma lista específica de versões com <strong>asdf list all php 8</strong>

Vamos instalar somente a última versão disponível, utilizando a tag latest:

<pre>asdf install php latest</pre>

Obs.: O PHP vai ser compilado na sua maquina então se começar a aparecer varias coisas no terminal não se assuste kkkkk. Essa compilação pode demorar um pouqinho então apenas aguarde o processo terminar com o terminal aberto.

<h2>Definindo uma versão</h2>
asdf executa uma verificação das versões das ferramentas a serem utilizadas através do arquivo <strong>.tool-versions</strong> presente desde diretório atual, até o diretório $HOME. A varredura ocorre no momento em que você executa uma ferramenta que o asdf gerencia.

<h3>Versões globais</h3>
Os padrões globais são gerenciados em <strong>$HOME/.tool-versions</strong>. Defina uma versão global através do comando:

<pre>asdf global php latest</pre>

<h3>Versões locais</h3>
A versão local só precisar ser definida caso queira utilizar uma versão diferente da global.

Versões locais são definidas no arquivo <strong>$PWD/.tool-versions</strong> (seu diretório atual). Geralmente, será um repositório Git para um projeto. Quando estiver no diretório desejado, execute:
<pre>asdf local php versão-que-precisar</pre>




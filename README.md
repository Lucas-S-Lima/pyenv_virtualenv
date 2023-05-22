# pyenv_virtualenv 🐍

Instruções para instalação do Pyenv e Virtualenv no sistema operacional Linux.
A intenção é que as descrições sejam didáticas e de fácil compreensão para facilitar
o entendimento do desenvolvedor.

<h2>Instalação do Pyenvv</h2>

<b>Toda a instalação do gerenciador de versões - Pyenv - será via Terminal.</b>

* A. Com o terminal aberto, iniciaremos com a instalação de algumas libs (bibliotecas) importantes que atuarão com ferramentas de compilação, desempacotamento e distribuição de projetos python. 

```
sudo apt-get install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm gettext libncurses5-dev tk-dev tcl-dev blt-dev libgdbm-dev git python-dev python3-dev aria2 vim libnss3-tools python3-venv liblzma-dev libpq-dev
```
Caso o seu sistema seja o Linux Mint Cinnamon 21.1, provavelmente a biblioteca " Python-dev " estará obsoleta. Assim, o terminal exibirá alguns pacotes alternativos que podem substituí-lo. Você pode alterar o nome do pacote obsoleto no comando acima e inserí-lo novamente. Porém, caso queira, poderá tentar atualizar o seu repositório de pacotes do sistema com o comando:

```
sudo apt update
```
* B. Em seguida, faremos o download do script de instalação do Pyenv por meio do repositório do GitHub passando um URL ao terminal. 
```
curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash
```
* C. Agora, abriremos o editor de texto e iremos inserir a porção de código que foi retornada ao final do processamento do terminal na instrução anterior.

==> Abrindo o editor
```
vim .bashrc
```
==> Comando a ser inserido
```
export PATH="/home/user/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
```
Que deve ser inserido após a expressão `fi` no editor. Lembrando que o `user` deve ser trocado pelo nome de seu usuário. 
Porém, como o próprio terminal irá retornar essa expressão a ser inserida no editor, tome o comando acima apenas como um
exemplo de quais linhas você deverá selecionar.

* D. Dentro do editor, para inserir um comando, pressione `i` em seu teclado. Após isso, estará apto a editar. Cole o comando acima com `CTRL + SHIFT + V` e em seguida `CRTL + C`para finalizar a inserção e `CRTL + O`para salvar. Por fim, na ultima linha coloque `:x`e pressione enter para sair do editor.

* E. Feito isso, iniciaremos a instalação do Pyenv propriamente dito com o comando:
```
pyenv  install -l
```
Para listas todas as versões. Identifique a que deseja instalar.

* F. Instalando a versão desejada:
```
Pyenv install <versão>
```
Exemplo - caso desejasse instalar a versão 3.9.16, o comando ficaria:
```
Pyenv install 3.9.16
```
Pressione ` ENTER` e aguarde a sua instalação ser concluída.

* G. Após finalizada, para usar tal versão, use:
```
pyenv global <versão>
```
A partir de agora, seu sistema está configurado para a versão selecionada. 

<h3>Consultas</h3>

Para verificar todas as versões disponiveis, use o comando:
```
pyenv versions
```
Para verificar qual versão está sendo usada:
```
python -V
```
Para retornar à versão nativa, use o comando:
```
pyenv global system
```
Finalmente, para saber se a ver se a versão utilizada é a do sistema nativo ou a do pyenv, use:
```
which python
```

<h2>Instalação do Virtualenv</h2>

* A. No terminal bash, criaremos uma nova pasta: `mkdir nome_da_pasta` cujo nome pode ser qualquer um.

* B. Listaremos as pastas de nosso diretório: `ls`ou `dir`

* C. Entraremos na pasta criada: `cd nome_da_pasta/`

* D. E então inicializamos a comando: `python3 -m venv venv`

* E. Ao navegarmos pela interface dos nossos arquivos, encontraremos a nova pasta criada, e uma segunda pasta dentro dela chamada `venv`. Dentro de `venv`, haverá inúmeros arquivos, dentre eles a pasta `bin`. É para dentro dela que navegaremos pelo terminal para ativar o nosso ambiente virtual.

* F. De volta ao terminal, iremos inserir o comando: `source venv/bin/activate`

Então é possível perceber que o login do administrador está após o nome da pasta `venv`, desta forma:
```
(venv) Usuer@user: ~/venv$ 
```
Isso indica que o Virtualenv já está ativado em seu sistama.
Para desativá-lo, use o comando:
```
deactivate
```





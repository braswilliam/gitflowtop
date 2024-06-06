# Git e Versionamento:

## Versionamento:

➡️ Registro de mudanças em arquivos, que possibilita recuperação ou acesso a versões anteriores;

➡️ Desenvolvimento de código em colaboração com outros integrantes;

# O que é o git:

Git é um sistema de versionamento de código, que guarda os registros de versão como snapshots (fotos)  do estado do projeto, além da referência para essa foto.

### Git e suas operações locais:

A maioria da operações feitas pelo Git são locais e por isso boa parte das operações são praticamente instantâneas devido à facilidade de acessar arquivos em seu próprio computador.

### Instalando o Git:

### Terminal git:

1.  Procure por Git no Google;
2. Efetue o download para o seu sistema;
3. E é só seguir os passos de forma defaut usando: next, next next…
4. Para saber se está instalado use o comando **`git version` ou `git --version`**

### Distribuições baseadas em Linux:

### Ubuntu/Debian

```bash
bashCopiar código
sudo apt update
sudo apt install git

```

### Fedora

```bash
bashCopiar código
sudo dnf install git

```

### CentOS/RHEL

Para CentOS/RHEL 8:

```bash
bashCopiar código
sudo dnf install git

```

Para CentOS/RHEL 7:

```bash
bashCopiar código
sudo yum install git

```

### Arch Linux

```bash
bashCopiar código
sudo pacman -S git

```

### OpenSUSE

```bash
bashCopiar código
sudo zypper install git

```

Depois de instalar o Git, você pode verificar se a instalação foi bem-sucedida e qual a versão instalada com o comando:

```bash

git --version

```

### GitHub Desktop:

1. Procure por GitHub Desktop;
2. [GitHub Desktop](https://desktop.github.com/)
3. É só baixar e instalar

### Como saber se ele foi instalado corretamente:

```bash
PS C:\Users\filmi> git --version
git version 2.45.1.windows.1
PS C:\Users\filmi>
```

### O github Desktop:

É uma ferramenta de versionamento da GitHub, que possui uma interface mais amigável.
Se você não gosta de usar linhas de comando. Lembrando que é essencial para quem estuda programação.
Nele você já loga com a sua conta do git já estará tudo pronto para trabalhar com versionamento.

![Untitled](./imgs/Untitled.png)

### IDEs como VS Code:

Algumas IDEs possuem como VS Code, Intellij, Pycharm,  possuem o terminal como ferramenta de trabalho. Facilitando o versionamento de código.

![Untitled](./imgs/Untitled%201.png)

## Configurando o Git:

Cadastrando o seu nome e e-mail:

```bash
$ git config --global user.name "Fulano de Tal"
```

```bash
$ git config --global user.email fulanodetal@exemplo.br
```

Para saber se está tudo devidamente configurado é só dar o comando:

```bash
$ git config --list
```

O retorno será:

```
user.name=Fulano de Tal
user.email=fulanodetal@exemplo.br
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
...
```

Ou usando comando específico:
`$ git config user.name`

Retorno:
`Fulano de Tal`

# Repositório Remoto:

### Primeiro vamos falar sobre repositório remoto

O repositório remoto trata-se de um repositório ou arquivo que está em outra máquina. Seja ela uma nuvem ou sites web. Um dos mais famosos é o Github.

O GitHub é uma plataforma de hospedagem de código-fonte que utiliza o sistema de controle de versão Git. Ele oferece uma ampla gama de recursos para desenvolvedores colaborarem em projetos de software, sejam eles públicos ou privados. Aqui estão alguns pontos-chave sobre o GitHub:

1. **Repositórios**: No GitHub, um repositório (ou "repo") é um local onde o código do projeto é armazenado. Ele pode conter múltiplos arquivos de código, documentação e outros recursos necessários para o desenvolvimento do projeto.
2. **Controle de Versão**: Usando Git, o GitHub permite aos desenvolvedores rastrear mudanças no código ao longo do tempo. Isso facilita a colaboração, pois cada desenvolvedor pode trabalhar em suas próprias cópias dos arquivos e, posteriormente, mesclar suas alterações.
3. **Colaboração**: GitHub facilita a colaboração entre desenvolvedores por meio de recursos como pull requests e code reviews. Pull requests permitem que você proponha mudanças no código, que outros membros do projeto podem revisar e discutir antes de serem mescladas no projeto principal.
4. **Issues e Projetos**: GitHub inclui sistemas de gerenciamento de tarefas e bugs através de "issues" (questões) e "projetos" (projetos). Isso ajuda as equipes a organizar e priorizar o trabalho.
5. **GitHub Actions**: É um recurso de integração contínua e entrega contínua (CI/CD) que permite automatizar fluxos de trabalho, como testes automatizados e implantação de software.
6. **Comunidade e Rede Social**: GitHub também funciona como uma rede social para desenvolvedores. Você pode seguir outros desenvolvedores, dar estrelas (stars) a repositórios que você acha interessante, e forkar (criar uma cópia) de repositórios para começar seus próprios projetos baseados em outros.
7. **GitHub Pages**: Um serviço que permite hospedar sites estáticos diretamente dos repositórios GitHub, ideal para documentações, portfólios e páginas de projetos.
8. **Integrações e APIs**: GitHub pode ser integrado com diversas outras ferramentas e serviços, e fornece uma API robusta para automatizar e melhorar o fluxo de trabalho.

Em resumo, GitHub é uma ferramenta poderosa para desenvolvimento colaborativo, gerenciamento de código e integração contínua, amplamente utilizada na comunidade de desenvolvimento de software.

## GitHub Cli:

Onde eu coloco esse danado desse token? **Boa pergunta!**
Usando A ferramenta **GitHub CLI**:

**Esse passo serve para quem não possui o CLI instalado:**

A GitHub CLI é uma ferramenta de código aberto para uso do GitHub na linha de comando do computador. Quando você está trabalhando na linha de comando, você pode usar GitHub CLI para economizar tempo e evitar mudar o contexto.

O GitHub CLI inclui recursos de GitHub como:

- Visualizar, criar, clonar e bifurcar repositórios
- Crie, feche, edite e visualize problemas e pull requests
- Rever, fazer diff e merge de pull requests
- Executar, visualizar e listar fluxos de trabalho
- Criar, listar, visualizar e excluir versões
- Criar, editar, listar, exibir e excluir gists
- Listar, criar, excluir e conectar um codespace
- Recuperar informações da API GitHub

### **Instalação:**

### Windows:

| Instalação: | Atualização: |
| --- | --- |
| winget install --id GitHub.cli | winget upgrade --id GitHub.cli |

### macOS:

Via:  [**Homebrew**](https://brew.sh/)

### Linux:

**Debian, Ubuntu Linux, Raspberry Pi OS (apt)**

Instalação:

1 - Comando de instalação dos pacotes:

```bash
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
&& sudo mkdir -p -m 755 /etc/apt/keyrings \
&& wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```

2 - **`sudo apt update` →** Ele é responsável por baixar, instalar, atualizar e remover programas do sistema, além de resolver as dependências de cada pacote instalado.

3 - **`sudo apt install gh` →** Comando para executar a instalação do CLI.

**Para demais distribuições é só acessar a documentação:**
https://github.com/cli/cli/blob/trunk/docs/install_linux.md

### Nota:

**A Instalação do github CLI pode ser feita assim que você instala o git, porem a autenticação que é o próximo passo vai ser de acordo com o tipo de autenticação que você deseja HTTP, SSH, GitHub Cli.**

## Como clonar um repositório do GitHub?

Isso aqui é um repositório no GitHub:

![Untitled](./imgs/Untitled%202.png)

Lá em cima, no canto superior direito tem a opção **`<>code`**. Vamos clicar lá.

![Untitled](./imgs/Untitled%203.png)

### Nota**!**

**Você verá 3, eu digo três formas de clonagem de um repositório no GitHub. Antes de escolher as opções leia as três formas e veja qual mais se adequa a sua necessidade:**

## 1º Formato - HTTPS

- **O que é:** Um método de clonagem usando o protocolo HTTPS.
- **Vantagens:** Fácil de configurar, ideal para iniciantes.
- **Desvantagens:** Pode exigir digitar suas credenciais GitHub com frequência, a menos que você use um gerenciador de credenciais.

### Nota**!**

Quando você trabalha em um projeto e desejar encaminhar as mudanças dele  para o repositório remoto, como **GitHub,** com o uso do HTTPS você sempre precisará inerir as suas credenciais, que são login e senha. As vezes é muito trabalhoso efetuar esse procedimento. para isso existem outras possibilidades.

A autenticação por token: Trata-se de uma autorização de acesso por código gerado no GitHub. Esse tipo de autorização pode ser feito de forma personalizada no próprio site…

Exemplo:

1 - Clique na sua foto que está localizada no canto superior esquerdo da página do seu `GitHub`.

2 - Selecione a opção `Settings`.

3 - Selecione agora a opção **`<>Developer settings`**.

4 - Clique `Personal acess tokens` vai abrir dois tipos de tokens o modo `Fine-grained tokens`   e o `Tokens(classic)`
5 - Primeiramente eu vou clicar na opção `Tokens(classic)`. 

6 - No botão da sua direita clique em **`Generate new token`** que vai abrir mais duas opções **`generate new Token(beta)`** e **`Generate new token(classic)` clique na opção `Generate new token(classic)` .**

7 - Com esse token você pode dar permissões específicas para determinado usuário. Não liberando determinadas ações não colocando em risco a performance do seu projeto.

**Gerando o token opção classic:**

![Untitled](./imgs/Untitled%204.png)

**Veja o que eu falei:**

![Untitled](./imgs/Untitled%205.png)

Nessa opção você pode gerar um token pra você com todas as permissões ou para o usuários limitando as permissões e ainda por cima colocar um prazo de validade para essa chave de acesso.  

Caso esteja aprendendo a usar a ferramenta, marque todas as opções. Coloque sempre um data de expiração por motivos de segurança muito cuidado com isso.

8 - depois de tudo efetuado, agora é só gerar o token de acesso:

![Untitled](./imgs/Untitled%206.png)

9 - Depois de clicado é só copiar o token de acesso e ir para o abraço!

![Untitled](./imgs/Untitled%207.png)

10 - Copia esse código e já deixa em um bloco de anotações. E nem adianta pegar esse código, porque ele já vai ser deletado, meu nobre!

11 - Agora é hora de autenticar :
11.1 - No terminal use o comando:  **`gh auth login`**

11.2 - Escolha a opção : **`GitHub.com`**

11.3 - Escolha a opção **`HTTPS`**

11.4 - Digite `yes`

11.5 -  escolha a opção  **`Paste an authentication token`**  usando o direcional **`⭡⭣⭠⭢`** do seu teclado.

![Untitled](./imgs/Untitled%208.png)

12.6 - Depois de selecionado… é só finalmente inserir o seu token:

![Untitled](./imgs/Untitled%209.png)

### `Pronto! configuração concluida com sucesso.`

### Comando de clonagem HTTPS:

Comando de clonagem do repositório HTTP:
Na aba HTTPS copie o link abaixo:

![Untitled](./imgs/Untitled%203.png)

No seu repositório local → Em qualquer lugar nas pastas de seu computador, de preferência nas pastas onde você costuma guardar projetos de estudo ou até mesmo projetos de trabalho…
Use o comando abaixo para clonar do repositório remoto.

### `git clone https://github.com/usuario/repo.git`

### **Nota!**
**Se você configurou o Token de acesso não pedirá autenticação. Caso contrário é só colocar usuário e senha do github.**

### `Finalmente!!` Você clonou do repositório remoto.

### `No meu PC roda 1:`  Veja a prova do projeto clonado no PC:

![Untitled](./imgs/Untitled%2010.png)

### 2º Formato - SSH

- **O que é:** Um método de clonagem usando o protocolo SSH.
- **Vantagens:** Mais seguro e conveniente, especialmente para acessos frequentes, porque usa chaves SSH para autenticação em vez de senhas.
- **Desvantagens:** Requer configuração inicial para gerar e adicionar chaves SSH à sua conta GitHub.

Comando de clonagem SSH:

![Untitled](./imgs/Untitled%2011.png)

## **`Atenção!`**

Antes de fazer isso Você precisa configurar a chave ssh no seu PC seja ele Windows ou Linux.

**Esse eu uso com frequência:**

### Configurando chave de acesso ssh sem a necessidade de instalar o GitHub Cli:

### Windows:

**Siga os comandos:**

1 -  `ssh-keygen -t ed25519 -C "coloca o seu email do GitHub"`

2 -   **`vai pedir para cadastrar uma senha, já que esse é o meu computador pessoa eu costumo não colocar senha, mas isso fica ao seu critério, caso não queira colocar senha digite [Enter].`** 

3 -  **`vai pedir para confirmar a sua senha, caso não tenha inserido senha é só apertar [Enter]
novamente.`**

4  - **Muita atenção**, esse nome que esta em azul substitua pelo seu usuário Windows para poder acessar seu repositório se não souber seu nome de usuário é só dar o comando: 

**`echo $env:USERNAME` → esse comando retornará o seu nome de usuário no PowerShell.**

Ou:
`whoami` - > **esse comando retornará o seu nome de usuário no `PowerShell` ou `GitBash`**

### Usando terminal PowerShell:

Seu git Gerou uma chave SSH no Diretório: **`C:\Users\seuUsuario\.ssh`** basta apenas dar o comando **`cd C:\Users\seuUsuario\.ssh` ,** o comando **`cd`** significa **'*change directory’***  é ******como se você tivesse clicando e acessando o conteúdo em uma pasta no sua interface seja Windows, macOs ou Ubuntu. depois de executar esse comando você estará dentro da pasta **`C:\Users\seuUsuario\.ssh`**

### Usando terminal GitBash:

Seu git Gerou uma chave SSH no Diretório:   `c/Users/**seuUsuario**/.ssh`   ****basta apenas dar o comando **`cd** c/Users/**seuUsuario**/.ssh` **,** o comando **`cd`** significa **'*change directory’***  é ******como se você tivesse clicando e acessando o conteúdo em uma pasta no sua interface seja ***Windows*, *macOs* ou *Ubuntu***. depois de executar esse comando você estará dentro da pasta **`C\Users\seuUsuario\.ssh`**

5 -  Com o comando **`ls`** ou **`dir`**, dependendo do **terminal, o terminal listará arquivos e pastas dentro do repositório:**

No PowerShell:

![Untitled](./imgs/Untitled%2012.png)

No GitBash:

![Untitled](./imgs/Untitled%2013.png)

6 - Dentro dessa pasta existe o arquivo **`id_ed25519.pub`** 

O arquivo `id_ed25519.pub` →  é uma chave pública SSH, que faz parte de um par de chaves SSH utilizadas para autenticação segura com servidores e serviços como GitHub.

Efetua o comando `cat id_ed25519.pub` é usado para exibir o conteúdo do arquivo `id_ed25519.pub` no terminal. Este arquivo contém a chave pública SSH

**copie** a chave SSG que estará desse maneira:

```bash
ssh-código da chave **seuEmail@email.com**
```

Copia todo o conteúdo da chave.

7 - Abra o GitHub

8 - clique na sua foto 

9 - Settings

10 - SSG and GPG keys

11 - Na  Aba:

![Untitled](./imgs/Untitled%2014.png)

clique em new SSH Key

12 - escolha um título qualquer para a sua chave. no meu eu coloquei  `Win` e depois cole a sua chave SSH dentro input de texto de nome `Key`.
13 - Por fim clique em **`AddSSH key`** .

14 -  Sua senha do Git e confirme.

### `Pronto!`

Agora volte para o seu terminal e execute o comando: **`ssh -T [git@github.com](mailto:git@github.com)`**

O terminal retornará a seguinte mensagem:

**`Hi FulanoDeTal! You've successfully authenticated, but GitHub does not provide shell access.`**

### Linux:

 **Só para distribuição Linux Linux!** → **Debian, Ubuntu Linux, Raspberry Pi OS (apt)**

**Instale o cliente SSH:**
 **`sudo apt install openssh-client`

Siga os comandos:**

1 -  `$ ssh-keygen -t ed25519 -C "coloca teu email do gitHub"`

2 -  **`vai pedir para cadastrar uma senha, já que esse é o meu computador pessoa eu costumo não colocar senha, mas isso fica ao seu critério, caso não queira colocar senha digite [Enter].`** 

3 -   **`vai pedir para confirmar a sua senha, caso não tenha inserido senha é só apertar [Enter]
novamente.`**

4  - `$ cd ~/.ssh`

5 -  `$ ls`
retorno do comando `l**s**`: **`id_ed25519  id_ed25519.pub`**

6 -  $ `cat id_ed25519.pub`
Copia todo o conteúdo da sua chave  entra no GitHub  efetuando todo o caminho informado no exemplo do Windows  e cola a chave.

### `Pronto!`

Agora volte para o seu terminal e execute o comando: **`ssh -T [git@github.com](mailto:git@github.com)`**

O terminal retornará a seguinte mensagem:

**`Hi FulanoDeTal! You've successfully authenticated, but GitHub does not provide shell access.`**

### Comando de clonagem SSH:

Comando de clonagem do repositório HTTP:
Na aba SSH copie o link abaixo:

![Untitled](./imgs/Untitled%2015.png)

No seu repositório local → Em qualquer lugar nas pastas de seu computador, de preferência nas pastas onde você costuma guardar projetos de estudo ou até mesmo projetos de trabalho…
Use o comando abaixo para clonar do repositório remoto.

### `git@github.com:braswilliam/gitflowtop.git`

### 3º Formato - Github CLI

**A forma mais prática e usada para quem que rapidez nas configurações e segurança:**

O GitHub CLI é uma ferramenta poderosa para desenvolvedores que trabalham com GitHub, proporcionando uma forma eficiente de interagir com repositórios e outros recursos do GitHub diretamente do terminal. Ele melhora a produtividade, permitindo que operações comuns e complexas sejam executadas rapidamente sem a necessidade de mudar para a interface web.

Configuração na sua máquina:

1 - No terminal use o comando:  **`gh auth login`**

2 - Escolha a opção : **`GitHub.com`**

3 - Escolha a opção **`HTTPS` ou `SSH`**

4 - Digite `yes`

5 -  escolha a opção  **`Login with a web browser`**  usando o direcional **`⭡⭣⭠⭢`** do seu teclado.

6 - Assim que clicado em **`Login with a web browser`** seu terminal vai gerar um código, ex: `First copy your one-time code: SEU-CODIGO` ****copia esse código e aperte a tecla **`[Enter]`.** Automaticamente vai abrir o seu navegador com a página de autenticação do GitHub exemplo:

![Untitled](./imgs/Untitled%2016.png)

Cole o código aqui dentro 

7 - Por fim autorize o uso do GitHub Cli a ter acesso ao seu usuário.
8 - insira a sua senha do github e sucesso.

![Untitled](./imgs/Untitled%2017.png)

### `Pronto!`

Seu terminal o notificará com a seguinte informação:
**`! You were already logged in to this account`**

### Comando de clonagem GitHub Cli:

Comando de clonagem do repositório usando GitHub Cli:
Na aba GitHub Cli copie o link abaixo:

![Untitled](./imgs/Untitled%2018.png)

No seu repositório local → Em qualquer lugar nas pastas de seu computador, de preferência nas pastas onde você costuma guardar projetos de estudo ou até mesmo projetos de trabalho…
Use o comando abaixo para clonar do repositório remoto.

### `gh repo clone braswilliam/gitflowtop`
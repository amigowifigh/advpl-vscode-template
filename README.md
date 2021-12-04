# Advpl Language Support

Bem vindo a extensão para desenvolvimento de Advpl no visual code. [VsCode MarketPlace](https://marketplace.visualstudio.com/items?itemName=KillerAll.advpl-vscode)

Essa extensão adiciona suporte a edição, compilação e debugging de ADVPL no Visual Code.

Caso você encontre algum problema, por favor abra uma issue no [GitHub](https://github.com/killerall/advpl-vscode/issues). 

> Atenção! Essa extensão não é desenvolvida ou suportada pela TOTVS. Utilize por sua conta e risco.

> Existe um migrador de projetos antigos do IDE Totvs (.PRJ) que pode se encontrado [aqui](https://github.com/killerall/advpl-vscode/blob/master/TDSProjectToVscode.jar).

> Caso esteje com problema para debugar, apos a atualização do VSCODE 1.10 apague o launch.json e o recrie dando F5.


## Features

Essa extensão possui as seguintes features implementadas:

* Syntax highlighting
* Compilação de fonte
* Chave de Compilação
* Debug single Thread e Multi Thread   
* Compilação de multiplos fontes
* Geração e aplicação de Path [Wiki](https://github.com/killerall/advpl-vscode/wiki/Trabalhando-com-Patchs)
* Exclusão de fontes do RPO
* Lista dos fontes/resources do rpo
* Geração Cliente WS Protheus
* Geração de PPO do fonte(Para fazer isso utilize CTRL+SHIFT+F9)
* Mac OSX (Configuração a baixo)

As próximas planejadas são:

* Auto complete
* Linux


## Requisitos para utilização

Para utilizar os recursos de compilação e debug é necessário que o AppServer esteja na build 131227A ou superior, tendo essa versão de binário tanto o Protheus 11 e 12 são suportados.
Essa extensão ainda não está disponível no Linux. 

## Configurações da extensão

Essa extensão contribui com as seguintes configurações.

* `advpl.smartClientPath`: Caminho completo para o diretório do smartclient. Esse diretório precisa possuir o apppre.exe e o smartclient.exe. 

Exemplo: `C:\\Protheus\\smartclient\\`
No caso de OSX:
Exemplo: `/Applications/`

> `advpl.environments` : Array com os ambientes configurados

> Cada ambiente deve especificar:   
> * `name` : Nome para o ambiente, caso não informado sera utilizado o enviroment para a seleção
> * `environment`: Nome do ambiente que será feito o debug e a compilação
> * `serverVersion`.": Versão do server - Atualmente suporta o 131227A , 170117A
> * `server`: Server IP, Padrão: localhost                  
> * `port` : Porta do servidor
> * `user`: Nome do usuário para se conectar no Protheus, se não informado utiliza "Admin"
> * `passwordCipher` : Senha criptografada do usuário de login no Protheus, para gerá-la utilize o comando CipherPassword
> * `includeList`: Lista de diretórios separado por ponto-e-vírugla. Exemplo: `C:\\Protheus\\include\\;C:\\Protheus\\include_2\\`
> * `language`: Língua do repositório, se não informado será português, valores permitidos: PORTUGUESE, ENGLISH, SPANISH
> * `rpoType`: Tipo do RPO, se não informado será  "TOP", valores permitidos: TOP, CTREE, DBF
> 

* `advpl.selectedEnvironment` Ambiente atualmente selecionado

* `advpl.startProgram`: Módulo ou função que será sugerido no launch do Debug
* `advpl.compileFolderRegex`: Regex que ira validar se na compilação de folders, o arquivo irá ser compilado ou não.

As variáveis abaixo devem ser preenchidas caso você tenha uma senha de compilação.
Caso você deseje pegar o ID utilizado pelo VSCODE para gerar uma nova chave, veja o comando getAuthorizationId 
* `advpl.authorization_generation`: Data de geração da chave no formato yyyyMMdd
* `advpl.authorization_validation`: Data de validade da chave no formato yyyyMMdd
* `advpl.authorization_permission`: 1 - Para permitir substituir fontes TOTVS, 0 - para não pemitir
* `advpl.authorization_code`: Chave de Autorização

Configuração de Patchs
* `advpl.pathPatchBuild` :  Patch do cliente que deve existir para geracao de patchs. Caso o arquivo ja exista, será sobrescrito.

Debug
* `advpl.debug_multiThread` : Caso seja colocado com true, habilita o debug multi Thread.
* `advpl.debug_ignoreSourceNotFound` : Ignorar os fontes não encotrados no debug.
* `advpl.debug_showTables` : Mostra as tabelas abertas.
* `advpl.debug_showPrivates` : Mostra as variaveis Privates.
* `advpl.debug_showPublic` : Mostra as variaveis Publicas.
* `advpl.debug_showStatics` : Mostra as variaveis Estaticas .

Compilação
* `advpl.compile_force_recompile` : Caso esteja como true, força recompilar os fontes mesmo que não tiveram alteração.
* `advpl.compile_threads` : Numero de Threads que serão utilizadas quando se compila uma Folder, o padrão é 4. Aumentar para mais de 4 Threads, fara o uso de CPU ficar bem alto

Log 
* `advpl.logger`: Crie um log da execução

## Configurações

Veja nossa [Wiki](https://github.com/killerall/advpl-vscode/wiki/Configura%C3%A7%C3%A3o)

## Teclas de Atalho padrões
* F5  - Inicia o Debug
* CTRL + F5  - Inicia o SmartClient sem debugar
* CTRL + F9 - Compila o fonte atual
* CTRL + SHIFT +  F9 - Compila o fonte atual
* CTRL + F11 - Executa o smartClient sem configuração e mostrando a tela de parametros

# No Debug
Utilizada as teclas padrões do VsCode
* F5 - Run/Contiue
* F10 - Step Into
* F11 - Step Over

## Para versão MAC
Efetuar o download do [executavel](https://github.com/killerall/advpl-vscode/raw/master/bin/AdvplDebugBridgeMac)
Copiar o mesmo para a pasta:
~/.vscode/extensions/KillerAll.advpl-vscode-x.x.x/bin
Dar acesso a execução no arquivo.

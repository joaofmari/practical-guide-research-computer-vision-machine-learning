# practical-guide-research-computer-vision-machine-learning

# GUIA PRÁTICO PARA PESQUISA CIENTÍFICA EM VISÃO COMPUTACIONAL E MACHINE LEARNING

João Fernando Mari - *[joaofmari.github.io](joaofmari.github.io)*


## AMBIENTE DE DESENVOLVIMENTO

###  Instalando o Python

* Baixar o instalador do Python a partir do site “python.org”.
* Ir na aba Downloads e baixar o instalador adequado ao seu Sistema Operacional “python-3.10.7-amd64.exe”.
* Escolha preferencialmente a versão mais recente.
* No caso deste exemplo, o Sistema Operacional é o Windows 10 e a última versão do Python é a 3.10.
* Foi realizado o download do instalador “python-3.10.7-amd64.exe”

* Duplo clique no arquivo baixado para iniciar a instalação. O processo é bem intuitivo: next, next, finish…
* Porém, existe uma forma mais prática e eficiente de instalar um ecossistema Python.
* Instalando alguma distribuição Python… 

### O Anaconda Python

* Para experimentos envolvendo computação científica com Python é recomendado instalar distribuições Python ao invés de instalar o interpretador Python diretamente.
* A distribuição Python mais difundida atualmente é o Anaconda Python. 
    * Possui versões para Windows, Linux e iOS.
    * Possui o “conda”, um gerenciador de pacotes e de ambientes próprio que facilita muito a realização de várias tarefas.
* Baixe o instalador do Anaconda Python a partir do site “anaconda.org”, na aba “Download Anaconda”:
    * Selecione a versão adequada para o seu Sistema Operacional e a versão padrão do interpretador Python.
    * No meu caso, o SO é o Windows 10 e a última versão do Python é a 3.9.
    * Foi baixado o instalador “Anaconda3-2022.05-Windows-x86_64.exe”.

### Instalando o Anaconda Python

Duplo clique no arquivo baixado para iniciar a instalação. 
O processo é bem intuitivo: next, next, finish…

### O Anaconda Prompt

ara acessar o interpretador Python do Anaconda, acesse o “Anaconda Prompt” ou o “Anaconda PowerShell Prompt”. 
É um prompt de comando (terminal) com acesso ao interpretador Python.
Antes do prompt de comando é possível visualizar um nome entre parênteses. Este é o nome do ambiente que está ativo.
Ao iniciar um novo prompt, o ambiente ativo é o ambiente padrão do Anaconda, que pode ser identificado pelo nome (base).
No ambiente (base) é possível acessar o interpretador Python (mesma versão da distribuição Anaconda que você instalou) e importar as bibliotecas fornecidas com a distribuição Anaconda.

### Console interativo do Python
* É possível utilizar o Python de forma interativa, executando instrução após instrução conforme são digitadas.
* Esta forma de utilização é adequada apenas para pequenos procedimentos e testes, pois para executar um mesmo procedimento novamente é preciso digitar as instruções novamente.
* Para acessar o console interativo digitando “python” no prompt de comando.
```
(base) C:\Users\[user_name]> python
```
O prompt do console interativo é identificado pelo símbolo “>>>”
```
>>>
```
Para sair do console interativo:
```
>>> exit()
```
* Outra forma de acessar o Python de forma interativa é por meio do iPython.
* Fornece acesso interativo ao interpretador do Python, porém com alguns recursos mais avançados, como marcação de sintaxe, por exemplo.
* Para acessar o console interativo digitando “ipython” no prompt de comando.
```
(base) C:\Users\[user_name]> ipython
```
O prompt do console do iPython é numerado “In[N]: ”, em que N é o número da linha.
```
In [1]: 
```

### Ambientes conda
* Uma boa prática para desenvolvimento de projetos usando Python consiste em construir e utilizar ambientes virtuais.
* É possível criar ambientes virtuais com interpretadores Python, bibliotecas e módulos independentes.
* Para construir um novo ambiente vamos utilizar o “conda”, fornecido juntamente com a distribuição Anaconda
```
(base) C:\Users\[user_name]> conda create -n [nome_do_ambiente] python=[versao_interpretador]
```
Exemplo:
```
(base) C:\Users\[user_name]> conda create -n env-teste python=3.7
```
No exemplo anterior, criamos um ambiente virtual conda com o nome env-teste e o interpretador Python deste ambiente possui a versão 3.7
    * Note que cada ambiente pode ter uma versão diferente do interpretador Python, completamente independente dos outros ambientes.
* Para utilizar o ambiente conda é necessário ativá-lo:
```
(base) C:\Users\[user_name]> conda activate [nome_do_ambiente]
```
*Exemplo:
```
(base) C:\Users\[user_name]> conda activate env-teste
```
* Após ativar o ambiente, o nome deste aparecerá entre parênteses antes do prompt de comando.
```
(env-test) C:\Users\[user_name]> 
```
* Observação: O Python fornece alguns pacotes para criação de ambientes virtuais independentes além do conda.
    * venv:
        * Presente na biblioteca padrão do Python
    * virtualenv
        * https://virtualenv.pypa.io/en/latest/
    * Entre outros…
* Opinião pessoal: Eu recomendo utilizar o conda para esta tarefa, pois é mais fácil e eficiente.
* Para atualizar o conda para a versão mas recente:
```
$ conda update -n base -c defaults conda
```

### Instalação de pacotes e módulos externos

* O conda fornece mecanismos para instalação e gerenciamento de módulos, pacotes e bibliotecas.
* Para instalar uma nova biblioteca no seu ambiente virtual conda:
```
$ conda install [nome_do_pacote]
```
* Ao omitir a versão do módulo, sempre será instalada a última versão compatível disponível. Para instalar uma versão específica:
```
$ conda install [nome_do_pacote]=[versao_do_pacote]
```
* É possível instalar vários módulos em um único comando conda:
```
$ conda install [nome_do_pacote_1] [nome_do_pacote_2] … [nome_do_pacote_N]
```
* Exemplos: 
    * Instalando o NumPy usando o conda
```
$ conda install numpy
```
* Instalando uma versão anterior do NumPy. Nesse caso, a versão 1.20.0 de 30 de janeiro de 2021:
```
$ conda install numpy=1.20.0
```
* Instalando o Scikit-learn e o Matplotlib:
```
$ conda install scikit-learn matplotlib
```
* Instalando o Scikit-learn, o Scikit-image (versão 0.20.4) e o Matplotlib:
```
$ conda install scikit-learn scikit-image=0.20.4 matplotlib
```

### O pip
* O Python fornece um gerenciador de pacotes nativo do Python (a partir do Python 3.4) independente da distribuição Anaconda, denominado pip.
* Para instalar pacotes usando o pip

$ pip install [nome_pacote]

Para instalar a versão anterior de um módulo como o pip:

$ pip install [nome_pacote]==[versao]

Também é possível  instalar vários pacotes com um comando único:

$ pip install [nome_pacote_1] [nome_pacote_2] … [nome_pacote_N]

As versões dos pacotes podem divergir entre o pip e o conda.
Alguns pacotes não disponíveis no conda, podem ser encontrados no pip.
Não existe restrição em instalar pacotes via pip e conda no mesmo ambiente.
Se tiver dúvidas sobre qual gerenciador usar, consulte a documentação oficial do pacote/biblioteca.

### Escrevendo programas (arquivos .py)

* Para escrever programas em Python e poder executá-los a qualquer momento, é necessário escrever os seus programas em arquivos com extensão .py.
* Para isso utilize qualquer IDE ou editor de textos com marcação de sintaxe para Python.
    * Visual Code
    * Notepad++
    * Vi/Vim
    * …
* Pessoalmente, eu sugiro utilizar o Visual Studio Code.

* Após escrever o script/programa em Python, salvar o arquivo com extensão .py.

* Para executá-lo, abra um Anaconda Prompt, ative o ambiente adequado e digite python, seguido no nome do programa. 
* É possível passar argumentos de linha de comando caso o programa requeira.


### Jupyter notebook
* Uma excelente ferramenta de desenvolvimento para dados.
Reúne o melhor de dois mundos: a interatividade do console iPython com a persistência de um programa .py.
* Para instalar o Jupyter Notebook:
```
$ pip install notebook
```
Para executar um servidor do Jupyter Notebook digite:
```
$ jupyter notebook
```
* O servidor terá a seguinte URL padrão: http://localhost:8888
* O Notebook irá abrir no seu browser padrão.

* Para criar um novo Notebook
    * New >> Python 3

* Você escreve o seu código em um notebook, que roda no seu browser.
* Um notebook é armazenado em um arquivo com extensão .ipynb.
* O notebook é dividido em células.
    * Cada célula pode conter código Python, ou texto escrito em linguagem de marcação Markdown.
    * Julia e R também são linguagens suportadas pelo Jupyter notebook.
        * Jupyter = JUlia, PYThon e R
    * Cada célula pode ser executada individualmente.
    * Os resultados da execução de cada célula são visualizados após a célula, incluindo imagens, gráficos, etc.
    * Facilita o desenvolvimento de aplicações que envolvem experimentação com dados.

    * No pop-up presente na barra de ferramentas, é possível alternar a função da célula atual de Code para Markdown.
    * Para saber mais sobre a linguagem de marcação Markdown:
        * https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown 
    * Para executar o conteúdo de uma célula: CTRL+ENTER
    * Para executar uma célula e criar uma nova célula abaixo: ALT+ENTER

### Jupyter Lab

* Jupyter Lab é a nova geração do Jupyter Notebook
    * Para instalar: 
```
$ conda install -c conda-forge jupyterlab
```
* Execute digitando:
```
$ jupyter lab
```
A utilização é muito parecida com o Jupyter Notebook

### Jupyter Notebook pelo VS Code



### Google Colab

* O Google fornece um ambiente de execução na nuvem.
* O Google Colab permite rodar um notebook em um ambiente de execução de alto desempenho em nuvem com acesso a GPU.
* Utilize uma conta Google e acesse:
    * https://colab.research.google.com/ 
* O acesso pode ser realizado pelo Google Drive, uma vez que os notebooks ficam armazenados nele.
* https://drive.google.com 

* Para criar um novo notebook no Google Colab, clique no botão Novo (ou clique com o botão direito) >> Mais, Google Colaboratory.

* Para habilitar o acesso à GPU, clicar em Editar >> Configurações e notebook

* Em Acelerador de hardware, escolha GPU e clique em salvar.

* Para testar se o acesso à GPU está funcionando 
```
!nvidia-smi
```

* Os dados de entrada e os resultados dos experimentos executados no Colab são armazenados no Google Drive. 
* Para montar o Google Drive no seu notebook:

< COMPLETAR >

Git e GitHub
Criar uma conta no GitHub (ou no GitLab).
https://github.com/

Instalar o git:
No Windows:
https://gitforwindows.org/
No Linux (Ubuntu):
$ sudo apt install git

Para clonar um repositório na sua máquina:
$ git clone <URL>
Para atualizar o conteúdo na máquina local como o conteúdo remoto
$ git pull
Para subir as alterações locais no repositório remoto
$ git add .
$ git commit -m “comentário”
$ git push -u origin main
Caso não queira que alguns arquivos ou pastas não sejam enviados para o repositório remoto, incluir os caminhos dos arquivos ou pastas no arquivo .gitignore


## ACESSANDO SERVIDORES COM GPU (UFV-CRP)

Transferindo arquivos por FTP - FileZilla

* O FileZilla é um cliente FTP que permite transferência de arquivos entre máquinas remotas.
* O FileZilla é útil para transferir arquivos para o servidor e também para transferir arquivos do servidor para a sua máquina local.
* Baixar o cliente FileZilla a partir do site:
    * https://filezilla-project.org/ 
* Gerenciando os dados em experimentos remotos com FileZilla:
* Transfira o conjunto de dados para o servidor usando o FileZilla
* Desenvolva e teste o seu código na máquina local usando a IDE de sua preferência
* Transfira o seu código para a servidor remoto usando o FileZilla
* Execute o seu código no servidor com GPU
* Ative (ou crie e ativo) o ambiente virtual conda no servidor
* Execute o código. Use nohup para execuções longas
* Transfira os resultados do servidor para a máquina local usando o FileZilla

### Acesso remoto por SSH

Os servidores equipados com GPUs permitem acesso por SSH.
Caso o usuário esteja fora da rede da UFV, é necessário estabelecer uma conexão por VPN.
Para isso, baixar o cliente VPN Open-VPN específico para a rede da UFV a partir do site:
https://vpn.ufvnet.ufv.br/windows.html
Na mesma página estão as instruções para instalação e configuração do cliente VPN.
Download e instruções para outros SOs em: https://vpn.ufvnet.ufv.br/ 
Para acessar um dos servidores é necessário possuir uma conta de usuário (Linux) naquela máquina e conhecer o IP da máquina.
Tendo essas informações em mãos, o acesso por SSH é realizado da seguinte forma:
$ ssh [nome_usuario]@[IP]
$ ssh joao@200.11.22.33

### Executando experimentos remotamente - nohup e tail

* Se durante a execução de uma programa remotamente via SSH a conexão for terminada, o processo também é interrompido 
* Para que o experimento não seja interrompido em uma seção remota por ssh, utilizamos o programa nohup.
* Dessa forma, o programa continua executando em segundo plano, mesmo que a conexão via SSH seja interrompida.
* Para executar um programa Python com o nohup faça:
```
$ nohup python [nome_do_programa].py &
$ nohup python my_prog_01.py &
```
* Caso o programa receba argumentos de linha de comando
```
$ nohup python [nome_do_programa].py [arg1] [arg2] … [argN] &
$ nohup python my_prog_01.py 16 0.01 sgd &
```
* Após executar um programa usando o nohup, será mostrado o número de processo do seu programa. Anote este número.
* Caso ocorra algum erro no seu programa e você precise terminá-lo, precisará do ID do processo para isso:
```
$ kill -9 <ID do processo>
```
* Ao executar um programa usando nohup, este irá rodar em segundo plano. As mensagens não serão mostradas no terminal.
* As mensagens para a saída padrão irão para um arquivo de texto chamado “nohup.out”
* Para visualizar as mensagens do programa, utilize o comando do Linux “tail”.
```
$ tail -f nohup.out
```
* Mas antes é preciso retornar para o prompt de comando usando CTRL+C.
* O “tail” mostra as últimas linhas de um arquivo de texto.
* Dessa forma é possível acompanhar a execução do seu programa.
* Você pode abandonar o tail a qualquer momento sem afetar a execução do seu programa. O tail apenas mostra o conteúdo do arquivo “nohup.out”
* Para finalizar o seu programa, use o “kill” e o ID do processo, como mostrado acima.
* Caso queira acessar o uso da GPU durante a execução do seu programa, siga as instruções na próxima seção.

### Executando o Jupyter remotamente

* Não é adequado para experimentos muito longos. Pois a queda da conexão pode interromper o experimento.
* Para experimentos longos execute o experimento via linha de comando e nohup.
* Ative o ambiente conda no terminal remoto (servidor)
* Consulte a seção “Acesso remoto por SSH”.

$ conda activate <nome_ambiente>

Inicie o servidor de Notebook no terminal remoto (servidor)

$ jupyter notebook --no-browser

Anote o número da porta que foi atribuída: <PORT>
Para rodar o Jupyter Lab ao invés do Notebook

$ jupyter lab --no-browser

.Na sua máquina local, digite:

$ ssh -L 8080:localhost:<PORT> <REMOTE_USER>@<REMOTE_HOST>
<PORT>: é o número da porta atribuído no terminal remoto
<REMOTE_USER>: é o seu nome de usuário
<REMOTE_HOST>: é o IP do terminal remoto.

Abrir o browser na máquina local:

http://localhost:8080

* Será solicitado um token que pode ser encontrado no terminal que você abriu na máquina remota.
* Pronto. Agora o notebook aberto no seu browser está rodando na máquina remota.
* Lembrando que se a conexão for interrompida, a execução do experimento também será.

### Executando o Jupyter remotamente usando VS Code

< COMPLETAR >

### Verificando o status da GPU

Antes de iniciar o experimento é possível verificar as configurações da GPU:
Modelo da GPU;
Versão do driver;
Memória disponível;
Processos que estão acessando ao GPU;
Etc.
Para isso digitar:
```
(conda-env)$ nvidia-smi
```
Durante a execução dos experimentos, desde que iniciado usando o nohup, é possível acompanhar a utilização da GPU usando a mesma ferramenta “nvidia-smi” interativamente.
Para isso, digite:
```
(conda-env)$ watch nvidia-smi
```

## Outras dicas

* Salve TODOS os resultados dos seus experimentos, da forma mais organizada possível.
* Salve as imagens processadas
* Salve os gráficos e plotagens em arquivos de imagens.
* Salve os resultados estruturados em arquivos .CSV
* Salve os valores em cada linha separados por vírgulas, ou ponto e vírgula, ou tabulações ('\t').
* Separe as linhas usando ‘\n’
* Arquivos .CSV podem ser abertos facilmente em qualquer aplicativo de planilha eletrônica (MS Excel, Open Office Calc, Google Sheets), assim como exportado para os formatos nativos destes aplicativos.
* Arquivos CSV também pode ser inspecionados em editores de texto e facilmente lidos por scripts/programas Python ou escritos em outras

## Referências

* www.overleaf.com 
* https://filezilla-project.org/ 
* https://vpn.ufvnet.ufv.br/windows.html
* https://vpn.ufvnet.ufv.br/ 
* https://docs.anaconda.com/anaconda/user-guide/tasks/remote-jupyter-notebook/
* https://ipython-books.github.io/36-introducing-jupyterlab/

## Contato


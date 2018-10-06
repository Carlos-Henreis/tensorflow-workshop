# Workshop Tensorflow


## O que esperar:

Este workshop é destinado a um público que é novo com Tensorflow com um conhecimento muito básico em Machine Learning. Faz parte do Hackathon Varejo 4.0 2018 realizado na Universidade Federal de Itajubá - UNIFEI. O desafio deste Hackathon é ensinar a aplicar técnicas de inteligência artificial e programação em Python para resolver problemas do varejo 4.0. No final uma empresa propõe problemas para serem resolvidos em grupos que competem pela melhor solução.  

### Agenda:

**Parte 1 - Introdução ao TensorFlow (4 horas):**

* Introdução/instalação
* Como funciona o TensorFlow
* Componentes Básicos
* Declarando Tensores: Usando espaços reservados (placeholders) e variáveis
* Trabalhando com Matrizes
* Grafos e Sessões
* x Declarando Operações
* Implementando Funções de Ativação
* Trabalhando com entradas de dados
* Exercícios

**Parte 2 - TensorFlow Detalhado (4 horas)** / Entendendo como melhor organizar um código TensorFlow:

* Escopos de Nomes e modularidade no Código
* Visualização com tensorboard
* Agora sim Tensoflow e ML <3
* Usando o TensorFlow em outra perspectiva (trabalhando com APIs de alto nível)
* Usando alguns Modelos interessantes)
* Exercícios
* Expor os problemas propostos pela IWS

# Notebooks sobre TensorFlow

Simplesmente abra os Notebooks [Jupyter](http://jupyter.org/) nos quais você está interessado:


* Usando o [github.com's notebook viewer](https://github.com/Carlos-Henreis/tensorflow-workshop/blob/master/index.ipynb) também funciona, mas é mais lento e as fórmulas matemáticas não são exibidas corretamente :(,
* Ou clone este repositório e execute o Jupyter localmente. Esta opção permite brincar com o código. Neste caso, siga as instruções de instalação abaixo.

## Instalação

Primeiro, você precisará instalar o [git](https://git-scm.com/), se você não o tiver ainda.

Em seguida, clone este repositório abrindo um terminal e digitando os seguintes comandos:

    $ cd $HOME  # ou qualquer outro diretório de desenvolvimento que você preferir
    $ git clone https://github.com/Carlos-Henreis/tensorflow-workshop.git
    $ cd tensorflow-workshop

Se você não deseja instalar o git, você pode fazer o download de [master.zip](https://github.com/Carlos-Henreis/tensorflow-workshop/archive/master.zip), descompactá-lo, renomear o diretório resultante para `tensorflow-workshop` e movê-lo para o diretório de desenvolvimento.

Se você estiver familiarizado com o Python e souber como instalar bibliotecas do Python, vá em frente e instale as bibliotecas listadas `requirements.txt` e salte para a seção [Iniciando o Jupyter](#iniciando-jupyter). Se você precisar de instruções detalhadas, por favor, continue a ler.

## Bibliotecas Python

Claro, você obviamente precisa do Python. O Python 2 já está pré-instalado na maioria dos sistemas hoje em dia, e às vezes até mesmo no Python 3. Você pode verificar qual(is) versão(ões) possui, digitando os seguintes comandos:

    $ python --version   # for Python 2
    $ python3 --version  # for Python 3

Qualquer versão do Python 3 deve estar bem, de preferência ≥3,5. Se você não tem o Python 3, eu recomendo instalá-lo (o Python ≥2.6 deve funcionar, mas ele está obsoleto, então o Python 3 é preferível). Para fazer isso, você tem várias opções: no Windows ou MacOSX, você pode simplesmente baixá-lo em [python.org](https://www.python.org/downloads/). No MacOSX, você pode alternativamente usar [MacPorts](https://www.macports.org/) or [Homebrew](https://brew.sh/). Se você estiver usando o Python 3.6 no MacOSX, será necessário executar o seguinte comando para instalar o pacote `certifi` pacote de certificados, pois o Python 3.6 no MacOSX não possui certificados para validar conexões SSL (veja esta [pergunta do StackOverflow](https://stackoverflow.com/questions/27835619/urllib-and-ssl-certificate-verify-failed-error)):

    $ /Applications/Python\ 3.6/Install\ Certificates.command

No Linux, a menos que você saiba o que está fazendo, você deve usar o sistema de pacotes do seu sistema. Por exemplo, no Debian ou no Ubuntu, digite:

    $ sudo apt-get update
    $ sudo apt-get install python3

Outra opção é baixar e instalar o [Anaconda](https://www.continuum.io/downloads). Este é um pacote que inclui o Python e muitas bibliotecas científicas. Você deve preferir a versão do Python 3.

Se você escolher usar o Anaconda, leia a próxima seção, ou então pule para a seção [Usando pip](#using-pip).

## Usando o Anaconda
Ao usar o Anaconda, você pode criar opcionalmente um ambiente Python isolado dedicado a este projeto. Isso é recomendado, pois permite ter um ambiente diferente para cada projeto (por exemplo, um para este projeto), com bibliotecas e versões de bibliotecas potencialmente diferentes:

    $ conda create -n wstensorflow python=3.5 anaconda
    $ source activate wstensorflow

Isso cria um novo ambiente chamado Python 3.5 wstensorflow(você pode alterar o nome se quiser) e o ativa. Este ambiente contém todas as bibliotecas científicas que acompanham o Anaconda. Isso inclui todas as bibliotecas que precisaremos (NumPy, Pandas, Jupyter e alguns outros), exceto o TensorFlow, então vamos instalá-lo:

    $ conda install -n wstensorflow -c conda-forge tensorflow

Isso instala a versão mais recente do TensorFlow disponível para o Anaconda (que normalmente não é a versão mais recente do TensorFlow) no ambiente `wstensorflow` (buscando-o no `conda-forge` repositório). Se você optou por não criar um ambiente wstensorflow, basta remover a opção `-n wstensorflow`.


Estás pronto! Em seguida, pule para a seção [Iniciando Jupyter](#iniciando-jupyter).

## Usando pip
Se você não está usando o Anaconda, você precisa instalar várias bibliotecas científicas do Python que são necessárias para este projeto, em particular o NumPy, Pandas, Jupyter e TensorFlow (e alguns outros). Para isso, você pode usar o sistema de empacotamento integrado do Python, pip, ou você pode preferir usar o sistema de empacotamento do próprio sistema (se disponível, por exemplo, no Linux ou no MacOSX ao usar MacPorts ou Homebrew). A vantagem de usar o pip é que é fácil criar vários ambientes Python isolados com diferentes bibliotecas e diferentes versões de bibliotecas (por exemplo, um ambiente para cada projeto). A vantagem de usar o sistema de pacotes do seu sistema é que há menos risco de haver conflitos entre as bibliotecas do Python e os outros pacotes do seu sistema. Como tenho muitos projetos com diferentes requisitos de biblioteca, Eu prefiro usar pip com ambientes isolados. Além disso, os pacotes pip geralmente são os mais recentes disponíveis, enquanto o Anaconda e os pacotes do sistema geralmente ficam um pouco atrasados.

Estes são os comandos que você precisa digitar em um terminal, se você quiser usar o pip para instalar as bibliotecas necessárias. Nota: em todos os comandos a seguir, se você escolher usar o Python 2 em vez do Python 3, deverá substituir `pip3` por `pip` e `python3` por `python`.

Use pip para instalar os pacotes python necessários. Se você não estiver usando o virtualenv, você deve adicionar a opção `--user` (alternativamente, você pode instalar as bibliotecas em todo o sistema, mas isso provavelmente exigirá direitos de administrador, por exemplo, usando em `sudo pip3` em vez de `pip3` no Linux).

    $ pip3 install --upgrade -r requirements.txt

Ótimo! Você está pronto, você só precisa começar o Jupyter agora.

## Iniciando Jupyter
Agora você pode iniciar o Jupyter, simplesmente digite:

    $ jupyter notebook

Isso deve abrir o seu navegador, e você deve ver a visão em árvore do Jupyter, com o conteúdo do diretório atual. Se o seu navegador não abrir automaticamente, visite [localhost:8888](http://localhost:8888/tree).

**Nota:** Se ainda estiver problemas com o Jupyter veja:
* https://datawookie.netlify.com/blog/2017/06/setting-up-jupyter-with-python-3-on-ubuntu/

* https://github.com/jupyter/notebook/issues/4050

Parabéns! Você está pronto para começarmos!

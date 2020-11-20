# Nossas boas-vindas

Este projeto foi desenvolvido por [Beatriz Souza da Silva](https://github.com/bia-souza), [Fadoa Glauss Vieira](https://github.com/fadoaglauss) e [Robert Cristiam Faustino de Souza](https://github.com/hobbitx) como parte da discplina de _Tópicos Especiais em Computação e Algoritmos: Algoritmos de Organização e Recuperação de Informação_ do Centro Federal de Educação Tecnológica de Minas Gerais (CEFET-MG). Seu objetivo é desenvolver uma **máquina de busca para a Wikipédia (em Português)**.

### Dependências
#### pickle
[pickle](https://docs.python.org/3/library/pickle.html) implementa protocolos binários para serialização e deserialização de objetos Python, assim a utilizamos no processo de ler e escrever os conteúdos indexados na memória secundária. 

Para instalar utilize:
```
pip install pickle
```
#### bs4

[bs4](https://www.crummy.com/software/BeautifulSoup/) é uma biblioteca para extrair dados de arquivos HTML e XML em árvore sintática, assim a utilizamos para extrair o conteúdo das páginas a serem indexadas.

Para instalar utilize:
```
pip install beautifulsoup4
```
#### nltk
[NLTK](https://www.nltk.org/) fornece interfaces de processamento de texto para classificação, tokenização, lematização, marcação, análise e raciocínio semântico, assim a utilizamos para identificação de *stopwords* no processo de *stemming*.

Para instalar utilize:
```
pip install nltk
```


## Índice

### Download
Para acessar o índice gerado na execução da Máquina de Busca, acesse o [link](https://drive.google.com/drive/folders/1kMQmPG75xclZ1djHPu-dFM3ZR24mZvIn?usp=sharing).

#### Visualização
Para visualizar o índice gerado na execução da Máquina de Busca, baixe o arquivo disponibilizado e salve-o na pasta principal desse programa. Após, instale a biblioteca `pickle` e utilize o código abaixo:
```
from index.indexer import *
from index.structure import *
import pickle

with open("index.idx", "rb") as idx_file:
    obj_index = FileIndex()
    t = obj_index.next_from_file(idx_file)

    while t != None:
        print(t)
        t = obj_index.next_from_file(idx_file)
```

## Discussão

#### Quais foram os principais desafios e soluções?

#### Qual é a vantagem/desvantagem das suas soluções sob as outras alternativas (por exemplo, uso do índice em memória principal vs. ocorrência de termos em memória secundária)? 

#### O que nós melhoramos no nosso código para diminuir o consumo de memória ou deixá-lo mais eficiente?


### Técnica de *stemming*
No contexto de Recuperação de Informação, *stemming* é o processo de reduzir as palavras flexionadas (ao derivadas) ao seu tronco [[Wik.]](https://pt.wikipedia.org/wiki/Stemiza%C3%A7%C3%A3o), para otimizar a consulta em máquinas de busca. Por exemplo, os tokens `observar`, `observadores`, `observasse`, `observou` e `observe` podem ser transformados para um mesmo *steam* `observ`.

Em nosso projeto, o processo de *stemming* consistiu em:
- utilização da biblioteca `BeautifulSoup` para extração de todo o texto da página indexada;
- substituição dos caracteres acentuados `aáéíóúâêôçãẽõü` por sua correspondência sem acento `aeiouaeocaeou`;
- substituição dos caracteres especiais `!?.:;,` por espaço;
- identificação das *stopwords* com a utilização da biblioteca de processamento de linguagem natural `nltk` para a língua portuguesa. Para mais informações acesse a [documentação oficial](http://www.nltk.org/howto/portuguese_en.html) para português.

## Suporte ou Contato
Você teve problema com o projeto? Entre em contato com o [suporte](mailto:fadoa.glauss@gmail.com) por e-mail.


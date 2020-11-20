# Seja Bem-Vindo

Este projeto foi desenvolvido por [Beatriz Souza da Silva](https://github.com/bia-souza), [Fadoa Glauss Vieira](https://github.com/fadoaglauss) e [Robert Cristiam Faustino de Souza](https://github.com/hobbitx) como parte da discplina de _Tópicos Especiais em Computação e Algoritmos: Algorimos de Organização e Recuperação de Informação_ do Centro Federal de Educação Tecnológica de Minas Gerais (CEFET-MG). Seu objetivo é desenvolver uma **máquina de busca para a Wikipédia (em Português)**.

## Índice

### Download
Para acessar o índice gerado na execução da Máquina de Busca, acesse o [link](https://drive.google.com/drive/folders/1kMQmPG75xclZ1djHPu-dFM3ZR24mZvIn?usp=sharing).

#### Vizualização
Para vizulizar o índice gerado na execução da Máquina de Busca, baixe o arquivo disponibilizado e salve-o na pasta principal desse programa. Após, instale a biblioteca `pickle` e utilize o código abaixo:
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

#### Quais fora os principais desafios e soluções?

#### Qual é a vantagem/desvantagem das suas soluções sob as outras alternativas (porexemplo,   uso   do   índice   em   memória   principal   x   ocorrência   de   termos   em   memóriasecundária)? 

#### O que nós melhorariamos  no nosso código para diminuir o consumo de memória ou deixálo mais eficiente?


### Blibliotecas Externas Utilizadas

### Técnica de *stemming*
No contexto de Recuperação de Informação, *stemming* é o processo de reduzir as palavras flexionadas (ao derivadas) ao seu tronco [[Wik.]](https://pt.wikipedia.org/wiki/Stemiza%C3%A7%C3%A3o), para otimizar a consulta em máquinas de busca. Por exemplo, os tokens `observar`, `observadores`, `observasse`, `observou` e `observe` podem ser transformados para um mesmo *steam* `observ`.

Em nosso projeto, o processo de *stemming* consistiu em:
- substituição dos caracteres acentuados `aáéíóúâêôçãẽõü` por sua correspondência sem acento `aeiouaeocaeou`;
- substiutiçaõ dos caracteres especiais `!?.:;,` por espaço;
- remoção das *stopwords* com a utilização da biblioteca `nltk`

## Suporte ou Contato
Você teve problema com o projeto? Entre em contato com o [suporte](mailto:fadoa.glauss@gmail.com) por e-mail.

## Seja Bem-Vindo

Este projeto foi desenvolvido por [Beatriz Souza da Silva](https://github.com/bia-souza), [Fadoa Glauss Vieira](https://github.com/fadoaglauss) e [Robert Cristiam Faustino de Souza](https://github.com/hobbitx) como parte da discplina de _Tópicos Especiais em Computação e Algoritmos: Algorimos de Organização e Recuperação de Informação_ do Centro Federal de Educação Tecnológica de Minas Gerais (CEFET-MG). Seu objetivo é promover o estudo e aprendizado de um indexador de próposito geral para Web.

### Indice Gerado
Para baixar o indice gerado basta acessar o link para download do  [arquivo](https://drive.google.com/drive/folders/1kMQmPG75xclZ1djHPu-dFM3ZR24mZvIn?usp=sharing)

### Como abrir o indice gerado
Basta rodar o seguinte codigo
from index.indexer import *
from index.structure import *
import pickle
with open("occur_index_15.idx","rb") as idx_file:
    obj_index = FileIndex()
    t = obj_index.next_from_file(idx_file)
    while t != None:
        print(t)
        t = obj_index.next_from_file(idx_file)
### Identificando o Bifaro Bot
O tráfego proveniente é identificado por seu agente de usuário: bifaroBot.

### Suporte ou Contato
Você teve problema com o projeto? Entre em contato com o [suporte](mailto:fadoa.glauss@gmail.com) por e-mail.

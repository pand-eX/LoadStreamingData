# Como carrego dados em tempo real?

[![NPM](https://img.shields.io/npm/l/react)](https://github.com/pand-eX/LoadStreamingData/blob/main/LICENSE) 

# About the project

Vou tomar como base que você viu o Project Data Warehouse em Nuvem com o Amazon Redshift, aqui vou explicar de forma rápida e direta como executar uma carga de dados em tempo real (dados de streaming) A AWS oferece algumas soluções que nos permitem executar esse tipo de tarefa.

Usarei o Amazon Kinesis Data Firehose que permite consumir, buffer e processar dados de streaming em tempo real, fornecendo insights em segundos ou minutos em vez de horas ou dias. Lembre-se de verificar os termos e preços de qualquer produto AWS!


## Why?

por que trabalhar com o Streaming é sempre desafiador para !!!

- Este projeto faz parte do meu portfólio pessoal, então ficarei feliz se você puder me dar algum feedback sobre o projeto, código, estrutura ou qualquer coisa que você possa relatar que possa me fazer um melhor engenheiro de dados!

Email-me: henricao_7@yahoo.com.br

Connect with me at [LinkedIn](https://www.linkedin.com/in/henrique-castro-484269203//).


## Iniciando o projeto

Existem 4 serviços que a Amazon Kinesis oferece 

-Fluxo de dados

-Fluxo de mangueira de fogo de dados

-Análise de dados

-Fluxo de vídeo


Vou usar o Firehose Stream para este projeto! Porque eu vou pegar o streaming e vou entregá-los para a Amazon Redshift.


-O serviço oferecido à AWS é tão incrível que eles, além de permitir que você crie streaming, permite que você use dados de teste que eles próprios estão gerando para você

![4](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/4.png)

Nesse processo, ele fala cria esta tabela depois que você usa esta tabela para gravar seu streaming e começar a capturar !!! eles fornecem dados de teste incríveis !!!

Aqui está a configuração do meu Kinesis mas este vários de acordo com suas necessidades eu vou deixar apenas como um exemplo !!!

![5](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/5.png)


## Carregando dados de streaming no Cluster Redshift

![1](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/1.png)


- Pegue os dados da fonte e vá para a entrega de streaming fará algum processo de transformação se não tiver configurado (este será o futuro, com o aumento de dados que está tendo no mundo o processo e a transformação será em tempo real faz as lojas de análise e prossegue para a próxima) grava isso no balde s3 usa o comando de cópia e escreve para o cluster redshift /\ basicamente foi o que eu fiz no lote mas não tinha o streaming AWS basicamente automatizado o processo para mim agora eu posso coletar os dados diretamente da fonte e colocar isso, armazenar diretamente em seu DW e você ainda pode criar o backup s3 Bucket porque como os dados são gerados em tempo real o volume é muito grande você geralmente descarta esses dados depois de fazer algum tipo de operação, mas no caso você queria salvar você pode usar s3 que o custo de armazenamento é muito menor 


- Esses dados são coletados da WEB através de um arquivo JSON que é processado por mangueira de fogo escrito no s3 e depois copiado para o Amazon Redshift e carregado na tabela tudo em tempo real
 

![2](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/2.png)



![3](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/3.png)


- Veja que ele gera alguns gráficos com bytes de entrada tem pouca coisa porque eu capturei por um curto período de tempo. 


- Este foi um exemplo de como podemos capturar dados em tempo real e armazenar diretamente no Redshift isso pode ser dado a partir de sensores da internet de coisas, IOT gerados a partir de dados da Web através de cliques do site de venda do site e a Kinesis faz tudo por você.

# Como efetuar carga de dados em tempo real?

[![NPM](https://img.shields.io/npm/l/react)](https://github.com/pand-eX/LoadStreamingData/blob/main/LICENSE) 

# Sobre o projeto

Vou tomar como base que você viu o projeto Data Warehouse em Nuvem com Amazon Redshift, aqui irei explicar de forma rápida e direta de como efetuar uma carga de dados em tempo real(Streaming de dados) A AWS ofereçe alguns soluções que nós permite realizar esse tipo de tarefa.


Usarei o Amazon Kinesis Data Firehose ele permite consumir, armazenar em buffer e processar dados de streaming em tempo real, proporcionando insights em segundos ou minutos em vez de horas ou dias. Lembre-se de verificar os termo e precificação de qualquer produto AWS!



## Why?

por que trabalhar com Streaming(conjunto de dados gerados em tempo real) é sempre desafiador !!!

-Este projeto faz parte do meu portfólio pessoal, então, eu vou ficar feliz se você pudesse me fornecer qualquer feedback sobre o projeto, código, estrutura ou qualquer coisa que você possa relatar que poderia me fazer um engenheiro de dados melhor!

Email-me: henricao_7@yahoo.com.br

Connect with me at [LinkedIn](https://www.linkedin.com/in/henrique-castro-484269203//).


## Iniciando o projeto

Existe 4 serviços que o Amazon Kinesis oferece 

-Data Stream

-Data Firehose Stream

-Data Analytics

-Video Stream


Utilizarei o Firehose Stream para esse projeto! Porque eu vou coletar os streaming e vou entregar para o Amazon Redshift.


-O serviço oferecido para AWS é tão incrível que eles além de permite que você crie o streaming ele permite que você usa dados de teste que eles mesmo estão gerando para você 

![4](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/4.png)

Nesse processo ele fala cria essa tabela depois você utiliza essa tabela para gravar o seu streaming e começe a capturar o streaming !!! eles fornecem dados de test incrível !!!

Aqui está a configuração do meu Kinesis mas isso vária de acordo com suas necessidades deixarei apenas com exemplo !!! 

![5](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/5.png)


## Carregando streaming de dados no Cluster Redshift

![1](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/1.png)


- Pegar os dados da fonte e ir para o delivery streaming vai fazer algum processo de transformação se eu tiver configurado  se não ele passa a diante (isso será o futuro, com o aumento de dados que está tendo no mundo o processo e transformação será em tempo real faz as analise armazena e segue para próxima) grava isso no s3 bucket utiliza o comando copy e grava no cluster Redshift /\ basicamente foi o que eu fiz no batch mas não tinha o streaming a AWS basicamente automatizou o processo para mim agora eu posso coletar os dados direto da fonte e colocar isso, armazenar direto no seu DW e você ainda pode criar o s3 Bucket backup porque como os dados são gerados em tempo Real o volume é muito grande normalmente você descarta esses dados depois de fazer algum tipo de operação mas caso você queria guardar você pode utilizar o s3 que o custo de armazenamento é muito menor 


- Esses dados são coletados da WEB através de um arquivo JSON ele é processado pelo Firehose gravado no s3 e então copiado para o Amazon Redshift e carregado na tabela tudo isso em Tempo real
 

![2](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/2.png)



![3](https://github.com/pand-eX/LoadStreamingData/blob/main/assets/3.png)


- Veja que ele gera alguns gráficos com bytes de entrada registro de entradas tem pouca coisa porque capturei por pouco tempo. 


- Esse foi um exemplo de como nós podemos capturar dados em tempo real e armazenar diretamente no Redshift isso pode ser dado de sensores dados da internet das coisas IOT dados gerados a partir de dados WEB dados através de clicks website de site de venda e o kinesis faz isso tudo para você.


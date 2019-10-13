# semantix
Projeto de engenheiro de dados

#Qual o objetivo do comando cache em Spark?
R: O comando cache tem como objetivo transformar os dados em memória para uma tabela com a estrutura Resilient Distributed Datasets (RDD) do spark que diminui o tamanho do arquivo em relação ao arquivo original e não é necessário refazer transformações e leituras.

#O mesmo código implementado em Spark é normalmente mais rápido que a implementação equivalente em MapReduce. Por quê?
R: O Spark utiliza o sistema de armazenamento de RDD que armazena os dados em cache entre os nós e os cluster que faz com que a iteração com os dados sejam executadas de forma mais rápida quando comparados com mapReduce.

#Qual é a função do SparkContext?
R: Ele tem como função se conectar à gerenciadores de clusters.

#Explique com suas palavras o que é Resilient Distributed Datasets (RDD).
R: RDD são conjuntos de dados alocados em memória distribuídos de forma que diminua a quantidade do tempo de leitura e transformação dos dados que estamos trabalhando, pois ele armazena o cacho dos dados que foram processados e assim evita reprocessamento do mesmo.

#GroupByKey é menos eficiente que reduceByKey em grandes dataset. Por quê?
R: Quando usamos o ReduceByKey os dados são primeiramente combinados e então enviados para os executores enquanto o GroupByKey não faz essa combinação ao enviar os dados.

#Explique o que o código Scala abaixo faz.
1) val textFile = sc.textFile("hdfs://...")
2) val counts = textFile.flatMap(line => line.split(" "))
3) .map(word => (word, 1))
3) .reduceByKey(_ + _)
4) counts.saveAsTextFile("hdfs://...")

R: Primeiramente é lido um arquivo na primeira linha de código seguido da contagem de cada palavra dentro desse arquivo, finalmente sendo salvo em um outro arquivo com os resultados dessas contagens.


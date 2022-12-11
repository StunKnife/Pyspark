# Spark com Pyspark

<br><br>
<img src="https://github.com/StunKnife/Pyspark/blob/main/figuras/fig_1_pyspark.png" width="1000">

# O que é o Spark?

  1. Ferramenta de Processamento de Dados (Não é Data Storage) 
  2. Distribuído em um Cluster
  3. Em memória
  4. Veloz
  5. Escalável
  6. Dados em HDFS ou Cloud
  7. Particionamento

O Spark também permite **Replicação** e tem **Tolerância a Falha**. 
    • Dados são copiados entre os nós do cluster. Isso traz o benefício de, entre outras coisas, tolerância a falhas
 <br><br>
 <img src="https://github.com/StunKnife/Pyspark/blob/main/figuras/cluster.png" width="1000">

 # Porque utilizar Spark frente a outras linguagens como Python ou R?
 
 Primeiro, você precisa Processar dados! Além disso, o Spark apresenta as seguintes vantagens:
     
    • Custo computacional: CPU, Memória, Rede etc.
    
    • Spark tem arquitetura voltada a processar dados!
    
    • Melhor performance, porém:    
        1. Não substitui Python
        2. Não substitui SQL ou um SGBDR

 # Estrutura do Spark
 
     1. Driver: Inicializa SparkSession, solicita recursos computacionais do Cluster Manager, transforma as operações em DAGs, distribui estas pelos executers
     2. Manager: Gerencia os recursos do cluster. Quatro possíveis: built-in standalone, YARN, Mesos e Kubernetes
     3. Executer: roda em cada nó do cluster executando as tarefas
 <br><br>
 <img align="center" src="https://github.com/StunKnife/Pyspark/blob/main/figuras/estrutura.png" width="500">

# Componentes

Quando efetuamos uma aplicação em Spark nos deparamos com as seguintes componentes:
  1. Job: Tarefa
  2. Stage: Divisão do Job
  3. Task: Menor unidade de trabalho. Uma por núcleo e por partição

Estas tarefas podem ser exemplificadas pela ilustação a seguite.
 <br><br>
 <img align="center" src="https://github.com/StunKnife/Pyspark/blob/main/figuras/componentes.png" width="500">

# SparkContext e SparkSession

    * O **SparkContext** se trata de uma Conexão transparente com o Cluster

    * **SparkSession** Fornece acesso ao **SparkContext**

# SparkContext / Session

Você pode rodar script Spark no shell (pyspark). Então, o Spark cria uma sessão automaticamente chamada spark

    • Se criar uma aplicação spark, você precisa criar, por exemplo:

    *. Bibliotecas 
        1. from pyspark.sql import SparkSession
        2. from pyspark.sql.functions import *
        
    *. Iniciar Aplicação Spark    
        spark = SparkSession.builder.appName("Exemplo").getOrCreate()

# Principais Estruturas de Dados no Spark

    *. **Resilient Distributed Datasets (RDD)**: Data Set espalhado pelo cluster
            1. Estrutura básica de baixo nível
            2. Dados “imutáveis”, distribuídos pelo cluster Em memória
            3. Pode ser persistindo em disco
            4. Tolerante a falha
            5. Operações sobre um RDD criam um novo RDD

    *. **Dataset e DataFrame**: Semelhante a uma tabela de Banco de Dados. Compatíveis com objetos DataFrame do R e Python
            1. Dataset está disponível apenas em Java e Scala
            2. Dataset não está disponível em R e Python

O **DataFrame** é a estrutura de dados ideal que os **Data Scientist** **utiliza** no dia a dia com **Python** ou **R**.
 
# RDD
Criando um RDD a partir de uma lista em Pyspark.

       1. **import pyspark**
       2. **from pyspark.sql import SparkSession**

       3. **spark = SparkSession.builder.getOrCreate()**

       4. **sc = spark.sparkContext # sc abreviação de  sparkContext**

       * Método parallelize > Construindo uma lista de números de 1 a 10
            1. rdd = sc.parallelize([1,2,3,4,5,6,7,8,9,10])
            2. rdd.collect()
O RDD está criado.

# DataFrame
      1. Tabelas com linhas e colunas
      2. Imutáveis
      3. Com schema conhecido
      4. Linhagem preservada
      5. Colunas podem ter tipos diferentes
      6. Existem análises comuns: Agrupar, ordenar, filtrar
      7. Spark pode otimizar estas analises através de planos de execução
      
 **Lazy Evaluation**: O processamento de transformação de fato só ocorre quando há uma Ação
      *. Permite cria rum plano de excecução otimizado
      
**Schema**: Você pode deixar para o Spark inferir a partir de parte dos dados ou você pode definir o schema.
      *. Por exemplo, definir os tipos das colunas.


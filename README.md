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
 


 
 

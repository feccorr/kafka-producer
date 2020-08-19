
subir zookeper (gerenciador de sistemas distribuidos)

$ bin/zookeeper-server-start.sh config/zookeeper.properties

------

Abrir outro terminal e executar:

$ bin/kafka-server-start.sh config/server.properties

------

Para criar os topicos:
(
->conectando no bootstrap-server em localhost:9090
->10 partiçoes no topico
-> fator de replicação 1
-> nome do topico 'teste-kafka'
)

$ bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --partitions 10 --replication-factor 1 --topic teste-kafka

------

Enviando eventos para o topico

$ bin/kafka-console-producer.sh --broker-list localhost:9092 --topic teste-kafka


------

Ligando o consumer :
(Na hora de consumir pode existir n group)
$ bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --group developer --topic teste-kafka

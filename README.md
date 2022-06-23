# WordCount-Mapreduce

Télecharger le fichier .jar et le placer sur sa VM dans /home/cloudera

1 -créer les dossiers dans hdfs
hadoop fs -mkdir /wordcount
hadoop fs -mkdir /wordcount/input
hadoop fs -put /home/cloudera/input.txt /wordcount/input

2 -Mettre le fichier .jar dans /home/cloudera

3 - Executer la commande suivante :
hadoop jar /home/cloudera/wordcount_f.jar wordcount/WordCount /wordcount/input/input.txt wordcount/out3

Démarrage du map reduce 

4 - Affichage du fichier part-r-00000
hdfs dfs -ls /wordcount/
hdfs dfs -ls /wordcount/out3

Commande pour afficher le resultat:
hdfs dfs -cat /wordcount/out3/part-r-00000

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

Résultat:

![image](https://user-images.githubusercontent.com/38456239/179606736-588312fe-f0e9-41a2-bbc3-0c8637e2e96f.png)

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

Explication du code

La classe Mapper implémente une méthode de carte publique, qui traite une ligne à la fois et divise chaque ligne en jetons séparés par des espaces. Il émet une paire clé-valeur de <word> , <1>, écrite dans le contexte.
  
![image](https://user-images.githubusercontent.com/38456239/179606858-c7209df3-22df-4df2-96d4-9e27e295c344.png)

Le framework rassemble toutes les paires avec la même clé et les transmet à la fonction reduce, qui additionne ensuite les valeurs pour donner le nombre d'occurrences.
  
![image](https://user-images.githubusercontent.com/38456239/179607030-af285013-1c2f-43a2-a6b2-3de94d630970.png)



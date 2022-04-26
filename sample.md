<!-- Headings -->
# Create a BLAST Database 
## Choosing genomes
<p> First, we have chosen our genomes by using two algorithms, One is random and the other one is diverse. Users should use the following command to get the genomes that are chosen either randomly or diversly:<br></p>

<!-- Code Blocks -->
```perl
    perl randomDB.pl (count) ecolist.txt > all_count_rand.list
    perl diverseDB.pl (count) eschmash.dist > all_count_diverse.list
```
## Make fasta files
<p> For making BLAST database, we need to create a fasta file. By using fastamaker.pl we got the sequences of genomes for the randomly or diversely selected n DB size. Users should use the follwing command to create a fasta file:
<br></p>

<!-- Code Blocks -->
```perl
    perl fastamaker.pl count_rand.list count_rand.fa
```
<p> After getting the fasta file we have to make BLAST database out of it by using the following command. But before running the next commands for creating BLAST database, we have to make sure that we have The following programs must be properly installed and loaded in the user's path <br> </p>

<!-- Code Blocks -->
```perl
    module load BLAST
    makeblastdb
    makeblastdb -in count_rand.fa -out count_rand -dbtype nucl -parse_seqids
```


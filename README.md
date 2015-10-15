# miRmaid
Identificaiton of miRNAs through machine-aided identification


* Programs Requirement
	Running miRmaid requires a GNU-like environment. It should be possible to
	run miRmaid on a Linux or Mac OS.  

	miRmaid requires other external tools which can be found
	bowtie- (currently )
	RNAfold
	java	http://www.java.com/en/download/

* compile
	cd src/
	javac *.java

* demo
	cd demo/
	./run.sh
	vim topre.map.align_1	( topre.map.align_1 is the final result )

* command in run.sh
./mirmaid.sh /project/cic2/xiaj/bb/mm9/mm9 ../data/seq.fa ../param.txt ../mmu.gff ../data/seq.fa_lib

the run.sh takes five inputs
	$1 bowtie-built index of the database. e.g mouse genome index
	$2 fasta file of the sequencing reads 
	$3 a list of parameters used in the program (see next section)

	optional inputs
	$4 the miRNA annotation file 
	$5 the number of reads


* format in fasta file
>seq_x100
CTAGTTTTTTTTAAAAAAA


* parameter file

	# directory of genome
	gendir = /project/cic2/database/mm9/

	# if genome has multiple files, isDiR = ture; otherwise, isDir = false  
	isDir = true

	# length of each slide (from 5' to 3')
	slideLen = 20

	# size of sliding window
	slidespan = 120


	# If positions of two reads are less than gapLen, they will be considered as one cluster
	gapLen = 50

	# the size of extension to both ends of each clusters
	extLen = 200

	# the minimum number of reads in a cluster
	mincopy = 10

	# minimum of hairpin folding energy
	mindg = 18

	# minimum length of miRNA-miRNA duplex
	hplen = 18





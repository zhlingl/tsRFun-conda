# tsRFun: a comprehensive platform for decoding tsRNA expression, functions and prognosis value by highthroughput small RNA-Seq and CLIP-Seq data
## Requirements
Linux system, enough disk space and Ram depending on the size of RNA deep sequencing data. (Tested system: ubuntu 12.04 LTS,
ubuntu 16.04 LTS)

## install conda
wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.10.3-Linux-x86_64.sh

bash Miniconda3-py39_4.10.3-Linux-x86_64.sh

source ~/.bashrc

## configure the environment with conda
conda env create -f tsRFun.yaml

## activate conda environment
conda activate tsRFun

## test if everything is installed properly:
perl -v

tsRFinder.pl -h

bowtie

samtools

bedtools

# run tsRFinder usage
tsRFinder.pl

The input files are:
Options:
  -i <file>	Input could be: .fastq/.fq or .fasta/.fa file. 
  
  -o <file>	Output address of annotation results.
  
  -t <int>	Number of threads to launch (default = 4).
  
  -x <str>	Address of bowtie index tRNA information .
  

Alignment:
  -l <int>	The minimal length of the output sequences (default = 15)
  
  -L <int>	The maximal length of the output sequences (default = 45)
  
  -M <int>	The total number of mismatches in the entire alignment (default = 0)
  
  -p <float>	The p-value threshold to determine whether the fragment is tsRNA.
  
Others:
  -v		Print version information
  
  -h		Print this usage message

## Example of use:
tsRFinder.pl -i PATH_of_example/fasta -o PATH_of_example/ -x hg38_index/

### If you have these errors,please refer to the following:
#### error1
perl: symbol lookup error: perl5/x86_64-linux-thread-multi//auto/Math/CDF/CDF.so: undefined symbol: Perl_Gthr_key_ptr
#### Solution1
export PERL5LIB=""
#### error2
samtools: error while loading shared libraries: libtinfow.so.5: cannot open shared object file: No such file or directory
#### Solution2
conda install -c conda-forge ncurses

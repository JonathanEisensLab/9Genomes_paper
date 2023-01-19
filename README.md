# Paper Title:
Genome Sequencing and Multifaceted Taxonomic Analysis of Novel Strains of Violacein Producing Bacteria and Non Violacein Producing Close Relatives
# Authors:
Marina Estella De León, Harriet S. Wilson, Guillaume Jospin, Jonathan A. E


Genome Assembly
```
bbduk2.sh in=UCD_MED1_S101_L006_R1_001.fastq.gz in2=UCD_MED1_S101_L006_R2_001.fastq.gz  -Xmx4g out=UCD_MED1_bbduk.1.fq out2=UCD_MED1_bbduk.2.fq qtrim=rl trimq=10 minlength=80 fref=adaptor_file.fa 2> bbduk.1.fq.bbduk.out
a5_pipeline.pl --threads=12 UCD_MED1_bbduk.1.fq UCD_MED1_bbduk.2.fq > UCD_MED1.log 2>> UCD_MED1.log
```

FastANI command 
```
fastANI --rl anifilelist.txt --ql anifilelist.txt -t 6 --matrix -o fastANI_new9Gs
```

Phylogeny:
```
/share/eisenlab/gjospin/miniconda3/gtdbtk-1.3.0/bin/gtdbtk classify_wf --genome_dir /share/eisenlab/gjospin/misc/Marina/Marina_test/Pat_screen/Jan2020/WGTree/genomes_placements/ncbi-genomes-2021-02-08 --out_dir /share/eisenlab/gjospin/misc/Marina/Marina_test/Pat_screen/Jan2020/WGTree/GTDB-Tk.all.2 --prefix AllGs.Feb21.2 -x .fna --cpus 6 

raxmlHPC-PTHREADS -m PROTGAMMABLOSUM62 -x 47 -p 8 -T 12 -N 250 -f a -s ../New9Gs.redo.2.bac120.user_msa.fasta -n New9Gs.redo.March2022
```

# PopCOgent

https://github.com/philarevalo/PopCOGenT

# Plots
make_heatmap.Rmd
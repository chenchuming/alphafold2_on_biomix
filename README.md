# AlphaFold2 on BIOMIX HPC Cluster
This repository hosts information about running AlphaFold2 on [BIOMIX HPC cluster](https://bioit.dbi.udel.edu/BIOMIX/BIOMIX-cluster.html) using singularity.

We have installed [AlphaFold2](https://github.com/google-deepmind/alphafold) on BIOMIX HPC Cluster based on [alphafold_singularity](https://github.com/prehensilecode/alphafold_singularity).

## Run as a Slurm job on BIOMIX 
See the example job script [`alphafold2_on_biomix_slurm.sh`](https://github.com/chenchuming/alphafold2_on_biomix/blob/main/alphafold2_on_biomix_slurm.sh).

Note: this example script must be modified to suit your specific needs. Only change the section mentioned below in the example slurm script.

### Customization for slurm enviroment
You can change your job name and add the following two SBATCH directives if you want to receive email notification of your job run status.

#SBATCH --job-name=afolds

#SBATCH --mail-user=youremail@university.edu

#SBATCH --mail-type=ALL

### Customization for input, output, and Alphafold2 model 
The next customization is to specify your input files and output directory. You need to provide your protein sequence in FASTA format. Each file only contains one sequence except a multi-sequence FASTA file for "multimer" model.

You also needs to change alphafold2 model by setting "--model_preset" parameter. Default is "monomer", but you can change it to "monomer_casp14", "monomer_ptm", or "multimer". 

# Python and Linux scripts for *in silico* vaccine discovery against protozoan parasites

In the paper “**A state-of-the-art methodology for high-throughput *in silico* vaccine discovery against protozoan parasites and exemplified with discovered candidates for Toxoplasma gondii**”, we combine current *in silico* vaccine discovery knowledge specific to protozoan parasites and develop a workflow representing a state-of-the-art approach. The approach reflectively integrates a parasite’s biology, a host's immune system defences, and importantly, bioinformatics programs needed to predict vaccine candidates. This GitHub repository provides the inhouse Python and Linux scripts used to demonstrate the workflow. The apicomplexan parasite, *Toxoplasma gondii* was used in the demonstration i.e., the scripts were setup specifically to run protein sequences from *T. gondii* RH-88 strain. However, the scripts can be easily modified to run protein sequences from any organism.

## Computer platform used for the development
All experiments and data generation were performed on a high performance computing (HPC) cluster node with 64 bit kernel, 32 MB memory, and 8 cores. The scripts were designed for a Linux operating system and have only been tested on Red Hat Enterprise Linux 7.9, but are expected to work on most Linux distributions. Python version used was 3.6.8.

## To run the software
The Python and Linux scripts have been separated into three separate directory structures: preparation_programs, cmi_pipeline, and humoral_pipeline.
Download the latest version from **https://github.com/goodswen/in_silico_vaccine_discovery/releases**

Decompress:

**tar –zxvf preparation_programs_v1.0.tar.gz**

**tar –zxvf cmi_pipeline_v1.0.tar.gz**

**tar –zxvf humoral_pipeline_v1.0.tar.gz**

Parent directories called **preparation_programs**, **cmi_pipeline**, and **humoral_pipeline** are obtained after decompressing the downloaded files. These directories can be moved to any location of your choice.

*preparation_programs* – contains scripts to aid in tasks such as sequence evaluation, sequence similarity (autoimmunity checks), clustering (for creating core proteome), determining low complexity regions (LCR), and toxicity predictions.

*cmi_pipeline* – contains a software pipeline to predict the binding affinity to MHC II molecules (run ./mchii_script), and a pipeline to process the results (run ./main_script).

*humoral_pipeline* – contains software pipelines to predict linear and conformational B-cell epitopes, and to predict proteins under positive selection (run ./main_script for each pipeline).

## Important notes
The Python and Linux scripts are provided only as a guide or template. The expectation is that every script will need to be modified to suit your target organism e.g., change the hardcoding such as threshold values and filenames at the top of the Python scripts. The pipelines are typically setup to automate the process of executing multiple scripts from different directories e.g., the scripts are saved in a series of numbered directories that denote the running order of the scripts. The input to a script is typically from the preceding output directory. The main controlling Linux scripts are typically called main_script e.g., to run a pipeline, enter ‘.\main_script’ in the command terminal.

Note that the third-party programs associated with the scripts need to be downloaded and installed e.g., CD-HIT, SEG, NetMHCII, BepiPred, and BLASTP (see ‘Materials and methods’ in paper for all required programs and versions).

Note that the scripts here for Python 3 were invoked by using the syntax ‘python3’ e.g., python3 extract_results.py. To run on your Python environment, you may need to modify the syntax accordingly e.g., python extract_results.py.

For **HELP**, please e-mail **Stephen.Goodswen@uts.edu.au**


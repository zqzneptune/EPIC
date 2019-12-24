# Running EPIC
The **EPIC** toolkit was initially published here: Hu, L. Z., et al. "EPIC: software toolkit for elution profile-based inference of protein complexes." Nature methods 16.8 (2019): 737-742. [Link to the publication](https://www.nature.com/articles/s41592-019-0461-4)

Forked from the orignial [repository](https://github.com/BaderLab/EPIC), **RunEPIC** aims to provide the code to run **EPIC** locally.

# Environment
The main function in **EPIC** was implemented in Python, given the headache caused by various libraries, the Anaconda enrionment was used. Simply install Anaconda Python 2.7 version for your convience, and we will start from there.

# Prerequisite
Let's create the virtual enrionment:
```
path to the anaconda directory/bin/conda create -n EPIC python=2.7 anaconda
```
then we need step up some chanels:
```
(EPIC)conda config --add channels defaults
(EPIC)conda config --add channels bioconda
(EPIC)conda config --add channels conda-forge
```
get R installed:
```
(EPIC)conda install r
```
start R:
```
(EPIC)R
```
install wccsom for computing WCC scores:
```
> install.packages("kohonen")
> install.packages("https://cran.r-project.org/src/contrib/Archive/wccsom/wccsom_1.2.11.tar.gz",
                 type = "source")
> q()
```
install conda packages:
```
conda install requests scikit-learn beautifulsoup4 mock numpy rpy2
python -mpip install -U matplotlib
```
lastly, make sure Java is installed, so that ClusterOne.jar could be used.

# Run EPIC
```
git clone https://github.com/zqzneptune/RunEPIC.git
```
The main.py in **EPIC** implemented all the functions:
```
python directory to RunEPIC/src/main.py \
       -s 11101001 \
       [Directory to Input Folder/] \
       -c [path to the gold standard file ] \
       [Directory to Output Folder/] \
       -o PrefixName \
       -M RF \
       -n 6 \
       -m COMB \
       -f STRING
```

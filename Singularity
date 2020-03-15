BootStrap: docker
From: continuumio/miniconda:latest
IncludeCmd: yes

%help

%setup

%files

%labels

%environment

%post
	umask 0022
	apt update
	apt -y dist-upgrade
	apt -y install build-essential git environment-modules wget libxml2-dev libssl-dev tar gzip libgsl-dev
	apt install -y libboost-all-dev libhts-dev libncurses5-dev libtinfo-dev zlib1g-dev lcov
	export PATH=/opt/conda/bin:$PATH
	ln -s /bin/gzip /usr/bin/gzip
	ln -s /bin/tar /bin/gtar
	conda install -c conda-forge -c bioconda -c defaults java-jdk snaptools r-devtools r-optparse r-tidyverse r-irlba r-dosnow r-plot3d r-doparallel
	Rscript -e "install.packages('Matrix', repos = 'http://cloud.r-project.org')"
	Rscript -e "library(devtools); install_github('r3fang/SnapATAC')"
	conda install -c bioconda bioconductor-rhdf5lib=1.6.0 bioconductor-rhdf5=2.28.0

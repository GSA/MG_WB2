# Well-Built for Wellbeing (WB2)

From 2016-17, GSA's Office of [Federal High Performance Buildings](https://www.gsa.gov/about-us/organization/office-of-governmentwide-policy/office-of-federal-highperformance-buildings) collected Indoor Environmental Quality (IEQ) data in several of GSA's buidlings. For several months, the program also collected data from GSA employees related to their wellbeing in the form of daily journals, wearnodes that monitored their vitals, and demographics. Additional datasets are also available to join to the IEQ data.

These datasets are stored in a number of csvs on our team's Google Drive. This repo contains scripts to join these datasets as well as analyses performed with the data.

## Getting Started

### Prerequisites

First, you'll need Python 3.7. We recommend using `pyenv` to get this (as well as other versions of Python).

Then you'll need Jupyter Notebook. You can find directions on how to get that [here](https://jupyter.org/install). They recommend downloading Anaconda to get it, but we suggest using `pip` if you're already using `pyenv` to manage your python versions.

Then you'll want to clone this repo and `cd` in to it:

```bash
git clone https://github.com/GSA/wb2.git
cd wb2
```

We use `pipenv` for a virtual environment. You can find instructions on installing that [here](https://pipenv.readthedocs.io/en/latest/install/#installing-pipenv).

Once you've got `pipenv` installed, you can start up the virtual environment using:

```bash
pipenv install
```

Next, activate the Pipenv shell:

```bash
pipenv shell
```

This will spawn a new shell subprocess, which can be deactivated by using `exit`.

One of the required packages you just installed is `ipykernel`. We use this to create a kernel that uses our virtual enivronment for the Jupyter Notebook:

```bash
ipython kernel install --user --name=wb2
```

At this point, you can start jupyter with `jupyter notebook`. Open this notebook and select the kernel (wb2) that you just created.

### Getting the Data

The data files are too large to keep in the repository, so we keep them in our team's google drive.

#### WB2 (Cohort) Data

This is the IEQ data collected as a part of the larger WB2 study, which included study participants. Download the WB2 data [here](https://drive.google.com/drive/folders/1H78txPPkhoerJxj0dHa2p7dSooDkjwbm). There's a csv for each modality (e.g. CO2). Once you've downloaded those files, move them into the `data/wb2` directory.


#### Post-Cohort Data

Download the post-cohort data [here](https://drive.google.com/drive/u/0/folders/1Ah7MOw99aKeQazV5bOAxG8r0zR4jHI5r). Move the two zip files into the `data/post-cohort` directory. Unzip those two files and then unzip all of the csvs within. You can do so in Linux or OSX with:

```bash
cd 2016
gunzip *.gz
```

If the above results in
```bash
-bash: /usr/bin/gunzip: Argument list too long
```
then try 
```bash
cd 2016
find . -type f -exec gunzip {} +
```

Another option that utilizes only Python is to in the notebook located [here](https://github.com/GSA/wb2/blob/gz_extract/GZ%20%Mass%20Extract.ipynb).

This enables you to input the drive folder and all .gz files will be extracted within same folder. This option is helpful
if the user does not have access to Linux or PowerShell. 

#### Absenteeism Data

This dataset contains HR leave records. You can download it [here](https://drive.google.com/drive/folders/1VpKn8hX4nYlBhVp946bsQt9whmtQ5q9C). Once you've got it, place it in `data/absenteeism`.

#### Computerized Maintenance Management System Data

This dataset contains information about maintenance operations in GSA's buildings. It can be joined with the IEQ data to gain additional information about the location of each wallnode such as the machinery in/near the room. You can find it [here](https://drive.google.com/drive/folders/1lZ1eHMh9NDwN5PVW6gQqAScWxRkGaEKu). Once you've got it, place it in `data/cmms`.

#### BookIt

This dataset contains workstation reservation data. It's needed to know where employees in the absenteeism data sit, which will help you join that data to the IEQ data. The files can be found [here]

## License

This project is licensed under the Creative Commons Zero v1.0 Universal License - see the [LICENSE.md](https://github.com/GSA/wb2/blob/master/LICENSE) file for details

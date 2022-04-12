# How to Lift and Verify Differential from the Machine Code of Cyber-Phisical Systems

This project aims to obtain the control differential equations of multiple embedded systems, and analyze them in a manner that provides higher level representation of those equations. This project is born as part of the Undergraduate Research Project for the Degree in Telecommunication's Engineering at [Universidad Pontificia Comillas - ICAI](https://www.icai.comillas.edu) and it is done as a collaboration with the [University of Illinois at Urbana-Champaign](https://www.illinois.edu) at the [Security and Privacy Research Laboratory at Illinois](https://spri.engr.illinois.edu).

Acknowledgements to Maxwell Bland and Kirill Levchenko for the support in this project.

2021-2022

## Tools and Resources

In the development of the project, the following tools were used:

* [python3](https://www.python.org)
* [IPython](https://ipython.org)
* [Ghidra](https://ghidra-sre.org)
  * [Ghidra Bridge](https://github.com/justfoxing/ghidra_bridge)
* [radare2](https://www.radare.org/n/radare2.html)
  * [r2pipe](https://www.radare.org/n/r2pipe.html)
  * [r2ghidra](https://github.com/radareorg/r2ghidra)
* [angr](https://angr.io)
* [DaDRA](https://github.com/jaredmejia/dadra)
* [ICSREF](https://github.com/momalab/ICSREF)

## Installation

A virtual environment such as [conda/minconda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) or [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/install.html) (Linux/Mac OS X only) is recommended for the installation of the packages. Firthermore, the python version should be 3.8+.

#### IPython

* Install the IPython package:

  ```
  $ pip3 install ipython
  ```

#### Ghidra

* Make sure that [Java Development Kit 11](https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html) is installed and on the PATH
* Access and download the latest [release](https://github.com/NationalSecurityAgency/ghidra/releases) of Ghidra
* Extract the Ghidra release file
* Launch Ghidra: **`./ghidraRun`** **(or** **`ghidraRun.bat`** for Windows)

##### Ghidra Bridge

* Install the ghidra_bridge package:
  ```
  $ pip3 install ghidra_bridge
  ```
* Install the server scripts to a directory on the Ghidra's script path (e.g., ~/ghidra_scripts, or you can add more directories in the Ghidra Script Manager by clicking the "3 line" button left of the big red "plus" at the top of the Script Manager).
  ```
  $ python3 -m ghidra_bridge.install_server ~/ghidra_scripts
  ```

#### Radare 2

* Install from git:

  ```
  $ git clone https://github.com/radareorg/radare2
  $ cd radare2
  $ sys/install.sh
  ```

  ##### r2pipe


  * Install the r2pipe package:
    ```
    $ pip3 install r2pipe
    ```

  ##### r2ghidra

  * Install r2ghidra using the radare2 package manager:

    ```
    $ r2pm update
    $ r2pm -ci r2ghidra
    ```

    Note: make sure that in the folder `~/.local/share/radare2/plugins` there is a sub-folder named `r2ghidra-sleigh`. If not, decompress the file named `r2ghidra_sleigh-x.x.x.zip` and change the resulting unzipped folder to `r2ghidra-sleigh`.

#### angr

* Install the angr package:
  ```
  $ pip3 install angr
  ```

#### DaDRA

* Install the DaDRA package:
  ```
  $ pip3 install --upgrade dadra
  ```

#### ICSREF

While ICSREF is not vital for the execution of the project, it may be installed to demonstrate some of the findings and simulate attacks on PLC.

Note: ICSREF is built on python2 and as such, a virtual environment should be used for the installation (mkvirtualenv is recommended).

* Install the system dependencies:
* ```
  $ sudo apt install git python-pip libcapstone3 python-dev libffi-dev build-essential virtualenvwrapper graphviz libgraphviz-dev graphviz-dev pkg-config
  ```
* Install from git:
  ```
  $ git clone https://github.com/momalab/ICSREF.git 
  $ cd ICSREF
  ```
* Install the python package dependencies from wheelhouse:
  ```
  $ pip install --no-index --find-links=wheelhouse -r requirements.txt
  ```
* Create a bash alias:
  ```
  $ echo -e "\n# ICSREF alias\nalias icsref='workon icsref && python `pwd`/icsref/icsref.py'\n" >> ~/.bash_aliases && source ~/.bashrc
  ```

## Usage

Currently, WiP (Work in Progress)

## Contact

* **Email**: jjarauta@alu.comillas.edu
* **Website**: [www.jarauta.com.es](https://www.jarauta.com.es)
* **LinkedIn**: [https://www.linkedin.com/in/javierjarautagastelu/](https://www.linkedin.com/in/javierjarautagastelu/)

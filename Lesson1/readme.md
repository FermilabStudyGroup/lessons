## Getting a scientific Python environment with Anaconda
Short guide on how to get a nice scientific python environment working quickly with Python, ROOT, PyROOT, notebooks, etc.

* First, download Anaconda from here: [https://www.continuum.io/downloads](https://www.continuum.io/downloads).

* If you are on the gpvm, you can just do:

```
https://repo.continuum.io/archive/Anaconda2-4.2.0-Linux-x86_64.sh" -O anaconda.sh
chmod +x anaconda.sh  
./anaconda.sh
```
* Install it, and pray everything goes fine.

* Make sure your PATH environment has your Anaconda bin directory in it!

* You'll also obviously need to change your path.

* Add the Conda NLeSC channel to Conda, it contains ROOT and other awesome stuff:

```
conda config --add channels https://conda.anaconda.org/NLeSC
```
* Create your nice environment:

```
conda create --name=py2 root=6 python=2
```
* RootNumpy is also useful in this case (but must be installed outside the environment, for some reason):

```
conda install -f root-numpy
```

* Done! Anytime you need your new virtual environment, all you need to do is:

```
source activate py2
```

* This can be a useful alias to have (but remember to change the path!):

```
alias soconda='run "export PATH=pathtoanacondadir/bin:${PATH}"; run "source activate py2"'
```



More instructions here:

[https://nlesc.gitbooks.io/cern-root-conda-recipes/content/using_the_conda_binary_packages.html](https://nlesc.gitbooks.io/cern-root-conda-recipes/content/using_the_conda_binary_packages.html)

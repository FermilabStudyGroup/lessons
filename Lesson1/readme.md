## Getting a scientific Python environment with Anaconda
Short guide on how to get a nice scientific python environment working quickly with Python, ROOT, PyROOT, notebooks, etc.

* First, download Anaconda from here: [https://www.continuum.io/downloads](https://www.continuum.io/downloads).

* Download the command line installer for Python 2.7

* And let's launch the installation with:

```
chmod +x anaconda.sh  
./anaconda.sh
```

* Install it, approving license terms and confirming location for install.

* You will get a message like this one at the end, if you don't want to mix up with your current Python installation just say 'no':

```
Do you wish the installer to prepend the Anaconda2 
install location to PATH in your /Users/testuser/.bash_profile ? [yes|no]
[yes] >>> no

You may wish to edit your .bashrc or prepend the Anaconda2 install location:

$ export PATH=/Users/testuser/anaconda2/bin:$PATH

Thank you for installing Anaconda2!

Share your notebooks and packages on Anaconda Cloud!
Sign up for free: https://anaconda.org

```

* But remember to do `export PATH=/Users/testuser/anaconda2/bin:$PATH` before using Anaconda (or you can prepend it to your .bash_profile)

* Add the Conda NLeSC channel to Conda, it contains ROOT and other awesome stuff:

```
conda config --add channels https://conda.anaconda.org/NLeSC
```

* Create your nice environment:

```
conda create --name=py2 root=6 python=2
```

* Let's test ROOT. It may or may not work (it depends on whether you recently updated your Mac/Linux machine).

* Test it now:

```
root -b -q
```

* If it works, hurray! If it doesn't don't worry, we'll fix it later. For now we'll be interested in the notebooks.

* If your ROOT installation worked, you can also try to install RootNumpy (but must be installed outside the environment, for some reason):

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

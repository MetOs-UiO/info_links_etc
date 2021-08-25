# How to use Virtual studio Code and Fram

If you like to run significant bits of code, you probably want to do it on a Server. I decided to run my code on Fram, one of the Sigma2 HPCs. 

I use Visual Studio Code (VS code) to connect to Fram and to run my scripts. To connect to any remote via ***ssh***, please follow the [instructions](https://code.visualstudio.com/docs/remote/ssh) on the VS code documentation. If you want to connect to Fram via VS code, use `<username>@fram.sigma2.no`, while Nird needs to know about the individual nodes. Nird: `<username>@loginX.nird.sigma2.no` where X is the node 0, 1, 2, or 3.

> **_NOTE:_**  The problem is that login.nird.sigma2.no is an alias corresponding to 4 login nodes:
> - login0.nird.sigma2.no
> - login1.nird.sigma2.no
> - login2.nird.sigma2.no
> - login3.nird.sigma2.no
>
> and that probably won't work with VS code unless if you stick to one login node and use specifically that one.


Once we are logged in to Fram, we will be in our home directory. Open the terminal with one of the below commands:
- Use the `Ctrl+` ` keyboard shortcut with the backtick character.
- Use the **View > Terminal** menu command.
- From the **Command Palette** (`Ctrl+Shift+P`), use the **View: Toggle Integrated Terminal** command. 
  
To check if you are in your home directory, type the following:
```
$ cd ~
$ pwd
/cluster/home/username
``` 
Since I want my science to be reproducible, I create my personal virtual environment for Python on Fram. [Why do I want to use a private virtual environment?](https://towardsdatascience.comwhy-you-should-use-a-virtual-environment-for-every-python-project-c17dab3b0fd0)

Fram has much [software already preinstalled](https://documentation.sigma2.no/software/installed_software/fram_modules.html), such as Python. Now I'm just following the documentation of Sigma2 on [Installing Python Packages](https://documentation.sigma2.no/software/userinstallsw/python.html#installing-python-packages) and [Using Python Environments in VS code](https://code.visualstudio.com/docs/python/environments#).
The following did the trick for me:
```
$ cd ~
$ pwd
/cluster/home/franzihe
# First load an appropriate Python module (use 'module list Python' to see all)
$ module load Python/3.8.6-GCCcore-10.2.0
# create the environment in your home directory
$ python3 -m venv .venv
```

You should now see `.venv` in your home directory. Please don't rename the virtual environment. It should be called `.venv`!

If you instead want to have the virtual environment to be within your project, you can also follow the VS code instructions on [How to manually specify an interpreter](https://code.visualstudio.com/docs/python/environments#_manually-specify-an-interpreter).

To install packages in your virtual environment, you have to activate the environment. 
```
$ source .venv/bin/activate
```
And packages have to be installed using pip. You can find your package on [pypi](https://pypi.org/). For example, pandas:
```
$ pip install pandas==1.3.2
```


In VS code, you can also develop code with _Jupyter Notebook_. To be able to use _Jupyter Notebook_, you have to install Jupyter:
```
$ pip install jupyter
```

After that, you can just create a file with VS code on your project directory, e.g., on Nird. 
```
$ cd /tos-project2/NSXXXK/<username>/python
$ code test.ipynb
```

Then you have to select the Jupyter Kernel in the upper right corner. If you click on it will give you a selection of python environments you can choose from where you select your personal environment `~.venv/bin/python`.

Happy coding.



Necessary VS code extensions to make it work:
* [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
* [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
* [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

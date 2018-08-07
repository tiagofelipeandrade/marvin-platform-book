# Installing Toolbox as MacOS user

1. Toolbox will need some OS dependencies
```
sudo easy_install pip
brew install openssl graphviz
```

2. We strongly recommend the use of VirtualEnv and VirtualEnvWrapper
```
sudo pip install --upgrade pip
sudo pip install virtualenvwrapper --ignore-installed six
```

3. Spark installation (**Optional**)
```
curl https://d3kbcqa49mib13.cloudfront.net/spark-2.1.1-bin-hadoop2.6.tgz -o /tmp/spark-2.1.1-bin-hadoop2.6.tgz
sudo tar -xf /tmp/spark-2.1.1-bin-hadoop2.6.tgz -C /opt/
sudo ln -s /opt/spark-2.1.1-bin-hadoop2.6 /opt/spark
echo "export SPARK_HOME=/opt/spark" >> $HOME/.bash_profile
```

If you do not have /opt directory created, before unpacking spark, run:
```
sudo mkdir /opt
```

4. Marvin uses dafault values for these environment variables, but you can customize them (**Optional**)
```
echo "export WORKON_HOME=$HOME/.virtualenvs" >> $HOME/.bash_profile
echo "export MARVIN_HOME=$HOME/marvin" >> $HOME/.bash_profile
echo "export MARVIN_DATA_PATH=$HOME/marvin/data" >> $HOME/.bash_profile
echo "source virtualenvwrapper.sh" >> $HOME/.bash_profile
source ~/.bash_profile
```

5. Install python-toolbox
```
mkvirtualenv python-toolbox-env
setvirtualenvproject
pip install marvin-python-toolbox
```

6. Creating a new engine
```
workon python-toolbox-env
marvin engine-generate
```
Respond to the prompt and wait for the engine environment preparation to complete. Don't forget to start dev box before if you are using vagrant.

7. Test the new engine
```
workon <new_engine_name>-env
marvin test
```

8. Bring up the notebook and access it from your browser
```
marvin notebook
```

9. For more information
```
marvin --help
```

10. Youtube tutorial

[![Python Toolbox Install](http://img.youtube.com/vi/2iljFG9EZ_Q/0.jpg)](https://www.youtube.com/watch?v=2iljFG9EZ_Q "Python Toolbox Install")

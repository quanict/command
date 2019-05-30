# virtual environments using conda for the Anaconda Python 

## 1.Setup

### 1.1.Retrieve the Latest Version of Anaconda

    https://www.anaconda.com/download/

### 1.2.Download the Anaconda Bash Script

    curl -O https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh

### 1.3.Verify the Data Integrity of the Installer

    sha256sum Anaconda3-2019.03-Linux-x86_64.sh

Output

    45c851b7497cc14d5ca060064394569f724b67d9b5f98a926ed49b834a6bb73a  Anaconda3-2019.03-Linux-x86_64.sh

### 1.4.Run the Anaconda Script

    bash Anaconda3-2019.03-Linux-x86_64.sh



## 1.Check conda is installed and in your PATH

```command
conda -V
```

## 2.check update

```command
conda update conda
```

## 3.Create a virtual environment

```command
conda create --name myenv
conda create -n yourenvname python=x.x anaconda
```

## 4.Activate your virtual environment

```command
source activate yourenvname
```

## 5.Deactivate your virtual environment.

```command
source deactivate
```

## 6.Delete a no longer needed virtual environment

```command
conda remove -n yourenvname -all
```

## List all environment

```command
conda info --envs
```


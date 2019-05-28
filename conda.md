# virtual environments using conda for the Anaconda Python 

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


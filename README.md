# mlops-airbnb

## Instalando o Conda
- linux

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
chmod u+x https://miniconda3-latest-linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh -b
```

## Setting up environment
Crie um ambiente a partir do arquivo environment.yml

```bash
conda env create -f environment.yml
```

verifique a existência do ambiente e a versão do python

```bash
conda env list
which python
```
desative qualquer ambiente existente a ative o ambiente criado

```bash
conda deactivate
conda activate mlops
```

Agora basta iniciar o jupyterlab digitando o seguinte comando no terminal

```bash
jupyter-lab
```

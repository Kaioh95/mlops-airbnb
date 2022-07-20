# mlops-airbnb

## Participantes
- João Vitor Dias Xavier
- Kaio Henrique de Sousa

## Link para vídeo

- https://www.loom.com/share/b0b99033408149308f2d5d4103bfc81f

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

(ATENÇÃO!!! em caso de problema na instalação recomenda-se instalar os pacotes jupyterlab, scikit-learn, ipywidgets, jupyterlab_widgets individualmente)

```bash
const install --name mlops scikit-learn=1.0.2
```

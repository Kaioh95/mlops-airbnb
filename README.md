# mlops-airbnb

## Participantes
- [João Vitor Dias Xavier](https://github.com/joaovdxavier)
- [Kaio Henrique de Sousa](https://github.com/Kaioh95)

## Autor dos Scripts

- [Ivanovitch Silva](https://github.com/ivanovitchm)

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
exemplo:
```bash
const install --name mlops scikit-learn=1.0.2
```

### Executing Steps

este comando executa apenas o passo ``decision_tree``:
```bash
mlflow run . -P hydra_options="main.execute_steps='decision_tree'"
```
e este comando executa do passo ``download`` até o passo ``evalute``:
```bash
mlflow run . -P hydra_options="main.execute_steps='download,preprocess,check_data,segregate,decision_tree,evalute'"
```

### Excluido ambientes criados pelo mlflow

listando ambientes criados
```bash
conda info --envs | grep mlflow | cut -f1 -d" "
```

comando para excluir ambientes criados
```bash
for e in $(conda info --envs | grep mlflow | cut -f1 -d" "); do conda uninstall --name $e --all -y;done
```



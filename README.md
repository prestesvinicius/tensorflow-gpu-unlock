# Tutorial de Configuração TensorFlow GPU
Siga o passo-a-passo para concluir a configuração da sua GPU no TensorFlow

## 1. Requisitos
Antes de tudo você precisa confirmar que sua placa de vídeo NVIDIA é compatível com CUDA e CUDNN CUDA que são drivers desenvolvidas para acelerar o processamento com GPUs em Deep Learning.
Você pode buscar o seu modelo no site oficial [NVIDIA.Developer](https://developer.nvidia.com/cuda-gpus).

## 2. Instalação
Se a sua placa gráfica é compatível, podemos seguir com a instalação.

### 2.1 Visual Studio Community
Baixe a versão 2022 no site oficial da [Microsoft VSCommunity](https://visualstudio.microsoft.com/pt-br/vs/community/)
Depois de executar o setup modifique a versão, marque apenas a caixa com *"Desenvolvimento para Desktop com C++"*

### 2.2 Anaconda 3
Baixe o instalador pelo site oficial do [Anaconda Distribution](https://www.anaconda.com/download)
Execute o instalador e certifique-se de selecionar de marcar o quadro com a opção *"Add Anaconda3 to my PATH environment variable"*

### 2.3 CUDA e CUDNN
As versões compatíveis dos drivers para TensorFlow 2.10 (última versão que funciona no windows) são CUDA 11.2 e cuDNN 8.1
Você pode instalar pelo Anaconda Prompt usando o seguinte código:
```plaintext
conda create --name nome-do-ambiente python=3.10
conda activate nome-do-ambiente
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
```
Mantenha o seu Anaconda Prompt aberto, voltaremos a ele daqui a pouco.
Em um cmd comum, adicione os diretórios bin CUDA e cuDNN ao Path do seu PC, pelo comando:
```plaintext
export PATH="/c/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v11.0/bin:$PATH"
export PATH="/c/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v11.0/extras/CUPTI/libx64:$PATH"
export PATH="/c/tools/cuda/bin:$PATH"
```
Troque pelo endereço de instalação no seu PC.

### 2.4 TensorFlow
Como dito anteriormente, a versão mais atualizada do TensorFlow que habilita GPU pelo Windows é a versão 2.10, instale ela usando pip install, dentro do ambiente conda criado no Anaconda Prompt.
```plaintext
pip install tensorflow==2.10
```




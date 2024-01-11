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

![image](https://github.com/prestesvinicius/tensorflow-gpu-unlock/assets/112510714/6ef3b412-50f1-4778-a73c-8a3c2399f614)


Execute o instalador e certifique-se de selecionar de marcar o quadro com a opção *"Add Anaconda3 to my PATH environment variable"*

![image](https://github.com/prestesvinicius/tensorflow-gpu-unlock/assets/112510714/a1ae1d5f-8f4f-4709-a976-0707b42e0f9b)

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
Substitua pelo endereço de instalação no seu PC.
Ou faça de forma manual, pela barra de tarefas > Editar as variáveis de ambientes do sistema > Variáveis de Ambiente... > Path > Adicione manualmente os endereços dos diretórios.

![image](https://github.com/prestesvinicius/tensorflow-gpu-unlock/assets/112510714/01e24163-0f73-4f58-84e2-8253a9f29cdc)


### 2.4 TensorFlow
Como dito anteriormente, a versão mais atualizada do TensorFlow que habilita GPU pelo Windows é a versão 2.10, instale ela usando pip install, dentro do ambiente conda criado no Anaconda Prompt.
```plaintext
pip install tensorflow==2.10
```
Se for necessário utilizar outra combinação, acesse o [diretório do TensorFlow](https://www.tensorflow.org/install/source_windows?hl=pt-br#gpu) e confira as versões compatíveis entre si.

![image](https://github.com/prestesvinicius/tensorflow-gpu-unlock/assets/112510714/58ea23c1-2551-4090-943c-fde8cbfe0fa3)


### 2.5 Jupyter Notebook/Jupyer Lab
Abra o Anaconda Navigator no seu PC.

Na aba *"Environments"* selecione o ambiente que você criou para a configuração da GPU.

![image](https://github.com/prestesvinicius/tensorflow-gpu-unlock/assets/112510714/5ae622d2-62b0-4e66-9f31-d2f1a57f452a)

Depois de selecionado, volte para a aba *"Home"* e instale o Jupyter Notebook ou Jupyter Lab, de acordo com sua preferência.

![image](https://github.com/prestesvinicius/tensorflow-gpu-unlock/assets/112510714/3ef30324-bc69-4a6a-bfe7-6fcf9db4fefe)



## 3. Verificação
Pelo Anaconda Navigator, inicie o Jupyter Notebook/Jupyter Lab que você instalou e crie um arquivo .ipynb


Execute o seguinte código:
```python
import tensorflow as tf
print(tf.config.list_physical_devices())
```
Se seu output conter algo desse tipo:
```plaintext
[...PhysicalDevice(name=’/physical_device:GPU:0',device_type=’GPU’]
```

SUCESSO!! Agora você pode aproveitar a aceleração de GPU em seus projetos de Deep Learning usando TensorFlow.




# dio-desafio-projeto-bootcamp-baires-modulo7-processamento-de-imagens-com-ml
Desafio de Projeto Módulo 7
🔎 Projeto de Busca de Similaridade de Imagens
Este é um projeto de aprendizado de máquina que demonstra como construir um sistema de busca de similaridade de imagens usando modelos de deep learning e um índice de busca eficiente. O sistema permite que você envie uma imagem e encontre as imagens mais parecidas em um grande banco de dados.

⚙️ Como Funciona
O projeto utiliza um modelo de extração de características (encoder) para converter cada imagem em um vetor numérico. Esses vetores capturam as características visuais das imagens. Em seguida, um índice de busca de vizinhos mais próximos, criado com a biblioteca Annoy, é usado para pesquisar esses vetores de forma rápida e eficiente. A aplicação web serve como uma interface para que o usuário possa interagir com o sistema.

🧠 Modelos e Arquitetura
A arquitetura do modelo é baseada em uma abordagem de transfer learning para adaptar um modelo pré-treinado à tarefa de extração de características para busca de similaridade.

Modelo Base: O projeto utiliza o modelo BiT (Big Transfer) do TensorFlow Hub, pré-treinado com um grande volume de dados de imagens. Esse modelo serve como um extrator de características robusto.

Arquitetura: Acima do modelo base, camadas personalizadas foram adicionadas:

Uma camada Dropout para evitar o overfitting.

Uma camada Dense para reduzir a dimensionalidade das características para 256 dimensões. Este vetor é a "impressão digital" da imagem.

Uma segunda camada Dropout e uma camada Dense final foram usadas para a etapa de fine-tuning e classificação, mas a aplicação de busca utiliza o vetor de 256 dimensões como base para a similaridade.

🏷️ Conjunto de Dados e Categorias
O sistema de busca foi treinado com um conjunto de dados de imagens customizado, organizado em pastas. As categorias do projeto foram definidas pelos nomes dessas pastas.

Categorias: As "classes" para o modelo foram extraídas do nome de cada diretório. Por exemplo, todas as imagens na pasta laptops pertencem à categoria 'laptops'. Essas categorias foram usadas para validar o treinamento do modelo e, na aplicação final, para descrever as imagens retornadas. As 4 classes escolhidas foram, violão, notebook, guitarra, smart tv.

Finalidade: Na aplicação web, o nome da categoria é exibido como a legenda para cada imagem similar encontrada, confirmando que o sistema de busca está funcionando como esperado.

🛠️ Tecnologias Utilizadas
Python: Linguagem principal de desenvolvimento.

TensorFlow & Keras: Para carregar e utilizar o modelo de extração de características.

Annoy: Biblioteca para a criação do índice de busca eficiente.

Streamlit / Gradio: Frameworks utilizados para construir a interface web interativa.

Google Colab: Ambiente de desenvolvimento para executar o notebook.

🚀 Como Rodar o Projeto
O projeto foi projetado para ser totalmente funcional no Google Colab. Basta seguir as instruções e executar as células sequencialmente.

Abra o arquivo .ipynb no Google Colab.

Siga as instruções e execute as células do notebook uma a uma.

A última célula irá gerar um link público para a aplicação web.

📂 Estrutura do Projeto
notebook.ipynb: O notebook principal do Google Colab que contém todo o código do projeto, desde a preparação dos dados até o lançamento da aplicação web.

projeto_salvo/: Diretório que armazena os arquivos persistentes do projeto, como o modelo (.keras), o índice (.ann) e os mapeamentos (.p).

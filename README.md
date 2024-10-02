# Fine-tuning de Modelos de Linguagem com Python e Jupyter

### Grupo 38
- Pedro Vianna Silveira
- Rafael Silva Souza
- Rodrigo de Freitas Ornellas

---

### 🔗 Repositório do Código

[\[Link para o repositório GitHub\]](https://github.dev/rornellas/tech-challenge-3-ia4devs)

---

## 1. Introdução

#### Contexto e Motivação
Neste projeto, buscamos explorar o processo de **fine-tuning** em um **modelo de linguagem de grande escala (LLM)**, utilizando Python e Jupyter como ferramentas principais. Nosso foco está na adaptação do modelo a um dataset específico para aprimorar a capacidade de gerar respostas adequadas com base em descrições de produtos. Isso reflete um cenário real, no qual plataformas de e-commerce se beneficiam ao melhorar a interação com os usuários através de respostas mais precisas e contextualizadas.

#### Objetivos do Projeto
O projeto tem três metas principais:
1. Realizar o fine-tuning de um modelo de linguagem pré-treinado, especificamente o **unsloth/mistral-7b-instruct-v0.3-bnb-4bit**.
2. Avaliar a evolução do modelo após o fine-tuning, comparando com sua versão original.
3. Documentar detalhadamente o processo de ajuste fino, abordando os desafios e soluções encontradas.

---

## 2. Descrição do Problema

- **Problema**: Como adaptar um modelo de linguagem para responder perguntas a partir de descrições de produtos, utilizando um dataset específico? O objetivo é criar um sistema que compreenda melhor essas interações textuais e gere respostas úteis e relevantes.
- **Relevância**: Plataformas de e-commerce se beneficiam ao fornecer respostas rápidas e precisas às perguntas dos usuários, melhorando a experiência de compra. Um modelo ajustado às descrições de produtos é um passo essencial para alcançar esse objetivo.

---

## 3. Fundamentação Teórica

- **Modelos de Linguagem (Foundation Models)**: Usamos o **unsloth/mistral-7b-instruct-v0.3-bnb-4bit**, que serve como base para o ajuste fino.
- **Fine-tuning**: Processo de especialização de um modelo pré-treinado em uma nova tarefa específica.
- **Pré-processamento**: Realizamos a normalização de texto, incluindo decodificação de HTML (para lidar com texto codificado em ASCII).
- **Treinamento Supervisionado (SFT)**: Técnica utilizada para ajustar o modelo, fornecendo exemplos de entradas e saídas.

---

## 4. Metodologia

- **Ambiente de Desenvolvimento**: O projeto foi desenvolvido no **Google Colab** com suporte a GPU, garantindo eficiência durante o treinamento do modelo.
- **Preparação dos Dados**: Usamos a biblioteca `pandas` para manipulação e pré-processamento do dataset, incluindo normalização e limpeza dos textos.
- **Seleção e Configuração do Modelo**: Implementamos o modelo **Mistral** utilizando a biblioteca `transformers`, ajustando as entradas com tokenização adequada.
- **Execução do Fine-tuning**: O processo de fine-tuning foi realizado com o **SFTTrainer** da biblioteca `trl`, que nos permitiu parametrizar o ajuste fino de maneira eficiente.
- **Avaliação e Validação**: Testamos o modelo fine-tunado e comparamos seus resultados com o desempenho original, identificando ganhos significativos.

---

## 5. Implementação

- **Ferramentas e Bibliotecas Utilizadas**: 
  - **Google Colab**: Ambiente de desenvolvimento com GPU.
  - **Transformers e datasets**: Para manipulação e treinamento de modelos pré-treinados.
  - **Torch**: Base para as operações de deep learning.
  - **TRL**: Utilizada para treinamento supervisionado do modelo.
  - **Unsloth**: Implementação do modelo `unsloth/mistral`.
  - **Pandas** e **nltk**: Manipulação de dados e processamento textual.
  
- **Carregamento e Limpeza de Dados**: Utilizamos scripts personalizados para carregar e processar o dataset, com limpeza, normalização e exclusão de stopwords, preparando o conjunto para o treinamento.
  
- **Fine-tuning do Modelo**: O ajuste fino foi realizado com o `SFTTrainer`, onde utilizamos dados de entrada e saída específicos para treinar o modelo de forma supervisionada.

- **Geração de Respostas**: Implementamos uma função para gerar respostas automatizadas com base nas perguntas dos usuários e nas descrições dos produtos disponíveis no dataset.

---

## 6. Resultados

- **Comparação de Desempenho**: Ao comparar o modelo pré-treinado com a versão fine-tunada, observamos uma melhoria significativa na capacidade do modelo em fornecer respostas mais coerentes e ajustadas ao contexto das perguntas.
  
- **Avaliação Qualitativa**: A análise qualitativa das respostas geradas pelo modelo treinado demonstrou que o fine-tuning ajudou o modelo a compreender melhor a relação entre as perguntas e as descrições dos produtos.

---

## 7. Conclusão

- **Resultados Principais**: O fine-tuning trouxe melhorias substanciais ao desempenho do modelo, tornando-o mais adequado para a tarefa específica de responder perguntas baseadas em descrições de produtos.
  
- **Limitações e Desafios**: Enfrentamos alguns desafios durante o pré-processamento dos dados e na parametrização do modelo, mas esses problemas foram contornados com ajustes técnicos e melhorias no pipeline de dados.
  
- **Próximos Passos**: Futuras melhorias podem incluir a utilização de modelos maiores ou o uso de técnicas de data augmentation para melhorar a diversidade e representatividade dos dados

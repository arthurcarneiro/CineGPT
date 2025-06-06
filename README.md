# Cine GPT

## Como executar?

Para recriar o ambiente, execute no terminal o seguinte comando na pasta raíz dessa aplicação:
```
pip install -r requirements.txt
```

Você deve no arquivo Cine GPT.ipynb logo abaixo da declaração das bibliotecas inserir o seu token do huggingface. Exatamente no trecho abaixo, substituindo 'seu-token' pelo que foi provido pelo huggingface

```
TOKEN_HUGGING_FACE = 'seu-token'
```
Com isso feito você está pronto para inicializar o Cine GPT.


## Seguem algumas informações:


Pequeno assistente virtual (Cine GPT) para um indicador de filmes utilizando uma base como referência (RAG).

Foi utilizada a base de filmes do IMDB top 1000, restrita a 50 filmes para economizar em tokens.

Utilizando SentenceTransformers, convertemos o filme, genero e sinopse em embeddings. Utilizando FAISS encontramos filmes para uma pergunta do usuário.

Utilizando um modelo de linguagem generativo pela API do hugging Face, o Zephyr 7b para as respostas. O modelo é leve e performa bem para tarefas simples. Além disso o prompt inicial é enriquecido com informações relevantes sobre os filmes que foram dados como resultados dos embeddings.

Há um laço de interação contínua do usuário com a plataforma, por razão de limitação de memória o modelo não consegue dispor de uma memória sobre as consultas, mas é algo plenamente possível com essa arquitetura uma vez que se insira o contexto nos prompts seguintes.

Ao utilizar o assistente, pergunte continuamente e quando quiser encerrar digite 'sair'.

Bibliotecas utilizadas:

- huggingface_hub
- sentence-transformers
- pandas
- faiss-cpu


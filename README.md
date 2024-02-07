# AI-900 | Machine Learning
## Criando um passo a passo do Desafio proposto nas aulas de certificação AI-900.

#### *O metodo e fonte de dados usados nesse passo a passo estão referenciados ao [final deste documento](#final)*.

<br>

### 01 - Acessando recurso do Azure Machine Learning

Após as devidas configurações da conta Azure, (*Configure seu primeiro acesso ao Azure gratuitamente [clicando aqui](https://azure.microsoft.com/pt-br/free/)*), o proximo passo é criar um recurso de Machine Learning.

Para iniciar, cliquei na opção "Criar um recurso", depois pesquisei por **Azure Machine Learning**, em seguida é só clicar sobre o icone para criar o recurso.

![Img](./imgs/img00.gif)

<br>

### 02 - Configurando o Azure Machine Learning

No painel intitulado "*Noções Básicas*", na seção "*Detalhes do Recurso*", foi inserida a assinatura correspondente à cobrança no campo designado como "*Assinatura*". Posteriormente, foi especificado o "*Grupo de Recursos*" que irá incorporar o recurso a ser criado.

Em seguida, na seção "*Detalhes da Área de Trabalho*", foram fornecidos os detalhes do espaço de trabalho a ser estabelecido. 

![Img](./imgs/img01.png)

Considerando que o contexto era de um laboratório, as configurações aplicadas foram mínimas. Finalmente, o recurso foi criado ao selecionar a opção "*Consultar + Criar*". Após a aprovação da validação, cliquei em "*Criar*".

<br>

Uma vez que o recurso foi estabelecido, procedi clicando no botão "*Ir para o Recurso*", o que direcionou à página correspondente ao recurso em questão.

![Img](./imgs/img02.png)

Nesta interface, note a presença do botão denominado "*Iniciar o Estúdio*", cuja função é redirecionar para o estúdio do **Azure Machine Learning**. Como ilustrado na imagem abaixo:

![Img](./imgs/img03.png)

<br>

### 03 - Acessando o estúdio do Azure ML

Uma vez dentro do *estúdio Azure ML*, cliquei na opção denominada "ML Automatizado" localizada no menu à esquerda. Já na página subsequente que se abriu, cliquei na opção "Novo Trabalho de ML Automatizado". Como mostra o vídeo:

![Img](./imgs/img04.gif)

Na seção "Configurações Básicas", preenchi os campos "Nome do Trabalho", "Novo Nome do Experimento", "Descrição" e clique no botão "Avançar".

Em seguida, na opção "Tipo de Tarefa e Dados", selecionei a tarefa do tipo "Regressão". Após isso, cliquei em "Selecionar Dados", em seguida no botão "Criar". Na janela que se abriu, na seção "Tipos de Dados", preenchi os campos "Nome", "Descrição" e o "Tipo" definindo-o como Tabular. Em seguida cliquei em "Avançar".

<br>

### 04 - Ingestão de dados

Ja na parte "Fonte de Dados", escolhi a opção "De Arquivos da Web" e novamente cliquei no botão "Avançar".

No passo "URL da Web", informei a URL: https://aka.ms/bike-rentals correspondente ao conjunto de dados usado. No passo "Configurações", preenchi as configurações do conjunto e ao avançar na opção "Esquema", verifiquei os tipos de dados. Finalmente, ao clicar em "Avançar", chequei as configurações criadas para o ativo de dados e em seguida cliquei no botão "Criar".

![Img](./imgs/img05.gif)

Na seção "Configurações de Tarefas", selecionei o conjunto de dados previamente importado. Posteriormente, na opção "Coluna de Destino", designei a coluna "rentals" como alvo.

Já na seção "Limite", foram inseridos os valores conforme indicado na imagem abaixo. Após ativei a opção "Habilitar Encerramento Antecipado".

![Img](./imgs/img06.png)

<br>

### 05 - Validando o modelo

Já na página "Validar e testar", na opção "Tipo de validação", escolhi "Divisão de validação de treinamento".

Ao avançar, já na parte de "Computação", mantive os valores informados no print:

![Img](./imgs/img07.png)

Agora cliquei em "Avançar" e examinei as configurações do trabalho, cliquei em "Enviar trabalho de treinamento".

Ao finalizar o trabalho de treinamento, o modelo ficou disponível na opção do menu esquerdo "Modelos".

![Img](./imgs/img08.png)

<br>

### 06 - Analisando as Métricas do modelo

Para acessar as métricas do modelo treinado, fui até a página do modelo e acessei o link disponibilizado com o nome do trabalho criado. Como mostra o vídeo:

![Img](./imgs/img09.gif)

<br>

### 07 - Testando o modelo

No menu a esquerda, cliquei em "Pontos de extremidade" e selecionei o ponto correspondente ao modelo gerado. Em seguida acessei a aba "Testar".

Para esse teste foi utilizado o json abaixo:

<code>
{
  "input_data": {
    "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]
  }
}

</code>

<br>

A previsão resultante do modelo foi estabelecida como: 361.95, como confirma o print abaixo:

![Img](./imgs/img10.png)

<br>

<a id="final"></a>

### *Referências*:

- Explore Automated Machine Learning in Azure Machine Learning - [*Microsoft Learn*](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)

- [Fonte de dados](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/main/data/ml/daily-bike-share.csv)

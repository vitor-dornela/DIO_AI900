# DIO_AI900_Lab1
Repositório para ser usado no lab1 de IA da DIO

1- Criar Workspace do Azure Machine Learning
Dashboard > Create a resource > Marktplace > Azure Machine Learning
Preencher dados de servidores, manter Container Registry 'none' > Review + Create

2- Abrir workspace, ir para ML automatizado, clicar em 'Novo Trabalho de ML automatizado', clicar em avançar após cada etapa a seguir:
-- Config básica 
  Nome do trabalho: msleam-bike-automl
  Novo nome do experimento: msleam-bike-rental
-- Tipo de tarefa e dados
  Selecionar tipo: Regressão > Criar
  Nome: aluguel de bikes
  Tipo: Tabular
-- Fonte de Dados
  De arquivo da WEB > https://aka.ms/bike-rentals]
-- Configurações
  Formato do arquivo: Delimitado
  Delimitador: Vírgula (Exemplo: Campol,Camp02,Camp03)
  Codificação: UTF-8
  Cabeçalhos de coluna: Somente o primeiro arquivo tem cabeçalhos
  Ignorar linhas: Nenhuma

3- Selecionar tarefa "aluguel de bikes" > avançar
-- Config de tarefas
Coluna de destino: rentals (Integer)
-- Config adicional
Métrica primária: NormalizedRootMeanSquaredError
  -> desmarcar 'Explicar o melhor modelo' & 'usar todos os modelos suportados'
Modelos: RandomForest; LightGBM
-- Limites
  Máximo de avaliações
  3
  Máximo de avaliações simultâneas
  3
  Máximo de nós O
  3
  Limite de pontuação da métrica
  0,085
  Tempo limite do experimento (minutos)
  15
  Tempo limite de iteração (minutos)-
  15
   -> Habilitar encerramento antecipado
-- Validar e testar
TIPO de validação: Divisão de validação de treinamento
Validação de percentual de dados: 10
-- Computação
  Manter padrão

4- Enviar trabalho de treinamento

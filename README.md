# Calcular indicadores financeiros
A cada dia que passa se totalizam números incontáveis de dados disponiveis em todas as  áreas de con conhecimento que nos cerca. Sendo assim,devido ao grande volume de  informaçoes, nos  tornamos incapazes de analisá-los com eficiência de forma manual.  A tecnologia tem papel fundamental para eficácia deste tipo de  análise, pois nos permite trabalhar com um grande volume de dados em um tempo bem reduzido. 

Este projeto tem como objetivo extrair e manipular informações a partir dos dados, realizar  comparações de ativos,automatizar  operações  que  antes  eram  manuais  e  demandam muito tempo. O projeto tem viés de  implementar indicadores e estratégias de forma fácil e rápida, utilizando o poder da tecnologia.

## Ambiente de desenvolvimento do projeto
O projeto foi escrito em PHYTON 3.7,que é uma  linguagem com sintaxe clara e direta, que permite que você invista mais tempo no desenvolvimento de ideias e aplicações.Neste caso utilizei a ferramenta ‘Jupyter Notebook’, para que cada funcionalidade fosse explicada de forma detalhada. A biblioteca escolhida para  manipulação da estrutura de dados foi a Pandas,Pandas-datareader e  a extensão jupyterlab plotly. Gerenciei tudo com o Git e Github, provedor que ultilizei para compartilhamento do projeto.

###### Instalando as bibliotecas utilizadas no processo: 
 ```
 python -m pip install --upgrade pip 
 pip install pandas-datareader 
 pip install jupyterlab 
pip install plotly 
```


Logo após a instalação das bibliotecas dentro da pasta eu iniciei o notebook com o comando ‘Jupyter notebook’ busquei os dados e filtrei com o comando **head** para conseguirmos selecionar um conjunto das primeiras linhas e o comando **tail** para as últimas.
- Obtém as primeiras 5 linhas
 `exemplo.head ()`


 - Obtém as últimas 5 linhas
`exemplo.tail()`
###### Podemos facilmente filtrar os períodos que gostaríamos de analisar ultilizando:

 `Exemplo[‘  ’]. head()
  
 Analisar a variação do preço do ativo,que é através de um gráfico de distribuição.utilizei escala 
 
 `daily_log_returns = np.log(exemplo.Close.pct_change()+1)`

## Plotando Candlestick 
Plotando o candlestickUma  técnica  muito  utilizada  por  investidores  é  a  análise  técnica  ouanálise  gráfica,  sendo  esta  análise  fortemente  baseada  no  que  chamamos  decandlestick  ou  candelabros  japoneses.  Ao  contrário  do  gráfico  de  linhas,onde  conseguimos  representar  apenas  um  dos  quatro  preços  disponíveis  doativo  (abertura,  fechamento,  máxima  ou  mínima),  o  candlestick  dá  apossibilidade  de  representar  todos  os  preços  no  mesmo  gráfico.

## Indicadores Tecnicos 

O  Primeiro  indicador  técnico ultilizado foi o média móvel. Média  móvel  em  estatística  é  um  valor  calculado  a  partir  de  uma  sériede  valores  de  diferentes  amostras  de  uma  população  e  foi  utilizado  para suavizar  os  dados  desta  amostragem,  sendo  muito  utilizado  como  um indicador  de  tendência  na  análise  de  ativos,  ou  seja,  indicando  se  o  ativo propende  a  continuar  uma  tendência  de  alta  ou  
O segundo indicador tecnico aplicado foi a   média  móvel  exponencial. Que  tem  como característica  diminuir  a  defasagem,  isto  é,  a  velocidade  com  que  ela  muda em  relação  ao  preço,  sendo  mais  rápida,  pois  ela  aplica  um  peso  maior  aos preços mais recentes. Inicia-se  calculando  o  coeficiente  de  multiplicação  para  o  período N  que  queremos  trabalhar,  que  chamaremos  de  K.  A  seguir  calcula-se  uma média  móvel  simples  para  os  primeiros  N  dias,  que  servirá  de  ponto  inicial para  os  cálculos.  A  partir  do  período  N+1  multiplica-se  o  preço  de fechamento  por  K,  multiplicando  a  MM  do  dia  anterior  por  (1-K)  eadicionando 2 aos números. Isto resulta nas seguintes equações:

Bandas de Bollinger foi aplicado por ser um indicador  capaz  de  medir  a  volatilidade  do preço.  Por  exemplo,  supondo  que  o  preço  atue  em  uma  zona  de  equilíbrio, ora  variando  para  cima  e  ora  variando  para  baixo,  este indicador  ajuda  na  visualização  de  pontos  de  mínimos  e pontos  de  máximos  no  preço,  ajudando  a  identificar  quando os  preços estão muito  valorizados  ou  muitos  desvalorizados.  Ao  identificar  que  um  preço está  subvalorizado,  tende-se  a  efetuar  uma  compra  esperando  que  o  preço volte a  subir,  ou  efetuar uma  venda, quando  supervalorizado,  esperando que o preço volte a cair. Este  indicador  caracteriza-se  pelo  desenho  de  duas  linhas  abrangendo um “canal” de preço, criando uma banda superior e uma banda inferior.
O cálculo  é realizado através da aplicação de uma média móvel  de  20 períodos  ao  preço de  fechamento  somado  a dois  desviospadrões de 20 períodos.



```
 Banda Superior = Média Móvel Simples (20 dias) + (2 x Desvio Padrão de 20 dias)
 Banda Inferior = Média Móvel Simples (20 dias) – (2 x Desvio Padrão de 20 dias) 

```

##   Gravar arquivo

import csv
c = csv.writer(open("indicadores.csv", "wb"))
c.writerow(["Timestamp","media-movel","bollinger-bandes","media-movel-exponencial",])

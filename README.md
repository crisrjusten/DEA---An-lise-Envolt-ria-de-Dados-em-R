#Pacote rDEA-- DEA---An-lise-Envolt-ria-de-Dados-em-R
Script em R para análise envoltória de dados - dado contábil de 92 municipios do RJ - eficiência de arrecadação de imposto
#script R - cristiane justen 

#limpar workspace

rm(list=ls())

#chamar bibliotecas para análise - instalar pacotes abaixo (utilizar: install.packages)

library(corrplot)

library(plotrix)

library(rDEA)

#importar base de interesse

base <- read.csv2("file:.../dados.csv")

#analise descritiva das variaveis analisadas para DEA

desc <- summary(base)

#correlação das variáveis utilizadas no DEA

cor_base <- cor(base)

corrplot(cor_teste1, type = "lower", method = "number",tl.col = "black", number.cex = .5)

#fazer análise envoltória dos dados para 92 municípios do RJ- Escolher variável imput e output
municipio= 1:92

Y<- cluster_dea[c("Var_A")]

X <- cluster_dea[c("Var_B","Var_C","Var_D","Var_E", "Var_F")]

d_naive <- dea(XREF = X, YREF = Y, X=X[municipio,], Y=Y[municipio,],model = "output",RTS = "non-increasing")

d_naive

#Fim da análise envoltória de dados

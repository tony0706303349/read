# read
getwd()
setwd("D:\\Users\\User\\Desktop\\Tony")
library(readxl)
rm(list = ls())
Data=read_excel("D:\\Users\\User\\Desktop\\Antony\\Kemri\\STIData.xls")
View(Data)
which(duplicated(Data$IdNumber))
Data=Data[duplicated(Data$IdNumber)==FALSE,]
#Inferential Analysis####
#Association#
#1. Pearson's Chi-square test

Tab1=table(Data$C3StiYesno,Data$Sex...47)
Tab1
dimnames(Tab1)=list(STI=c("No","Yes"),Gender=c("Female","Male"))
Tab1
chisq.test(Tab1,correct = F)
#2.Fisher's exact
Tab2=table(Data$C3StiYesno,Data$A5MaritalStatus)
Tab2
fisher.test(Tab2)
#3. McNemar
mcnemar.test(Tab1)
cor

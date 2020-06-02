How to calculate the Palmer Drought Severity Index (PDSI)
    
#prepare the data used & the library 

#Instal the percintcon, SPEI and scPDSI and use these library
library(precintcon) 
library(scPDSI)
library(SPEI)

#data used for the calculation are 
    #1. Monthly precipitation series without NA [mm](p)
    #2. Monthly potential evapotranspiration (PE)

#prepare daily ranfall data

#iMPORT THE DAILY RAINFALL DATA 
pric<-read.csv(choose.files())
pric

#calculate the daily rainfall using prcintcon.daily first
pric.d<-as.precintcon.daily(pric)
View(pric.d)

now calculate (P) Which is the Monthly precipitation series without NA [mm]

P<-as.precintcon.monthly(pric.d)
View(P)

#export P the Monthly precipitation series without NA [mm]
sink(P.csv)
print(P)
sink()

#go to the directory where the output (p) is stored in my case C drive Document 

#Calculate PE
  #2. Monthly potential evapotranspiration (PE) USING SPEI package 
#first prepare the Tavg data in excel 
#calculate Tavg 
#import Tavg data
Tavg<-read.csv(choose.files())
View(Tavg)
#now
# calculate PE using SPEI thornthwaite model
 PE<-thornthwaite(Tavg$Tavg, lat = 13.9731)
View(PE)

#you can also calculate PE using penman
#now export the output (PE) as csv
#export output
sink("PE.csv")
print(PE)
sink()

# go to the directory where the data exported 
  (c drive document) In may case

# prepare the PSDI data as (combing the P & PE output)
# Import the data 

Pdsi_data<-read.csv(choose.files())
View(Pdsi_data)

library(scPDSI)

#now we can calculate the PSDI which is drought indicator and map it 
#calculate PDSI & Plot 
first assign the p and PE data 

PE<-Pdsi_data$PE
P<-Pdsi_data$P

sc_pdsi<-pdsi(Pdsi_data$P, Pdsi_data$PE, start = 1977, sc=FALSE)


#plot PDSI
plot(sc_pdsi)

#plot PHDI
plot(sc_pdsi, index = "PHDI")

#plot weighted PDSI
plot(sc_pdsi, index = "WPLM")

*****************Thank you for waching if you like it share it*******************
If you have comment & questions please send me 

options(PDSI.coe.K1.1 = 1.6)


drought intensity???

help(drought) 

# covid_data
SIR models on the pandemic affecting three countries (UAE, Oman, Kuwait)

# **SIR Models on COVID data**

### **Data Source:**
https://www.ecdc.europa.eu/en/covid-19/data

### **Project Objective:**
The data consists of COVID cases over all countries from its origin until 2021. The three countries used for analysis are Kuwait, UAE, and Oman. We have used analysis to determine the exponential and logistic growths of all waves of each country. We have used SIR models to model a prediction on the different waves of each country. We have modified the SIR models by adding few more parameters in relation with behaviour psychology. Python was used for this project, and matplotlib was used for all the visualizations.

### **SIR models:**

Following notations are used when defining the SIR model:

S: Susceptible state

I: Infected/infector state

R: Removed state (either recovered or dead)

The transition from system to system is as follows:
S -> I -> R

The population size for each country is considered ‘N’, and for data modelling, this N is considered constant for all days. “S” is the number of potentials that can be infected via COVID19. “I” is the number of currently infected at any point ‘t’, and also the number of infectors that might infect other potentials. “R” is the number of removed, either recovered from the virus or dead from the virus.

We consider any potential to be infected is removed (recovered or dead) after 10 days. From the aforementioned parameters, we can write:

S + I + R = N (constant)

For normalization of values, we use: {S/N,I/N,R/N} 

We make the following assumptions:

S -> I is aSI for some constant ‘a’. Susceptible ‘S’ has a relation with Infected ‘I’ as our model assumes the “susceptible” to get in contact with the virus to become “infected”. There, let ‘a’ be some rate of flux, and once a susceptible number has turned infected, it will never revert to susceptible (even after 10 days when it is removed). This is because we assume once infected and recovered, they cannot be infected again.

The rate of ‘S’ can be written as: dS/dt= -aSI (eqn 2.1), minus sign because the number ‘S’ will only decrease with time because of our assumption.

S -> I and I -> R for some constants ‘a’ and ‘b’. The relation between S and I have already been established. Now after some defined number of days, the infected ‘I’ are moved to removed, that is, they are either recovered from the virus or are dead. Either way the infected ‘I’ is decreased. However, for some constant ‘a’ the infected is increased as the susceptible ‘S’ get in contact with the virus. Therefore, The rate of ‘I’ can be written as: dI/dt= aSI-bI (eqn 2.2), minus(-) bI because the number ‘I’ will decrease after a certain constant ‘b’ and ‘R’ will increase. Plus(+) aSI because the number ‘I’ increases for some constant ‘a’.
Given the above rate of ‘I’, rate of ‘R’ can be written as: dR/dt= bI (eqn 2.3), for some constant ‘b’.

According to the SIR model, when Susceptible is close to 1, the exponent r ≈ a – b, therefore, a = r + b

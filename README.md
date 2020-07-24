# BRSPFIT
All Matlab code were written in Matlab Version R2017a.
To test our codes please save all files in the same computer folder.
To run our optimization algorithm used to find optimized model parameters please open: resultados_19072020_otimizar.m in Matlab, it should Run in versions R2017a or above.
Algorithm is set to run the optimization of the SUEIHCDR Model for Brazil and Sao Paulo.
The setting parameter to run optimizations are:
Iteracoes: the number of iterations to run: 5000 iterations take approximately 7-8 minutes to run; 15 minutes for both the state and country. For purpose of testing good Fits can be achieved with less iterations. 
globalSkip: number of iterations before code resets to initial guess.
Peso_RAND: Weight of randomness on next iterations. It can be changed depending on the accuracy of the initial guess.
Peso_Atual: Weight of current optimal solution in next iteration; it can be changed depending on the accuracy of the initial guess.
NROD: Number of iterations for CI Determination. Suggestion 300.
 
Optimization using genetic algorithm to demine optimal strategy and window sizes were done using ESTECO’s mode Frontier (Esteco s.p.a; 2017R4-5.6.0.1).To test our objective function used (FuncaoObjetivo_Software.m)  in the software please open in Matlab the file: Test_FuncaoObjetivo_Software.m. This algorithm can be used to test different scenarios one by one. It uses optimized results found in the file optimized_results_28052020.xls.
Input parameters are:
CP: value for the parameter alpha after present day.  Setting it to zero makes protection percentage continue in the same level of the day of the analyses. Negative values make protection decrease with time and positive values make protection values increase with time. 
ESTRATEGIA: By changing ESTRATEGIA 3 Strategies can be tested: 1 for stepping down 2 for intermittent or 3 for Constant social distance strategy.
JANELA: By changing JANELA the number of days per window can be changed; Values: 1 for 40 days 2 for 60 days and 3 for 80 days 
NOVOSD: 2 x the maximum SD values for strategies 1 and 2, 4 x the SD value for strategy 3.
TEMPOCP %number of days from which protection stays constant x 10. RANGE USED: min=300 %max=5000
%Region: 1 for Brazil 2 for Sao Paulo


This zipped folder contains 19 files including this one. Please save all files in the same computer folder.
There are 5 .xls files:
dados_estados_completo_28052020.xls contains data for Acc Cases Acc Death and recovered cases for Brazil and São Paulo.
Data_google_apple_28052020.xls contains mobility data from Google and Apple for Brazil and São Paulo.
guesses_28052020_02.xls contain initial parameter guesses for optimization algorithm.
optimized_results_28052020.xls contains results from optimization run for the submission of the article. 
PAIS_POP_FATOR1_2_28052020.xls contains country of Brazil and State of Sao Paulo population, and correction factors for cases and deaths used. 

There is one .DAT file:
Parameters_19072020.DAT: it contains the results from the last optimization run on May282020

There are 12 .m files:
Funcao_GOOGLE_APPLE_28052020.m : Function that estimates social distancing from Google and Apple data.
FuncaoObjetivo_Software.m: Objective Function used to find optimal strategy and window size in ESTECO’s mode Frontier (Esteco s.p.a; 2017R4-5.6.0.1). 
Test_FuncaoObjetivo_Software.m: Algorithm intended to help test objective function 
FuncaoObjetivo_Software.m
getA_OS_11.m: operational for solving the model
RK4_OS.m: runge kutta order 4 to solve the model
SUEIHCDR_OS_19072020.m: SUEIHCDR model.
SUEIHCDR_OS_28052020_CASES.m: SUEIHCDR model algorithm to test future scenarios where we manipulate social distancing and protection in future dates.
otimizador_OS_19072020.m: operational: optimization algorithm used to find model parameters
Plot_modeloptimization_19072020.m: function used to determine and plot 95% confidence intervals of model parameter pertubations
plot_areaerrorbar_Os: Auxiliary function to Plot_modeloptimization_19072020.m to include CI with shaded color 
plot_areaerrorbar_Os_yright: Auxiliary function to Plot_modeloptimization_19072020.m to include CI with shaded color for righ-side axis data
Resultados_19072020_otimizar.m: Algorithm intended to run optimization of model parameters for Brazil and Sao Paulo. 

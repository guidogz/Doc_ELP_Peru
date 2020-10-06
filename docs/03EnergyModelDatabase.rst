



3.2 Datos e información
+++++++++


.. figure:: img/RES_Energia.png
   :align:   center
   :width:   700 px

Como ya se ha mencionado en "Data Processing", el modelo OSeMOSYS de energía y transporte está compuesto por diferentes comodities y fuels que son propios de cada país o sistema. Ahora trataremos la configuración del modelo OSeMOSYS, esta se da a través de los siguientes items:

 - *Sets*
 - *Parameters*
 - *Variables*
 - *Obejetive functions*
 - *Constraints*

Nosotros trataremos con un modelo simple, el cual es la vesión más manejable, por el momento debido a las necesidades, en el modelo OSeMOSYS Perú. Cada item está compuesto por un conjunto de items y sus valores son particulares del sistema a modelar, a continuación mostaremos todos estos para la cnfiguración de un modelo simple, lo cual sisgnifica que nuestra función objetivo de costo es corta. 


================== ============================ ==================================== ========= ======================================== 
                                       Items de configuración para un modelo simple
---------------------------------------------------------------------------------------------------------------------------------------  
      Sets          Parameters                   Variables                           Ojective          Constraints
                    ("Insumos")                  ("salidas")                         functions
================== ============================ ==================================== ========= ========================================   
EMISSION           AccumulatedAnnualDemand      AccumulatedNewCapacity               OFS_Cost  Acc1_FuelProductionByTechnology
FUEL               AnnualEmissionLimit          AnnualEmissions                                Acc2_FuelUseByTechnology
MODE OF OPERATION  AnnualExogenousEmission      AnnualFixedOperatingCost                       Acc3_AverageAnnualRateOfActivity
REGION             AvailabilityFactor           AnnualTechnologyEmission                       CAa1_TotalNewCapacity
STORAGE            CapacityFactor               AnnualTechnologyEmissionByMode                 CAa2_TotalAnnualCapacity                        
REGION             CapacityOfOneTechnologyUnit  AnnualVariableOperatingCost                    CAa5_TotalNewCapacity        
TECHNOLOG          CapacityToActivityUnit       CapitalInvestment                              CC1_UndiscountedCapitalInvestment        
TIMESLICE          CapitalCost                  Demand                                         E2_AnnualEmissionProduction            
YEAR               CapitalCostStorage           DiscountedSalvageValue                         EBa10_EnergyBalanceEachTS4            
                   DepreciationMethod           DiscountedTechnologyEmissionsPenalty           EBa1_RateOfFuelProduction1                          
                   DiscountRate                 NewCapacity                                    EBa2_RateOfFuelProduction2              
                   EmissionActivityRatio        NewStorageCapacity                             EBa4_RateOfFuelUse1            
                   EmissionsPenalty             NumberOfNewTechnologyUnits                     EBa5_RateOfFuelUse2           
                   FixedCost                    ProductionByTechnology                         NCC1_TotalAnnualMaxNewCapacityConstraint              
                   InputActivityRatio           ProductionByTechnologyAnnual                   NCC2_TotalAnnualMinNewCapacityConstraint          
                   ModelPeriodEmissionLimit     RateOfActivity                                 OC1_OperatingCostsVariable             
                   ModelPeriodExogenousEmission RateOfProductionByTechnology                   OC2_OperatingCostsFixedAnnual            
                   OperationalLife              RateOfProductionByTechnologyByMode             SI6_SalvageValueStorageAtEndOfPeriod1                 
                   OperationalLifeStorage       RateOfUseByTechnology                          SV3_SalvageValueAtEndOfPeriod3      
                   OutputActivityRatio          RateOfUseByTechnologyByMode                    SV4_SalvageValueDiscountedToStartYear            
                   REMinProductionTarget        SalvageValue                                   TAC1_TotalModelHorizonTechnologyActivity      
                   RETagFuel                    SalvageValueStorage                            Short_Code_Equations                               
                   RETagTechnology              TotalAnnualTechnologyActivityByMode                            
                   ReserveMargin                TotalCapacityAnnual                                                   
                   ReserveMarginTagFuel         TotalTechnologyAnnualActivity                                    
                   ReserveMarginTagTechnology   TotalTechnologyModelPeriodActivity                                    
                   ResidualCapacity             Trade                                                    
                   SpecifiedAnnualDemand        UseByTechnology                                                  
                   SpecifiedDemandProfile                                                                              
                   TradeRoute                                                                                        
                   VariableCost                                                                                             
                   YearSplit                                        
================== ============================ ==================================== ========= ======================================== 
*Fuente: Propia*
 
No todos estos items han sido insertados en el modelo, debido que se ha trabajado un modelo que se acomoda más a las necesidades del Perú, ahora se pueden encontrar todos los valores de corespondiente a todos los item de configuración en `Items <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.


3.2.1 Sets
---------



Los sets son el conjunto de configuraciones que son establecidos para el modelo, estos 
son particulares por país y región, para su configuración se debe tener un análisis 
del sistema a modelar, los sets se muestrana contiuación.

 - *Región*
 - *Year*
 - *Timeslices*
 - *Emissions*
 - *Commodity*
 - *Technology*
 - *Mode of operation*


3.2.1.1 Región
---------

Para El Perú se ha hipotetizado una sola región para poder simplificar el análisis de nuestro sistema, se puede mencionar que el modelo TIMES se considera 4 regiones, centro, norte, oriente y sur.

+----------+---------------+
|región(es)|   Perú        |
+----------+---------------+
*Fuente: Propia*



3.2.1.2 Año
---------


Los años de análisis se consideran desde el 2015 hasta el 2050, este es el marco de tiempo de horizonte de estudio para el modelo de energía y transporte.

=========== ========== ===========
Parámetro   Inicio      Final        
=========== ========== ===========
Año         2015        2050
=========== ========== ===========
*Fuente: Propia*




3.2.1.3 Timeslices
---------

En el modelo de OSeMOSYSY Perú se han tomado una fraccion anual de 2 para un escenario alto y de 4 para un escenario medio y bajo.


============== ===============
Timeslice        Perú
============== ===============
An_alto          0.5
An_bajo          0.25
An_medio         0.25
============== ===============
*Fuente: Propia*



3.2.1.4 Emissions
---------

Para las emisiones se han considerado todos los tipos de gases de efecto invernadero (GEI) que son resultado de la actividad de los procesos, como CO2, CH4 y N2O, todos estos son transformado en CO2 euivalentes, en la tabla a continuación se puede observar estos factores de equivalencia.

========== ============ ============ ============
Parámetro       CO2          CH4          N2O              
========== ============ ============ ============
Factor           1           21           310
========== ============ ============ ============
*Fuente: Anexo 2 del informe 9 del PROSEMER*



3.2.1.5 Commodities
---------

Los commodities son los bienes, insumos, productos, etc. Estos ingresan a cada 
tecnología para ser transformados y procesados en otros comodities dentro de toda 
la cadena energética, en el Perú contamos con una gran variedad de commodities desde
insumos primarios como bosta y yesta para producción de carbón hasta la electricidad 
generada por cada tecnología eléctrica y los combustibles consumidos por el sector
transporte, las etiquetas para cada commodity considerados se muestran a continuación.
Los commodities se pueden encontrar en Anexos Fuels_. 

.. _Fuels: https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/


+--------------------+-----------------------------------------------------------------------+
| Combustibles       | Los combustibles fósiles son residuos de materia orgánica obtenidos   |
| Fósiles            | de forma extrativas, estas son crudo, gas natural y carbón.           |
+--------------------+-----------------------------------------------------------------------+
| Biocombustibles    | Son los combustibles que son sintetizados a partir de materia organica|
|                    | tales como la cañade azucar, oleaginosas y microalgas                 |
+--------------------+-----------------------------------------------------------------------+
| Electricidad       | La electricidad como commodity, es un producto de la generación de    |
|                    | diferentes tipos de tecnología como la combustión, fotovoltaico.      |
+--------------------+-----------------------------------------------------------------------+
| Demandas de        | Para las demandas de trasnporte puede ser de pasajeros públicos y     |
| Transporte         | privados y carga, falta aún poner esta parte.                         |
+--------------------+-----------------------------------------------------------------------+
| Productos de       | Actualmente se exporta una parte de hidrocarburos y gas natural.      |
| Exportación        |                                                                       |
+--------------------+-----------------------------------------------------------------------+
*Fuente: Propia*


3.2.1.6 Technologies
---------

Los procesos o tecnologías son representados en forma de bloque y pueden tener o no una 
entrada de commodities, sin embargo, siempre tienen una salida de commodities, Los procesos 
tienen involucrados costos como CAPEX(Capital Expenditure), OPEX (Operacional Expenditure), los 
costos examinados por capacidad para las plantas de gas y refinerías han sido estudiadas 
para tener datos con los cuales poder suministrar al modelo. Las principales tecnologías 
para el peru se muestran a continuación.

+--------------------+----------------------------------------------------------------------+
|Producción          | La producción de commodities incluye extración, procesamiento,       |
|                    | transformación de materia primaría hasta llegar a ser commodity.     |
+--------------------+----------------------------------------------------------------------+
|Importaciones       | Importaciones incluyen todos los procesos y acciones comerciales para|
|                    | lograr el suministro de commodities al país.                         |
+--------------------+----------------------------------------------------------------------+
|Refinería           | Refinería incluye todo el procesamiento de crudo para la obtención   |
|                    | de los subproductos como la gasolina o el diesel.                    |
+--------------------+----------------------------------------------------------------------+
|Carboneras          | Carboneras incluye el proceso de extracción de una mina carbón       |
|                    | mineral y trasnformación de en carbon vegetal.                       |
+--------------------+----------------------------------------------------------------------+
|Planta de gas       | Las plantas de gas incluye la licuación, transporte de gas           |
|                    |                                                                      |
+--------------------+----------------------------------------------------------------------+
|Plantas eléctricas  | En las plantas eléctricas se incluye todos las plantas de diversos   |
|                    | tipos de tecnologías como las hidroelectricas, termoelectricas, etc. |
+--------------------+----------------------------------------------------------------------+
|Transmisión         | La transmisión eléctrica incluye todos las formas de transmision en  |
|eléctrica           | alta y media tensión.                                                |
+--------------------+----------------------------------------------------------------------+
|Distribución        | La distribución eléctrica incluye distribución en baja tensión       |
|eléctrica           | hasta el usario final.                                               |
+--------------------+----------------------------------------------------------------------+
|Distribución        | La distribución energética incluye todos los medios y procesos para  |
|energética          | la repartición de los productos.                                     |
+--------------------+----------------------------------------------------------------------+
|Transporte          | Transporte en el Perú  incluyen todos las formas de transporte tanto |
|                    | carretero (pasajero y carga), ferroviario, naval, aéreo.             |
+--------------------+----------------------------------------------------------------------+
|Residencial, comer- | Esta tecnología incluye todos los procesos de transformación de      |
|cial y carga        | energía para los sectores residencial, comercial y carga.            |   
+--------------------+----------------------------------------------------------------------+
|Agropecuario, Pesqu-| Estas tecnologías incluyen todos los procesos de ransformacion de    |
|ero, industría      |  energía  para los sectores agropecuarios, minero e industría.       |
+--------------------+----------------------------------------------------------------------+
*Fuente: Propia*

 Todas las tecnologías se puede ver a en Anexos Tecnologías_.

.. Hay que cambiar este hyperlink

.. _Tecnologías: https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/ 



3.2.1.7 Mode of operation
---------

Para los procesos se ha hipotetizado un modo de operación, lo que quiere decir que por cada inpt solo obtenemos un tipo de output.





3.2.2 Parameters
---------

Los parámetros son los insumos del modelo, han sido completados con información obtenida de las diferentes fuentes de información, como publicaciones oficiles de los diferentes ministerios, publicaciones de entidades internacionales, papers científicos publicados, etc.  


3.2.2.1 Accumulated Annual Demand
---------

El Accumulated Anual Demand es la demanda anual de energía en el Perú, esta comprende la demanda de energía primaría y secundaría en sus diferentes formas como crudo, leña, bagazo, bosta y yareta para la energía primaria; y en derivados de petróloe, gas natural, GLP, biocombustibles, y mexcla de estos como Diesel-B5, gasohol, etc. También comprende las demandas finales de energía de los diferentes sectores, como transporte, comercial, público, residencial, minero, agro y pesca; tambien exportaciones de energía, todos los valores han sido tomados de los balances nacionales de energía y se han hecho las prediciones en baso a variaables exógenas como PBI, la población y la tendencia. A continuación se presenta una tabla con los valores de demanda correspondientes a las demandas de los todos los fuels correspondientes s la energía primaria, secundaria, neta y exportaciones.


========================================= ========== ========== ========== ==========
                      Damanda de energía en el Perú (PJ)
------------------------------------------------------------------------------------- 
Codificación                                 2015     2016       2017       2018
========================================= ========== ========== ========== ==========
Energía primaria Bagazo                     20.79     18.25      19.61      19.46
Energía primaria Carbón mineral             32.81     33.69      29.26      26.22
Energía primaria Gas natural y LGN         659.43     719.32     681.08     662.92
Energía primaria Petró                     300.10     304.12     350.87     337.55
Energía primaria Bosta, Yareta y Leña       87.60     113.19     108.97     109.55
Energía secundaria Carbón vegetal            1.65     4.62       5.32       5.25
Energía secundaria Coke                      1.07     1.39       2.11       2.10
Energía secundaria Diesel                  222.54     227.52     223.98     230.33
Energía secundaria Derivados NE             12.76     11.23      12.33      12.12
Energía secundaria Fueloil                   9.71     9.31       10.07      2.91
Energía secundaria Gas licuado              75.00     79.35      82.80      88.50
Energía secundaria Gasohol                  64.15     71.98      74.49      77.77
Energía secundaria Gasolina                 10.53     11.70      12.63      13.44
Energía secundaria Gas refinería            80.50     81.46      87.26      96.26
Energía secundaria Turbo                    39.19     43.45      44.22      16.14
Electriciad Para transmisión               233.65     240.79     246.79     254.10
Demanda de energía Comercial-público        54.6      56.7       56.9       57.6
Demanda de energía PAMI                    230.4      236.5      244.0      250.2
Demanda de energía Residencial             153.3      152.9      153.6      154.5
Demanda de Transporte pasajero público    154443.0    154420.5   158914.5   163322.1
Demanda de Transporte pasajero privado    71873.0     76093.5    80411.2    84662.7
Demanda de Transporte de carga            288037.0    299041.4   311398.8   324147.7
Exportaciones de Gas natural               194.0      232.8      221.2      231.4
========================================= ========== ========== ========== ==========
*Fuente: Balances nacional de enegía* 





3.2.2.1 YearSplit
---------

Duración de una parte del tiempo modelado expresado com una fracción del año, la suma de cada entrada del modelo debe sumar 1.

=========== ========
TIMESLICE    Año
=========== ========
An_alto       0.5
An_bajo       0.25
An_medio      0.25
=========== ========
*Fuente: Propia*


3.2.2.1 Capacity To Activity Unit 
---------

"Capacity To Activity Unit" es la actividad generada por la capacidad de las diferentes tecnologías, esta es diferentes para cada una las tecnologías existentes y además es constante.



3.2.2.2 Availability Factor
---------

El factor de disponibilidad, es la fracción de la capacidad instalada que esta disponible durante un año, este valor es de 0 a 1 y ve reflejada las salidas de operación programadas y fortuitas del sistema. El factor de disponibilidad para las refinerías, plantas de gas y carbón se ha tomado de los informes del PROSEMER, los valores de las plantas de generación eléctrica se han obtenido de bibliografia internacional, solo para el caso de las energías renovables no convecionales se tiene que los valores de factores de disponibilidad se han extraido de bibliografía web.

=================================== =======================
Tecnologías                         Availability factor
=================================== =======================
Producción                              1
Importaciones                           1
REfinerías                             0.9
Carboneras                             0.9
Plantas de gas natural                 0.92
Plantas de generación con biofuels     0.9
Plantas térmica de gas natural         0.9
Plantas generación hidráulica          0.9
Planats de generación solar PV         0.94
Plantas de generación eólica           0.95
Plantas térmica de diesel o fueloil    0.9
G_PGDV_02                              0.9
G_PGGTH_02                             0.8
H_STDE_01                                1
H_STDE_02                                1
=================================== =======================
*Fuente*
 - *Anexo 2 -Informe 9 PROSEMER*
 - *Availability factor of a PV power plant: evaluation based on generation and inverter running periods*




3.2.2.3 Capacity Factor
---------

El factor de capacidad es la capacidad disponible de la capacidad anual, si hubiera trabajado a plena carga, de cada tecnología y para cada timeslice. El factor de capacidad de las refinerías, plantas de gas y carboneras han sido calculados a partir del anuario estadístico de hidrocarburos de la dirección general de hidrocarburos (DGH) y los balances nacionales de energía, para las demás tecnologías se ha utilizado valores de referencia del IRENA y calculos de los factores de planta de las plantas de generación que publica el COES. A continuación se mostrará los factores de planta para las distintas tecnologías en los años 2015, 2016, 2017 y 2018.    


=================================== ======== ======= ======= =========
Tecnologías                          2015     2016    2017    2018
=================================== ======== ======= ======= =========
Refinerías                           0.776   0.777   0.834   0.80
Plantas de gas                       0.659   0.659   0.659   0.659
Plantas de generación con biofuels   0.755   0.672   0.858   0.764
Plantas térmica de gas natural       0.62    0.62    0.54    0.52
Plantas generación hidráulica        0.65    0.57    0.61    0.6
Planats de generación solar PV       0.28    0.29    0.27    0.28
Plantas de generación eólica         0.48    0.51    0.5     0.46
Plantas térmica de diesel o fueloil  0.1     0.1     0.1     0.1
G_PGDV_02                            0.17    0.17    0.17    0.17
=================================== ======== ======= ======= =========
*Fuente*
 -*Calculados del anuario de estadisticas de hidrocarburos DGH 2016-2018*
 -*Calculados a partir, Anexo 2 -Informe 9 PROSEMER*
 -*IRENA (2020), Renewable Power Generation Costs in 2019, International Renewable Energy Agency*
 -*Calculados de las estadísticas anuales del 2019- COES*
 -*LAZARD’S LEVELIZED COST OF ENERGY ANALYSIS VERSION 13.0*
 -*2019 Annual Technology Baseline- NREL*





3.2.2.4 Operational Life
---------

El Operation Life es la vida de operacional de las tecnologías, generalmente estan diseñados para largos periodos de tiempo, estas pueden variar, debido a que las plantas reciben actualizaciones, modificaciones, o simplemente se acaba la materia prima para hacerlas funcionar. Los valores de Operational Life se han obtenido de fuentes bibliográficas como LAZARD’S y National Renewable Energy Laboraqtory (NREL).


=================================== ==========================
Tecnologías                         Operational Life (Años)
=================================== ==========================
Producción                              -
Importaciones                           -
Refinerías                             40
Carboneras                              -
Plantas de gas natural                 20
Plantas de generación con biofuels     30
Plantas térmica de gas natural         30
Plantas generación hidráulica          30
Planats de generación solar PV         30
Plantas de generación eólica           20
Plantas térmica de diesel o fueloil    20
G_PGDV_02                              25
=================================== ==========================
*Fuente*
 -*LAZARD’S LEVELIZED COST OF ENERGY ANALYSIS VERSION 13.0*
 -*2019 Annual Technology Baseline- NREL


3.2.2.5 Capital Cost
---------

Capital Cost son los costos de capital por capaciad instalada, los costos generalmente estan en dolares americanos y la capacidad está expresado en unidades de potencia. Los costos de capital para las tecnologías que estan en desarrollo tienen a disminuir con el timepo en sus proyecciones, sin embargo, las tecnologías que ya estan maduras como las de tratamiento y refinación de gas o de refinación de crudo sus valores con el tiempo no disminuyen, sino que se mantienen en el tiempo. Acontinuación se mostrará los valores de Capital Costs para el año 2018. 

=================================== ============= =============
Tecnologías (2018)                  Capital Costs  Unidades
=================================== ============= =============
Producción                              -                 
Importaciones                           -                   
Refinerías                             15.93      kUSD/b/d                    
Carboneras                              -                     
Plantas de gas natural                 3.76       MMUSD/PJ/año             
Plantas de generación con biofuels     1693.37    USD/KW                    
Plantas térmica de gas natural         1290.76    USD/KW                 
Plantas generación hidráulica          1455.86    USD/KW                    
Planats de generación solar PV         1200       USD/KW          
Plantas de generación eólica           1053.86    USD/KW
Plantas térmica de diesel o fueloil    947.56     USD/KW                                        
=================================== ============= =============
*Fuente*
 -*Costos normalizados de  IRENA (2020), Renewable Power Generation Costs in 2019, International Renewable Energy Agency*
 -*Calculados a partir, Anexo 2 -Informe 9 PROSEMER*
 -*Evolución futura de costos de las energías renovables y almacenamiento en América Latina, Banco interamericano de desarrollo, división energía*
 -*LAZARD’S LEVELIZED COST OF ENERGY ANALYSIS VERSION 13.0*




3.2.2.6 Fixed Cost
---------

Los costos fijos son gastos que tienen las diferentes tecnologías por operación y mantenimiento en un periodo anual, los gatos fijos son menores en tecnologías que tienen altos costos variables, como es el caso de las tacnologías de generación térmica. Las fuentes bibliográficas consultadas para estos valores has sido los informes del PROSEMER, el IRENA y LAZARD’S. Acontinuación se mostrará los valores de Capital Costs para los años 2015, 2016, 2017 y 2018. Acontinuación se mostrará los valores de Capital Costs para el año 2018. 


=================================== ============= =============
Tecnologías (2018)                  Fixed Costs    Unidades
=================================== ============= =============
Producción                              -             
Importaciones                          12.079      MM USD/PJ  
Refinerías                             2.339       MM USD/PJ   
Carboneras                             2.71        MM USD/PJ   
Plantas de gas natural                 4.898       MM USD/PJ    
Plantas de generación con biofuels     3.55        MM USD/PJ  
Plantas térmica de gas natural         0.424       MM USD/PJ     
Plantas generación hidráulica          3.92        MM USD/PJ    
Planats de generación solar PV         4.68        MM USD/PJ   
Plantas de generación eólica           4.07        MM USD/PJ 
Plantas térmica de diesel o fueloil    0.658       MM USD/PJ     
=================================== ============= =============
*Fuente*
 -*Calculados a partir del Balance nacional de energía 2018, anuario estadístico de hidrocarburos 2018, y bibliografía internacional*
 -*Anexo 2 -Informe 9 del PROSEMER pag 111*
 -*2019 Annual Technology Baseline- NREL*
 -*Renewables Power Generation Costs in 2018, IRENA,pag. 82*
 -*LAZARD’S LEVELIZED COST OF ENERGY ANALYSIS VERSION 13.0*
 -*2019 Annual Technology Baseline- NREL*


3.2.2.7 Variable Costs
---------

Variable Costs son los costos de operación y mantenimiento que son variables en el tiempo para las diferentes tecnologías en un modo de operación, estos costos son significativos para las tecnologías térmicas, debido a que incluyen el precio de de los conbustibles. En las tecnologías solar fotovoltáica y eólica el valor de costos varibles es cero. Las fuentes bibliográficas consultadas son las mismas que las de costos fijos de operación y mantenimiento. Acontinuación se mostrará los valores de Capital Costs para el año 2018. 


=================================== ============== =============
Tecnologías (2018                   Variable Costs  Unidades
=================================== ============== =============
Producción                              -                 
Importaciones                           -                   
Refinerías                              -                          
Carboneras                              -                     
Plantas de gas natural                 1.536       MM USD/PJ             
Plantas de generación con biofuels     0.006       USD/kW-h                  
Plantas térmica de gas natural         0.0085      USD/kW-h               
Plantas generación hidráulica           -                          
Planats de generación solar PV          -                
Plantas de generación eólica            -      
Plantas térmica de diesel o fueloil    0.1813      USD/kW-h                                       
=================================== ============== =============
*Fuente*
 -*Boletìn anual 2015-2018, Operación del sector eléctrico*
 -*Calculados a partir, Anexo 2 -Informe 9 PROSEMER*
 -*Renewables Power Generation Costs in 2018, pag. 81*
 -*2019 Annual Technology Baseline- NREL*


3.2.2.8 Emission Activity Ratio
---------

Las razones de emisiones de CO2e por actividad son particulares para cada tipo de tecnología y constantes en el tiempo, estas han sido tomadas de un estudio para este tipo de tecnlogías hecho en europa. 



=================================== ======================= ==============
Tecnologías                         Emission Activity Ratio   Unidades
=================================== ======================= ==============
Producción                              -                    gCO2e/kWh
Importaciones                           -                    gCO2e/kWh         
Refinerías                             854.5                 gCO2e/kWh              
Carboneras                             1114.5                gCO2e/kWh                 
Plantas de gas natural                 738                   gCO2e/kWh                 
Plantas de generación con biofuels     68.4                  gCO2e/kWh                     
Plantas térmica de gas natural         738                   gCO2e/kWh                   
Plantas generación hidráulica          15                    gCO2e/kWh                     
Planats de generación solar PV         79                    gCO2e/kWh                     
Plantas de generación eólica           17.5                  gCO2e/kWh                      
Plantas térmica de diesel o fueloil    880                   gCO2e/kWh                 
=================================== ======================== ==============
*Fuente*
 -*GREENHOUSE GAS EMISSIONS FROM ENERGY SYSTEMS: COMPARISON AND OVERVIEW (R. Dones, T. Heck, S. Hirschberg)*


3.3 Consideraciones del modelo 
+++++++++
.. figure:: img/Proyección_Demanda_Total-Modelo_de_ajuste_con_PBI.png
   :align:   center
   :width:   700 px






3.3.1 Narrativas
---------

3.3.2 Síntesis cuantitativa de escenarios
---------


3.4 Resultados de los escenarios base
+++++++++


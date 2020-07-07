   .. _docgen:



Energy System Modeling: Data Analysis
=======================================

Characterization of Energy Sectors
-----------------------------------------------------
 Fitter Data and Outlier Correction
  blaa... 
  
.. figure:: img/RES_Energia.png
   :align:   center
   :width:   700 px
  *Figure 3.1: Diagrama del modelo desarrollado.*



El sector de energía Peruano se divide ampliamente en los macrobloques de demanda
y de oferta, las tecnologías son mostrados en bloques y estan asociados a los 
commodities que son mostradas como líneas verticales. De los commodities se toma 
una división, la cual va a la tecnología correspondiente para su transformación.    

La diversidad de la matriz energética en el Peru se muestra en una amplia cantidad 
de technologías y commodities, todo este conjunto de información para el sector 
energía han sido tomadas de los informes hechos por el PROSEMER en los cuales su 
principal objetivo es el desarrollo de un modelo para la optimización de la oferta 
del sistema energético basados en modelos de optimización TIMES que fue desarrollado 
como parte del IEA-ETSAP's metodología usada para escenarios de energía para conducir 
en un profundo análisis de la energía.

Las tecnologías de entrada son la importación y produción de los commodoties, hay 
tecnologías intermedias como refinación, procesasmiento de gas, producción de 
carbón, plantas de generación, transmisión y distribución de energía eléctrica.

*____________________________________________________________________*

3.2.1 Sets
---------
Los sets son el conjunto de configuraciones que son establecidos para el modelo, estos 
son particulares por país y región, para su configuración se debe tener un análisis 
del sistema a modelar, los sets se muestrana contiuación.

-Región
-Year
-Timeslices
-Emissions
-Commodity
-Technology
-Mode of operation


3.2.1 Procesos
---------
Los procesos o tecnologías son representados en forma de bloque y pueden tener o no una entrada de commodities, sin embargo, siempre tienen una salida de commodities, las tecnologías para el peru se muestran a continuación.


Los procesos son los siguientes:
+---------------+---------------------------------------------------------------------------+
|A_BACKSTOP     | Backup Power Systems                                                      |
+---------------+---------------------------------------------------------------------------+
|B_PROD_01      | Producción de combustibles actual                                         |
+---------------+---------------------------------------------------------------------------+
|B_PROD_02      | Producción de combustibles actual                                         |
+---------------+---------------------------------------------------------------------------+
|C_IMPO_01      | Importaciones de energia actual                                           |
+---------------+---------------------------------------------------------------------------+
|C_IMPO_02      | Importaciones de energia futura                                           |
+---------------+---------------------------------------------------------------------------+
|D_REFI_01      | Refinería actual                                                          |
+---------------+---------------------------------------------------------------------------+
|D_REFI_02      | Refinería futura                                                          |
+---------------+---------------------------------------------------------------------------+
|E_CARB_01      | Carbonera actual                                                          |+---------------+---------------------------------------------------------------------------+
|E_CARB_02      | Carbonera futura                                                          |+---------------+---------------------------------------------------------------------------+
|F_PGN_01       | Plantas de gas natural actual 
+---------------+---------------------------------------------------------------------------+
|F_PGN_02       | Plantas de gas natural futura
+---------------+---------------------------------------------------------------------------+
|G_PEBIO_01     | Planta eléctrica biomasa o biogas actual  +---------------+---------------------------------------------------------------------------+
|G_PEBIO_02     | Planta eléctrica biomasa o biogafutura
+---------------+---------------------------------------------------------------------------+
|G_PEGA_01      | Planta eléctrica de gas natural actual 
+---------------+---------------------------------------------------------------------------+
|G_PEGA_02      | Planta eléctrica de gas natural futura
+---------------+---------------------------------------------------------------------------+
|G_PEHI_01      | Planta hidroeléctrica actual 
+---------------+---------------------------------------------------------------------------+
|G_PEHI_02      | Planta hidroeléctrica futura
+---------------+---------------------------------------------------------------------------+
|G_PEREN_01     | Planta eléctrica renovable actual
+---------------+---------------------------------------------------------------------------+
|G_PEREN_02     | Planta eléctrica renovable futura
+---------------+---------------------------------------------------------------------------+
|G_PETE_01      | Planta térmicas actual
+---------------+---------------------------------------------------------------------------+
|G_PETE_02      | Planta térmicas futura
+---------------+---------------------------------------------------------------------------+
|G_PGDS_02      | Plantas de generación distribuida solar 
+---------------+---------------------------------------------------------------------------+
|G_PGDV_02      | Plantas de generación distribuida eólica  
+---------------+---------------------------------------------------------------------------+
|H_STDE_01      | Transmisión y distribución de electricidad actual 
+---------------+---------------------------------------------------------------------------+
|H_STDE_02      | Transmisión y distribución de electricidad futura
+---------------+---------------------------------------------------------------------------+
|I_DISTENECOMP_1| Distribución de energía comercio y público 
+---------------+---------------------------------------------------------------------------+
|I_DISTENEPAMI_1| Distribución de energía pesca, agricola, minas e industria 
+---------------+---------------------------------------------------------------------------+
|I_DISTENERESI_1| Distribución de energía residencial 
+---------------+---------------------------------------------------------------------------+
|J_TPBUSE_02    | Transporte público bus eléctrico o hidrógeno futuro 
+---------------+---------------------------------------------------------------------------+
|J_TPUBUSG_02   | Transporte público bus por gas natural futura
+---------------+---------------------------------------------------------------------------+
|J_TPUBUSHC_01  | Transporte público bus por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|J_TPUBUSHC_02  | Transporte público bus por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|J_TPUTXEL_02   | Transporte público taxi - app eléctrico futuro 
+---------------+---------------------------------------------------------------------------+
|J_TPUTXGN_02   | Transporte público taxi - app por gas natural futuro 
+---------------+---------------------------------------------------------------------------+
|J_TPUTXHC_01   | Transporte público taxi - app por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|J_TPUTXHC_02   | Transporte público taxi - app por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|K_TPRMOEL_02   | Transporte privado motocleta eléctrico futuro 
+---------------+---------------------------------------------------------------------------+
|K_TPRMOHC_01   | Transporte privado motocicleta por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|K_TPRMOHC_02   | Transporte privado motocicleta por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|K_TPRVEEL_02   | Transporte privado vehículo eléctrico futuro 
+---------------+---------------------------------------------------------------------------+
|K_TPRVEGN_02   | Transporte privado vehículo por gas natural futuro
+---------------+---------------------------------------------------------------------------+
|K_TPRVEHC_01   | Transporte privado vehículo por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|K_TPRVEHC_02   | Transporte privado vehículo por hidrocarburo actual 
+---------------+---------------------------------------------------------------------------+
|L_TPANOMO_01   | Transporte de pasajeros no motorizado actual 
+---------------+---------------------------------------------------------------------------+
|L_TPANOMO_02   | Transporte de pasajeros no motorizado futuro
+---------------+---------------------------------------------------------------------------+
|M_TRENPAEL_01  | Transporte tren eléctrico actual 
+---------------+---------------------------------------------------------------------------+
|M_TRENPAEL_02  | Transporte tren eléctrico futuro 
+---------------+---------------------------------------------------------------------------+
|M_TRENPAHC_01  | Transporte tren de diesel  actual 
+---------------+---------------------------------------------------------------------------+
|N_TCCLEL_02    | Transporte de carga liviana por eléctricidad o H2 futura
+---------------+---------------------------------------------------------------------------+
|N_TCCLGN_02    | Transporte de carga liviana por gas futura
+---------------+---------------------------------------------------------------------------+
|N_TCCLHC_01    | Transporte de carga liviana por hidrocarburos actual 
+---------------+---------------------------------------------------------------------------+
|N_TCCLHC_02    | Transporte de carga liviana por hidrocarburos futura
+---------------+---------------------------------------------------------------------------+
|O_TCCMEL_02    | Transporte de carga mediana por eléctricidad o H2 futura
+---------------+---------------------------------------------------------------------------+
|O_TCCMGN_02    | Transporte de carga mediana por gas futura
+---------------+---------------------------------------------------------------------------+
|O_TCCMHC_01    | Transporte de carga mediana  por hidrocarburos actual 
+---------------+---------------------------------------------------------------------------+
|O_TCCMHC_02    | Transporte de carga mediana por hidrocarburos futura
+---------------+---------------------------------------------------------------------------+
|P_TCCPEL_02    | Transporte de carga pesada por eléctricidad  futura
+---------------+---------------------------------------------------------------------------+
|P_TCCPGN_02    | Transporte de carga pesada por gas natural futura
+---------------+---------------------------------------------------------------------------+
|P_TCCPHC_01    | Transporte de carga pesada por hidrocarburos actual 
+---------------+---------------------------------------------------------------------------+
|P_TCCPHC_02    | Transporte de carga pesada por hidrocarburos futura
+---------------+---------------------------------------------------------------------------+
|Q_TRENCAEL_02  | Transporte tren de carga eléctrico futuro 
+---------------+---------------------------------------------------------------------------+
|Q_TRENCAHC_01  | Transportetren carga de diesel futuro                                     |
+---------------+---------------------------------------------------------------------------+
|Q_TRENCAHC_02  | Transporte tren carga de diesel  actual                                   |
+---------------+---------------------------------------------------------------------------+
|R_TAVMAR_01    | Transporte por aviación o mar actual                                      |
+---------------+---------------------------------------------------------------------------+
|R_TAVMAR_02    | Transporte por aviación o mar futuro                                      |
+---------------+---------------------------------------------------------------------------+


3.2.1 Comodities
---------



3.2.1 Costos 
---------



3.1.1 Emisiones
---------

 
   3.2.1 Datos de entrada
---------


    
.. figure:: img/Proyeccion_del_crecimiento_del_PBI_anual.png
   :align:   center
   :width:   500 px

   *Figure 3.1: Proyección del crecimiento del PBI anual.*

Para los valores proyectados se utilizaron los valores proporcionados para el 
periodo 2016-2026 por la consultora APOYO, los valores para el periodo 2027-2040 
se tomaron de los escenarios proporcionados por el MINEM y para el periodo 
2040-2055 se tomaron la proyección de la tendencia de los valores de los últimos 
10 años anteriores al 2040. 

   
.. figure:: img/proyeccion_del_crecimiento_CAPEX_energias_renovables.png
   :align:   center
   :width:   700 px

   *Figure 3.2: Proyección del crecimiento CAPEX energias renovables.*

Para la proyección del CAPEX (Capital expenditure) de las energías renovables 
se tomaron valores del "Evolución futura de costos de las energías renovables 
y almacenamiento en América Latina" para el periodo 2018-2030, para el periodo 
2030-2055 se ha utilizado un ajuste lotgarítmico para poder proyectar los valores.


.. figure:: img/Proyeccion_del_precio_de_carbon.png
   :align:   center
   :width:   700 px

   *Figure 3.3: Proyección del precio de carbon.*

Para la proyección de los precios del carbón se utliza las proyección del carbon 
australia del banco mundial (octubre del 2018), todos los costos de internación 
son considerados e incluye  flete y otros costos de transporte, el carbón tiene 
un costo de internación  de 18.6 US$/ton.


.. figure:: img/Proyeccion_del_precio_del_gas_en_la_planta.png
   :align:   center
   :width:   700 px

   *Figure 3.4: Proyección del precio del gas en la planta.*

Los precios del gas han utilizado como base las proyeciones de "high oil and gas 
resource and technology" (HRT) del EIA que han sido proyectadas hasta el 2050, y 
como las proyeciones del caso de referencia EIA . 

.. figure:: img/Proyeccion_del_precio_promedio_del_crudo.png
   :align:   center
   :width:   700 px

   *Figure 3.5: Proyección del precio promedio del crudo.*

Para la proyección del precio del crudo se ha utilizado las proyecciones de WTI que 
se estabblecen en dos escenarios uno es el de referencia y el otro es el alto, se 
incluyen todos los costos, el crudo tienen un costos de integración de 5 US$/bbl.

.. figure:: img/Proyeccione_de_precio_por_capacidad_de_la_planta_de_gas.png
   :align:   center
   :width:   700 px

   *Figure 3.6: Proyecciones del precio por capacidad de la planta de gas.*

Los cálculos se hicieron con los datos de costos de capital y operación de plantas 
de gas y la actividad de las refinería que se encuentran en el informe 9 "Desarrollo 
del Plan Energético a Nivel de Grupos de Regiones y Acompañamiento".  

.. figure:: img/Proyeccione_de_precio_por_capacidad_de_refineria.png
   :align:   center
   :width:   700 px

   *Figure 3.7: Proyecciones del precio por capacidad de la refineria.*

Los cálculos se hicieron con los datos de costos de capital, operación y variación de 
plantas de refinación y la actividad de las refinería que se encuentran en el informe 9 
"Desarrollo del Plan Energético a Nivel de Grupos de Regiones y Acompañamiento".  





*____________________________________________________________________*

 Clustering and Representative Networks
 
 Time-Series Analysis and Forecasting

Electricity Sector Simulation
-----------------------------------------------------
 Data Structure and Elements of Electric System
  power..
   

.. figure:: img/Proyeccion_de_la_maxima_demanda_de_electricidad_anual.png
   :align:   center
   :width:   700 px

   *Figure 3.8: Proyección de la maxima demanda de electricidad anual.*

.. figure:: img/Proyeccion_de_la_demanda_de_electricidad_anual.png
   :align:   center
   :width:   700 px

   *Figure 3.9: Proyección de la demanda de electricidad anual.*

Para ambas tipos de proyecciones se va a considerar únicamente las zonas del país conectadas al SEIN. Iquitos no se incluye en el modelaje.

*____________________________________________________________________*

 Electricity Power Flow and Efficiency
 
 Emissions from Electricity Sector

Transport Sector Simulation
-----------------------------------------------------

 Data Structure and Elements of Transport System
 Traffic Flow Analysis and Efficiency of the System
 Emissions and Air Pollution from Transport Sector


.. figure:: img/proyecion_sector_transporte_publico_privado.png
   :align:   center
   :width:   700 px

   *Figure 3.10: Proyección del sector transporte publico y privado.png.*

.. figure:: img/proyecion_sector_transporte_carga.png
   :align:   center
   :width:   700 px

   *Figure 3.11: Proyección del sector transporte carga.png.*
   
   
.. figure:: img/proyecion_sector_transporte.png
   :align:   center
   :width:   700 px

   *Figure 3.12: Proyección del sector transporte.*

.. figure:: img/Proyeccion_del_precio_de_vehiculos_electricos.png
   :align:   center
   :width:   700 px

   *Figure 3.13: Proyección del precio de vehiculos electricos.*

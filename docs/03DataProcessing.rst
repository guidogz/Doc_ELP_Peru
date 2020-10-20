   .. _docgen:

=======================================
3. OSeMOSYS-Peru
=======================================


3.1 Energy System Modeling: Data Analysis
=======================================


3.1.1 Characterization of Energy Sectors
++++++++++++++++++++++
 Fitter Data and Outlier Correction

  

.. figure:: img/RES_Energia.png
   :align:   center
   :width:   700 px
*Figure 3.1: Diagrama de referencía. Fuente: Propia*


El sector de energía Peruano se divide ampliamente en los macrobloques de demanda
y de oferta, las tecnologías son mostradas en bloques y estan asociados a los 
commodities que son mostradas como líneas verticales. De los commodities se toma 
una división, la cual va a la tecnología correspondiente para su transformación.    

La diversidad de la matriz energética en el Peru se muestra en una amplia cantidad 
de technologías y commodities, todo este conjunto de información para el sector 
energía han sido tomadas de los informes hechos por el PROSEMER en los cuales su 
principal objetivo es el desarrollo de un modelo para la optimización de la oferta 
del sistema energético basados en modelos de optimización TIMES_ que fue desarrollado 
como parte del IEA-ETSAP's metodología usada para escenarios de energía para conducir 
en un profundo análisis de la energía.

Las tecnologías de entrada son la importación y produción de los commodoties, hay 
tecnologías intermedias como refinación, procesasmiento de gas, producción de 
carbón, plantas de generación, transmisión y distribución de energía eléctrica.
Las commodities inciales son por lo general insumos procesados por tecnologías
o productos importados, estos pasan por tecnologías para su transformación a 
comodities de mayor calidad. 



.. ``bueno ya es hora de divertirse, como para poner lineas de código, esto se debe eliminar``


.. _TIMES: https://iea-etsap.org/index.php/etsap-tools/model-generators/times/




.. Una oración que enlaza a Wikipedia_ y al `Linux kernel archive`_.

.. .. _Wikipedia: http://www.wikipedia.org/
.. .. _Linux kernel archive: http://www.kernel.org/

.. Otra oración con un `enlace anónimo al sitio de Python`__.

.. __ http://www.python.org/

.. `Python <http://www.python.org/>`_. 



3.1.1.1 Demanda en energía y transporte
--------------

Las demandas energética en el Perú son actualmente proyectadas en base a premisas 
macroeconómicas poblacionales y de eficiencia energética, los resultados atienden a 
la necesidad de otros modelos de optimización dentro de la cadena de planifición 
energética, como OPTGEN y TIMES, para luego ser parte de un bucle de optimización 
con la integración del modelo TIMES-CGE. Los resulatdos obtenidos pueden variarse 
al escenario suspuesto, con la finalidad de situarse y analizarlos, además los 
resulatdos estan desagregados en región, tipo de combustible, escenario, etc. 

Por otra parte, los valores proyectados de las series de tiempo para lograr la 
descarbonización del Perú al 2050 utilizados han sido construidos con modelos autoregresivos
que tienen diferentes variables explicativas por sector, las proyecciones al 2050 de 
la demanda para los sectores económicos se muestran la siguiente gráfica, en donde 
la participacion de sector residencial y manufactura son predominantes.  

.. figure:: img/proyecciones_demanda_sectores.png
   :align:   center
   :width:   500 px
*Figure 3.1: Predicciones de la demanda de energía por sector productivo. Fuente: Propia*

 Todas los valores de demanda, se puede ver a en Anexos demanda_.

.. Hay que cambiar este hyperlink

.. _demanda: https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/ 

EL sector transporte es el sector productivo que más energía consume y lo hace principalmente a través de combustibles fósiles, con la finalidad de realizar una proyección del sector ha sido conveniente de dividirlo en subdivisiones para facilitar el desarrollo de los modelos que serán utilizados para realizar las predicciones de demanda, es importante aclarar que hay demandas de energía expresadas en *pkm* o *tkm*, que expresan un servicio en lugar de terminos de energía neta (PJ). A continuación se presentarán las subdivisiones realizadas. 

============ =================================
Subdivisión  Tipo
============ =================================
Carretero    Pasajero publico y privado, Carga
Ferroviario  Pasajero y Carga
Naval        Energía neta
Aéreo        Energía neta
============ =================================
*Fuente: Propia* 

Las predicciones sobre la demanda historica de sector transporte específicamente en la subdivision Carretero han tomado como variable explicativa al PBI, sin embargo, no todas las subdivisiones del sector utilizan PBI como variable explicativa tanbien se utiliza la población y una tendecia.


.. figure:: img/proyecciones_demanda_transporte_carretero_pasajero.png
   :align:   center
   :width:   700 px
*Figure 3.10: Proyección del sector transporte, carretero público y privado. Fuente: Propia*
   
.. figure:: img/proyecciones_demanda_transporte_carretero_carga.png
   :width:   700 px
*Figure 3.12: Proyección del sector transporte, carretero de carga. Fuente: Propia

.. figure:: img/proyecciones_demanda_transporte_ferroviario.png
   :align:   center
   :width:   700 px
*Figure 3.10: Proyección del sector transporte, ferroviario de pasajeros. Fuente: Propia*
  
.. figure:: img/proyecciones_demanda_transporte_ferroviario_carga.png
   :width:   700 px
*Figure 3.12: Proyección del sector transporte, ferroviario de carga. Fuente: Propia

.. figure:: img/proyecciones_demanda_transporte_ferroviario_carga.png
   :width:   700 px
*Figure 3.12: Proyección del sector transporte, Naval y Aéreo. Fuente: Propia

Los valores de las proyecciones de demanda de enegía para los sectores productivos y transporte se pueden observar en los anexos de este documento, `Proyecciones de demanda <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.


Las proyecciones del sector trasnporte conlleva un problema grave para el medio ambiente, el uso de los combustibles fósiles para el transporte son un problema importante hoy, por eso, es importante mencionar los precios de los vehículos eléctricos, se han utilizado las proyecciones del precio de los vehículos eléctricos del PROSEMER al 2050.

.. figure:: img/Proyeccion_del_precio_de_vehiculos_electricos.png
   :align:   center
   :width:   700 px
*Figure 3.13: Proyección del precio de vehiculos electricos, Fuente: Propia*

Todos los valores de demanda de energía de transporte y proyecciones de de los precios de los vehículos de gas natural se puede ver en Anexos en A13 y A10 respectivamente `precios y costos <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

3.1.1.2 Oferta de energía  
--------------


3.1.1.2.1 Plantas de generación 
~~~~~~~~~~~~~~~~~~~~~~~
La capacidad instalada en el Perú ha crecido con el pasar de los años, ha pasado de ser 10,150.0 MW el año 2015 a 13,179.53 MW el año 2019 (COES), y la matriz energética se ha diversificado, sin embargo, la participación de las energías renovables no convecionales en la producción de energía eléctrica aún es pequeña en comparación con la energía eléctrica generada en las plantas de energías renovables convencionales y no renovables. Las empresas de generación en el 2019 han sido un total de 58, las cuales en conjunto
tienen una capacidad instalada de 13179.53 MW y capacidad efectiva de 12636.89 MW, en el 
2019 la producción de energía anual ejecutada se valoró en 52949.19 GW.h  y la máxima 
demanda ejecutada fue de 7017.57 MW en el mes de diciembre. El recurso que tuvo la mayor 
participación en la producción de energía fue el agua con 57.04% seguido de los combustibles 
fósiles con un 38.41%, la potencia efectiva por tipo de generación que predominó fueron las 
termoeléctricas con un 54.67 % y el recurso que que más capacidad efectiva disponia para la 
producción de energías fue el agua con un 37.58 %. A continuación se enlista en tablas  del tipo de la participación 
por tipo de recurso, tipo de generación y finalmente la energía ejecutada. 



============================== ========================== =============
POTENCIA EFECTIVA POR TIPO DE RECURSO ENERGÉTICO 2019       
----------------------------------------------------------------------- 
TIPO DE RECURSO ENERGÉTICO     POTENCIA EFECTIVA (MW)        (%)    
============================== ========================== =============
  AGUA                                  4,748.37               37.58 
  RENOVABLES                            1,041.01                8.24 
  GAS NATURAL DE CAMISEA                3,775.21               29.87 
  GAS NATURAL DE AGUAYTIA                 176.05                1.39 
  GAS NATURAL DE MALACAS                  343.61                2.72 
  DIESEL 2                              2,334.21               18.47 
  RESIDUAL                                 77.73                0.62 
  CARBÓN                                  140.71                1.11 
------------------------------ -------------------------- -------------
  TOTAL                                12,636.89              100.00     
============================== ========================== ============= 

*Fuente: Estadística Anual 2019, Capítulo 2 - Estado actual de la infraestructura del SEIN, Cuadro 2.5*


====== =============== ============== ======= ======== ============
POTENCIA EFECTIVA POR TIPO DE GENERACIÓN A DICIEMBRE 2019 (MW)             
-------------------------------------------------------------------               
ÁREA   HIDROELÉCTRICA  TERMOELÉCTRICA  SOLAR   EÓLICA    TOTAL
====== =============== ============== ======= ======== ============
NORTE      610.07           801.24             114.01    1,525.32 
CENTRO   3,839.10         4,075.82             261.45    8,176.38 
SUR        618.48         2,031.69     285.02            2,935.20 
------ --------------- -------------- ------- -------- ------------
TOTAL    5,067.66         6,908.75     285.02  375.46   12,636.89 
====== =============== ============== ======= ======== ============
*Fuente: Estadística Anual 2019, Capítulo 1 - Estadística relevante del SEIN, Cuadro 1.5*


====== ================ ================ ====== ========== =========================== ==========
PRODUCCIÓN DE ENERGÍA Y MÁXIMA DEMANDA - 2019  (GWh)  
------------------------------------------------------------------------------------------------- 
ÁREA    HIDROELÉCTRICA   TERMOELÉCTRICA  SOLAR    EÓLICA   "IMPORTACIÓN DESDE ECUADOR"   TOTAL
====== ================ ================ ====== ========== =========================== ==========
NORTE     3,370.54           757.83                443.68          60.05                 4,632.10 
CENTRO   22,735.89        19,504.41              1,202.48                               43,442.79 
SUR       4,061.99            50.59      761.73                                          4,874.31 
TOTAL    30,168.43        20,312.83      761.73  1,646.16          60.05                52,949.19 
====== ================ ================ ====== ========== =========================== ==========
*Fuente: Estadística Anual 2019, Capítulo 1 - Estadística relevante del SEIN, Cuadro 1.7*


|
|        **Las proyecciones de la demanda de energía anual al 2050**
|

Para la demanda de energía anual se ha desarrollado un modelo autoregresivo tomando como variables explicativa el PBI y la tendencia, Para las predicciones se va a considerar únicamente las zonas del país 
conectadas al SEIN. Iquitos no se incluye en el modelaje.  


.. figure:: img/proyeccion_de_la_demanda_de_electrcidad_anual_para_un_modelo_autoregresivo.png
   :align:   center
   :width:   700 px
*Figure 3.9: Proyección de la demanda de electricidad anual, Fuente: Propia*

 Todos los valores de demanda anual se puede ver a en Anexos `demanda electrica <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

   
3.1.1.2.2 Plantas de gas 
~~~~~~~~~~~~~~~~~~~~~~~

Las plantas de gas en el peru suman 8 en las cuales tenemos que 3 son exclusivamente de 
procesamiento (separación), 3 son únicamente de fraccionamiento, 1 de procesamiento y fracionamiento y 
finalmente 1 de licuación, en conjunto suman una capacidad instalada de 1333 PJ con una 
disponibilidad promedio de 92% y un factor de capacidad promedio de 48%. Los costos de 
tratamiento de gas en las plantas se valorizan en 4228.2 MMUSD en el 2013 y tuvo una 
actividad de 639 PJ. En las siguientes tablas se muestra la información.


=================== =================== =============== =============================== =======
Plantas de gas      Capacidad instalada Capacidad de     Tipo de tratamiento            Región
                         PJ (2018)      Procesamiento 
=================== =================== =============== =============================== =======
Malvinas                  804            1160 [MMPCD]   Procesamiento (separación)      Sur
Curimaná                   29              65 [MMPCD]   Procesamiento (separación)      Oriente
GMP-procesamiento          18              80 [MMPCD]   Procesamiento (separación)      Norte
GMP-fraccionamiento         5               3  [MBPD]   Fraccionamiento                 Norte
Pisco                     215              85  [MBPD]   Fraccionamiento                 Sur
Yarinacocha                 8               4.4[MBPD]   Fraccionamiento                 Oriente
Pariñas                    16              61 [MMPCD]   Procesamiento y Fraccionamiento Norte
Pampa Melchorita          238                           Licuefacción                    Centro
------------------- ------------------- --------------- ------------------------------- -------
Total instalado          1333                                                                 
=================== =================== =============== =============================== =======
*Fuente: Anexo 2 - informe 9 PROSEMER, página 101. OSINERGMIN 2020*


================== ================ ==========
Sector                Costo         MUSD 2013
================== ================ ==========
TRATAMIENTO - GAS   OPEX VARIABLE    981.4
TRATAMIENTO - GAS   OPEX FIJO       3246.7
TRATAMIENTO - GAS   CAPEX 
------------------ ---------------- ----------
TRATAMIENTO - GAS   TOTAL           4228.2
================== ================ ==========
*Fuente: Imforme 9 PROSEMER, página 303*


========== ========= ========= ========= ========= ========= =========
Producto   2013 [PJ] 2014 [PJ] 2015 [PJ] 2016 [PJ] 2017 [PJ] 2018 [PJ]
========== ========= ========= ========= ========= ========= =========
Gas seco**    457                 513      571       547      537     
LGN           182                 146      148       134      126     
---------- --------- --------- --------- --------- --------- ---------
Total         639                 659      719       681       663    
========== ========= ========= ========= ========= ========= =========
*Fuente: Informe 9 PROSEMER, pag. 303. Balances Nacionales de Energía*


|
|          **Las proyecciones del precio del gas natural y costos por capacidad**
|
Para estas proyecciones se han tomado los valores del los informes del PROSEMER y se han extendido 
de forma lineal hasta el 2050, cabe mencionar que los valores puestos son de inversiones corrinets. Para los precios de gas se han tomado los valores proyectados al 2050
del HENRY HUB.

.. figure:: img/Proyeccion_del_precio_del_gas_en_la_planta.png
   :align:   center
   :width:   700 px

*Figure 3.4: Proyección del precio del gas en la planta, Fuente: PROSEMER*

Los precios del gas han utilizado como base las proyeciones de "high oil and gas 
resource and technology" (HRT) del EIA que han sido proyectadas hasta el 2050, y 
como las proyeciones del caso de referencia EIA . 


Todos los valores de los precios de gas natural, CAPEX y OPEX  se puede ver en Anexos en A7 y A12 respectivamente `precios y costos <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.




3.1.1.2.3 Refinerías 
~~~~~~~~~~~~~~~~~~~~~~~

Las refinerías en el Perú suman un total de 9, las cuales en conjunto tienen una 
capacidad de producción de 221-228 miles de barriles diarios, El Milagro ya no se considera
como un refinería economicamente viablea partir del 2016, con una disponibilidad 
en promedio del 90%, esta capacidad de procesamiento cambiará después de la modernización 
de la refinería de talara, su capacidad será de 245.3 miles de barriles diarios.
La produción en PJ de energía en el año 2017 alcanzó un total de 350 con una producción  
de 91459.9 barriles, y tambien para el mismo año los costos operativos se valorizaron en 
492.6 MMUSD, en las siguinetes tablas se puedes apreciar estas cifras. 

=========== ============================ ======================================= ==========
Refinería    Capacidad instalada (2018)  Tipo de combustible refinado            Región
----------- ---------------------------- --------------------------------------- ----------
Nombre         Miles de barriles de
               petróleo día (MBPD)
=========== ============================ ======================================= ==========
Talara        65-95*                     Diesel, Turbo, GLP, Fueloil, Gasolina   Norte
Conchán       15.5                       Diesel, Fueloil, Gasolina               Centro
Pampilla      117                        Diesel, Turbo, GLP, Fueloil, Gasolina   Centro
Iquitos       12.0                       Diesel, Turbo, Fueloil, Gasolina        Oriente
Pucallpa       3.3                       Diesel, Turbo, Gasolina                 Oriente
El Milagro      2                        Diesel, Turbo, Fueloil, Gasolina        Norte
Huayuri        4.0                       Crudo multiuso, Diesel, HFO, Nafta      Oriente
Shiviyacu      5.2                       Crudo, Diesel, Nata, Residual, Multiuso Oriente
Yacimiento     4.0                       Crudo, Diesel, HFO, Nafta/Residual      Oriente
=========== ============================ ======================================= ==========
*Fuente: Anexo 2 - informe 9 PROSEMER, informe 7 PROSEMER, OSINERGMIN*


============ ======= ============
Sector        Costo  2017 (MUSD)
============ ======= ============
REFINERIAS    OPEX    412.4
REFINERIAS    CAPEX    80.1
------------ ------- ------------ 
REFINERIAS    TOTAL   4204.1
============ ======= ============
*Fuente: Informe 9 PROSEMER, pag. 302*


========= ========= ========= =========
Producción total en las refinerías 
--------------------------------------- 
2015 [PJ] 2016 [PJ] 2017 [PJ] 2018 [PJ]
========= ========= ========= =========
300.78    304.153   356.426   337.547
--------- --------- --------- ---------
[MBLS]    [MBLS]    [MBLS]    [MBLS]
--------- --------- --------- ---------
73773.6   79515     91007.70  87144.80
========= ========= ========= =========
*Fuente: Producción total de energia en miles de barriles equivalentes de petróloe y en Peta-Joule*

|
|                  **Las proyecciones del precio del crudo y costos por capacidad**
|
Para estas proyecciones se han tomado los valores del los informes del PROSEMER y se han extendido 
de forma lineal hasta el 2050. Para los hodrocarburos se han tomado los valores proyectados al 2050
del WTI.


.. figure:: img/Proyeccion_del_precio_promedio_del_crudo.png
   :align:   center
   :width:   700 px

*Figure 3.5: Proyección del precio promedio del crudo, Fuente: Propia*

Para la proyección del precio del crudo se ha utilizado las proyecciones de WTI que 
se estabblecen en dos escenarios uno es el de referencia y el otro es el alto, se 
incluyen todos los costos, el crudo tienen un costos de integración de 5 US$/bbl.


Todos los valores de los precios del WTI, CAPEX y OPEX  se puede ver en Anexos en A8 y A11 respectivamente `precios y costos <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.



3.1.1.2.4 Carboneras 
~~~~~~~~~~~~~~~~~~~~~~~
Para el 2013 la capacidad instalada de procesamiento de carbon es de 5.08 PJ, 2.97 para 
la región centro y 2.11 para la región norte, además se asume un costo de producción de 
2.71 MMUSD/PJ que incluye todos lo contos de extración, mina, transporte y acopio. Tambien
se consideró un costo de inversión 2,76 MMUSD/PJ para incrementar la capacidad existente y 
disminuir los costos existentes, cabe mencionar que los valores de transporte para la región 
norte y centro son de 0.69 MMUSD/PJ.


=========== ===========================
Carboneras  Capacidad instalada (2013)
                      PJ-año
=========== ===========================
Norte                  2.11
Centro                 2.97
----------- ---------------------------
Total                  5.08
=========== ===========================
*Fuente: Informe 9 PROSEMER, pag. 302* 

============ ======= ================
Sector        Costo  2017 (MMUSD/PJa)
============ ======= ================
CARBONERAS    TOTAL     2.71
------------ ------- ----------------
CARBONERAS    TOTAL     2.71
============ ======= ================
*Fuente: Informe 9 PROSEMER, pag. 302* 

|
|                  **Las proyecciones del precio del crudo y cotos por capacidad**
|

.. figure:: img/Proyeccion_del_precio_de_carbon.png
   :align:   center
   :width:   700 px

*Figure 3.3: Proyección del precio de carbon, Fuente: Propia*

Para la proyección de los precios del carbón se utliza las proyección del carbon 
australia del banco mundial (octubre del 2018), todos los costos de internación 
son considerados e incluye  flete y otros costos de transporte, el carbón tiene 
un costo de internación  de 18.6 US$/ton.

Todos los valores de los precios de carbón se puede ver en Anexos en A9 `precios <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.


3.1.1.3 Distribución de energía
--------------

La distribución de la energía en Perú se da a traves de diferentes medios, como la distribución eléctrica a traves de líneas eléctricas de transmisión y distribución, el gas natural a traves de gaseoductos o redes virtuales, las refinerías a traves de redes virtuales y oleoductos, etc.

3.1.1.3.1 Transmisión y distribución del Sistema interconectado nacional 
~~~~~~~~~~~~~~~~~~~~~~~

El sistema interconectado nacional está constituido por redes de trasmisión y distribución eléctrica, las redes de transmisión se encuentran constituidas por líneas de transmisión de 500, 220, 138, 66, 60, 50 y 33 kV. El SEIN está integrado por 4 categorías de instalaciones, el sistema garantizado de transmisión (SGT), el sistema complementario de transmisión (SCT), el sistema principal de transmisión (SPT) y el sistema secundario de transmisión (SST). En el 2019 se instalaron un total de 966.4 km de líneas de transmisión, en la siguinete tabla se puede observar el total de líneas de transmisión que hay en el Perú en el sistema principal de transmisión y sistema secundario de transmisión al 2019.

================================= ========= ========= ========= =========
         Longitud de las líneas de transmisión del SEIN (km)
-------------------------------------------------------------------------       
Líneas                             500 kV    220 kV    138 kv    >75 kV
================================= ========= ========= ========= =========
Sistema primario de transmisión     2735.9   6774.54    552.27     0.0
Sistema secundario de transmisión   142.76   6856.84   4361.88   8571.41
--------------------------------- --------- --------- --------- ---------
Total                              2878.66  13631.38   4914.15   8571.41
================================= ========= ========= ========= =========
*Fuente: Estadistica anual 2019, COES*


.. figure:: img/Lineas_ExistentesCOES_Dic2019-SEIN_copia-1.jpg
   :align:   center
   :width:   700 px

*Figure 3.3: Sistema interconectado nacional. Fuente: COES*


3.1.1.3.2 Distribución de crudo y derivados del petróleo 
~~~~~~~~~~~~~~~~~~~~~~~

La distribución del crudo se hace a través de oleoductos, el crudo es llevado hacia las plantas de refinación como sucede en el noroeste y la selva de nuestro país, sin embargo para su distribución se hace uso de redes virtuales. El oleoducto norperuano tiene una longitud aproximada de 1100 km y una capacidadf de 200 MMBD



3.1.1.3.3 Distribución de gas natural
~~~~~~~~~~~~~~~~~~~~~~~

Actualmente se explota gas natural en los lotes 56, 88, por pluspetrol y el lote 57 por repsol, el lote 58 comenzará a explotarse el año 2023 por la empresa CNPC. En camisea se extrae gas natural que es procesado para su separación en líquidos de gas natural y gas seco que son enviados a través del poliducto hasta la planta de fraccionamiento de Pisco, el gas seco que no es reinyectado es transportado a través del TGP hasta el City Gate en Lurín, la empresa caliodad es reponsable de su distribvución en lima y callao.  



3.1.1.4 Importaciones 
--------------


Las importaciones de energía en el Perú son actualmente significativas, más de la mitad de crudo que se necesita se importa, aunque el Perú es autosuficiente con el gas natural hasta la fecha no se han hecho estudios de más reservas de gas, en el sector eléctrico realizamos importaciones del ecuador dependienos del costo marginal de la electricidad.

Las importaciones según el "Anuario estadístico sectorial de hidrocarburos 2018" el 2018 fueron de un total aproximado de 316 (PJ), para crudo, GLP, gasolina y carbón, que representan un valor de 3819.72 MMUSD.


================================= ========= ========= ========= =========
        Importaciones de hidrocarburos (MBLS)
-------------------------------------------------------------------------       
Producto                            2015       2016     2017      2018
================================= ========= ========= ========= =========
Crudo                              31326.81  38489.18  45735.96  41117.13
GLP/butano/propano                  1119.18   1816.05   2491.53   4240.30
Gasolina                            5063.36   6979.09   7776.87   8428.90
================================= ========= ========= ========= =========

*Fuente: Anuario estadístico sectorial de hidrocarburos 2018 DGH, pag. 73*


================================= ========= ========= ========= =========
        Importaciones de hidrocarburos (MMUSD)
-------------------------------------------------------------------------       
Producto                            2015       2016     2017      2018
================================= ========= ========= ========= =========
Crudo                             1642254.8 1600634.4 2458799.2 2853824.6
GLP/butano/propano                 40171.64  60123.61 109991.91 208664.13
Gasolina                          380893.66 423613.28 559352.13 716835.44
================================= ========= ========= ========= =========

*Fuente: Anuario estadístico sectorial de hidrocarburos 2018 DGH, pag. 73*


.. figure:: img/importaciones_PJ.jpg
   :align:   center
   :width:   700 px

*Figure 3.3: Importaciones de energía en PJ. Fuente: propia*

.. figure:: img/importaciones_MMUSD.jpg
   :align:   center
   :width:   700 px

*Figure 3.3: Importaciones de energía en MMUSD. Fuente: propia*


.. _Proyecciones de importaciones: https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/ 

3.1.1.5 Exportaciones
--------------

Las importaciones según el "Anuario estadístico sectorial de hidrocarburos 2018" el 2018 fueron de un total aproximado de 316 (PJ), para crudo, GLP, gasolina y carbón, que representan un valor de 3819.72 MMUSD.


================================= ========= ========= ========= =========
                  Importaciones de hidrocarburos (MBLS)
------------------------------------------------------------------------- 
Producto                            2015       2016     2017      2018
================================= ========= ========= ========= =========
Crudo                               2906.63    845.25    572.58   2367.23
Gas Natura                         50898.88  60314.94  51808.68  51399.36
GLP/propano/butano                  1075.67   1460.97    607.97     66.17
Gasolinas                          16707.74  18678.92  19961.24  17803.36
================================= ========= ========= ========= =========

*Fuente: Anuario estadístico sectorial de hidrocarburos 2018 DGH, pag. 73*


================================= ========= ========= ========= =========
               Importaciones de hidrocarburos (MMUSD)
------------------------------------------------------------------------- 
Producto                            2015       2016     2017      2018
================================= ========= ========= ========= =========
Crudo                             120071.32  24015.81  25644.31 138873.88
Gas Natura                        449075.22 522171.53 747859.38 998645.90
GLP/propano/butano                 34427.77  32047.07  31875.49   4192.79
Gasolinas                         860197.63 789710.14 1091366.4 1182051.6
================================= ========= ========= ========= =========

*Fuente: Anuario estadístico sectorial de hidrocarburos 2018 DGH, pag. 73*

.. figure:: img/exportaciones_PJ.jpg
   :align:   center
   :width:   700 px


*Figure 3.3: Exportaciones de energía en PJ. Fuente: propia*

.. figure:: img/exportaciones_MMUSD.jpg
   :align:   center
   :width:   700 px

*Figure 3.3: EXportaciones de energía en MMUSD. Fuente: propia*

.. _Proyecciones de exportaciones: https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/ 


3.1.2 Emisiones de gases de efecto invernadero (GEI), precio social del carbono.
++++++++++++++++++++++

Las emisiones en un futuro cercanos se volveran un serio problema, no sólo medioambiental
sino existencial, ahora nos embarcamos en una lucha por reducir los productos de 
contaminación y la principal acción del sector energía y transportes es sustituir
los insumos que podrucen contaminación, las políticas climáticas hoy en día han 
planificado al 2050 lograr la carbononeutralidad. En la siguiente tabla se muestra el consumo de energía en PJ, las emisiones en Mega-ton CO2e y razón que hay de cada una por sector en el 2018. Además, se puede observar que los sectores que más Mton CO2e generan por unidad de PJ es el sector transporte seguido del sector industrial.


==================== ========= ========= ========= ========= =========== ========== ========== 
                       Energía consumida y emisones por sector (MMUSD)
---------------------------------------------------------------------------------------------- 
2018                  Pesca    Agro      Público    Minero   Residencial Industrial Transporte
                                                             y Comercial   
==================== ========= ========= ========= ========= =========== ========== ========== 
Energía [PJ]          3.075     6.388    12.176    75.847     210.704    163.819    359.798  
Emisiones [MtonCO2e]  0.123     0.139     0.326     1.281       4.4        7.006     24.94
Razón [MtonCO2e/PJ]   0.04      0.0218    0.0268    0.0169      0.0209     0.0428     0.0693
==================== ========= ========= ========= ========= =========== ========== ========== 
*Fuente: Balance nacional de energía 2018*

Los gases de efecto invernadero considerados son el CO2, NH4 y N2O, además tenemos que estos son tomados en su valor equivalente en CO2e, estos valores son tomados del IPCC 2006, a continuación se mostrarán.


+----------+------------+------------+------------+
|          |      CO2   |       CH4  |     N2O    |         
+----------+------------+------------+------------+
|Factor    |       1    |       21   |     310    |
+----------+------------+------------+------------+
*Fuente: Anexo 2 del informe 9 del PROSEMER*

Para los valores correspondientes a las tecnología de producción de energía eléctrica, que relacionan las emisones de GEI, en forma de CO2e, con la Produccióin de energía, se han encontrado en bibliografía los valores o rangos de valores de estos.

========================== ================ ================ =================
Tecnología                  Rango            Media            Unidades 
========================== ================ ================ =================
Refinerías                  949 to 1280             854.5      gCO2e/kWh 
Carboneras                  519 to 1190             1114.5     gCO2e/kWh 
Plantas de gas natural                                         gCO2e/kWh 
Plantas de biodiesel                                68.4       gCO2e/kWh           
Plantas térmicas de gas     485 to 991              738        gCO2e/kWh 
Plantas hidraúlicas           3 to 27                 15       gCO2e/kWh   
Plantas Photovoltáicas       79 to --                 79       gCO2e/kWh                       
Planta eólicas                14 to 21              17.5       gCO2e/kWh  
Plantas térmicas de diesel   519 to 1190            880        gCO2e/kWh    
========================== ================ ================ =================
                                  
*Fuente: GREENHOUSE GAS EMISSIONS FROM ENERGY SYSTEMS: COMPARISON AND OVERVIEW (R. Dones, T. Heck, S. Hirschberg)*





El precio social del carbono es una medida que captura el valor de los daños que causa la emisión de CO2, ayuda a devolver la responsabilidad de los daños a quienes lo causan y ellos puedan evitar eso, hoy en dia los precios de la tonelada de carbono en el mundo es aún bajo, sin embargo, hay países como suecia en donde los presios de la tonelada de carbono esta 126 US$/ton_CO2 (2016) y en proomedio de 10 US$/ton_CO2 para america latina, los precios de la tonelada de carbono en un escenario de descarbonización aumentarían. 

El precio social del carbono en Perú tiene un valor de 7.17 us$/ton-CO2 para el año 2016.


=============================== =======================
Parámetro                             us$/ton-CO2
=============================== =======================
Precio social del carbono                 7.17
=============================== =======================
*Fuente: CIUP, 2016*



3.1.3 Proyección de demanda - Ecuaciones de predicción de los sectores productivos
++++++++++++++++++++++

3.1.3.1 Metodología general usada para la predicción de los Sectores Productivos
--------------

Mediante el uso de modelos econométricos se ha proyectado las series de la demandas de los sectores productivos, tomando como variables exógenas: la población, el PBI por sectores, PBI per cápita, etc, en algunos de estas se incluye la tendencia lineal, tambien se ha proyectado con las tazas de crecimiento constantes para el sector agropecuario y público; analizando las series de tiempo para los sectores como procesos autoregresivos (a excepto de agropecuario y público, transporte ferroviario, naval y aéreo) donde con las variables explicativas se ha podido proyectar las demandas de los múltiples sectores hasta el 2050.
Los sectores analizados son los mismos que toma el PROSEMER, que a su vez son los mismos que toma del BEU 2013 (balance de energía útil); los sectores son:


**Se consideran 7 sectores productivo**

- k=1, (Residencial)
- k=2, (Comercial 
- k=3, (Público)
- k=4, (Industrial manufacturera en general)
- k=5, (Pesca)
- k=6, (Agropecuaria)
- k=7, (Minería y metalurgia)

Para el caso de transporte se ha dividido para su análisis en macrogrupos como carretero, ferroviario, naval, aéreo, metro y transporte masivo, a su vez transporte carretero y ferroviario están subdivididos en pasajero y carga.   

Los resultados de los sectores están en diferentes unidades como se puede observar en la Tabla 1, los resultados de transporte carretero están en pkm  y tkm debido que se quiere representar la demanda como un servicio <<necesidad de un servicio>>, sin embargo, los resultados para los demás sectores las unidades están en PJ (energía neta).


============================= ============================= ======================================== =========
Sector                        Variables explicativas               Uso                               Resultado
============================= ============================= ======================================== =========
Residencial                   PBI per cápita                Cons=f(ConsRes(t-1),PIBpc(t-1),tend(t))  PJ
Comercial                     PBI sector terciario          Cons=f(ConsCom(t-1),PIBter(t-1),tend(t)) PJ
Público                       Tasa de crecimiento constante                                          PJ
Agropecuario                  Tasa de crecimiento constante                                          PJ
Pesca                         Producción pesca y tendencia  Cons=f(ConsPesca(t-1),Prod(t-1),tend(t)) PJ
Minería                       PBI minería                   Cons=f(ConsMin(t-1),PIBMin(t-1),tend(t)) PJ
Manufactura insdustrial       PBI manufactura industrial    Cons=f(ConsMan(t-1),PIBMan(t-1),tend(t)) PJ
Energía escenario 2           PBI                           Cons=f(ConsEnerg(t-1),PIB(t-1),tend(t))  PJ
Trans. carretero pas. privado PBI                           Cons=f(ConsTransCarrPriv(t-1),PIB(t-1))  pkm
Trans. carretero pas. público PBI                           Cons=f(ConsTransCarrPubl(t-1),PIB(t-1))  pkm
Trans. carretero carga        PBI                           Cons=f(ConsTransCarrCarg(t-1),PIB(t-1))  tkm
Trans. ferroviario carga      PBI                           Cons=f(ConsTransFerrCarg(t-1),PIB(t-1))  tkm
Trans. ferroviario pasajeros  Población (POB)               Cons=f(ConsTransFerrPas(t-1),POB(t-1))   pkm
Trans. naval                  PBI                           Cons=f(ConsTransNav(t-1),PIB(t-1))       PJ
Trans. éreo                   PBI                           Cons=f(ConsTransAereo(t-1),PIB(t-1))     PJ
============================= ============================= ======================================== =========

*Fuente: Propia*

3.1.3.2 Variables explicativas de las demanda por sectores productivos
--------------

**PBI**

La variable utilizada como varible expliativa en la mayoría de los modelos es el PBI (producto bruto interno), los valores de esta variable se han tomado del T21, estos resultados son de un estudio que se realizó con el objetivo de predecir el crecimiento del PBI al 2050, los valores tabulados de crecimiento del PBI se pueden encontrar en anexos de este documento, Anexos en A3 `PBI <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_. En las siguientes gráficas se puede observar los valores de PBI, el porcentaje de crecimiento PBI, el PBI per cápita, y la producción por sector energético. 


.. figure:: img/Proyeccion_del_crecimiento_del_PBI_anual.png
   :align:   center
   :width:   700 px
*Figure 3.13: Proyección del crecimiento del PBI anual, Fuente: T21*

.. figure:: img/PBI_peru_miles_millones.png
   :align:   center
   :width:   700 px
*Figure 3.13: Proyección del PBI en miles de millones, Fuente: T21*

.. figure:: img/PBI_per_cápita.png
   :align:   center
   :width:   700 px
*Figure 3.13: Proyección del PBI per cápita, Fuente: T21*

.. figure:: img/produccion_sectores.png
   :align:   center
   :width:   700 px
*Figure 3.13: Proyección de la producción por sectores, Fuente: T21*

**Población**
Los valores de población corresponden a los resultados del T21, los valores grafiados se pueden observar en los anexos en A4 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_. En las siguientes gráficas se puede observar el crecimiento de la población.

.. figure:: img/población_peru_T21.png
   :align:   center
   :width:   700 px
*Figure 3.13: Proyección de la población en el Perú, Fuente: T21*


3.1.3.3 Ecuaciones utilizados para los diferentes sectores
--------------



**Sector residencial**
     Para el sector residencial se ha utilizado los valores históricos de demanda energética, PBI per cápita y tendencia de PBI para poder realizar las predicciones de la demanda,  a continuación se halla el pronóstico final (véase ecuación), los coeficientes se calculan mediante mínimización del error.

Donde:

- a, b, c y d                Coeficiente obtenidos por optimización.
- Demanda(t-1)               Consumo de Energía residencial año 𝑡-1.
- Tendencia PBI per-cápita   Tendencia del PBI per cápita.
- PBI Per cápita(t-1)        Producto Bruto Interno per cápita en el año t-1.


+--------------------+----------------------------+-----------------------+--------------------------+
| a                  | b                          | c                     |                          |
+--------------------+----------------------------+-----------------------+--------------------------+
| 0.332515326546485  | 0.683876696497229          | 0.266328892526584     |   -0.000362984959480442  |                    
+--------------------+----------------------------+-----------------------+--------------------------+
*Fuente: Propia*

.. math::

 \operatorname{Log}\left(Demanda_{t}\right) = a + b * \operatorname{Log}\left(Demanda_{t-1}\right) + c * \operatorname{Log}\left(PBI \operatorname{per capita}_{t-1}\right) + d * \text { Tendencia PBI per capita }



Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.



**Sector comercial**
    Para el sector comercial se ha utilizado los valores históricos de demanda energética, PBI sector terciario y tendencia de PBI terciario para poder realizar las predicciones de la demanda,  a continuación se halla el pronóstico final (véase ecuación), los coeficientes se calculan mediante mínimización del error.


Donde:

- a, b, c y d                       Coeficiente obtenidos por optimización.
- Demanda(t-1)                      Consumo de Energía residencial año 𝑡-1.
- Tendencia PBI sector terc         Tendencia de PBI sector terciario.
- PBI sector terciario(t-1)         Producto Bruto Interno del sector terciario en el año t-1.

+--------------------+----------------------------+-----------------------+--------------------------+
| a                  | b                          | c                     |                          |
+--------------------+----------------------------+-----------------------+--------------------------+
|-9.77046303344915   | -0.0173571403183178        | 1.16336449076213      |   0.0000107417534041619  |                    
+--------------------+----------------------------+-----------------------+--------------------------+
*Fuente: Propia*


.. math::

 \operatorname{Log}\left(Demanda_{t}\right) = a + b * \operatorname{Log}\left(Demanda_{t-1}\right) + c * \operatorname{Log}\left(PBI \operatorname{sector terciario}_{t-1}\right) + d * \text { Tendencia PBI terciario}



Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.


**Sector manufactura industrial**

     Para el sector comercial se ha utilizado los valores históricos de demanda energética, PBI manufacturero y tendencia de PBI manufacturero para poder realizar las predicciones de la demanda,  a continuación se halla el pronóstico final (véase ecuación), los coeficientes se calculan mediante mínimización del error.


.. math::

 \operatorname{Log}\left(Demanda_{t}\right) = a + b * \operatorname{Log}\left(Demanda_{t-1}\right) + c * \operatorname{Log}\left(PBI \operatorname{sector manufactura}_{t-1}\right) + d * \text {Tendencia PBI manufactura}


Donde:
 
- a, b, c y d           Coeficiente obtenidos por optimización.
- Demanda(t-1)          Consumo de Energía residencial año 𝑡-1.
- Tendencia PBI manu    Normalizado del consumo de Energía residencial año 𝑡-1.
- PBI manu              Producto Bruto Interno per cápita en el año t-1.

+--------------------+----------------------------+-----------------------+--------------------------+
| a                  | b                          | c                     |                          |
+--------------------+----------------------------+-----------------------+--------------------------+
|-1.08509758781935   | 0.760781402962728          | 0.23355680052771      |  -0.0000030471976246794  |                    
+--------------------+----------------------------+-----------------------+--------------------------+
*Fuente: Propia*



Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Sector minería**

     Para el sector comercial se ha utilizado los valores históricos de demanda energética, PBI minería y tendencia de PBI mineria para poder realizar las predicciones de la demanda,  a continuación se halla el pronóstico final (véase ecuación), los coeficientes se calculan mediante mínimización del error.


.. math::

 \operatorname{Log}\left(Demanda_{t}\right) = a + b * \operatorname{Log}\left(Demanda_{t-1}\right) + c * \operatorname{Log}\left(PBI \operatorname{sector minero}_{t-1}\right) + d * \text { Tendencia PBI minero}



Donde:
 
- a, b, c y d                  Coeficiente obtenidos por optimización.
- Mi(t-1)                      Consumo de Energía minería en el año 𝑡-1.
- PBI mine(t-1)                Producto Bruto Interno del sector minería en el año t-1.
- Tendencia PBI mine(t-1)      Tendencia del Producto Bruto Interno del sector minería en el año t-1.

+--------------------+----------------------------+-----------------------+--------------------------+
| a                  | b                          | c                     |                          |
+--------------------+----------------------------+-----------------------+--------------------------+
|-0.762910481127139  | 0.452903476632176          | 0.285379315325919     |  0.000013718561762997    |                    
+--------------------+----------------------------+-----------------------+--------------------------+
*Fuente: Propia*



Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Sector agropecuario**
     Para el sector agropecuario se ha tomado una tasa de crecimiento constante la cual se ha fijado en 1.5% anual para la proyección hasta el 2050.

Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Sector público**
     Para el sector público se ha tomado una tasa de crecimiento constante la cual se ha fijado en 1% anual para la proyección hasta el 2050.

Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.


**Sector pesca**
     Para el sector pesca se ha utilizado los valores históricos de demanda energética y PBI producción para poder realizar las predicciones, en un inicio se hacen ajustes estadísticos del PBI sector pesca y de la demanda, luego con una regresión lineal se halla la tendencia del PBI (tendenciaPBI), para después incorporarla a la ecuación de autoregreción (vésase ecuación 9) .



+-----------------------+----------------------+---------------------+------------------------+
| a                     | b                    | c                   |  d                     |
+-----------------------+----------------------+---------------------+------------------------+
|-0.177833164570406     | 0.49497916077867     | 0.284105977921334   | -0.000663149769280645  |
+-----------------------+----------------------+---------------------+------------------------+
*Fuente: Propia*

.. math::

 \operatorname{Log}\left(Demanda_{t}\right) = a + b * \operatorname{Log}\left(Demanda_{t-1}\right) + c * \operatorname{Log}\left(PBI \operatorname{sector pesca}_{t-1}\right) + d * \text { Tendencia PBI pesca}



Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

3.1.2.3 Ecuaciones utilizados para el sector transporte
---------

La proyección del consumo de energía del sector de transporte considera los modales de transporte de pasajero por carretera (privado y público) y de carga, el ferroviario (pasajero y carga), el marítimo, aéreo y metro.


==== ==================== ======================= ==================== ======================
m     Modal                  Pasajero                Uso                   Resultado
==== ==================== ======================= ==================== ======================
01    Por carretera          Pasajero público      Vehiculos públicos      pkm
02    Por carretera          Pasajero privado      Vehículos privado       pkm
03    Por carretera          Carga                 hehículos de carga      tkm
04    Ferroviario            Pasajero              Líneas 1,2,3            pkm
05    Ferroviario            Carga                 Líneas 1 e 2            tkm
05    Naval                  Pasajero & Carga                              En. neta
06    Aéreo                  Pasajero & Carga                              En. neta
07    Metro                  Pasajero                                      En. neta
08    Transporte masivo      Pasajero                                      pkm
==== ==================== ======================= ==================== ======================
*Fuente: Propia*
   
**Subdivisión transporte carretero privado**

Para la subdivisión del sector transporte se ha utilizado un modelo autoregresivo, para el cual primero se ha utilizado los valores del logaritmo del PBI y de la demanda del sector transporte para luego ajustar la ecuación del modelo, todo esto en la herramienta solver de Excel, se obtiene los coeficientes del modelo para finalmente poder hallar el pronóstico final.
Como ya se ha mencionado anteriormente antes los resultados de estas proyecciones están en pkm.


.. math::

 \text { T}_{t} = a * \operatorname{ln}\left(T_{t-1}\right) + b * \operatorname{ln}\left(PBI_{t-1}\right)+c

+----------------+----------------------------+-----------------------+
| a              | b                          | c                     |
+----------------+----------------------------+-----------------------+
| 0.84331819     | 0.1209881                  | 0.36183109            |
+----------------+----------------------------+-----------------------+
*Fuente: Propia*

- a, b y c          Coeficiente obtenidos por optimización.
- T(t-1)            Consumo de Energía sector transporte privado en el año 𝑡-1.
- PBI(t-1)          Producto Bruto Interno en el año t-1.



Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Subdivisión transporte carretero público**

Para la subdivisión del sector transporte público se ha utilizado un modelo autoregresivo, para el cual primero se ha utilizado los valores del logaritmo del PBI y de la demanda del sector transporte para luego ajustar la ecuación del modelo, todo esto en la herramienta solver de Excel, se obtiene los coeficientes del modelo para finalmente poder hallar el pronóstico final.
Como ya se ha mencionado anteriormente antes los resultados de estas proyecciones están en pkm.


.. math::

 \text { T}_{t} = a * \operatorname{ln}\left(T_{t-1}\right) + b * \operatorname{ln}\left(PBI_{t-1}\right)+c

+----------------+----------------------------+-----------------------+
| a              | b                          | c                     |
+----------------+----------------------------+-----------------------+
| 0.78746426     | 0.19176726                 | 0.24507861            |
+----------------+----------------------------+-----------------------+
*Fuente: Propia*

- a, b y c          Coeficiente obtenidos por optimización.
- T(t-1)            Consumo de Energía sector transporte público en el año 𝑡-1.
- PBI(t-1)          Producto Bruto Interno en el año t-1.

Las medidas de error para el modelo fueron 

+----------------------------------------+----------------------------+
| Tipo de error                          | Valoración                 |
+----------------------------------------+----------------------------+
| RMSE (root mediun square error )       | 1248.217912                |
+----------------------------------------+----------------------------+
| MAPE (mean absolute percentage error ) | 0.37%                      |
+----------------+-----------------------+----------------------------+
*Fuente: Propia*

Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Subdivisión transporte carretero carga**

Para la subdivisión del sector transporte público se ha utilizado un modelo autoregresivo, para el cual primero se ha utilizado los valores del logaritmo del PBI y de la demanda del sector transporte para luego ajustar la ecuación del modelo, todo esto en la herramienta solver de Excel, se obtiene los coeficientes del modelo para finalmente poder hallar el pronóstico final.
Como ya se ha mencionado anteriormente antes los resultados de estas proyecciones están en pkm.


.. math::

 \text { T}_{t} = a * \operatorname{ln}\left(T_{t-1}\right) + b * \operatorname{ln}\left(PBI_{t-1}\right)+c

+----------------+----------------------------+-----------------------+
| a              | b                          | c                     |
+----------------+----------------------------+-----------------------+
| 0.82591532     | 0.16141611                 | 0.29490398            |
+----------------+----------------------------+-----------------------+
*Fuente: Propia*

- a, b y c          Coeficiente obtenidos por optimización.
- T(t-1)            Consumo de Energía sector transporte de carga en el año 𝑡-1.
- PBI(t-1)          Producto Bruto Interno en el año t-1.

Las medidas de error para el modelo fueron 

+----------------------------------------+----------------------------+
| Tipo de error                          | Valoración                 |
+----------------------------------------+----------------------------+
| RMSE (root mediun square error )       | 442.3843504                |
+----------------------------------------+----------------------------+
| MAPE (mean absolute percentage error ) | 0.08%                      |
+----------------+-----------------------+----------------------------+
*Fuente: Propia*

Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Subdivisión transporte ferroviario pasajeros**
    Para esta subdivisón se ha utilizados las ecuaciones del modelo TIMES para obtener la proyección, las cuales en un inicio calcula Q_(t,m), (cantidad de vehículos en venta) con los valores de población, con este resultado se prosigue a calcular los valores de consumo de energía de las principales flotas de trenes en el país, a este valor  le multiplica por un peso que denota el ratio de pasajero por kilómetro, que se denota por  K. 

.. math::

  \operatorname{ln}\left(Q_{t,m}\right) =\alpha_{m} *+ \beta_{m}  * \operatorname{ln}\left(POB_{t}\right)

.. math::

 W_{t, m, l}=W_{t-1, m, l} \times \frac{Q_{t, m}}{Q_{t-1, m}}

.. math::

 pkm_{m, t, r}=\sum_{l}\left(W_{t, m, l} \times k m_{-} W_{m, l} \times \omega_{m, l}\right)

Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A16 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Subdivisión transporte ferroviario carga**
    Para esta subdivisón se ha utilizados las ecuaciones del modelo TIMES para obtener la proyección, las cuales en un inicio calcula Q_(t,m), (cantidad de vehículos en venta) con los valores de PBI, con este resultado se prosigue a calcular los valores de consumo de energía de las principales flotas de trenes en el país, a este valor  le multiplica por un peso que denota el ratio de pasajero por kilómetro, que se denota por  

.. math::

  \operatorname{ln}\left(Q_{t,m}\right) =\alpha_{m} *+ \beta_{m}  * \operatorname{ln}\left(PBI_{t}\right)

.. math::

 W_{t, m, l}=W_{t-1, m, l} \times \frac{Q_{t, m}}{Q_{t-1, m}}

.. math::

 pkm_{m, t, r}=\sum_{l}\left(W_{t, m, l} \times k m_{-} W_{m, l} \times \omega_{m, l}\right)

Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A16 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.

**Subdivisión transporte naval**
    Para esta subdivisón se ha utilizados las ecuaciones del modelo TIMES para obtener la proyección, las cuales en un inicio calcula Q_(t,m), con los valores de PIB, ahora con los valores de la demanda anterior se calcula el nuevo valor con la ecuación 14. 

.. math::

 \operatorname{ln}\left(Q_{t,m}\right) =\alpha_{m} *+ \beta_{m}  * \operatorname{ln}\left(PBI_{t}\right)

.. math::

 E_{t, m}=E_{t-1, m} \times \frac{Q_{t, m}}{Q_{t-1, m}}


Subdivisión transporte aéreo
Para esta subdivisón se ha utilizados las ecuaciones del modelo TIMES para obtener la proyección, las cuales en un inicio calcula Q_(t,m), con los valores de PIB, , ahora con los valores de la demanda anterior se calcula el nuevo valor con la ecuación 16

.. math::

 \operatorname{ln}\left(Q_{t,m}\right) =\alpha_{m} *+ \beta_{m}  * \operatorname{ln}\left(PBI_{t}\right)

.. math::

 E_{t, m}=E_{t-1, m} \times \frac{Q_{t, m}}{Q_{t-1, m}}

Los valores tabulados al 2050 se pueden encontrar en anexos de este documento, en Anexos en A14 respectivamente `demandas <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.




3.2 Datos e información
=======================================



Como ya se ha mencionado en "Data Processing", el modelo OSeMOSYS de energía y transporte está compuesto por diferentes comodities y fuels que son propios de cada país o sistema. Ahora trataremos la configuración del modelo OSeMOSYS, esta se da a través de los siguientes items:

 - *Sets*
 - *Parameters*
 - *Variables*
 - *Obejetive functions*
 - *Constraints*

Nosotros trataremos con un modelo simple, el cual es la vesión más manejable, por el momento debido a las necesidades, en el modelo OSeMOSYS Perú. Cada item está compuesto por un conjunto de items y sus valores son particulares del sistema a modelar, a continuación mostaremos todos estos para la cnfiguración de un modelo simple, lo cual sisgnifica que nuestra función objetivo de costo es corta. 


+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                                      Items de configuración para un modelo simple                                                         |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|     Sets        | Parameters                 | Variables                          |Ojective  |       Constraints                          |
|                 | ("Insumos")                | ("salidas")                        |functions |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|EMISSION         | AccumulatedAnnualDemand    | AccumulatedNewCapacity             | OFS_Cost |Acc1_FuelProductionByTechnology             |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|FUEL             | AnnualEmissionLimit        | AnnualEmissions                    |          |Acc2_FuelUseByTechnology                    |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|MODE OF OPERATION| AnnualExogenousEmission    | AnnualFixedOperatingCost           |          |Acc3_AverageAnnualRateOfActivity            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|REGION           | AvailabilityFactor         | AnnualTechnologyEmission           |          |CAa1_TotalNewCapacity                       |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|STORAGE          | CapacityFactor             | AnnualTechnologyEmissionByMode     |          |CAa2_TotalAnnualCapacity                    |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|REGION           | CapacityOfOneTechnologyUnit| AnnualVariableOperatingCost        |          |CAa5_TotalNewCapacity                       |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|TECHNOLOG        | CapacityToActivityUnit     | CapitalInvestment                  |          |CC1_UndiscountedCapitalInvestment           |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|TIMESLICE        | CapitalCost                | Demand                             |          |E2_AnnualEmissionProduction                 |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|YEAR             | CapitalCostStorage         | DiscountedSalvageValue             |          |EBa10_EnergyBalanceEachTS4                  |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | DepreciationMethod         |DiscountedTechnologyEmissionsPenalty|          |EBa1_RateOfFuelProduction1                  |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | DiscountRate               | NewCapacity                        |          |EBa2_RateOfFuelProduction2                  |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | EmissionActivityRatio      | NewStorageCapacity                 |          |EBa4_RateOfFuelUse1                         |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | EmissionsPenalty           | NumberOfNewTechnologyUnits         |          |EBa5_RateOfFuelUse2                         |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 |FixedCost                   |ProductionByTechnology              |          |NCC1_TotalAnnualMaxNewCapacityConstraint    |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | InputActivityRatio         | ProductionByTechnologyAnnual       |          |NCC2_TotalAnnualMinNewCapacityConstraint    |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | ModelPeriodEmissionLimit   | RateOfActivity                     |          |OC1_OperatingCostsVariable                  |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 |ModelPeriodExogenousEmission| RateOfProductionByTechnology       |          |OC2_OperatingCostsFixedAnnual               |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 |OperationalLife             |RateOfProductionByTechnologyByMode  |          |SI6_SalvageValueStorageAtEndOfPeriod1       |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | OperationalLifeStorage     | RateOfUseByTechnology              |          |SV3_SalvageValueAtEndOfPeriod3              |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | OutputActivityRatio        | RateOfUseByTechnologyByMode        |          |SV4_SalvageValueDiscountedToStartYear       |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | REMinProductionTarget      | SalvageValue                       |          |TAC1_TotalModelHorizonTechnologyActivity    |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | RETagFuel                  | SalvageValueStorage                |          |Short_Code_Equations                        |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | RETagTechnology            | TotalAnnualTechnologyActivityByMode|          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | ReserveMargin              | TotalCapacityAnnual                |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | ReserveMarginTagFuel       | TotalTechnologyAnnualActivity      |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | ReserveMarginTagTechnology |TotalTechnologyModelPeriodActivity  |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | ResidualCapacity           | Trade                              |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | SpecifiedAnnualDemand      | UseByTechnology                    |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | SpecifiedDemandProfile     |                                    |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | TradeRoute                 |                                    |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | VariableCost               |                                    |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
|                 | YearSplit                  |                                    |          |                                            |
+-----------------+----------------------------+------------------------------------+----------+--------------------------------------------+
*Fuente: Propia*
 
No todos estos items han sido insertados en el modelo, debido que se ha trabajado un modelo que se acomoda más a las necesidades del Perú, ahora se pueden encontrar todos los valores de corespondiente a todos los item de configuración en `Items <https://github.com/guidogz/Doc_ELP_Peru/blob/master/docs/999Annexes.rst/>`_.


3.2.1 Sets
++++++++++++



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
++++++++++++

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
















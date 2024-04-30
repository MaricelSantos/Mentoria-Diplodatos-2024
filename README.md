# **Mentoria-Diplodatos-2024**

# **Conexiones Transparentes: Descubriendo Relaciones Cruciales para la Calidad del Agua en el Río de La Plata**

## Descripción y Objetivos propuestos: 

En este proyecto se propone estudiar un dataset que contiene información de monitoreo de agua para diferentes periodos y estaciones a lo largo de la costa del Rio de La Plata. El objetivo es encontrar las interrelaciones entre variables, así como la sensibilidad de las mismas, además de tratar de encontrar posibles patrones relacionados a la estacionalidad y las características de las poblaciones circundantes a la estación monitoreada. Esto puede ser valioso a la hora de tomar decisiones gubernamentales para evitar y penar la contaminación protegiendo así la calidad de nuestras aguas. 
El análisis de agua tiene en cuenta aspectos físicos, químicos, microbiológicos y organolépticos. Es importante reconocer que algunos de estos parámetros de control son más costosos de evaluar, tanto en términos de recursos como de tiempo necesario. En este contexto, resulta particularmente interesante explorar las posibles correlaciones entre estas variables utilizando herramientas del aprendizaje supervisado. Este enfoque permitirá no solo comprender las relaciones intrínsecas entre los diversos aspectos del agua, sino también identificar oportunidades para optimizar los recursos, centrándose en la predicción de variables mediante la observación y monitorización de aquellas menos costosas y que incluso en algunos casos pueden ser medidas en tiempo real. 


## DATOS
El dataset constará de la conjunción de algunos datos públicos del Ministerio de Ambiente y Desarrollo Sostenible (2015-2023). El registro cuenta con información de 42 estaciones, monitoreadas entre una y cuatro veces por año (primavera, verano, otoño. Invierno). Se compilará información del año 2022, año en cual tambien fueron registradas más de 200 sustancias químicas medidas en superficie y en sedimento. A su vez, se anexa información sobre la población, caracteristicas y actividades del municipio al que pertenece el sitio de monitoreo.
En este repositorio puede encontrar los datos originales, descargados de https://ciam.ambiente.gob.ar/repositorio.php?tid=1&stid=2&did=386# y el merge de los mismo. El resultado es el csv con el que trabajaremos "Conexiones_Transparentes.csv". Las features disponibles son las siguientes y sus unidades:

## Variables principales

* Las columnas 'orden', 'sitio' y 'codigo' se relacionan con las estaciones de monitoreo. El monitoreo abarca de Tigre a Berisso, porque lo que el orden 1 corresponde a estaciones de Tigre mientras que 42 a Berisso. A su vez la columna sitio informa exactamente de que lugar se trata mientra que la última la códifica.
* campaña: estación del año en que fue monitoreada.
* tem_agua: temperatura del agua [°C]
* tem_aire: temperatura del aire [°C]
* od: óxigeno disuelto [mg/L]
* pH: potencial hidrogeno escala 1-14
* olores: presencia/ausencia
* color: presencia/ausencia
* espumas: presencia/ausencia
* mat_susp: material suspendido - presencia/ausencia
* colif_fecales_ufc_100ml: coliformes fecales [U.F.C/100mL] (unidades formadoras de colonia/100mL)
* escher_coli_ufc_100ml: Escherichia coli [U.F.C/100mL]
* enteroc_ufc_100ml: Enterococos [U.F.C/100mL]
* nitrato_mg_l: Nitratos (NO3-) [mg/L]
* nh4_mg_l: Amonio (NH4+) [mg/L]
* p_total_l_mg_l: Fósforo Total [mg/L]
* fosf_ortofos_mg_l: Fosfatos (PO4) [mg/L]
* dbo_mg_l: demanda biológica de óxigeno [mg/L]
* dqo_mg_l: demanda química de óxigeno [mg/L]
* turbiedad_ntu: Turbidez NTU: Unidades Nefelométricas de Turbidez
* hidr_deriv_petr_ug_l: Hidrocarburos derivados del Petróleo [ug/L]
* cr_total_mg_l: Cromo Total [mg/L]
* cd_total_mg_l: Cadmio Total [mg/L]
* clorofila_a_ug_l: Clorofila ‘a’ [ug/L]
* microcistina_ug_l: Microcistina  [ug/L]
* ica: Indice de calidad de agua. Deberiva de ecuaciones que relacionan las características organolepticas, biologicas, químicas y físicas del agua.
* calidad_de_agua: Clasificación que depende del ICA

## Variables sitio de monitoreo
* gobierno_local: Municipio al cual pertenece el sitio
* latitud: del sitio
* longitud: del sitio
* Poblacion_partido: Población del partido/municipio
* Personas_con_cloacas: Personas/población que tienen cloaca
* Actividad_principal: que se desarrolla en el municipio (variable categorica)

Las siguientes columnas ordenan al municipio al que pertenece el sitio respecto a la actividad, siendo el que más aporta a dicha actividad el número 1 (variables ordinales).

* Agricultura, ganadería, caza y silvicultura:
* Pesca explotación de criaderos de peces y granjas piscícolas y servicios conexos
* Explotación de minas y canteras
* Industria Manufacturera
* Electricidad, gas y agua
* Construcción
* Servicios

## Sustancias químicas en superficie y sedimentos

Estas columnas puede contener el valor númerico de la medición correspondiente con las unidades que se detallan en la lista de agrupación de sustancia o la siguiente codificación:
   - <LC: Menor al límite de cuantificación.
   - ND: No detectable según metodología empleada
   - D-NC: Detectable no cuantificable según metodología empleada.
Las variables que terminan en _x pertenecen a superficie, mientras que las que terminan en _y pertenecen a sedimentos.
Las unidades de las variables son en función de volumen (principalmente litros) para superficie y en función de masa (generalmente kilogramo) para sedimentos. Las mismas se informan por grupo, caso contrario aparece contiguo al nombre de la variable. 

Grupos

* Parámetros generales [mg/L]/[mg/kg] :
    - Dureza [mg CaCO3]
    - Fluoruros
    - Nitritos
    - Sólidos_totales
    - Sulfatos
    - Sulfuros
    - Granulometría_Arena [%]
    - Granulometría_Limo [%]
    - Granulometría_Arcilla [%]
    - Carbono_orgánico_total [%]
    - Nitrógeno_total
    - Cianuro
    - SAAM (sustancias activas al azul de metileno)
    - Fósforo_total
    - Amonio
    - Nitratos
    - Fenoles_totales
* Plaguicidas multiresiduo [ng/L]/[µg/kg]
    - 2,4_D
    - 2,4_DB
    - Alacloro
    - Aletrina
    - AMPA
    - Atrazina
    - Atrazina_2_hidroxi
    - Atrazina_desetil
    - Atrazina_desisopropil
    - Acetamiprid
    - Acetoclor
    - Aldicarb
    - Ametrina
    - Azoxistrobina
    - Benazolina
    - Benomilo
    - Bispiribac
    - Boscalid
    - Butóxido_de_piperonilo
    - Carbarilo
    - Carbendazim
    - Carbofurano
    - Cipermetrina
    - Clorantraniliprol
    - Clorimuron_Etil
    - Clorpirifos_(Etil_y_Metil)
    - Ciproconazol
    - Deltametrina
    - Diazinon
    - Dicamba
    - Diclosulam
    - Difenoconazol
    - Diflubenzuron
    - Dimetoato
    - Diuron
    - Epoxiconazol
    - Fenitrotión
    - Fipronil
    - Fludioxonil
    - Flumioxazin
    - Flurocloridona
    - Glifosato
    - Glufosinato
    - Haloxifop_metil
    - Imazapic
    - Imazapir
    - Imazaquin
    - Imidacloprid
    - Imazetapir
    - Kresoxim_metil
    - Lactofen
    - Lambda_cialotrina
    - Linurón
    - Mancozeb
    - Malatión
    - MCPA
    - Metalaxil
    - Metconazol
    - Metolacloro
    - Metomilo
    - Metribuzina
    - Metsulfuron_metil
    - Paratión_etil
    - Pendimetalina
    - Permetrina
    - Picoxistrobina
    - Piraclostrobina
    - Prometrina
    - Spinosad_A
    - Spinosad_D
    - Saflufenacilo
    - Sulfentrazona
    - Sulfluramida
    - TCP_(Metab_Clorpirifos)
    - Tebuconazol
    - Tetrametrina
    - Tiacloprid
    - Tiametoxam
    - Thiodicarb
    - Trifloxistrobina
    - Trifluralina
    - Triticonazol
    - Tropamezona    

* Ionóforos de uso veterinario [ng/L]/[µg/kg]
    - Clortetraciclina
    - Doxiciclina
    - Lasalocid
    - Maduramicina
    - Monensina
    - Oxitetraciclina
    - Salinomicina
    - Semduramicina
    - Tetraciclina
    - Tilosina

* Productos de Cuidado Personal [ng/L]/[µg/kg]
   - Anilina
   - Metiltriclosan
   - Metil_parabeno
   - Etil_parabeno
   - Propil_parabeno
   - Butil_parabeno
   - Triclosan
   - Metil_triclosan

* Antibióticos (sulfamidas) [ng/L]/[µg/kg]
   - Sulfapiridina
   - Sulfadiazina
   - Sulfatiazol
   - Sulfamerazina
   - Sulfametazina
   - Sulfametoxazol
   - Sulfadimetoxina
   - Sulfaguanidina
   - Sulfametoxipiridazina

* Familia de Abamectinas [ng/L]/[µg/kg]
   - Abamectina
   - Emamectina
   - Moxidectina
   - Doramectina
   - Ivermectina

* Farmacos de uso Humano [ng/L]/[µg/kg]
   - Alprazolam
   - Amoxicilina
   - Atenolol
   - Azitromicina
   - Bromazepam
   - Cafeína
   - Carbamazepina
   - Carvedilol
   - Cefalexina
   - Ciprofloxacina
   - Claritromicina
   - Clonazepam
   - Cloranfenicol
   - Diclofenaco
   - Difenhidramina
   - Dipirona
   - Enalapril
   - Enrofloxacina
   - Eritromicina
   - Etinilestradiol
   - Estradiol
   - Florfenicol
   - Fluoxetina
   - Ibuprofeno
   - Indometacina
   - Lorazepam
   - Metformina
   - Norfloxacina
   - Oxicarbamacepina
   - Paracetamol
   - Propinox
   - Salbutamol
   - Sildenafilo

* Plaguicidas organoclorados persistentes [ng/L]/[µg/kg]
   - Aldrin
   - pp_DDD
   - op_DDE
   - pp_DDE
   - op_DDT
   - pp_DDT
   - Dieldrin
   - Endosulfanes
   - Endrina
   - Heptacloro
   - Epóxido_de_heptacloro_(isóm_A)
   - Epóxido_de_heptacloro_(isóm_B)
   - Alfa_HCH
   - Beta_HCH
   - Gama_HCH
   - Metoxicloro
   - Dicofol
   - Gama_clordano
   - Alfa_endosulfan
   - Alfa_clordano
   - DDE
   - Endrin
   - Beta_endosulfan
   - DDD
   - Endosulfán_sulfato
   - DDT
   - Endrin_cetona
   - a_BHC
   - b_BHC
   - g_BHC

* Metales y Metaloides [µg/L]/[µg/g]
   - Aluminio
   - Cobalto
   - Níquel
   - Cobre
   - Zinc
   - Arsénico
   - Estaño
   - Mercurio
   - Plomo

* Compuestos Fenolicos [ug/L]/[µg/kg]
   - 2-sec-Butil-4,6-dinitrofenol
   - p_Clorometacresol
   - 2-Clorofenol
   - o-metilfenol
   - m-metilfenol
   - p-metilfenol
   - 2-Ciclohexil-4,6-dinitrofenol
   - 4-Cloro-3-metilfenol
   - 2,4-Diclorofenol
   - 2,6-Diclorofenol
   - 2,4-Dimetilfenol
   - 2,4-Dinitrofenol
   - 2-Metil-4,6-dinitrofenol
   - 2-Nitrofenol
   - 4-Nitrofenol
   - Pentaclorofenol
   - Fenol
   - Tetraclorofenol
   - Triclorofenol_(isómeros)
   - 2,4,6-Triclorofenol
   - Nonilfenol

* Hidrocarburos aromáticos [ng/L]/[µg/kg]
   - Naftaleno
   - Acenaftileno
   - Acenafteno
   - Fluoreno
   - Fenantreno
   - Antraceno
   - Fluoranteno
   - Pireno
   - Benzo(a)antraceno+criseno
   - Benzo(b)fluoranteno
   - Benzo(k)fluoranteno
   - Benzo(a)pireno_+_Dibenzo_(a,h)antraceno
   - Indeno(1,2,3-c,d)pireno
   - Benzo(g,h,i)perileno
   - HAPs_totales

* Compuestos Organicos (Sólo sedimento) [µg/kg]
   - cloroformo
   - Acetona
   - Acetonitrilo
   - Acroleína_(Propenal)
   - Benceno
   - Cloruro_de_Bencilo
   - Bromobenceno
   - Bromoclorometano
   - Bromoformo_
   - Bromometano
   - n-Butanol
   - 2-Butanona_(MEK)_
   - t-Butil_alcohol
   - Tetracloruro_de_Carbono
   - clorobenceno_
   - 1-clorobutano_
   - cloroetano_
   - 2-cloroetanol_
   - 1-clorohexano
   - clorometano_
   - 2-clorotolueno_
   - 4-clorotolueno_
   - 1,2-Diclorobenceno_
   - 1,3-Diclorobenceno_
   - 1,4-Diclorobenceno_
   - 1,3-Dicloropropano
   - 1,2-Dicloropropano_
   - 2,2-Dicloropropano_
   - 1,4-Dioxano_
   - Acetato_de_Etilo
   - Etil_benceno_
   - 2-Hexanona_
   - Isobutil_alcohol_
   - Metil_tert-butil_eter_(MTBE)
   - Metilciclohexano_
   - Diclorometano
   - 4-Metil-2-pentanona_(MIBK)
   - Nitrobenceno_(NB)
   - Piridina
   - Estireno
   - 1,1,1,2-Tetracloroetano
   - 1,1,2,2-Tetracloroetano
   - Tetracloroeteno
   - Tolueno
   - 1,2,3-Triclorobenceno
   - 1,2,4-Triclorobenceno
   - 1,1,1-Tricloroetano
   - 1,1,2-Tricloroetano
   - 1,2,3-Trimetilbenceno_
   - 1,2,4-Trimetilbenceno_
   - 1,3,5-Trimetilbenceno_
   - Cloruro_de_Vinilo
   - m-xileno
   - o-xileno_
   - p-xileno_
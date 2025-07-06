# Mappings of Hungarian healthcare code sets to OMOP CDM standards 

This repository contains translations of various health-related code sets used in the Hungarian healthcare system to OMOP CDM (Common Data Model) standard concepts. The translations aim to facilitate the integration and standardization of health data for research and analytics.

All mappings in this repository use OMOP CDM Vocabulary v5.0 (released on 31-AUG-23).

# Mapping files

## Diagnoses

Diagnosis codes are BNO codes in the Hungarian healthcare system, most of which can easily be transformed to ICD10 codes by adding a dot after the third character. After this step, the official ICD10 SNOMED CT mapping was used, downloaded from Athena. The other codes, which are not possible to map with this automated method, were mapped by hand to SNOMED CT. 

## Procedures

As procedure codes (OENO codes) contain procedures, measurements, observations, devices, and even medicines, there are several target vocabularies and domains. The main target was the vocabulary SNOMED CT, Procedure domain, but others include Device, Observation, and Measurement domain; LOINC, RxNorm, and RxNorm Extension vocabularies, when needed.   
A publication about the mapping can be found here: [https://doi.org/10.1186/s12874-023-02036-x](https://doi.org/10.1186/s12874-023-02036-x)   
As the mapping procedure codes are done by hand, not all OENO codes are mapped yet; it is an ongoing work. If someone would like to take part and validate or complement the mapping, please contact us. 

## Drugs

The medicines in Hungary are identified by the TTT code. Our mapping is based on the regularly updated official medicine list (PUPHA) published here:  
[https://www.neak.gov.hu/felso\_menu/szakmai\_oldalak/gyogyszer\_segedeszkoz\_gyogyfurdo\_tamogatas/egeszsegugyi\_vallalkozasoknak/pupha/Vegleges\_PUPHA](https://www.neak.gov.hu/felso_menu/szakmai_oldalak/gyogyszer_segedeszkoz_gyogyfurdo_tamogatas/egeszsegugyi_vallalkozasoknak/pupha/Vegleges_PUPHA)   
The mapping was done with the help of the DrugMapping Tool ([https://github.com/EHDEN/DrugMapping](https://github.com/EHDEN/DrugMapping)) to RxNorm and RxNorm Extension. The main target Concept Class is Clinical Drug, although where it was not possible, other target concept classes are: Clinical Drug Comp, Clinical Drug Form, and Ingredient. 

ATC codes are present in the original Pupha file; therefore, there is an official mapping available. 

Our mapping only contains marketed medicines. Besides the marketed medicines, other products can have a TTT code. These others, which are not included in the mapping, are the following: Formulae Normales and magistral drugs, the Pharmacopoeia Hungarica drugs, nutritional formulas or medicinal food products, and medical aids or devices. 

## Laboratory

Every laboratory uses its own codes to describe the measured entities. There are certain procedure (OENO) codes, which serve as a reimbursement code for the laboratory procedure. Although these codes are frequently not precise laboratory measurements, but wider concepts. Therefore, we do not upload a laboratory code mapping. In case someone is interested in an OENO-LOINC mapping, a Hungarian university, the University of Debrecen, created one and uploaded it to their website: [https://labmed.unideb.hu/hu/loinc-tablazatok](https://labmed.unideb.hu/hu/loinc-tablazatok) 

## 

# How to use

The suggested use of these files are:  
BNO and OENO mappings

1. Create your own source code files according to “Importing Source Codes into Usagi” part of the Usagi documentation ( [https://ohdsi.github.io/Usagi/usage.html\#Importing\_Source\_Codes\_into\_Usagi](https://ohdsi.github.io/Usagi/usage.html#Importing_Source_Codes_into_Usagi) ) then import it.  
2. Choose File –\> Apply previous mapping, and select the provided Usagi mapping files. ( [https://ohdsi.github.io/Usagi/usage.html\#Updating\_an\_Usagi\_mapping](https://ohdsi.github.io/Usagi/usage.html#Updating_an_Usagi_mapping) )  
3. Identify codes that have not inherited approved mappings from the provided mapping, and map them as usual.

Drug mapping files:

1. Add your mappings to the input files of the Drug Mapping Tool according to the documentation ( [https://github.com/EHDEN/DrugMapping](https://github.com/EHDEN/DrugMapping) )  
2. Run the mapping  
    

# Contributions

All contributions are welcome\! Please contact us or create an issue. 


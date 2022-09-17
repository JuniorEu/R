Application de visualisation de la base FLORES pour l'ESS

Content :
•	Structure du projet
•	Traitement des données
________________________________________
Le projet est structuré en deux étapes : 
1.Le nettoyage des données en trois niveaux :
→input : dossier contenant les tables de FLORES (ayant déjà été prétraitées : standardisation des noms des variables)
→ treatment : dossier contenant les traitements des tables. Ce fichier contient 3 fichiers différents:
- `treatment_DEP.R` : traitements des tables départementales *(TC1 à TC13)*

- `treatment_REG.R` : traitements des tables régionales *(TC13 à TC24)*

- `treatment_EPCI.R` : traitements des tables EPCI *(EPCI_T1 , EPCI_T2, EPCI_T3)*
→ Les codes R treatment créerons alors de nouvelle tables .csv dans treated_dataset.

Remarque : dans la suite de l'application seul ce dossier treated_dataset sera utilisé pour l'import de données.
2.Les dossiers finaux :
→ treated_dataset
→ app.R : partie server de l'application
→ www : partie UI de l'appliquation 
________________________________________
Traitement des données
REG :
•	Abstraction du détail des typologies
•	Reformatation des variables qualitative contenant des numeros en plus du noms des modalités. Les modalités étant suffisamment courte , on éliminera le numeros ou les détails superflux.
EPCI :
- A l'inverse du traitments des tables régionale , les variables qualitative des tables EPCI on des modalités précises et dont les `strings` sont longues. Ainsi a l'inverse on conservera uniquement les numeros des modalités. Puis l'on forme une table supplementaire permettant de faire le lien pour chaque varaibles qualitative entr un numeros et le label correspondant

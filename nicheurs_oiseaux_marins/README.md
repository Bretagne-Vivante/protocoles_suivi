# Oiseaux Marins Nicheurs de Bretagne

Sous-module de saisie GeoNature Monitoring du protocole Oiseaux Marins Nicheurs - Bretagne Vivante dans le cadre de l'ORA (Observatoire régional de l'Avifaune)

-----------------

## DOC
https://github.com/PnX-SI/gn_module_monitoring/blob/02f5fd56753f992808383f559c9f14d6ca13f24e/docs/sous_module.md?plain=1#L77

============

Pour installer l'outil de saisie, vous devez disposer d'une instance GeoNature, dotée du module monitorings. 

Il faut créer un JDD avec le module 

============
## Groupe de site = Secteur de comptage basé sur le découpage Zonages ORA
Voir xxx
    
Les entités sont intégrées dans l_area pour faciliter la prise en main du module.

## Site = Nid 
Nid Identifiant = text (chiffres + lettres)
Type de NID (spécifique terrier/nid )
Taxon ? le nid est spécifique et ne peut pas être occupé par une autre espèce ?
Média ?photo du nid fixe en début de saison ? pour aider a se répérer sur site

## Visite = Passage sur le nid 
Média ? photo du nid par passage ? utile ?

## Observation = Observation du nid 

Taxon ?
SI TAXO = cormor , 
champs additionnels macrodechet  
-> 1 champs avec un effectif par tranche (O/5 | 5/10 |etc)
-> 1 champs avec choix multiple pour la composition des macro (récupérer liste avec marine)

SI Stade de vie =  Adulte
Bague parent 1
Bague parent 2
Count = 2 par défaut avec denombr = Individu ? ou alors count = 1 mais denombr = couple ?

SI Stade de vie =  Oeuf
count = 1 par défaut
type denombr = couple


SI Stade de vie =  Juvénile
Count = 1 par défaut avec denombr = Individu ?
Champs additionnel : juv_age_nb_semaine integer

"cd_nomenclature": ["1", "2", "3", "4", "5","10"]
-> Indéterminé - Adulte - Juvénile - Immature -  Sub-adulte - Œuf

> Il est conseillé de "Enchainer les saisies" pour la rapidité
> param Chained et keep sur obs pour faire le taff sans l'action de l'utilisateur

cd_nom == 2447 -> CORMOR HUPPE 
cd_nom == 2440 -> GRAND CORMOR

=========
## Questions a poser :
adulte détail du sexe ou bague 1/2 suffisant ?
Sexe détectable pour les poussins ?

les nids non occupés sont aussi suivis ?
Ex nid 242 de l'ile x est non occupé alors que chaque année c'est un récurrent, on met un passage ou pas ?

Nomenclature Ponte ok ?
etat biologique ? trouvé vivant /mort, utile ou pas  ?

Utilité des statuts  Juvénile - Immature - Sub-adulte 
Age des juv uniforme dans un nid ?

SOA (Site apparemment occupé) TOA (terrier) NOA (Nid)
différence entre un site et un nid ? terrier c'est clair comme def

Taxon a mettre au niveau du nid ou de l'Observation ? le nid est spécifique et ne peut pas être occupé par une autre espèce ? (les pratiques de nids )

Nomenclatures a intégrer en dur ? a intégrer dans geonature 

-----------------

Installation 
=========

geonature monitorings install <mon_chemin_absolu_vers_mon_module> <mon_module_code>
geonature monitorings install /home/geonatureadmin/protocoles_suivi-master/NICHEURS_OISEAUX_MARINS nicheurs_oiseaux_marins

> Pour le moment, pas besoin d'ajouter les nomenclatures car déjà présentes en bdd ou en dur dans le code. Nettoyage de nomenclature.json a faire pour enlever les obsolètes.

Si vous utilisez un autre "module_code" que nicheurs_oiseaux_marins tout en minuscule, vous devrez adapter les scripts SQL d'exports pour récupérer les données du modules dans vos exports standards et d'analyse.

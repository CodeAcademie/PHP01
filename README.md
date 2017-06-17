# PHP01 : Création d'un formulaire PHP et export XML

> Objectif : Réaliser une formulaire PHP permettant un envoi vers une page externe. 

> Sous-objectif : Permettre de pratiquer la création de formulaire et traitement des données. Découverte de l'XML et DTD

> PreRequis : WP00, HTML00

> Tags : Developpeur Logiciel

> Temps : 8h

> Materiel  : Papier, stylo, pc, video proj


L'objectif de cet atelier est de réaliser un formulaire en PHP. 
Ce formulaire a pour but de faciliter la vie du formateur de la Code Académie. Dans le cadre de sa profession, le formateur doit réaliser des activités de formation telles que celle-ci. 

Pour se faire, il a déjà structuré ses données dans un fichier XML et réalisé une nomenclature claire par le biais d'un DTD.
Mais jusqu'à maintenant, il n'a jamais pris la peine de mettre en place un outil lui permettant de créer le contenu plus facilement; par le biais d'un formulaire.

> Pour le bon déroulement de cet exercice, il est attendu que les apprenants soient assis par nombre pair à chaque table.
> Les apprenants doivent ainsi commencer par définir des binômes

## Aide
 * Mettez des commentaires, votre code sera lu par votre binome
 * N'oubliez pas de mettre des logs ```error_log```, 
 * Ouvrez un terminal et suivez le fichier error.log ``` tail -f /var/log/nginx/error.log``` . Il y sera listé toutes vos erreurs ainsi que vos logs.
 * N'oubliez pas de vous référer à la [doc PHP](http://php.net/manual/fr/)

## Exercice N°1

### Compréhension du besoin (9h - 9h30)
Cherchez sur internet durant 30min sur ce qu'est un DTD et sa relation avec un fichier XML

 * [W3School DTD](https://www.w3schools.com/xml/xml_dtd_intro.asp)
 * [W3School XML](https://www.w3schools.com/xml/default.asp)
 * ...


### Analyse du besoin (9h30 - 10h)
Lisez le DTD ci-dessous, et à partir de documentations trouvées sur internet, visualisez individuellement comment est structuré une Activité.

```
<!ELEMENT root (Programme*) >
<!ELEMENT Programme (Module*) >
<!ATTLIST Programme formation CDATA #IMPLIED>
<!ELEMENT Module (Objectif, PreRequis, Materiel, Sequence*)>
<!ATTLIST Module language CDATA "">
<!ATTLIST Module group CDATA "">
<!ELEMENT Sequence (Objectif, Code, Activite*)>
<!ATTLIST Sequence evaluation CDATA "">
<!ELEMENT Activite (Objectif, Code, Temps?, SousObjectif?, Description?)>
<!ATTLIST Activite done (true|false) "false">
<!ELEMENT Objectif (#PCDATA)>
<!ELEMENT Description (#PCDATA)>
<!ELEMENT PreRequis (#PCDATA) >
<!ELEMENT Materiel (#PCDATA) >
<!ELEMENT SousObjectif (#PCDATA) >
<!ELEMENT Temps (#PCDATA) >
<!ELEMENT Code (#PCDATA) >
```

et  essayez de modeliser une Activite !

### Concertation sur le besoin  (10h - 10h15)
Par table, mettez en commun vos modélisations et voyez s'il y a des différences. Si tel est le cas, définissez une structure commune. 
L'objectif étant pour l'instant de se focaliser uniquement sur une activité (La partie root jusque Sequence est à ignorer ). 

### Développement (10h30 - 12h30 ++)
Au sein d'un fichier PHP **form.php**, créez un formulaire qui permettra la saisie d'une activité. 
Un bouton de validation sera présent et enverra les données à une autre page **exportToXML.php**. 

La page exportToXML.php devra afficher le contenu qui a été saisi au sein du formulaire en respectant la structure que vous avez définie lors de la concertation du besoin. Le tout devra être affiché en structure XML, présentées au sein de balises ```<pre> <Activite ...></Activite> </pre>```.

### Bonus

Faites en sorte que la structure générée respecte le [W3 Validator](https://validator.w3.org/)

### Bonus 2

Implémentez la suite de root jusque Sequence.


### Evaluation par des pairs : Refactor du code (16h - 17h30)
Par binomes de table, donnez votre modélisation à la personne située à votre droite.
Ces derniers devront Remise en question de l'implémentation réalisée. 
 * Qu'en pensez-vous? Serait-il possible de rendre ce code plus "propre" (indentation, commentaires, structure ...)
 * Est-il possible d'améliorer les choix réalisés lors de l'implémentation de votre binôme ? Si oui, comment ? 
 * Pensez-vous qu'il est possible de réaliser la même conversion en Javascript ? 
 

 

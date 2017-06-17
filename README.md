# PHP01 : Création d'un formulaire PHP et export XML

> Objectif : Réaliser une formulaire PHP permettant un envoi vers une page externe

> Sous-objectif : Permettre de pratiquer la création de formulaire, utile dans de nombreux sites.

> PreRequis : WP00, HTML00

> Tags : Developpeur Logiciel

> Temps : 8h

> Materiel  : Papier, stylo, pc, video proj

L'objectif de cet atelier est de réaliser un formulaire en PHP. 
Ce formulaire a pour but de faciliter la vie du formateur de la Code Académie. Dans le cadre de sa profession, le formateur doit réaliser des activités de formation telles que celle-ci. 

Pour se faire, il a déjà réalisé une nomenclature claire par le biais d'un DTD.
Mais jusqu'à maintenant, il n'a jamais pris la peine de mettre en place un outil lui permettant de créer le contenu par le biais d'un formulaire.

## Aide
 * Mettez des commentaires, votre code sera lu par vos voisins
 * Mettez des logs, ouvrez un terminal et suivez le fichier error.log ``` tail -f /var/log/nginx/error.log``` . Il y sera listé toutes vos erreurs ainsi que vos logs ```error_log```
 * N'oubliez pas de vous référer à la [doc PHP](http://php.net/manual/fr/)

## Exercice N°1

### Compréhension du besoin (9h - 9h30)
Chercher sur internet durant 30min sur ce qu'est un DTD et sa relation avec un fichier XML

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

### Développementc
Au sein d'un fichier PHP **form.php**, créez un formulaire qui permettra la saisie d'une activité. 
Un bouton de validation sera présent et enverra les données à une autre page **exportToXML.php**. 

La page exportToXML.php devra afficher le contenu qui a été saisi au sein du formulaire en respectant la structure que vous avez définie lors de la concertation du besoin. Le tout devra être affiché en structure XML, présentées au sein de balises ```<pre> <Activite ...></Activite> </pre>```.

### Bonus

Faites en sorte que la structure générée respecte le [W3 Validator](https://validator.w3.org/)

### Bonus 2

Implémentez la suite de root jusque Sequence.


### Refactor du code (16h - 17)
Par table, donnez votre modélisation à la personne située à votre droite.
Remise en question de l'implémentation réalisée. 
 * Qu'en pensez-vous? 
 * Est-il possible d'améliorer le processus ? Si oui, comment ?
 

 

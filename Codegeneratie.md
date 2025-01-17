# Code genereren op basis van het Gemeentelijk Gegevensmodel

Deze handleiding is onderdeel van [Het Gemeentelijk Gegevensmodel (GGM)](readme.md).

Bij het GGM is een set codegeneratietemplates die binnen Enterprise Architect gebruikt kunnen worden voor het genereren van [Data Definition Language (DDL)](https://nl.wikipedia.org/wiki/Data_definition_language). Hiermee kunnen direct tabellen in een RDMBS gegenereerd worden. Er zijn templates beschikbaar voor:

1. Oracle
2. MySQL (ongetest)

De geleverde codegeneratietemplates zijn uitbreidingen op de standaard templates van [Enterprise Architect](https://sparxsystems.com), als onderdeel van het [Code Template Framework](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/codetemplates_2.html). 

Enterprise Architect ondersteunt ook andere databases en daarnaast programmeertalen zoals Python, C# en Java. Wij nodigen ontwikkelaars van harte uit deze te gebruiken en verder geschikt te maken voor het GGM. 

## Genereren DDL

Het uitgenereren vanuit het GGM naar DDL bestaat uit twee stappen:
1. Transformeren logische model naar logische tabelrepresentatie.
2. Genereren van DDL uit logische tabelrepresentatie.

Zorg allereerst dat er in je project naast het GGM ook een plek is waar je de tabellen heen kunt schrijven. Hiervoor gebruiken wij een aparte node naast de root node. In het voorbeeld is dat de map `<<DataModel>> Tables/Ruimte/Afval`.

![Maak een plek om tabellen uit te genereren][tablesAfval]

Zorg vervolgens dat je in Enterprise Architect het default RDBMS selecteert. Hiervoor ga je naar _Preferences_

![Ga naar Preferences om het default RDBMS te selecteren][kiesPreferences]

Kies vervolgens onder _Source Code Engineering/Code Editors_ de optie _Default Database_. In ons voorbeeld Oracle. 

![Selecteer het default RDBMS dat je als doel hebt][selecteerDefaultRDBMS]

### Stappen voor genereren DDL

Voor het genereren naar DDL neem je de volgende stappen:

1. Selecteer het onderdee van het model dat je wilt uitgenereren. In het voorbeeld de map`Gemeentelijk Gegevensmodel/Ruimte/Afval/Model`. je kunt ook in een diagram de gewenste objecttypen selecteren.

![Selecteer de map in het model][selecteerInModel]

2. Voor de eerste stap in de generatie kies _Apply Transformation_

![Kies Apply Transformation][applyTransformation]

3. Selecteer aan de recchterkant van het popup _Tables_ in het vlak _Transformations_. Zorg dat aan de linkerkant van de popup alle objecttypen geselecteerd zijn die uitgegenereerd moeten worden.

![Kies Tables onder Transformation][kiesTables]

4. In het nieuwe popup _Select Target Package_ selecteer de plek die je hebt gemaakt om de tabellen heen te schrijven. In ons voorbeeld `<<DataModel>> Tables/Ruimte/Afval`. 

![Kies Target Package][selectTargetPackage]

5. Om de eerste stap in de transformatie en generatie te starten click op _Do Transform_

![Kies Do Transform][selectDoTransform]

6. Even wachten, en de eerste stap in de generatie is uitgevoerd: de tabellen in Enterprise Architect zijn aangemaakt. De eerste stap in het generatieproces is nu uitgevoerd. Er is een "logische" en RDBMS-onafhankelijke versie van de tabellen aangemaakt. 

![Even wachten... en de tabellen zijn aangemaakt][tabellenAangemaakt]

7. In de volgende stap genereer je vanuit de "logische" en RDBMS-onafhankelijke versie van de tabellen de DDL waarmee je de tabellen in je database kunt maken. Selecteer de map met de tabellen die zojuist is gegenereerd.

![Selecteer de map met de tabellen die je wilt genereren][selecteerTabellen]

8. Onder _Develop Datamodelling_ kies _Generate_

![Onder _Develop Datamodelling_ kies _Generate_][kiesGenerate]

9. Vul een bestandsnaam en map in en druk op de knop _Generate_

![druk op de knop _Generate_][kiesGenerateDDL]

10. Even wachten en de DDL staat klaar. Succes! 

[tablesAfval]: image/TablesAfval.png "Maak een plek om de tabellen uit te genereren"
[selecteerInModel]: image/SelecteerInModel.png "Selecteer de map in het model"
[applyTransformation]: image/ApplyTransformation.png "Kies Apply Transformation"
[kiesTables]: image/KiesTables.png "Kies Tables onder Transformation"
[selectTargetPackage]: image/SelectTargetPackage.png "Kies Target Package"
[selectDoTransform]: image/SelectDoTransform.png "Kies Do Transform"
[tabellenAangemaakt]: image/TabellenAangemaakt.png "Even wachten... en de tabellen zijn aangemaakt"
[kiesPreferences]: image/KiesPreferences.png "Ga naar Preferences om het default RDBMS te selecteren"
[selecteerDefaultRDBMS]: image/SelecteerDefaultRDBMS.png "Selecteer het default RDBMS dat je als doel hebt"
[selecteerTabellen]: image/SelecteerTabellen.png "Selecteer de tabellen die je wilt genereren"
[kiesGenerate]: image/KiesGenerate.png "Kies Generate"
[kiesGenerateDDL]: image/KiesGenerateDDL.png "Kies Generate"

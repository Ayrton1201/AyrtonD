<h1>AyrtonD DataScienceMinor Portfolio</h1>

In dit document ga ik mijn portfolio laten zien voor de Data Science minor.
Gemaakt door Ayrton Donderwinkel 22140468

Aangezien ik een externe student ben en in het begin eerst nog Datacamp moest doen om uberhaupt iets te kunnen liep ik achter op hetgeen mijn groepje mee bezig was.
Nadat blok 1 voorbij was, en dus het foodboost project, begonnen we met het container project waarbij we besloten om reinforcement learning modellen toe te passen.
Hier heb ik achteraf gezien teveel tijd in gestoken en ik kwam er (te laat) achter dat ik niet veel werk kon inleveren voor mijn portfolio en dus besloot ik om zelfstandig een model te maken.

In hoofdstuk "Foodboost project" en subsection "Final model" kan mijn uiteindelijke foodboost model bekeken worden waarin data verwerkt is en er uiteindelijk 3 verschillende modellen gefit en getraind zijn.

## Table of Contents
- [Datacamp](#Chapter-1)
- [Container project](#Chapter-2)
    - [Online Game Taxi](#Subsection-1)
    - [Reinforcement Learning model groot (DQN)](#Subsection-2)
    - [Reinforcement Learning model klein (DQN)](#Subsection-3)
- [Foodboost project](#Chapter-3)
    - [Foodboost versie 1 (Jaggard Coefficient _ Top 10 lekkere recepten _ geen model gefit en getraind)](#Subsection-4)
    - [Decision Tree Classifier Model](#Subsection-5)
    - [Final model](#Subsection-11)
- [Communicatie](#Chapter-4)
    - [Presentatie](#Subsection-6)
    - [Paper](#Subsection-7)
- [Literatuuronderzoek](#Chapter-5)


# <a id="Chapter-1"></a> Datacamp
Mijn progressie voor de Datacamp course kan bekeken worden in: <br>
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Datacamp%20score.png">Datacamp score</a><br>
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Datacamp%20lessen%20voltooid.png">Datacamp lessen voltooid</a>

# <a id="Chapter-2"></a> Container project
## <a id="Subsection-1"></a> Online Game Taxi
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Ayrton_Onlinegame_Taxi.ipynb">OnlineTaxiSpel</a><br>
Omdat ik eerst nog veel onderzoek moest doen naar verschillende reinforcment learning methodes heb ik eerst gebruikt gemaakt van Q-learning voor een taxi probleem die online werd opgelost, maar deze koos telkens voor de eerst volgende beste oplossing. Aangezien Q-learning meer voor de korte termijn beste oplossing is. Een DQN model moet veel getraind worden, maar kan op lange termijn wel tot de beste oplossing komen die mogelijk is.

## <a id="Subsection-2"></a> Reinforcement Learning model groot (DQN)
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Ayrton_container_RLmodel_GrootVeld.ipynb">Container_Reinforcement_Learning_Groot</a><br>
Maar dan het container stacking probleem zelf.
Eerst moest er een custom environment gemaakt worden en dit is gedaan door middel van de gym importeren en een class aan te maken.
In dit model heb ik gewerkt met een x en y grid, dus in de lengte en hoogte, vergelijkbaar met tetris. De containers hebben een eigen prioriteit welke bij voorhand aangegeven wordt en deze wordt in dit model ook net zoals tetris van bovenaf geplaats. Van bovenaf in de best gekozen kolom en telkens een stapje omlaag totdat de container geplaatst kan worden volgens de restricties. 
Wanneer de container geplaatst kan worden krijgt deze een bepaalde positieve reward en wanneer de container niet geplaatst kan worden dan krijgt het een bepaalde negatieve reward.
De environment begint met een begin state en na elke step/action wordt de state bijgewerkt tot de state die het op dat moment is.
Door middel van stablebaselines3 is een DQN model geïmplementeerd die werd gebruikt voor een ruimtelandingsspel.
Wanneer de total_timesteps op 10.000 gezet wordt dan gaat het model eerst proberen alle containers in 1 dezelfde kolom te plaatsen. Pas met een veel hogere total_timestep begint het model betere scores te geven. De maximale score is in dit geval 128 wat betekent dat alle containers uberhaupt geplaatst konden worden.
De bijbehorende grafiek laat zien dat er op zijn minst een score van 106 behaald wordt en dit betekent dat niet alle containers altijd geplaatst konden worden.
Dit model zou verder aangepast kunnen worden door te kijken dat de hoge prioriteit strafpunten krijgen wanneer deze richting het midden en onderin geplaatst worden. Dat een container niet tussen 2 containers in geplaatst kan worden (door de reachstacker). 
Uiteindelijk werkt de environment met het model op een XY as en de grootte en prioriteiten aanpassen werkt allemaal. Dus de volgende stap kan zijn om de environment aan te passen naar een XYZ axis.

## <a id="Subsection-3"></a> Reinforcement learning model klein (DQN)
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Ayrton_container_RLmodel_KleinVeld.ipynb">Container_Reinforcement_Learning_Klein</a><br>
Nu heb ik ook dit zelfde model gebruikt maar dan in een 3 bij 3 en een andere score systeem. De maximale score wordt vaak gehaald, wat betekent dat alle containers geplaatst worden. Alleen valt er te zien dat er vaak een 1 tussen een 2 in zit. Of een 1 op een 2. Dit kan ten eerste komen doordat de containers random aangeleverd worden. Hier kan dus naar gekeken worden om hier extra straffen voor uit te delen.

# <a id="Chapter-3"></a> Foodboost project
Introductie:

In dit onderzoek zal ik me richten op het voorspellen van de smaak van recepten. Hiervoor zal ik gebruik maken van twee datasets: een dataset met recepten en een dataset met tags. Deze data zal ik analyseren en verwerken om een machine learning model te ontwikkelen dat in staat is om te voorspellen of een recept wel of niet lekker gevonden zal worden door mezelf.

Om dit te realiseren zal ik eerst een literatuuronderzoek uitvoeren om te bepalen welk machine learning model het beste zal passen voor dit specifieke probleem. Er zijn veel verschillende soorten modellen beschikbaar, zoals decision trees, logistische regressie, k-nearest neighbors, en vele andere. Elk van deze modellen heeft zijn eigen unieke voordelen en beperkingen, dus het is belangrijk om de juiste keuze te maken.

Na het literatuuronderzoek zal ik de datasets analyseren en verwerken om ze geschikt te maken voor het geselecteerde machine learning model. Hierna zal ik het model trainen en testen op de verwerkte data. Hierbij zal ik ook verschillende parameters van het model aanpassen om te kijken welke instellingen het beste resultaat opleveren.

Daarna zal ik de resultaten van het model evalueren en analyseren, en besluiten of het model aan de verwachtingen voldoet. Indien nodig zal ik verdere aanpassingen aan het model of de data doen om de voorspellingscapaciteit te verbeteren.

## <a id="Subsection-4"></a> Foodboost versie 1 (Jaggard Coefficient _ Top 10 lekkere recepten _ geen model gefit en getraind)
Voor het foodboost project ben ik begonnen met <a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Ayrton_Foodboost_v1.ipynb">Foodboost versie 1</a>.<br>
Hierin heb ik vooral met data gewerkt om uiteindelijk een lijst te krijgen met top 10 recepten die ik lekker zou vinden, maar hierop is geen machine learning model getraind.
In eerste instantie heb ik de recepten lijst ingeladen en hierbij de overbodige kolommen weggehaald.
Hierna heb ik een lijst van 200 recepten random verkregen en gezegd of ik een recept wel of niet lekker vond.
Met de lijst van recepten die wel of niet lekker waren heb ik een query gebruikt om alleen alle lekkere recepten nog te laten zien.
Nu heb ik dus een lijst van recepten die lekker zijn.

Daarna heb ik de tags dataset ingeladen en hierbij zag ik dat er sommige waarden dubbel waren. Die hetzelfde recept en tag hadden.
Dus moest hierbij eerst alle duplicates eruit gefilterd worden.

Nu wil ik een lijst hebben met recepten die lekker zijn met de daarbij behorende tags.
Hierbij zijn de waarden die bij elkaar horen van recept en tag samengevoegd in een nieuwe lijst.

Met de lijst van lekkere recepten en de bijbehorende tags kan ik de jaggard-coëfficient toepassen die ervoor zorgt dat alle tags van alle lekkere recepten bij elkaar opgeteld worden.
Nu elke tag een bepaald aantal keer voor komt heb ik een dictionary aangemaakt met recept scores.
Elk recept gaat de tags langs die voorkomen in dat recept en telt dit bij elkaar op.
Hiermee heeft elk recept een score gekregen en de top 10 hoogste scores worden uiteindelijk laten zien.

## <a id="Subsection-5"></a> Decision Tree Classifier Model
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Ayrton_ReceptenTags_DecisionTree.ipynb">Decision Tree Classifier Model</a><br>
In deze versie ben ik weer vanaf 0 begonnen en geprobeerd om een model te kunnen fitten en trainen.
Eerst heb ik de tags.csv dataset ingeladen en hiermee alle kolommen weggehaald op de tag kolom na en gefilterd op alle unieke tags die voorkomen.
Hierna heb ik dezelfde 200 receptenlijst gebruikt als voor foodboost versie 1. Dus dezelfde recepten zijn gerate op wel of niet lekker.
Daarna heb ik de tags.csv dataset opnieuw ingeladen, zodat alle kolommen er weer zijn.
En met de functie itterrows ga ik kijken of een bepaalde tag ook voorkomt bij een recept dat ik lekker vind en zo ja dan vult het een 1 neer in een nieuwe tabel die is aangemaakt.
De tabel bevat een kolom met recepten, kolom met wel of niet lekker, en de rest van de kolommen zijn alle unieke tags die beschikbaar zijn.
Met deze nieuwe tabel met allemaal 1tjes en 0en kan ik een model gaan fitten en trainen.
Ik heb in eerste instantie gekozen voor een decision tree classifier. Met 70% als trainingset en 30% als testset.
Deze laat uiteindelijk een confusion matrix zien met de accuracy, precision, en recall score die eruit komen.
Er valt te zien dat de scores behoorlijk laag zijn, dit zou kunnen komen dat het model overfit is.
Ook is er een tree visualisatie te zien, en deze ziet er naar mijn mening niet zo goed uit.
Er zijn teveel features, ofwel teveel tags in de kolommen. Terwijl veel tags misschien niet eens gebruikt worden of heel weinig in de recepten die ik lekker vind.
Ook kan het zijn dat de 200 recepten die op wel of niet lekker gerate zijn te weinig is en dus de training data te weinig.

## <a id="Subsection-11"></a> Final model
Een decision tree classifier is een goed model voor deze situatie omdat het in staat is om complexe beslissingsregels te modelleren aan de hand van de beschikbare features (in dit geval de tags). Het maakt gebruik van een boomstructuur waarbij op basis van de waarde van de verschillende features, beslissingen worden genomen over welke klasse (in dit geval wel lekker "1" of niet lekker "0 ") een recept hoort. Het is ook visueel eenvoudig te interpreteren en kan gemakkelijk worden geëvalueerd op basis van de prestaties.

Een random forest classifier is ook een goed model voor deze situatie omdat het een verfijning is van de decision tree classifier. Het maakt gebruik van meerdere decision trees en combineert hun voorspellingen om een meer nauwkeurige voorspelling te krijgen. Dit kan helpen om overfitting te voorkomen, wat kan optreden bij het gebruik van een enkele decision tree.

Een SVM (Support Vector Machine) is een ander type classifier dat ook geschikt kan zijn voor deze situatie. Het maakt gebruik van een complexe analyse van de data om een hyperplane te vinden die de verschillende klassen het beste scheidt. Dit kan in sommige gevallen een hogere nauwkeurigheid opleveren dan een decision tree of random forest classifier. Echter, de interpretabiliteit van de SVM is vaak minder duidelijk dan die van de andere modellen.

In deze final model <a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Ayrton_ReceptenTags_FinalModel.ipynb">Final Model</a> heb ik eerst dezelfde code als in <a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Ayrton_ReceptenTags_DecisionTree.ipynb">Decision Tree Classifier Model</a> gebruikt en hier een Random Forest Classifier en een SVM aan toegevoegd.

Na het runnen gaf de Decision Tree Classifier:
- Accuracy = 0.57
- Precision = 0.75
- Recall = 0.28

Random Forest Classifier gaf:
- Accuracy = 0.54
- Precision = 0.63
- Recall = 0.31

En de SVM Classifier gaf:
- Accuracy = 0.64
- Precision = 0.66
- Recall = 0.66

Aangezien dit een binair classificatieprobleem is, en het belangrijker is in dit geval om een recept dat lekker is niet te verwarren met een recept dat niet lekker is, kies ik ervoor om precision score te verbeteren.
Precision is de verhouding van ware positieve voorspellingen die door het model zijn gemaakt uit alle positieve voorspellingen.
Het is een goede metriek om te gebruiken wanneer alle vals positieven duurder zijn dan vals negatieven.

Het lijkt er op dat in dit geval de Decision Tree Classifier het beste werkt met een precision score van 0.75.
Maar door het model lijkt mij overfit te zijn en dus ga ik minder features gebruiken. De features (tags) die weinig tot niet gebruikt worden, worden weggehaald.
En ook zal ik meer data aan de trainingset meegeven en dus nog eens 200 recepten raten op wel of niet lekker.

Nadat ik eerst 200 recepten heb gerate en toegevoegd en de waarde voor test_size en random_state wat heb aangepast kreeg ik slechtere scores.
Ook nadat ik de kolommen heb verwijderd waarbij een tag minder dan 10 keer voor komt, krijg ik dezelfde of slechtere scores. Alleen de recall score gaat een stuk omhoog.

Bij een aanpassing aan de code was om alleen de kolommen met de tags (aziatisch, hollands, hoofdgerecht) te gebruiken.
Hierbij ging de precision van elk model omhoog. Alleen werden de scores van elk model ook hetzelfde.
Precision score:
Decision Tree Classifier 0.73
Random Forest Classifier 0.73
SVM Classifier 0.73

Uiteindelijk teruggegaan naar naar alle kolommen met tags worden laten zien en hierbij de kolommen verwijderd waarvan de tags minder dan 30 keer voorkomen.
Het lijkt er op dat de Decision Tree Classifier het beste presteert in alle gevallen die zijn geprobeerd.
In de laatste poging is de precision voor de Decision Tree iets lager dan de 0.75 die er als allereerste uit kwam, maar de accuracy en recall zijn nu ook hoger geworden.
Precision score:
Decision Tree Classifier 0.73
Random Forest Classifier 0.66
SVM Classifier 0.61

Visualisatie:
Hierin heb ik ook de Decision Tree Classifier gevisualiseerd met een Tree structuur die er naar mijn mening vrij aardig eruit ziet.
Eeen confusion matrix visualisatie, waarbij opvalt dat de True Negatives een stuk hoger ligt dan de rest wat lijkt op dat de niet lekkere recepten vrij goed voorspelt worden.
Ook valt er een ROC_curve en een precision_recall_curve te zien.

Evaluatie:
Ik heb de data verwerkt in verschillende stappen en een lijst met tags toegevoegd als kolommen aan een dataframe met recepten die wel of niet lekker zijn.
Er zijn 3 modellen gefit en getraind en met elkaar vergeleken en gekozen om precision score te verbeteren, omdat dit gaat over verhouding van ware positieve voorspellingen die door het model zijn gemaakt uit alle positieve voorspellingen.
Door middel van meer input data toe te voegen, model waardes aan te passen, en minder features te gebruiken, is er geprobeerd om de scores van het model te verbeteren.
Uiteindelijk is er voor de Decision Tree Classifier ook een visualisatie gemaakt.


# <a id="Chapter-4"></a> Communicatie
## <a id="Subsection-6"></a> Presentatie
Tijdens het 2de blok heb ik samen met Eric de externe eindpresentatie gegeven over onze voortgang voor het containerprobleem.
De powerpoint kan (klikken op "view raw" of het bestand downloaden) bekeken worden in <a href="https://github.com/Ayrton1201/AyrtonD/blob/main/container%20-%20eindpresentatie%20week%2010.pptx">Eindpresentatie week 10</a><br>
Dit was een externe presentatie die online gegeven werd. De powerpoint hebben Eric en ik samen aan gewerkt op school. Ikzelf meer de tekst en layout en Eric meer de visualisaties.
Tijdens de presentatie besprak ik de eerste helft van de powerpoint. Opening, inleiding, onderzoeksopzet, eerste en tweede prototype, en de restricties.
De presentatie verliep goed en was naar mijn mening duidelijk.

<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/container%20-%20week%2018.pptx">Interne presentatie week 19</a><br>
In het laatste blok, in week 19, heb ik een interne presentatie gegeven samen met Eric. Dit was een vrij korte presentatie, omdat iedereen vooral bezig is met de portfolio en de paper. Hierbij heb ik de recap verteld en ons huidig werk.

## <a id="Subsection-7"></a> Paper
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Conclusie.docx">Paper</a><br>
Voor de paper heb ik een groot deel van de conclusie geschreven. Het is vooral een samenvatting, omdat de resultaten nog niet bekend waren op het moment van schrijven. Uiteindelijk zou iemand anders de echte conclusie/discussie hier nog aan toevoegen en was het aan iedereen de taak om alles goed door te lezen en te verbeteren waar nodig. Ik heb een aantal aanpassingen gemaakt aan de onderdelen "abstract" en "toekomstig werk" nadat er hier feedback over werd gegeven.

# <a id="Chapter-5"></a> Literatuuronderzoek
De literatuuronderzoek wat ik heb gedaan kan gevonden worden in deze pdf:
<a href="https://github.com/Ayrton1201/AyrtonD/blob/main/Literatuuronderzoek_Ayrton.pdf">Literatuuronderzoek</a>


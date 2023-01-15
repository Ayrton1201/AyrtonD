<h1>AyrtonD DataScienceMinor Portfolio</h1>

In dit document ga ik mijn portfolio laten zien voor de Data Science minor.
Gemaakt door Ayrton Donderwinkel 22140468

Aangezien ik een externe student ben en in het begin eerst nog Datacamp moest doen om uberhaupt iets te kunnen liep ik achter op hetgeen mijn groepje mee bezig was.
Nadat blok 1 voorbij was en dus het foodboost project begonnen we met het container project waarbij we besloten om reinforcement learning modellen toe te passen.
Hier heb ik achteraf gezien teveel tijd in gestoken en ik kwam er (te laat) achter dat ik niet veel werk kon inleveren voor mijn portfolio en dus besloot ik om zelfstandig een model te maken.

## Table of Contents
- [Datacamp](#Chapter-1)
- [Container project](#Chapter-2)
    - [Online Game Taxi](#Subsection-1)
    - [Reinforcement Learning model groot (DQN)](#Subsection-2)
    - [Reinforcement Learning model klein (DQN)](#Subsection-3)
- [Foodboost project](#Chapter-3)
    - [Foodboost versie 1 (Jaggard Coefficient _ Top 10 lekkere recepten _ geen model gefit en getraind)](#Subsection-4)
    - [Subsection 2](#Subsection-5)
- [Communicatie](#Chapter-4)
    - [Presentatie](#Subsection-6)
    - [Paper](#Subsection-7)
- [Literatuuronderzoek](#Chapter-5)
    - [Machine Learning types](#Subsection-8)
    - [Verschillende modellen](#Subsection-9)
    - [Bibliography](#Subsection-10)


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

## <a id="Subsection-5"></a> Subsection 2

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

# <a id="Chapter-5"></a> Literatuuronderzoek
## <a id="Subsection-8"></a> Machine Learning types
## <a id="Subsection-9"></a> Verschillende modellen
## <a id="Subsection-10"></a> Bibliography



<h3>Foodboost project</h3>

******

<h3>Communicatie</h3>



Paper: **********




<h3>Literatuuronderzoek</h3>

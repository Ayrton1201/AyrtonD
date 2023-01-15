<h1>AyrtonD DataScienceMinor Portfolio</h1>

In dit document ga ik mijn portfolio laten zien voor de Data Science minor.
Gemaakt door Ayrton Donderwinkel 22140468

<h2>Verplicht gedeelte</h2>

<h3>DataCamp</h3>

Mijn progressie voor de Datacamp course kan bekeken worden in:
<a href="[https://github.com/username/repo/blob/branch/README.md](https://github.com/Ayrton1201/AyrtonD/blob/main/Datacamp%20score.png)">Datacamp score</a>
https://github.com/Ayrton1201/AyrtonD/blob/main/Datacamp%20score.png

"datacamp score.png"  
"datacamp lessen voltooid.png"

<h3>Container project</h3>

Deze code heb ik volledig zelfstandig en kan ingezien worden in "Ayrton_container_RLmodel.pdf"

Container stacking problem:

Eerst moest er een custom environment gemaakt worden en dit is gedaan door middel van de gym importeren en een class aan te maken.
In dit model heb ik gewerkt met een x en y grid, dus in de lengte en hoogte, vergelijkbaar met tetris. De containers hebben een eigen prioriteit welke bij voorhand aangegeven wordt en deze wordt in dit model ook net zoals tetris van bovenaf geplaats. Van bovenaf in de best gekozen kolom en telkens een stapje omlaag totdat de container geplaatst kan worden volgens de restricties. 
Wanneer de container geplaatst kan worden krijgt deze een bepaalde positieve reward en wanneer de container niet geplaatst kan worden dan krijgt het een bepaalde negatieve reward.
De environment begint met een begin state en na elke step/action wordt de state bijgewerkt tot de state die het op dat moment is.
Door middel van stablebaselines3 is een DQN model geïmplementeerd die werd gebruikt voor een ruimtelandingsspel.
Wanneer de total_timesteps op 10.000 gezet wordt dan gaat het model eerst proberen alle containers in 1 dezelfde kolom te plaatsen. Pas met een veel hogere total_timestep begint het model langzaam betere scores te geven. De maximale score wordt niet gehaald, maar dit zal komen doordat de container prioriteit random aangeleverd worden en er misschien ook geen betere oplossing is.

Eerst gebruikte ik Q-learning voor een taxi probleem die online werd opgelost, maar deze koos telkens voor de eerst volgende beste oplossing. Aangezien Q-learning meer voor de korte termijn beste oplossing is. Een DQN model moet veel getraind worden, maar kan op lange termijn wel tot de beste oplossing komen die mogelijk is.
Dit model zou verder aangepast kunnen worden door te kijken dat de hoge prioriteit strafpunten krijgen wanneer deze richten het midden en onderin geplaats worden. Dat een container niet tussen 2 containers in geplaatst kan worden (door de reachstacker). 
Uiteindelijk werkt de environment met het model op een XY as en de grootte en prioriteiten aanpassen werkt allemaal. Dus de volgende stap kan zijn om de environment aan te passen naar een XYZ axis.


<h3>Foodboost project</h3>

******

<h3>Communicatie</h3>

Tijdens het 2de blok heb ik samen met Eric de externe eindpresentatie gegeven over onze voortgang voor het containerprobleem.
De powerpoint kan bekeken worden in "container - eindpresentatie week 10".
Dit was een externe presentatie die online gegeven werd. De powerpoint hebben Eric en ik samen aan gewerkt. Ikzelf meer de tekst en layout en Eric meer de visualisaties.
Tijdens de presentatie besprak ik de eerste helft van de powerpoint. Opening, inleiding, onderzoeksopzet, eerste en tweede prototype, en de restricties.
De presentatie verliep goed en was naar mijn mening duidelijk.

Paper: **********


<h3>Reflectie</h3>

Aangezien ik van een andere studie af kom, en deze minor doe als externe minor, begon ik met veel minder tot geen kennis. Hierdoor had ik een achterstand op mijn groepsgenoten wat in theorie geen probleem hoefde te zijn, maar dit toch wel werd in de praktijk. In het eerste blok probeerde ik mee te helpen met het filteren van de foodboost dataset, maar was toch meer gefocust op de Datacamp course om een basis te krijgen van Data Science.

Sindsdien hebben we als groep steeds afspraken gemaakt wie wat ging doen, maar telkens had 1 groepslid diezelfde dag nog alle taken zelf gedaan. Hierdoor had ik weinig te doen en kon ik ook weinig ervan leren. Zeker op het moment dat dit groepslid, buiten de lessen van school en Datacamp om, bepaalde codes ging implementeren.

Uiteindelijk had ik Datacamp afgerond, probeerde te begrijpen waar de anderen mee bezig waren, maar ik leerde niets meer. Ook omdat ik zelf nogal een stil persoon ben en niet gauw zeg tegen de groep dat mij iets dwarszit. Maar zelfs toen ik wel aangaf dat er mij iets dwarszat en dat ik weinig deed en ik vroeg meermaals wat ik kon doen, omdat mijn portfolio anders leeg zou blijven, hielp mijn groep niet om het probleem op te lossen. Een aantal weken later hadden we besloten dat ieder groepslid zijn eigen Reinforcement Learning model zou maken, maar aangezien ik hier totaal geen kennis van had en dus heel veel onderzoek moest doen, duurde het een tijd voordat ik met iets kwam. Veel voorbeelden op internet werkte niet in jupyter, omdat de versie niet goed was of bepaalde libraries niet geïmporteerd konden worden.

Tot op het punt dat mijn groepje zelfs naar meneer Andrioli ging om over mij te klagen. Hierna heb ik een persoonlijk gesprek gevoerd met meneer Andrioli en heb ik besloten om zelfstandig aan de projecten te werken, zodat ik toch een werkend model kon krijgen.

Sindsdien heb ik eerst geprobeerd om het foodboost project zelfstandig op te lossen, maar dit was toch moeilijker dan gedacht. Dus besloot ik om de container opdracht te proberen. Hierbij moest ik eerst veel onderzoek doen naar verschillende manieren om een eigen custom environment te maken die voor mij te maken viel. Dit werd uiteindelijk een vergelijkbaar iets als in tetris, behalve dat de containers in mijn environment recht naar beneden gaan.

Nadat mijn environment gemaakt was moest ik onderzoek doen naar verschillende manieren om mijn model te trainen. Dit kon op verschillende manieren, maar uiteindelijk leek een DQN methode mij het beste toepasbaar om het op een lange termijn beter te kunnen voorspellen. Waarin een Q-learning model meer gericht was op de korte termijn voorspelling.

Op het moment dat dit model een goede voorspelling gaf heb ik besloten om dit te laten voor wat het is en toch nog het foodboost project op te pakken. Aangezien hier meer gewerkt wordt met data. Ook hetgeen aan bod kwam in de eerste 5 lessen en de Datacamp course kon hierin toegepast worden. Eerst was ik met name bezig met het veranderen van de data, maar zonder echt een idee wat voor opdracht ik zelf wilde beantwoorden. Dus op een gegeven moment heb ik zelf een soort opdracht bedacht en pas hierna het werken met data toegepast.

Met name in dit project heb ik veel onderzoek moeten doen naar hoe pandas werkt en hoe het beste de date veranderd kan worden naar mijn behoefte. Uiteindelijk heb ik hieruit de benodigde tabellen kunnen creëren die gebruikt konden worden om een model te fitten en trainen.
Nu richting het einde van de minor kan ik zeggen dat ik niet tevreden ben met mijn eigen in breng in het groepsdeel, maar door het uiteindelijk helemaal zelf te doen denk ik dat ik toch tevreden mag zijn met wat ik geleerd heb in de minor.
Data verwerken naar de behoeftes, lineair regressie/classificatie model fitten en trainen, eigen environment maken, en een Reinforcement Learning model toepassen en trainen.

Ook ben ik tot de conclusie gekomen dat Data Science zeker interessant voor mij is, maar dat er nog veel geleerd en geoefend moet worden in de praktijk.


<h3>Literatuuronderzoek</h3>

<h1>AyrtonD DataScienceMinor Portfolio</h1>

In dit document ga ik mijn portfolio laten zien voor de Data Science minor.

<h2>DataScienceMinor</h2>

<h3>DataCamp</h3>

Mijn progressie voor de Datacamp course kan bekeken worden in "datacamp score.png" en "datacamp lessen voltooid.png".

<h3>Container project</h3>

Deze code heb ik volledig zelfstandig en kan ingezien worden in .....

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



<h3>Communicatie</h3>
Tijdens het 2de blok heb ik samen met Eric de eindpresentatie gegeven over onze voortgang voor het containerprobleem.

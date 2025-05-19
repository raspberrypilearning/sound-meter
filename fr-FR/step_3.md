## Sonner l'alarme 

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Dans cette étape, tu ajouteras une alarme qui se déclenchera lorsque le niveau sonore sera trop élevé. Pour éviter que l'alarme n'augmente le bruit, tu veilleras à ce qu'elle ne se déclenche qu'une seule fois et puisse être réinitialisée quand tu le souhaites. 
</div>
<div>

![Le code pour déclencher l'alarme. À l'intérieur d'un bloc "chaque 500 ms", le niveau sonore est tracé sur les LED. Ensuite, une instruction si est utilisée pour vérifier si le niveau sonore dépasse le maximum et si la variable d'alarme est définie à faux. À l'intérieur du bloc "si", un son est joué et la variable d'alarme est définie sur "vrai".](images/alarm-code-demo.png){:width="300px"}

</div>
</div>

### Définir le maximum

Tu devras créer une variable pour maintenir le niveau sonore qui déclenchera l'alarme.

--- task ---

Ouvre le menu `Variables`{:class="microbitvariables"} et clique sur **Créer une variable**.

<img src="images/variable-menu.png" alt="Le menu Variables avec le bouton &quot;Créer une variable&quot; en surbrillance." width="350"/>

--- /task ---

--- task ---

Nomme ta nouvelle variable `maximum`.

<img src="images/max-variable-name.png" alt="La fenêtre &quot;Nom de la nouvelle variable&quot; avec le nom &quot;maximum&quot; écrit dans la case." width="400"/>

--- /task ---

--- task ---

Dans le menu `Variables`{:class="microbitvariables"}, prends le bloc `définir maximum`{:class="microbitvariables"}.

<img src="images/set-max-start.png" alt="Le menu Variables avec le bloc &quot;définir maximum à 0&quot; en surbrillance." width="350"/>

Place le bloc à l'intérieur du bloc `au démarrage`{:class="microbitbasic"} et modifie `0` par `150`.

```microbit
let maximum = 150
```

--- /task ---

La valeur `150` est un peu plus de la moitié du niveau sonore maximum que le micro:bit peut détecter, ce qui devrait donc être un bon niveau pour commencer.

--- collapse ---

---
title: Pour micro:bit V1
---

Cette valeur maximale fonctionne aussi pour les niveaux d'intensité lumineuse !

--- /collapse ---

### Éteindre l'alarme

Tu dois également t'assurer que le bruit de l’alarme n’ajoute pas de bruit à l’environnement déjà bruyant !

Pour cela, tu utiliseras une autre variable qui sera définie sur `faux` pour commencer, et qui passera à `vrai` quand l'alarme sonne.

--- task ---

Crée une nouvelle `Variable`{:class="microbitvariables"}, cette fois appelée `alarme`.

<img src="images/alarm-variable-name.png" alt="La fenêtre &quot;Nom de la nouvelle variable&quot; avec le nom &quot;alarme&quot; écrit dans la case." width="350"/>

--- /task ---

--- task ---

Fais glisser le bloc `définir alarme`{:class="microbitvariables"} du menu `Variables`{:class="microbitvariables"}.

Place-le à l'intérieur du bloc `au démarrage`{:class="microbitbasic"}.

--- /task ---

Tu dois définir cette nouvelle variable sur `faux` au lieu d'un nombre.

--- task ---

Ouvre le menu `Logique`{:class="microbitlogic"}.

Prends un bloc `faux`{:class="microbitlogic"}.

<img src="images/false-block-location.png" alt="La partie inférieure du menu Logique, montrant l'emplacement du bloc faux dans la section &quot;Booléen&quot;." width="200"/>

Place ce bloc au-dessus du `0`.

```microbit
let maximum = 150
let alarme = false
```

--- /task ---

### Vérifier si l'alarme doit s'allumer

L'alarme ne doit sonner que **si :**

+ Le niveau sonore est **plus grand** que le maximum   
  **ET**
+ La variable alarme n'est **pas vraie**

--- task ---

Dans le menu `Logique`{:class="microbitlogic"}, prends un bloc `si...alors`{:class="microbitlogic"}.

<img src="images/if-block-location.png" alt="Le menu Logique avec un bloc &quot;si&quot; en surbrillance." width="350"/>

Place le bloc à l'intérieur de la boucle `chaque`{:class="microbitloops"} sous le bloc `log data`{:class="microbitdatalogger"}.

```microbit
loops.everyInterval(500, function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
    if (true) {

    }
})
```

--- /task ---

--- task ---

Ouvre à nouveau le menu `Logique`{:class="microbitlogic"} et prends un bloc `et`{:class="microbitlogic"}.

<img src="images/and-block-location.png" alt="La partie inférieure du menu Logique, montrant l'emplacement du bloc &quot;et&quot; dans la section &quot;Booléen&quot;." width="200"/>

Place-le dans la section `vrai` du bloc `si...alors`{:class="microbitlogic"}.

```microbit
loops.everyInterval(500, function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
    if (false && false) {

    }
})
```

--- /task ---

Tu dois maintenant ajouter les **deux** conditions de chaque côté du **et**.

--- task ---

Encore une fois dans le menu `Logique`{:class="microbitlogic"}, prends un bloc condition `0 < 0`{:class="microbitlogic"}.

Place-le d'un côté du bloc `et`{:class="microbitlogic"}.

Utilise le menu déroulant pour changer le symbole moins que (`<`) par plus que (`>`).

![Une démo qui consiste à cliquer sur le menu déroulant et à changer le symbole "moins que" en "plus grand que" dans la condition.](images/changing-condition.gif)

--- /task ---

--- task ---

Dans le menu `Entrée`{:class="microbitinput"}, fais glisser un bloc `niveau sonore`{:class="microbitinput"}.

Place-le dans le premier bloc `0` de `0 > 0`{:class="microbitlogic"}

Dans le menu `Variables`{:class="microbitvariables"}, fais glisser un bloc `maximum`{:class="microbitvariables"}.

Place-le dans le deuxième bloc `0` de `0 > 0`{:class="microbitlogic"}.

Ton code devrait ressembler à ceci :

```microbit
loops.everyInterval(500, function () {
    let maximum = 0
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
    if (input.soundLevel() > maximum && false) {

    }
})
```

--- collapse ---

---
title: Pour micro:bit V1
---

Dans le menu `Entrée`{:class="microbitinput"}, fais glisser un bloc `niveau d'intensité lumineuse`{:class="microbitinput"}.

Place-le dans le premier bloc `0` de `0 > 0`{:class="microbitlogic"}.

Dans le menu `Variables`{:class="microbitvariables"}, fais glisser un bloc `maximum`{:class="microbitvariables"}.

Place-le dans le deuxième bloc `0` de `0 > 0`{:class="microbitlogic"}.

Ton code devrait ressembler à ceci :

```microbit
loops.everyInterval(500, function () {
    let maximum = 0
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    if (input.lightLevel() > maximum && false) {

    }
})
```

--- /collapse ---

--- /task ---

Tu ne souhaites éteindre l'alarme que si la variable `alarme`{:class="microbitvariables"} n'est **pas** définie sur `vrai`{:class="microbitlogic"}.

--- task ---

Prends un bloc `non`{:class='microbitlogic'} du menu `Logique`{:class='microbitlogic'}.

Place-le de l'autre côté du bloc `et`{:class='microbitlogic'}.

```microbit
loops.everyInterval(500, function () {
    let maximum = 0
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
    if (input.soundLevel() > maximum && !(false)) {

    }
})
```

--- /task ---

--- task ---

Place un bloc variable `alarme`{:class='microbitvariables'} dans le bloc `non`{:class='microbitlogic'} comme ceci :

```microbit
loops.everyInterval(500, function () {
    let alarme = 0
    let maximum = 0
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
    if (input.soundLevel() > maximum && !(alarme)) {

    }
})
```

--- /task ---

### Sonner l'alarme 

Il est maintenant temps d'ajouter ton son d'alarme !

--- task ---

Dans le menu `Musique`{:class='microbitmusic'}, prends un bloc `jouer`{:class='microbitmusic'}.

<img src="images/play-block-location-v2.png" alt="La section 'micro:bit v2' du menu Musique, avec le bloc &quot;jouer&quot; en surbrillance en haut de la section." width="250"/>

Place ceci à l'intérieur du bloc `si`{:class='microbitlogic'} qui vérifie si l'alarme doit sonner.

```microbit
loops.everyInterval(500, function () {
    let alarme = 0
    let maximum = 0
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
    if (input.soundLevel() > maximum && !(alarme)) {
        music.play(music.builtinPlayableSoundEffect(soundExpression.giggle), music.PlaybackMode.UntilDone)
    }
})
```

--- collapse ---

---
title: Pour micro:bit V1
---

Le micro:bit V1 n'a pas de haut-parleur, il faut donc adapter le programme pour l'alarme.

Au lieu d'une alarme sonore, tu peux afficher une icône sur les LED lorsque le niveau d'intensité lumineuse dépasse le maximum.

Dans le menu `Base`{:class='microbitbasic'}, prends un bloc `montrer l'icône`{:class='microbitbasic'}.

Place ceci à l'intérieur du bloc `si`{:class='microbitlogic'} qui vérifie si l'alarme doit sonner.

**Sélectionne** une icône à utiliser pour ton alarme.

```microbit
loops.everyInterval(500, function () {
    let alarme = 0
    let maximum = 0
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.lightLevel()))
    if (input.lightLevel() > maximum && !(alarme)) {
        basic.showIcon(IconNames.Sad)
    }
})
```

--- /collapse ---

--- /task ---

--- task ---

**Choisis** le son d'alarme que tu souhaites utiliser, parmi les sons disponibles dans le menu déroulant.

--- /task ---

--- task ---

Dans ton bloc `au démarrage`{:class='microbitbasic'}, **fais un clic droit** sur le bloc `définir`{:class='microbitvariables'} et sélectionne **Reproduire**.

![Une démo de clic-droit sur le bloc "Définir alarme à faux", puis de le dupliquer.](images/duplicate-block.gif)

Place le bloc dupliqué sous le bloc `jouer`{:class='microbitmusic'}.

Remplace `faux`{:class='microbitlogic'} par `vrai`{:class='microbitlogic'}.

```microbit
let alarme = false
loops.everyInterval(500, function () {
    let maximum = 0
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
    if (input.soundLevel() > maximum && !(alarme)) {
        music.play(music.builtinPlayableSoundEffect(soundExpression.mysterious), music.PlaybackMode.UntilDone)
        alarme = true
    }
})
```

--- /task ---

### Réinitialiser l'alarme

Lorsque l'alarme se déclenche, tu dois la réinitialiser.

Tu peux utiliser le logo tactile sur le micro:bit pour faire cela.

<img src="images/logo-location.png" alt="Le logo micro:bit." width="200"/>

--- task ---

Dans le menu `Entrée`{:class='microbitinput'}, fais glisser un bloc `sur le logo`{:class='microbitinput'}.

<img src="images/onlogo-block-location.png" alt="Le logo sur le dessus du micro:bit au-dessus des LED." width="200"/>

Depuis ton bloc `au démarrage`{:class='microbitbasic'}, duplique le bloc `définir alarme`{:class='microbitvariables'} et place-le à l'intérieur du bloc `sur le logo`{:class='microbitinput'}.

```microbit
let alarme = false
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    alarme = false
})
```

--- collapse ---

---
title: Pour micro:bit V1
---

Il n'y a pas de capteur tactile dans le logo du micro:bit V1, tu peux donc utiliser à la fois les boutons `A` et `B`.

Dans le menu `Entrée`{:class='microbitinput'}, fais glisser un bloc `lorsque le bouton`{:class='microbitinput'}.

<img src="images/on-button-location.png" alt="Le menu Entrée avec le bloc &quot;lorsque le bouton A&quot; en surbrillance." width="350"/>

Utilise le menu déroulant pour changer le bouton en `A+B`{:class='microbitinput'}.

Depuis ton bloc `au démarrage`{:class='microbitbasic'}, duplique le bloc `définir alarme`{:class='microbitvariables'} et place-le à l'intérieur du bloc `lorsque le bouton`{:class='microbitinput'}.

```microbit
let alarme = false
input.onButtonPressed(Button.AB, function () {
    alarme = false
})
```

--- /collapse ---

--- /task ---

Ensuite, tu vas utiliser les boutons `A` et `B` pour modifier la sensibilité de ton alarme !

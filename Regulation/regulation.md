# Notes de régulation

## Définitions

### Procédé
    > Un procédé transforme un ensemble de matières premières en un ensemble de produits transformés. Pour ce faire, il manipule les matières premières, les modifie et contrôle l’ensemble des caractéristiques des produits transformés.

### Charge
    > Le débit de vidange du réservoir s’appelle la charge. Il faudra compenser la charge du procédé si l’on désire garder le niveau d’eau constant dans le réservoir. La charge est la variable imposée au procédé. C’est elle qui produit la variation systémique de la grandeur à contrôler.

### Grandeur Physique
    > C'est une quantité d'un élément physique comme le débit, la pression, l'humidité...

### Mesure
    > Utilisé pour savoir la variable manipulée pour ensuite la comparé au SP, un instrument de mesure de niveau est installé sur le réservoir.

### Régulateur
    > Le régulateur est cette partie intelligente qui calculera l’écart entre la valeur du niveau dans le réservoir et ajustera l'élément final.

### Élément final
    > L’élément final manipule d’une façon univoque la variable d’entrée du procédé (ici le débit d’eau).

### Valeur de consigne
    > La valeur de consigne SP peut être ajustée directement sur le régulateur ou lui être fournie à distance.
 
### Variable mesurée
    > Le signal fourni au régulateur par le bloc de mesure s’appelle variable mesurée (PV).

### Variable à contrôler
    > La grandeur physique à contrôler que l’on retrouve à la sortie du bloc procédé se nomme la variable à contrôler.


## 1. Introduction

### Procédés continus
    > Un procédé continu fait varier graduellement les valeurs physique afin d'en garder certaines constantes ou en asservir d'autres. Son produit est continu.

### Procédés séquentiels
    > Un procédé séquentiel transite brusquement d'une étape à une autre, son produit est discontinu.

### Régulation
    > La régulation sert à stabiliser une grandeur physique autour d'une valeur de consigne fixe.

### Asservissement
    > L'asservissement sert à faire varier une grandeur physique en fonction de une ou plusieurs variables. Le produit de consigne (SP) n'est pas fixe, il dépend d'une autre variable.

## 2. Diagramme fonctionnel
![alt text](diagramme_fonctionnel.png "Boucle de régulation")

### Composants de base d'une boucle de régulation

1. Procédé à contrôler
2. Instrument de mesure
3. Régulateur
4. Élément final

### Éléments du bloc régulateur
    1. Calculateur d'écart entre SP et PV (Rond signe somme)
    2. Algorithme de contrôle (Triangle)

### Boucle ouverte
    > Une boucle de régulation, sans le bloc régulateur, élément final ajusté manuellement, procédé et mesure.

### Chaîne directe
    > La boucle ne contient pas de bloc mesure et le régulateur est alors en mode manuel. Elle contient aussi un bloc procédé et élément final.
    Ex: Des essais, durant des travaux d'installation ou maintenance.

### Chaîne de rétroaction
    > Transforme la variable à contrôler en PV avec les diverses instruments dans le bloc mesure.

![alt text](bruit_perturbation.png "Bruits et perturbations")

### Bruit
    > On appelle bruit les imperfections des signaux de contrôle de la boucle fermée. Le bruit se retrouve sur le signal de PV ou sur celui du SP si ce dernier vient d’un instrument à distance. 

#### Bruit de signal
    > Perturbation de signal se situant entre le bloc mesure et le bloc regulateur.

#### Bruit de commande
    > Perturbation de signal se situant entre le bloc régulateur et le bloc élément final.

### Perturbations
    > On appelle perturbation les imperfections retrouvées dans les grandeurs des variables physiques

#### Perturbation avant
    > Variable manipulée (entre élément final et procédé)

#### Perturbation après
    > Variable à contrôler (entre procédé et mesure)

### Bruit vs perturbation résumé 
    > En résumé, les bruits sont donc sur les signaux et les perturbations sont dans les grandeurs physiques.

## 3. Procédés

![alt text](types_procedes.png "Graphique types procédés")

### Procédé autorégulateur
![alt text](autoregulateur.png "Autorégulateur")
> Prenons, par exemple, un procédé de remplissage d’un réservoir d’eau dont la charge est
déterminée par l’ouverture de la vanne de vidange qui se vide à pression atmosphérique et par la
pression hydrostatique au fond du réservoir.  *

Exemple:
1. Le chauffage et la climatisation d’un local,
2. La vitesse d’une auto

### Procédé intégrateur
![alt text](integrateur.png "Intégrateur")
> Un procédé est dit intégrateur si, lorsqu’on lui applique une entrée constante, la sortie augmente indéfiniment et à un taux constant proportionnel à l’écart entre la valeur de l’entrée et celle de la charge.


Exemple:
1. Les vérins
2. les chaudières à vapeur
3. le niveau d’eau derrière un barrage 

### Procédé à emballement
![alt text](emballement.png "À emballement")
    > Un procédé est dit à emballement si lorsqu’on lui applique une variable manipulée constante, la variable à contrôler augmente indéfiniment et à un taux de plus en plus rapide.


Exemple:
1. Croissance population
2. Réaction nucléaire

### Déterminer le type de procédé
>   Pour savoir si un procédé est autorégulateur, intégrateur ou à emballement:
1. on place le procédé dans un état stable;
2. on change la position de l’élément final et on le garde fixe à cette position;
3. si la variable à contrôler se stabilise à une autre valeur, le système est autorégulateur;
4. si la variable à contrôler varie à taux constant sans jamais se stabiliser, c’est un système
intégrateur;
5. si la variable à contrôler augmente ou diminue exponentiellement, c’est un système à
emballement.
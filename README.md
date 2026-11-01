# Robot riešiaci bludisko
Tímový projekt VRS – autonómny mobilný robot so STM32, mapovaním bludiska a plánovaním kratšej trasy

## Opis projektu

Navrhnúť a zostrojiť autonómneho mobilného robota, ktorý pomocou snímačov vzdialenosti rozpoznáva steny, samostatne prechádza bludiskom, vytvára jeho mapu a následne vypočíta kratšiu trasu k cieľu.
Na konci porovnáme úspešnosť navigácie, čas prejazdu a opakovateľnosť pohybu. Riadenie a rozhodovanie bude zabezpečovať mikrokontrolér STM32.

## Čo plánujeme urobiť

- Navrhnúť elektromechanické rozhranie a objednať súčiastky.
- Zostaviť podvozok a zapojiť elektromechanické rozhranie.
- Pripojiť snímače vzdialenosti k STM32.
- Naprogramovať pohyb a rozhodovanie na križovatkách.
- Ukladať informácie o prejdenom bludisku.
- Vyskúšať kratšiu trasu a porovnať výsledky.


## Predpokladaný hardvér

| Súčiastka     					| Možný konkrétny model |
| ----------------------------------| ----------------------- |
| 1x Vývojová doska STM32F303K8     | STM32 NUCLEO-F303K8  |
| 2x Hnacie kolesá 					| Kolesá pre stavebnice áut rôzne typy   |
| 2x Nezávisle riadené DC motormi   | DFROBOT TT Motor so zabudovaným enkóderom   |
| 1x Driver pre DC motory   		| Motor driver TB6612FNG / Motor driver 3V – 10V dual H-bridge DRV8833   |
| 3x Snímače vzdialenosti  			| Laserový senzor vzdialenosti VL53L0x v2 / Laserový senzor vzdialenosti - VL53L1X   |
| 1x pasívne otočné koliesko   		| Otočné koliesko pre stavebnice autíčok  |
| Batérie   						| Box na batérie 6V / 4xAA s krytom a vypínačom  |
| Napäťové regulátory   			| 5V 3A step down converter ZDR344 USB  |
| 1x Podvozok  						| Zostrijume sami   |

## Navrhnúť elektromechanické rozhranie

 - Snímače vzdialenosti budú umiestnené v prednej časti robota a orientované dopredu, diagonálne doprava a diagonálne doľava. 
DC motory budú nezávisle riadené, aby sa robot mohol otáčať aj na mieste.
 - Motory majú napätie 6 V, preto nepotrebujú menič napätia medzi batériou a driverom. 
Napájanie z batérie bude taktiež pripojené k mikrokontroléru STM32 NUCLEO-F303K8 pomocou meniča napätia na 5 V. 
 - Mikrokontrolér bude následne napájaný cez USB alebo prípadne priamo cez pin 5V.
Mikrokontrolér bude riadiť motory pomocou PWM signálov, ktoré budú vstupovať do drivera. 
Zároveň bude prijímať signály z enkodérov na meranie otáčok motorov a prejdenej vzdialenosti.
	
## Popis uloh

 - Hardware assembly - zapojenie hardvaru 
 - Motor control – riadenie motorov.
 - Encoder processing – spracovanie údajov z enkodérov.
 - Distance sensing – komunikácia so snímačmi vzdialenosti.
 - Wall detection – rozpoznávanie stien.
 - Maze mapping – vytváranie mapy bludiska.
 - Navigation – rozhodovanie o ďalšom pohybe.
 - Path planning – výpočet trasy k cieľu.
 - Motion control – vykonávanie pohybov a otáčania.


## Členovia tímu

| Meno a priezvisko     | Technická časť projektu |
| --------------------- | ----------------------- |
| **Mykhailo Plys**     | Bude doplnené neskôr.   |
| **Peter Simon Kolar** | Hardvare assembly, Distance sensing, Motor control   |
| **Marek Kotian**      | Bude doplnené neskôr.   |
| **Dmytro Petrishko**  | Bude doplnené neskôr.   |


## Aktuálny stav

Zkonstruovana je specifikacia pre projekt a ulohy su rozdelene medzi clenmy.

# Úkol: Piškvorky 3/5

Tento úkol navazuje na [Piškvorky 2](https://github.com/Czechitas-podklady-WEB/Ukol-Piskvorky-2). Čeká tě oživení herních políček a volitelně i vylepšení tlačítka pro restart hry.

## Zadání

1.  Pokračuj v repozitáři `piskvorky` z předchozích úkolů.

1.  V několika dalších krocích budeš oživovat políčka herní plochy. První řádek oživených políček by vypadal nějak takto, ale s pomocí `querySelectorAll` zvládneš oživit najednou všechna políčka :-)

    ![zvýrazněných prvních deset políček](zadani/prvnich-deset.png)

1. Cílem bude, aby klikáním na políčka se v nich objevovaly kolečka a křížky a v levé části nad herní plochou se zobrazovala informace o tom, kdo je na tahu.

1. Křížek a kolečko tentokrát budeme potřebovat v černé barvě. Příslušné obrázky si můžeš stáhnout z tohoto repository z adresáře: [podklady](https://github.com/Czechitas-podklady-WEB/ukol-piskvorky-3/tree/main/podklady).

1. Nachystej si dvě CSS třídy (například `board__field--circle` a `board__field--cross`), které políčko dostylují tak, aby se na něm zobrazilo kolečko nebo křížek. Neboj se třídy otestovat tak, že je na zkoušku přidáš tlačítkům přímo v HTML. Po testu je ale z HTML nezapomeň smazat, protože tyto třídy bude přidávat a odebírat pouze javascript.

      ![HTML zkouška tříd](zadani/html-zkouska.png)

1. Vytvoř a napoj do stránky `hra.html` javascriptový soubor `hra.js`.

1. V javascriptu si nachystej proměnnou, která bude obsahovat informaci o tom, kdo je na tahu. Například `let currentPlayer = 'circle'`, protože hru začíná kolečko. `let` je potřeba proto, protože kdo je zrovna na tahu se bude v průběhu hry měnit.

1. Všem tlačítkům přidej posluchač události na kliknutí –  použij `querySelectorAll`. Vyřešíš sto tlačítek jednou ranou :-)

1. Pokud všechna tlačítka nemají společného rodiče, protože jsou třeba v tabulce, bude potřeba použít složený selektor. Např. vybrat buňku tabulky a v ní tlačítko – např. `document.querySelector('td button')` vybere pátou buňku tabulky a v ní vybere tlačítko.

1. Vytvoř funkci pro obsluhu události `click` (posluchač události), která políčku, na které uživatel kliknul (`event.target`), přidá příslušnou třídu. (Pro zjednodušení zkus přidávat nejdříve jen kolečka.)

      ![přidávání koleček](zadani/jen-kolecka.gif)

      ![střídání symbolů](zadani/stridani.gif)

1. S každým kliknutím změň hodnotu proměnné `currentPlayer` na opačnou. Z `circle` na `cross` a naopak.

1. Podle hotnoty proměnné na stránce uprav znázornění, kdo právě hraje.

      ![úprava, kdo hraje](zadani/kdo-hraje.gif)

1. Zamez, aby uživatel mohl na již zahraná políčka kliknout vícekrát pomocí vlastnosti `disabled` (`event.target.disabled = true`).

      ![dvojitý tah](zadani/dvojity-tah.gif)

      ![opraven dvojitý tah](zadani/opraven-dvojity-tah.gif)

## Bonus

1. Může se stát, že uživatel se omylem uklikne a modrým tlačítkem pro restart přijde o rozehranou hru. Proto přidej modrému odkazu posluchač události, který se po kliknutí uživatele zeptá zabudovanou funcí `confirm`, jestli chce hru opravdu restartovat. Pokud ne, zavolej `event.preventDefault()`, čímž zabráníš tomu, aby prohlížeč přešel na odkazovanou stránku (tj. načetl stránku s prázdnou hrou). Funkce `confirm` vrací `true` nebo `false` podle toho, zda uživatel souhlasil nebo nesouhlasil s potvrzovací zprávou v dialogu.

  ![ukázka restartu](zadani/restart.gif)

1. Pomocí animací přidej symbolům efekt postupného zvětšení. V náhledu je animace zpomalená z času `0.15s` na `0.45s`, aby bylo lépe vidět, jak má vypadat. V tvém kódu po otestování použij čas kratší, aby hra působila svižně.

  ![animace](zadani/klik-animace.gif)

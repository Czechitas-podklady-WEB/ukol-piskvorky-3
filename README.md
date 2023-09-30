# Úkol: Piškvorky 3/5

Tento úkol navazuje na [Piškvorky 2](https://github.com/Czechitas-podklady-WEB/Ukol-Piskvorky-2). Čeká tě oživění prvních pár políček a volitelně i vylepšení tlačítka pro restart hry.

## Zadání

1.  Pokračuj v repozitáři `piskvorky` z předchozích úkolů.

1.  V několika dalších krocích budeš oživovat pouze první řádek herní plochy, prvních deset políček. Zbylých 90 políček budeš oživovat až v dalších úkolech. Až po tom, co si v lekcích ukážeme další javascriptové vychytávky. Zbylá políčka na obrázku jsou zašedlá jen pro lepší představu. Ty je přestylovávat nemusíš.

    ![zvýrazněných prvních deset políček](zadani/prvnich-deset.png)

1.  Zařiď, aby klikáním na políčka se v nich objevovaly kolečka a křížky a v levé části nad herní plochou se zobrazovala informace o tom, kdo je na tahu. Co budeš potřebovat:

    - Nachystej si dvě CSS třídy (například `board__field--circle` a `board__field--cross`), které políčko dostylují tak, aby se na něm zobrazilo kolečko nebo křížek. Neboj se třídy otestovat tak, že je na zkoušku přidáš tlačítkům přímo v HTML. Po testu je ale z HTML nezapomeň smazat, protože tyto třídy bude přidávat a odebírat pouze javascript.

      ![HTML zkouška tříd](zadani/html-zkouska.png)

    - Vytvoř a napoj do stránky `hra.html` javascriptový soubor `hra.js`.

    - V javascriptu si nachystej proměnnou, která bude obsahovat informaci o tom, kdo je na tahu. Například `let currentPlayer = 'circle'`, protože hru začíná kolečko.

    - Všem deseti tlačítkům přidej posluchač události na kliknutí.

      - V selektorech si můžeš pomoct pseudotřídou `nth-child`. Například `document.querySelector('button:nth-child(5)')` vybere páté tlačítko (za předpokladu, že prvky `<button>` mají stejného rodiče). `document.querySelector('button:nth-child(6)')` vybere šesté, atd. Pokud všechna tlačítka nemají společného rodiče, protože jsou třeba v tabulce, bude potřeba pomocí `nth-child()` vybrat buňku tabulky a v ní tlačítko – např. `document.querySelector('td:nth-child(5) button')` vybere pátou buňku tabulky a v ní vybere tlačítko. Vybrat takhle tlačítka v dalších řádcích tabulky by bylo ještě komplikovanější, ale v tom nám v dalších lekcích pomůže JavaScript.

    - Vytvoř funkci pro posluchač, která políčku, na které uživatel kliknul (`event.target`), přidá příslušnou třídu. (Pro zjednodušení zkus přidávat nejdříve jen kolečka.)

      ![přidávání koleček](zadani/jen-kolecka.gif)

      ![střídání symbolů](zadani/stridani.gif)

    - S každým kliknutím změň hodnotu proměnné `currentPlayer` na opačnou. Z `circle` na `cross` a naopak.

    - Podle hotnoty proměnné na stránce uprav znázornění, kdo právě hraje.

      ![úprava, kdo hraje](zadani/kdo-hraje.gif)

    - Zamez, aby uživatel mohl na již zahraná políčka kliknout vícekrát pomocí vlastnosti `disabled` (`event.target.disabled = true`).

      ![dvojitý tah](zadani/dvojity-tah.gif)

      ![opraven dvojitý tah](zadani/opraven-dvojity-tah.gif)

## Bonus

- Může se stát, že uživatel se omylem uklikne a modrým tlačítkem pro restart přijde o rozehranou hru. Proto přidej modrému odkazu posluchač události, který se po kliknutí uživatele zeptá zabudovanou funcí `confirm`, jestli chce hru opravdu restartovat. Pokud ne, zavolej `event.preventDefault()`, čímž zabráníš tomu, aby prohlížeč přešel na odkazovanou stránku (tj. načetl stránku s prázdnou hrou). Funkce `confirm` vrací `true` nebo `false` podle toho, zda uživatel souhlasil nebo nesouhlasil s potvrzovací zprávou v dialogu.

  ![ukázka restartu](zadani/restart.gif)

- Pomocí animací přidej symbolům efekt postupného zvětšení. V náhledu je animace zpomalená z času `0.15s` na `0.45s`, aby bylo lépe vidět, jak má vypadat. V tvém kódu po otestování použij čas kratší, aby hra působila svižně.

  ![animace](zadani/klik-animace.gif)

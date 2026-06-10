# 01 Arcade Shark / Arcade Shark

[🇨🇿 Česky](#česky) | [🇬🇧 English](#english)

![Náhled hry / Game preview](https://raw.githubusercontent.com/aglio-olio-bros/01-arcade-shark/main/assets/preview.png)

---

## Česky

### O hře

**Arcade Shark** je jednoduchá hra vytvořená v **Microsoft MakeCode Arcade**.
Hráč ovládá žraloka, který plave pod mořem a chytá rybičky. Za každou chycenou rybu získá bod. Když ryba proplave až za pravý okraj obrazovky, hráč přijde o jeden život.

Hra je vhodná jako první nebo raný projekt pro děti a začátečníky, protože ukazuje několik důležitých herních principů na malém a srozumitelném příkladu.

### Cíl hry

Cílem je **pochytat co nejvíce ryb** a získat co nejvyšší skóre.

- Žralok je hlavní postava hráče.
- Ryby se objevují na levé straně obrazovky.
- Každá ryba plave směrem doprava.
- Když se žralok dotkne ryby, ryba zmizí a skóre se zvýší o 1 bod.
- Když ryba uplave mimo obrazovku, hráč ztratí 1 život.
- Hra začíná s 5 životy.

### Ovládání

V emulátoru MakeCode Arcade se žralok ovládá šipkami na klávesnici.

Na herní konzoli nebo gamepadu se používá směrový ovladač.

### Jak projekt spustit v MakeCode Arcade

1. Otevři stránku [Microsoft MakeCode Arcade](https://arcade.makecode.com/).
2. Klikni na **Import**.
3. Vyber **Import URL**.
4. Vlož adresu tohoto repozitáře:

   ```text
   https://github.com/aglio-olio-bros/01-arcade-shark
   ```

5. Projekt se otevře v MakeCode Arcade a můžeš ho spustit v emulátoru.

### Co je v kódu

Projekt je napsaný v TypeScriptu pro MakeCode Arcade a obsahuje i soubor s bloky.

Nejdůležitější části hry:

#### 1. Vytvoření ryby

Funkce `vytvorRybu` vytvoří novou rybu, nastaví jí pozici, rychlost a jednoduchou animaci ze dvou obrázků.

Díky tomu se stejný kód nemusí opakovat pro každou barvu ryby zvlášť.

#### 2. Žralok jako hráč

Žralok je vytvořen jako sprite typu `SpriteKind.Player`.
Má více obrázků, které se rychle střídají, takže vypadá, jako by plaval.

#### 3. Pohyb hráče

Příkaz `controller.moveSprite(...)` dovolí hráči ovládat žraloka pomocí směrových tlačítek.

#### 4. Chytání ryb

Událost `sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, ...)` sleduje, jestli se žralok dotkne ryby.
Když k tomu dojde:

- ryba se zničí,
- zobrazí se malý efekt,
- skóre se zvýší o 1.

#### 5. Ztráta života

V části `game.onUpdate(...)` se kontroluje, jestli některá ryba doplavala za pravý okraj obrazovky.
Pokud ano:

- ryba zmizí,
- hráč ztratí 1 život,
- kamera se krátce zatřese.

#### 6. Pravidelné vytváření ryb

Každou sekundu se vytvoří nová ryba.
Hra náhodně vybere jeden ze čtyř typů ryb. Jednotlivé ryby mají různé barvy a různé rychlosti.

### Co se na tomto projektu dá naučit

Na této hře se začátečníci mohou naučit:

- jak vytvořit sprite,
- jak nastavit obrázek postavy,
- jak rozpohybovat sprite,
- jak použít animaci,
- jak pracovat s náhodnými čísly,
- jak počítat skóre,
- jak používat životy,
- jak poznat dotyk dvou objektů,
- jak pravidelně spouštět část programu,
- jak rozdělit opakovaný kód do funkce.

### Nápady na vylepšení

Tato první verze hry je dobrý základ. Dá se rozšířit například takto:

- přidat úvodní obrazovku s názvem hry,
- přidat konec hry s výsledným skóre,
- zvyšovat rychlost ryb podle skóre,
- přidat nebezpečné předměty, kterým se žralok musí vyhnout,
- přidat větší rybu za více bodů,
- přidat zvuky při chycení ryby a při ztrátě života,
- přidat časový limit,
- přidat různé úrovně obtížnosti,
- přidat další mořské pozadí nebo animované bubliny.

### Struktura projektu

```text
01-arcade-shark/
├── main.ts       # hlavní program hry
├── main.blocks   # bloková podoba programu pro MakeCode
├── pxt.json      # nastavení MakeCode projektu
├── README.md     # popis projektu
└── LICENSE.txt   # licence projektu
```

### Licence

Projekt je zveřejněný pod licencí MIT. Podrobnosti jsou v souboru `LICENSE.txt`.

---

## English

### About the game

**Arcade Shark** is a simple game made in **Microsoft MakeCode Arcade**.
The player controls a shark swimming under the sea and catching fish. Each fish caught gives the player one point. If a fish swims past the right edge of the screen, the player loses one life.

The game is a good first or early project for children and beginners because it demonstrates several important game-development ideas in a small and easy-to-understand example.

### Goal of the game

The goal is to **catch as many fish as possible** and get the highest score you can.

- The shark is the player character.
- Fish appear on the left side of the screen.
- Each fish swims to the right.
- When the shark touches a fish, the fish disappears and the score increases by 1 point.
- When a fish escapes off the screen, the player loses 1 life.
- The game starts with 5 lives.

### Controls

In the MakeCode Arcade emulator, move the shark with the arrow keys.

On a handheld console or gamepad, use the directional pad.

### How to open the project in MakeCode Arcade

1. Open [Microsoft MakeCode Arcade](https://arcade.makecode.com/).
2. Click **Import**.
3. Choose **Import URL**.
4. Paste the repository address:

   ```text
   https://github.com/aglio-olio-bros/01-arcade-shark
   ```

5. The project will open in MakeCode Arcade and you can run it in the emulator.

### What is in the code

The project is written in TypeScript for MakeCode Arcade and also includes a Blocks file.

The most important parts of the game are:

#### 1. Creating a fish

The `vytvorRybu` function creates a new fish, sets its position, speed, and a simple two-frame animation.

This keeps the code shorter because the same logic can be reused for fish with different colors and speeds.

#### 2. The shark as the player

The shark is created as a `SpriteKind.Player` sprite.
It has multiple animation frames that change quickly, making the shark look like it is swimming.

#### 3. Player movement

The `controller.moveSprite(...)` command lets the player move the shark with the directional controls.

#### 4. Catching fish

The `sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, ...)` event checks whether the shark touches a fish.
When that happens:

- the fish is destroyed,
- a small effect is shown,
- the score increases by 1.

#### 5. Losing a life

The `game.onUpdate(...)` part checks whether any fish has reached the right edge of the screen.
If a fish escapes:

- the fish is removed,
- the player loses 1 life,
- the camera shakes briefly.

#### 6. Spawning fish regularly

Every second, the game creates a new fish.
It randomly chooses one of four fish types. The fish have different colors and different speeds.

### What beginners can learn from this project

This game can help beginners learn:

- how to create a sprite,
- how to set a character image,
- how to move a sprite,
- how to use animation,
- how to use random numbers,
- how to count score,
- how to use lives,
- how to detect overlap between two objects,
- how to run code repeatedly,
- how to move repeated code into a function.

### Ideas for improvements

This first version is a good base for future changes. You could add:

- a title screen,
- a game-over screen with the final score,
- fish that get faster as the score increases,
- dangerous objects that the shark must avoid,
- a bigger fish worth more points,
- sound effects for catching fish and losing a life,
- a time limit,
- difficulty levels,
- more underwater backgrounds or animated bubbles.

### Project structure

```text
01-arcade-shark/
├── main.ts       # main game program
├── main.blocks   # block version of the program for MakeCode
├── pxt.json      # MakeCode project configuration
├── README.md     # project description
└── LICENSE.txt   # project license
```

### License

This project is released under the MIT license. See `LICENSE.txt` for details.

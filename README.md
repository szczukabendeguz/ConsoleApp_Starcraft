# Console StarCraft

A turn-based strategy console game inspired by StarCraft, developed as a major university project assignment during my early studies.

## Tech Stack

[![Tech Stack](https://skillicons.dev/icons?i=cs,dotnet,visualstudio)](https://skillicons.dev)

## Project Goal

This project is a **console-based turn-based strategy game** where two players (Terran vs Zerg) compete on a 10×10 grid battlefield. Each player controls a base and can spawn different unit types with unique stats, move units across the field, attack enemy forces, and manage population and resources. The objective is to destroy the opponent's base while defending your own.

This was developed as a **major university assignment (NagyHázi)** during my early academic studies, representing one of my first larger programming projects. As such, it served as a learning experience in object-oriented programming, game logic implementation, and console application development in C#.

## Getting Started

### Prerequisites

- .NET Framework 4.7.2 or higher
- Visual Studio 2015 or later (or any C# compiler supporting .NET Framework 4.7.2)
- Windows operating system (console application designed for Windows)

### Running the Game

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/ConsoleApp_Starcraft.git
   cd ConsoleApp_Starcraft
   ```

2. **Open the solution**:
   - Open `NagyHázi_Starcraft.sln` in Visual Studio

3. **Build the project**:
   - Build the solution using Visual Studio (F6 or Build → Build Solution)

4. **Run the game**:
   - Press F5 to run in debug mode, or Ctrl+F5 to run without debugging
   - Alternatively, navigate to `NagyHázi_Starcraft\bin\Debug\` and run the `.exe` file

### Game Files

The game requires the following text files in the same directory as the executable:
- `Rules.txt` - Game rules and instructions
- `Credits.txt` - Credits information

## Gameplay

### Teams

- **Terran** (Blue): One of the two playable factions
- **Zerg** (Red): The opposing faction

### Unit Types

Each faction can spawn three types of units with different characteristics:

| Unit Type | Lives | Attack Strength | Range | Population Cost | Build Time |
|-----------|-------|----------------|-------|----------------|------------|
| **Marauders** | 6 | 3 | 3 | 3 | 3 rounds |
| **CacoDemons** | 4 | 5 | 3 | 5 | 4 rounds |
| **Snakes with Knives** | 2 | 2 | 1 | 2 | 1 round |

### Controls

- **Arrow Keys**: Move cursor on the battlefield
- **[M]**: Move selected unit
- **[A]**: Attack with selected unit
- **[P]**: Place a new unit (when in base range)
- **[S]**: Confirm unit movement
- **[T]**: Confirm attack target
- **[Enter]**: Save game state
- **[Escape]**: Exit game
- **[Backspace]**: Pass turn / Cancel action

### Game Mechanics

- **Turn-based gameplay**: Players alternate turns with a limited number of actions per turn (default: 3 actions)
- **Population management**: Maximum population of 20, with each unit consuming different amounts
- **Unit limit**: Maximum of 6 units per player
- **Base range**: Units can only be spawned within 4 tiles of your base
- **Combat**: Units can attack enemies within their range, dealing damage equal to their attack strength
- **Victory condition**: Destroy the enemy base (base has 10 health points)

### Save/Load System

The game features a binary serialization-based save system:
- Press **[Enter]** during gameplay to save the current game state
- Select "Load a previous Game" from the main menu to restore a saved game
- Save files: `PF.dat`, `Zerg.dat`, `Terran.dat`, `cursor.dat`

## Architecture

The project follows an object-oriented design with the following key components:

- **`Frontend`**: Handles console rendering, slow-print effects, and field visualization
- **`Playingfield`**: Manages the 10×10 game grid, storing unit positions, health, strength, and range
- **`Units`**: Base class for all unit types (Marauders, CacoDemons, SnakesWithKnives, Base)
- **`Interactions`**: Handles user input, cursor movement, unit placement, movement, and combat logic
- **`Players`**: Manages player state, including population, units, actions, and team affiliation
- **`Menu`**: Provides main menu navigation, rules display, and credits
- **`Program`**: Entry point and main game loop

## Note

This project was created as a learning exercise during my early university studies. As mentioned in the original README: *"This is my first bigger project so please excuse my mistakes!"* The code reflects my programming skills at that time and may not follow all modern best practices.

---

# Console StarCraft

Egy körökre osztott stratégiai konzolos játék, amelyet a StarCraft ihletett, és egyetemi tanulmányaim elején készítettem nagy házi feladatként.

## Tech Stack

[![Tech Stack](https://skillicons.dev/icons?i=cs,dotnet,visualstudio)](https://skillicons.dev)

## Projekt célja

Ez a projekt egy **konzolos, körökre osztott stratégiai játék**, amelyben két játékos (Terran vs Zerg) versenyez egy 10×10-es rácson. Minden játékos irányít egy bázist, különböző egységtípusokat hozhat létre egyedi statisztikákkal, mozgathatja az egységeket a pályán, megtámadhatja az ellenséges erőket, valamint kezelheti a populációt és az erőforrásokat. A cél az ellenfél bázisának elpusztítása, miközben megvéded a sajátodat.

Ezt a projektet **egyetemi nagy házi feladatként (NagyHázi)** fejlesztettem tanulmányaim elején, és ez volt az egyik első nagyobb programozási projektem. Mint ilyen, tanulási tapasztalatként szolgált az objektum-orientált programozásban, a játéklogika implementálásában és a C# konzolos alkalmazások fejlesztésében.

## Kezdő lépések

### Előfeltételek

- .NET Framework 4.7.2 vagy újabb
- Visual Studio 2015 vagy újabb (vagy bármely C# compiler, amely támogatja a .NET Framework 4.7.2-t)
- Windows operációs rendszer (a konzolos alkalmazás Windowsra készült)

### A játék futtatása

1. **Repository klónozása**:
   ```bash
   git clone https://github.com/yourusername/ConsoleApp_Starcraft.git
   cd ConsoleApp_Starcraft
   ```

2. **Solution megnyitása**:
   - Nyisd meg a `NagyHázi_Starcraft.sln` fájlt Visual Studio-ban

3. **Projekt build-elése**:
   - Build-eld a solution-t Visual Studio-ban (F6 vagy Build → Build Solution)

4. **Játék indítása**:
   - Nyomd meg az F5-öt debug módban való futtatáshoz, vagy Ctrl+F5-öt debug nélküli futtatáshoz
   - Alternatívaként navigálj a `NagyHázi_Starcraft\bin\Debug\` mappába és futtasd az `.exe` fájlt

### Játék fájlok

A játékhoz szükséges a következő szöveges fájlok az executable-lel egy könyvtárban:
- `Rules.txt` - Játékszabályok és instrukciók
- `Credits.txt` - Credits információk

## Játékmenet

### Csapatok

- **Terran** (Kék): Az egyik játszható frakció
- **Zerg** (Piros): Az ellenfél frakció

### Egységtípusok

Minden frakció három különböző tulajdonságokkal rendelkező egységtípust hozhat létre:

| Egységtípus | Életerő | Támadóerő | Hatótáv | Populáció költség | Build idő |
|-------------|---------|-----------|---------|-------------------|-----------|
| **Marauders** | 6 | 3 | 3 | 3 | 3 kör |
| **CacoDemons** | 4 | 5 | 3 | 5 | 4 kör |
| **Snakes with Knives** | 2 | 2 | 1 | 2 | 1 kör |

### Irányítás

- **Nyílbillentyűk**: Kurzor mozgatása a csatatéren
- **[M]**: Kiválasztott egység mozgatása
- **[A]**: Támadás a kiválasztott egységgel
- **[P]**: Új egység lehelyezése (ha a bázis hatótávolságában vagy)
- **[S]**: Egység mozgatásának megerősítése
- **[T]**: Támadási cél megerősítése
- **[Enter]**: Játékállás mentése
- **[Escape]**: Kilépés a játékból
- **[Backspace]**: Kör átadása / Művelet megszakítása

### Játékmechanikák

- **Körökre osztott játékmenet**: A játékosok felváltva lépnek, korlátozott számú akcióval köröként (alapértelmezett: 3 akció)
- **Populáció kezelés**: Maximum 20 populáció, minden egység különböző mennyiséget fogyaszt
- **Egység limit**: Maximum 6 egység játékosonként
- **Bázis hatótáv**: Egységek csak a bázistól 4 mezőnyi távolságon belül hozhatók létre
- **Harc**: Az egységek megtámadhatják az ellenségeket a hatótávolságukon belül, a támadóerejükkel egyenlő sebzést okozva
- **Győzelmi feltétel**: Az ellenséges bázis elpusztítása (a bázis 10 életerővel rendelkezik)

### Save/Load rendszer

A játék bináris szerializáción alapuló mentési rendszert használ:
- Nyomd meg az **[Enter]** billentyűt játék közben az aktuális játékállás mentéséhez
- Válaszd a "Load a previous Game" opciót a főmenüben egy mentett játék visszatöltéséhez
- Mentés fájlok: `PF.dat`, `Zerg.dat`, `Terran.dat`, `cursor.dat`

## Architektúra

A projekt objektum-orientált tervezést követ a következő kulcsfontosságú komponensekkel:

- **`Frontend`**: Kezeli a konzol renderelést, slow-print effekteket és a pálya vizualizációját
- **`Playingfield`**: Kezeli a 10×10-es játékrácsot, tárolja az egységek pozícióit, életerejét, erejét és hatótávolságát
- **`Units`**: Alaposztály minden egységtípushoz (Marauders, CacoDemons, SnakesWithKnives, Base)
- **`Interactions`**: Kezeli a felhasználói inputot, kurzor mozgatást, egység lehelyezést, mozgatást és harci logikát
- **`Players`**: Kezeli a játékos állapotát, beleértve a populációt, egységeket, akciókat és csapathovatartozást
- **`Menu`**: Biztosítja a főmenü navigációt, szabályok megjelenítését és credits-et
- **`Program`**: Belépési pont és fő játék loop

## Megjegyzés

Ez a projekt tanulási gyakorlatként készült egyetemi tanulmányaim elején. Ahogy az eredeti README-ben is említettem: *"This is my first bigger project so please excuse my mistakes!"* A kód az akkori programozási tudásomat tükrözi, és nem feltétlenül követi az összes modern best practice-t.

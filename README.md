🎮 Features

Username Entry — Players enter their name before the game starts
Main Menu — Navigate between Play, How to Play, Highscore, and Quit using keyboard input
3 Progressively Challenging Levels — Each level features a unique, hand-coded maze with increasing ghost count and difficulty
7 Ghosts — Each ghost has its own position, direction handle, and movement logic
Coin System — 600 coins per level; collecting all coins advances to the next level
Power Pellets (*) — Present in Level 2 for extra challenge
Lives System — Players start with 3 lives; ghost collisions cost a life
Score Tracking — Score updates in real time, with +1 animations on coin collection
Highscore Board — Top 3 scores (name, score, level) saved to and loaded from score.txt
Sound Effects — .wav audio integration via winmm.lib:

Intro music
Chomp sound
Eat fruit sound
Death sound


How to Play Screen — In-game instructions with a snarky ASCII-art ghost
Colorful ASCII Graphics — Pinky and Blinky ghost sprites drawn with P, W, B characters and rendered using Irvine32 color attributes


🗂️ Project Structure
Pacman-ASM-Irvine32/
│
├── main.asm                    # Core game logic (7100+ lines of x86 Assembly)
├── macros.inc                  # Custom macros
├── Irvine32.inc                # Irvine32 library header
├── Pacman-ASM-Irivine32.sln   # Visual Studio solution file
├── Pacman-ASM-Irivine32.vcxproj # VS project configuration
├── Pacman-ASM-Irivine32.lst   # Assembler listing file
│
├── pacman_beginning.wav        # Intro music
├── pacman_chomp.wav            # Chomp sound effect
├── pacman_eatfruit.wav         # Fruit eat sound effect
├── pacman_death.wav            # Death sound effect
│
└── score.txt                   # Highscore persistence file (auto-generated)

🛠️ Built With
Tool / TechnologyPurposeMASM (Microsoft Macro Assembler)Assembly language assemblerIrvine32 LibraryConsole I/O, color output, cursor controlwinmm.libWindows Multimedia API for .wav playbackVisual StudioIDE and build environmentx86 ArchitectureTarget CPU instruction set

⚙️ Prerequisites
Before running this project, make sure you have:

Windows OS (x86/x64)
Visual Studio (2019 or later recommended) with MASM support enabled
Irvine32 Library installed and configured

Download from Kip Irvine's official site
Follow the setup guide to link Irvine32.lib and Irvine32.inc in VS


.wav sound files placed in the same directory as the executable


🚀 Getting Started

Clone the repository

bash   git clone https://github.com/msaimsawaid/Pacman-Assembly.git
   cd Pacman-ASM-Irvine32

Open the solution

   Open Pacman-ASM-Irivine32.sln in Visual Studio

Configure Irvine32

Ensure Irvine32.inc, Irvine32.lib, and SmallWin.inc are in your include path
Set the project to use the x86 platform target


Build and Run

Set build configuration to Debug | x86
Press Ctrl + F5 to build and run without debugger


🕹️ Controls
KeyActionWMove UpSMove DownAMove LeftDMove Right1, 2, 3, 4Navigate menusEnterConfirm input8Go Back (How to Play screen)

🧩 Maze Design
Three unique mazes were hand-crafted directly in assembly .data section:

Level 1 — 22-row classic maze, 1 ghost, speed delay: 150ms
Level 2 — Extended 22-row maze with power pellets, 2 ghosts, speed: 125ms
Level 3 — Larger maze, 4 ghosts, speed: 100ms (hardest)

Walls are represented as X, coins as ., power pellets as *, and spaces as  .

📊 Highscore System

Scores are persisted to score.txt in the working directory
The game stores the top 3 entries: Name, Score, Level
File I/O is handled entirely in assembly using CreateFile, ReadFile, and WriteFile via Irvine32 wrappers


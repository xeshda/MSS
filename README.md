## Making SFML even Simpler

***table of contents***
- [Introduction](#introduction)
- [Credits](#credits)
    - [Tutorial](#tutorial)
    - [Window](#window)
        - [Chaning Resolution](#changing-resolution)
    - [Text](#text)
        - [Item Description Example](#item-description-example)
    - [Animation](#animation)
    - [Compiling](#compiling)

# Introduction
This little modification builds on top of [SFML](https://www.sfml-dev.org/) to make wonderful library even more accessable to beginners. Which is also useful for people studying Game Engines so they can get to see how little lines can be turned into big projects.

I absolutely do not own anything of SFML and have not written it myself, I am merely an entheusiast who wants to make it more accessable for others without giving up on learning how to make games without an A+++ bloated game engine.

SFML's License can be found [__here__](https://www.sfml-dev.org/license.php)

### Credits

***Font:*** [FFF Forward](https://www.1001fonts.com/fff-forward-font.html) by [Fonts For Flash](https://www.1001fonts.com/users/fontsforflash/)

# Tutorial

## Window

### Changing Resolution
Changing the resolution can be possible by simply using:
```win::resolution(1280, 720);```
and matching those numbers with whatever resolution you see fit.

## Text
To draw a text on the screen you can use:

```d_text::dialogue("This is a test");```

This will try to center the text in the middle of the screen.

### Item Description Example
If you're working on an RPG, you likely want some item descriptions when you're interacting with objects in the overworld, a little example for this would be:

```d_text::description("The door won't budge");```

As of right now, we don't have multilple sentences available. Meaning when you want to write descriptions, you can't press on "Next" and have it say even more. It's limited to one string as of now.

## Animation
The setup of the animation system is there is an int called `counterAnimation` which is under the `animation` namespace. When you have your spritesheet/texture ready, you need to count how how many frames you want it to cycle

***NOTE: WHEN YOU'RE CREATING THE SPRITESHEET, PLEASE SET FRAMES OF ONE STATE VERTICALLY FROM TOP TO BOTTOM AS THIS IS WHAT THIS GUIDE USES***

Let's assume you made an `if` statement for moving right. And you have exactly 10 frames for that walking cycle. You'd use:

```animation::counterAnimation = 0
animation::speed(1.8);
animation::frames(10);
player.setTextureRect(sf::IntRect{0, 32*animation::counterAnimation, 16, 32});
```

## Compiling
When you write code you usually (hopefully) want to get the chance to actually see if it works. In order to do that you need to compile your program with the necessary libraries. Since we're using SFML, we need to add those options.

```g++ main.cpp -lsfml-window -lsfml-graphics -lsfml-system -lsfml-audio -lsfml-network```

for more information, please refer to SFML's Page on ["SFML and Linux"](https://www.sfml-dev.org/tutorials/2.5/start-linux.php)

["Compiling SFML with CMAKE"](https://www.sfml-dev.org/tutorials/2.5/compile-with-cmake.php)

or ["SFML and Code::Blocks (MinGW)"](https://www.sfml-dev.org/tutorials/2.5/start-cb.php)

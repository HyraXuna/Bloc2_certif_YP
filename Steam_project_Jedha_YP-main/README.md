# Steam project

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com) [![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com)

This is the Big Data project, where the goals is to use pyspark to deal with a large amount of data and to do some data exploration and analysis.

## Getting Started

* Part 1 : Discovering of the dataset - https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1194151080643746/3544767636475944/4091875463035457/latest.html
* Part 2 : Analysis at Macro level - https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1194151080643746/3843038297527147/4091875463035457/latest.html
* Part 3 : Analysis on the genres - https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1194151080643746/3609660208733958/4091875463035457/latest.html
* Part 4 : Platforms Analysis - https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1194151080643746/4024589675953913/4091875463035457/latest.html


### Prerequisites

The code was made on databricks, with pyspark.

### Some Results

* *Part 1*:

The global schema of the data.

```
root
 |-- data: struct (nullable = true)
 |    |-- appid: long (nullable = true)
 |    |-- categories: array (nullable = true)
 |    |    |-- element: string (containsNull = true)
 |    |-- ccu: long (nullable = true)
 |    |-- developer: string (nullable = true)
 |    |-- discount: string (nullable = true)
 |    |-- genre: string (nullable = true)
 |    |-- header_image: string (nullable = true)
 |    |-- initialprice: string (nullable = true)
 |    |-- languages: string (nullable = true)
 |    |-- name: string (nullable = true)
 |    |-- negative: long (nullable = true)
 |    |-- owners: string (nullable = true)
 |    |-- platforms: struct (nullable = true)
 |    |    |-- linux: boolean (nullable = true)
 |    |    |-- mac: boolean (nullable = true)
 |    |    |-- windows: boolean (nullable = true)
 |    |-- positive: long (nullable = true)
 |    |-- price: string (nullable = true)
 |    |-- publisher: string (nullable = true)
 |    |-- release_date: string (nullable = true)
 |    |-- required_age: string (nullable = true)
 |    |-- short_description: string (nullable = true)
 |    |-- tags: struct (nullable = true)
 |    |    |-- 1980s: long (nullable = true)
 |    |    |-- 1990's: long (nullable = true)
 |    |    |-- 2.5D: long (nullable = true)
 |    |    |-- 2D: long (nullable = true)
 |    |    |-- 2D Fighter: long (nullable = true)
 |    |    |-- 2D Platformer: long (nullable = true)
 |    |    |-- 360 Video: long (nullable = true)
 |    |    |-- 3D: long (nullable = true)
 |    |    |-- 3D Fighter: long (nullable = true)
 |    |    |-- 3D Platformer: long (nullable = true)
 |    |    |-- 3D Vision: long (nullable = true)
 |    |    |-- 4 Player Local: long (nullable = true)
 |    |    |-- 4X: long (nullable = true)
 |    |    |-- 6DOF: long (nullable = true)
 |    |    |-- 8-bit Music: long (nullable = true)
 |    |    |-- ATV: long (nullable = true)
 |    |    |-- Abstract: long (nullable = true)
 |    |    |-- Action: long (nullable = true)
 |    |    |-- Action RPG: long (nullable = true)
 |    |    |-- Action RTS: long (nullable = true)
 |    |    |-- Action Roguelike: long (nullable = true)
 |    |    |-- Action-Adventure: long (nullable = true)
 |    |    |-- Addictive: long (nullable = true)
 |    |    |-- Adventure: long (nullable = true)
 |    |    |-- Agriculture: long (nullable = true)
 |    |    |-- Aliens: long (nullable = true)
 |    |    |-- Alternate History: long (nullable = true)
 |    |    |-- Ambient: long (nullable = true)
 |    |    |-- America: long (nullable = true)
 |    |    |-- Animation & Modeling: long (nullable = true)
 |    |    |-- Anime: long (nullable = true)
 |    |    |-- Arcade: long (nullable = true)
 |    |    |-- Archery: long (nullable = true)
 |    |    |-- Arena Shooter: long (nullable = true)
 |    |    |-- Artificial Intelligence: long (nullable = true)
 |    |    |-- Assassin: long (nullable = true)
 |    |    |-- Asymmetric VR: long (nullable = true)
 |    |    |-- Asynchronous Multiplayer: long (nullable = true)
 |    |    |-- Atmospheric: long (nullable = true)
 |    |    |-- Audio Production: long (nullable = true)
 |    |    |-- Auto Battler: long (nullable = true)
 |    |    |-- Automation: long (nullable = true)
 |    |    |-- Automobile Sim: long (nullable = true)
 |    |    |-- BMX: long (nullable = true)
 |    |    |-- Base-Building: long (nullable = true)
 |    |    |-- Baseball: long (nullable = true)
 |    |    |-- Based On A Novel: long (nullable = true)
 |    |    |-- Basketball: long (nullable = true)
 |    |    |-- Battle Royale: long (nullable = true)
 |    |    |-- Beat 'em up: long (nullable = true)
 |    |    |-- Beautiful: long (nullable = true)
 |    |    |-- Benchmark: long (nullable = true)
 |    |    |-- Bikes: long (nullable = true)
 |    |    |-- Blood: long (nullable = true)
 |    |    |-- Board Game: long (nullable = true)
 |    |    |-- Boss Rush: long (nullable = true)
 |    |    |-- Bowling: long (nullable = true)
 |    |    |-- Boxing: long (nullable = true)
 |    |    |-- Building: long (nullable = true)
 |    |    |-- Bullet Hell: long (nullable = true)
 |    |    |-- Bullet Time: long (nullable = true)
 |    |    |-- CRPG: long (nullable = true)
 |    |    |-- Capitalism: long (nullable = true)
 |    |    |-- Card Battler: long (nullable = true)
 |    |    |-- Card Game: long (nullable = true)
 |    |    |-- Cartoon: long (nullable = true)
 |    |    |-- Cartoony: long (nullable = true)
 |    |    |-- Casual: long (nullable = true)
 |    |    |-- Cats: long (nullable = true)
 |    |    |-- Character Action Game: long (nullable = true)
 |    |    |-- Character Customization: long (nullable = true)
 |    |    |-- Chess: long (nullable = true)
 |    |    |-- Choices Matter: long (nullable = true)
 |    |    |-- Choose Your Own Adventure: long (nullable = true)
 |    |    |-- Cinematic: long (nullable = true)
 |    |    |-- City Builder: long (nullable = true)
 |    |    |-- Class-Based: long (nullable = true)
 |    |    |-- Classic: long (nullable = true)
 |    |    |-- Clicker: long (nullable = true)
 |    |    |-- Co-op: long (nullable = true)
 |    |    |-- Co-op Campaign: long (nullable = true)
 |    |    |-- Coding: long (nullable = true)
 |    |    |-- Cold War: long (nullable = true)
 |    |    |-- Collectathon: long (nullable = true)
 |    |    |-- Colony Sim: long (nullable = true)
 |    |    |-- Colorful: long (nullable = true)
 |    |    |-- Combat: long (nullable = true)
 |    |    |-- Combat Racing: long (nullable = true)
 |    |    |-- Comedy: long (nullable = true)
 |    |    |-- Comic Book: long (nullable = true)
 |    |    |-- Competitive: long (nullable = true)
 |    |    |-- Conspiracy: long (nullable = true)
 |    |    |-- Controller: long (nullable = true)
 |    |    |-- Conversation: long (nullable = true)
 |    |    |-- Cooking: long (nullable = true)
 |    |    |-- Cozy: long (nullable = true)
 |    |    |-- Crafting: long (nullable = true)
 |    |    |-- Creature Collector: long (nullable = true)
 |    |    |-- Cricket: long (nullable = true)
 |    |    |-- Crime: long (nullable = true)
 |    |    |-- Crowdfunded: long (nullable = true)
 |    |    |-- Cult Classic: long (nullable = true)
 |    |    |-- Cute: long (nullable = true)
 |    |    |-- Cyberpunk: long (nullable = true)
 |    |    |-- Cycling: long (nullable = true)
 |    |    |-- Dark: long (nullable = true)
 |    |    |-- Dark Comedy: long (nullable = true)
 |    |    |-- Dark Fantasy: long (nullable = true)
 |    |    |-- Dark Humor: long (nullable = true)
 |    |    |-- Dating Sim: long (nullable = true)
 |    |    |-- Deckbuilding: long (nullable = true)
 |    |    |-- Demons: long (nullable = true)
 |    |    |-- Design & Illustration: long (nullable = true)
 |    |    |-- Destruction: long (nullable = true)
 |    |    |-- Detective: long (nullable = true)
 |    |    |-- Difficult: long (nullable = true)
 |    |    |-- Dinosaurs: long (nullable = true)
 |    |    |-- Diplomacy: long (nullable = true)
 |    |    |-- Documentary: long (nullable = true)
 |    |    |-- Dog: long (nullable = true)
 |    |    |-- Dragons: long (nullable = true)
 |    |    |-- Drama: long (nullable = true)
 |    |    |-- Driving: long (nullable = true)
 |    |    |-- Dungeon Crawler: long (nullable = true)
 |    |    |-- Dungeons & Dragons: long (nullable = true)
 |    |    |-- Dynamic Narration: long (nullable = true)
 |    |    |-- Dystopian : long (nullable = true)
 |    |    |-- Early Access: long (nullable = true)
 |    |    |-- Economy: long (nullable = true)
 |    |    |-- Education: long (nullable = true)
 |    |    |-- Electronic: long (nullable = true)
 |    |    |-- Electronic Music: long (nullable = true)
 |    |    |-- Emotional: long (nullable = true)
 |    |    |-- Epic: long (nullable = true)
 |    |    |-- Episodic: long (nullable = true)
 |    |    |-- Escape Room: long (nullable = true)
 |    |    |-- Experience: long (nullable = true)
 |    |    |-- Experimental: long (nullable = true)
 |    |    |-- Exploration: long (nullable = true)
 |    |    |-- FMV: long (nullable = true)
 |    |    |-- FPS: long (nullable = true)
 |    |    |-- Faith: long (nullable = true)
 |    |    |-- Family Friendly: long (nullable = true)
 |    |    |-- Fantasy: long (nullable = true)
 |    |    |-- Farming: long (nullable = true)
 |    |    |-- Farming Sim: long (nullable = true)
 |    |    |-- Fast-Paced: long (nullable = true)
 |    |    |-- Feature Film: long (nullable = true)
 |    |    |-- Female Protagonist: long (nullable = true)
 |    |    |-- Fighting: long (nullable = true)
 |    |    |-- First-Person: long (nullable = true)
 |    |    |-- Fishing: long (nullable = true)
 |    |    |-- Flight: long (nullable = true)
 |    |    |-- Football: long (nullable = true)
 |    |    |-- Foreign: long (nullable = true)
 |    |    |-- Free to Play: long (nullable = true)
 |    |    |-- Funny: long (nullable = true)
 |    |    |-- Futuristic: long (nullable = true)
 |    |    |-- Gambling: long (nullable = true)
 |    |    |-- Game Development: long (nullable = true)
 |    |    |-- GameMaker: long (nullable = true)
 |    |    |-- Games Workshop: long (nullable = true)
 |    |    |-- Gaming: long (nullable = true)
 |    |    |-- God Game: long (nullable = true)
 |    |    |-- Golf: long (nullable = true)
 |    |    |-- Gore: long (nullable = true)
 |    |    |-- Gothic: long (nullable = true)
 |    |    |-- Grand Strategy: long (nullable = true)
 |    |    |-- Great Soundtrack: long (nullable = true)
 |    |    |-- Grid-Based Movement: long (nullable = true)
 |    |    |-- Gun Customization: long (nullable = true)
 |    |    |-- Hack and Slash: long (nullable = true)
 |    |    |-- Hacking: long (nullable = true)
 |    |    |-- Hand-drawn: long (nullable = true)
 |    |    |-- Hardware: long (nullable = true)
 |    |    |-- Heist: long (nullable = true)
 |    |    |-- Hentai: long (nullable = true)
 |    |    |-- Hero Shooter: long (nullable = true)
 |    |    |-- Hex Grid: long (nullable = true)
 |    |    |-- Hidden Object: long (nullable = true)
 |    |    |-- Historical: long (nullable = true)
 |    |    |-- Hockey: long (nullable = true)
 |    |    |-- Horror: long (nullable = true)
 |    |    |-- Horses: long (nullable = true)
 |    |    |-- Hunting: long (nullable = true)
 |    |    |-- Idler: long (nullable = true)
 |    |    |-- Illuminati: long (nullable = true)
 |    |    |-- Immersive: long (nullable = true)
 |    |    |-- Immersive Sim: long (nullable = true)
 |    |    |-- Indie: long (nullable = true)
 |    |    |-- Instrumental Music: long (nullable = true)
 |    |    |-- Intentionally Awkward Controls: long (nullable = true)
 |    |    |-- Interactive Fiction: long (nullable = true)
 |    |    |-- Inventory Management: long (nullable = true)
 |    |    |-- Investigation: long (nullable = true)
 |    |    |-- Isometric: long (nullable = true)
 |    |    |-- JRPG: long (nullable = true)
 |    |    |-- Jet: long (nullable = true)
 |    |    |-- Job Simulator: long (nullable = true)
 |    |    |-- Jump Scare: long (nullable = true)
 |    |    |-- Kickstarter: long (nullable = true)
 |    |    |-- LEGO: long (nullable = true)
 |    |    |-- LGBTQ+: long (nullable = true)
 |    |    |-- Lemmings: long (nullable = true)
 |    |    |-- Level Editor: long (nullable = true)
 |    |    |-- Life Sim: long (nullable = true)
 |    |    |-- Linear: long (nullable = true)
 |    |    |-- Local Co-Op: long (nullable = true)
 |    |    |-- Local Multiplayer: long (nullable = true)
 |    |    |-- Logic: long (nullable = true)
 |    |    |-- Loot: long (nullable = true)
 |    |    |-- Looter Shooter: long (nullable = true)
 |    |    |-- Lore-Rich: long (nullable = true)
 |    |    |-- Lovecraftian: long (nullable = true)
 |    |    |-- MMORPG: long (nullable = true)
 |    |    |-- MOBA: long (nullable = true)
 |    |    |-- Magic: long (nullable = true)
 |    |    |-- Mahjong: long (nullable = true)
 |    |    |-- Management: long (nullable = true)
 |    |    |-- Mars: long (nullable = true)
 |    |    |-- Martial Arts: long (nullable = true)
 |    |    |-- Massively Multiplayer: long (nullable = true)
 |    |    |-- Masterpiece: long (nullable = true)
 |    |    |-- Match 3: long (nullable = true)
 |    |    |-- Mature: long (nullable = true)
 |    |    |-- Mechs: long (nullable = true)
 |    |    |-- Medical Sim: long (nullable = true)
 |    |    |-- Medieval: long (nullable = true)
 |    |    |-- Memes: long (nullable = true)
 |    |    |-- Metroidvania: long (nullable = true)
 |    |    |-- Military: long (nullable = true)
 |    |    |-- Mini Golf: long (nullable = true)
 |    |    |-- Minigames: long (nullable = true)
 |    |    |-- Minimalist: long (nullable = true)
 |    |    |-- Mining: long (nullable = true)
 |    |    |-- Mod: long (nullable = true)
 |    |    |-- Moddable: long (nullable = true)
 |    |    |-- Modern: long (nullable = true)
 |    |    |-- Motocross: long (nullable = true)
 |    |    |-- Motorbike: long (nullable = true)
 |    |    |-- Mouse only: long (nullable = true)
 |    |    |-- Movie: long (nullable = true)
 |    |    |-- Multiplayer: long (nullable = true)
 |    |    |-- Multiple Endings: long (nullable = true)
 |    |    |-- Music: long (nullable = true)
 |    |    |-- Music-Based Procedural Generation: long (nullable = true)
 |    |    |-- Musou: long (nullable = true)
 |    |    |-- Mystery: long (nullable = true)
 |    |    |-- Mystery Dungeon: long (nullable = true)
 |    |    |-- Mythology: long (nullable = true)
 |    |    |-- NSFW: long (nullable = true)
 |    |    |-- Narration: long (nullable = true)
 |    |    |-- Narrative: long (nullable = true)
 |    |    |-- Nature: long (nullable = true)
 |    |    |-- Naval: long (nullable = true)
 |    |    |-- Naval Combat: long (nullable = true)
 |    |    |-- Ninja: long (nullable = true)
 |    |    |-- Noir: long (nullable = true)
 |    |    |-- Nonlinear: long (nullable = true)
 |    |    |-- Nostalgia: long (nullable = true)
 |    |    |-- Nudity: long (nullable = true)
 |    |    |-- Offroad: long (nullable = true)
 |    |    |-- Old School: long (nullable = true)
 |    |    |-- On-Rails Shooter: long (nullable = true)
 |    |    |-- Online Co-Op: long (nullable = true)
 |    |    |-- Open World: long (nullable = true)
 |    |    |-- Open World Survival Craft: long (nullable = true)
 |    |    |-- Otome: long (nullable = true)
 |    |    |-- Outbreak Sim: long (nullable = true)
 |    |    |-- Parkour: long (nullable = true)
 |    |    |-- Parody : long (nullable = true)
 |    |    |-- Party: long (nullable = true)
 |    |    |-- Party Game: long (nullable = true)
 |    |    |-- Party-Based RPG: long (nullable = true)
 |    |    |-- Perma Death: long (nullable = true)
 |    |    |-- Philosophical: long (nullable = true)
 |    |    |-- Photo Editing: long (nullable = true)
 |    |    |-- Physics: long (nullable = true)
 |    |    |-- Pinball: long (nullable = true)
 |    |    |-- Pirates: long (nullable = true)
 |    |    |-- Pixel Graphics: long (nullable = true)
 |    |    |-- Platformer: long (nullable = true)
 |    |    |-- Point & Click: long (nullable = true)
 |    |    |-- Political: long (nullable = true)
 |    |    |-- Political Sim: long (nullable = true)
 |    |    |-- Politics: long (nullable = true)
 |    |    |-- Pool: long (nullable = true)
 |    |    |-- Post-apocalyptic: long (nullable = true)
 |    |    |-- Precision Platformer: long (nullable = true)
 |    |    |-- Procedural Generation: long (nullable = true)
 |    |    |-- Programming: long (nullable = true)
 |    |    |-- Psychedelic: long (nullable = true)
 |    |    |-- Psychological: long (nullable = true)
 |    |    |-- Psychological Horror: long (nullable = true)
 |    |    |-- Puzzle: long (nullable = true)
 |    |    |-- Puzzle-Platformer: long (nullable = true)
 |    |    |-- PvE: long (nullable = true)
 |    |    |-- PvP: long (nullable = true)
 |    |    |-- Quick-Time Events: long (nullable = true)
 |    |    |-- RPG: long (nullable = true)
 |    |    |-- RPGMaker: long (nullable = true)
 |    |    |-- RTS: long (nullable = true)
 |    |    |-- Racing: long (nullable = true)
 |    |    |-- Real Time Tactics: long (nullable = true)
 |    |    |-- Real-Time: long (nullable = true)
 |    |    |-- Real-Time with Pause: long (nullable = true)
 |    |    |-- Realistic: long (nullable = true)
 |    |    |-- Reboot: long (nullable = true)
 |    |    |-- Relaxing: long (nullable = true)
 |    |    |-- Remake: long (nullable = true)
 |    |    |-- Replay Value: long (nullable = true)
 |    |    |-- Resource Management: long (nullable = true)
 |    |    |-- Retro: long (nullable = true)
 |    |    |-- Rhythm: long (nullable = true)
 |    |    |-- Robots: long (nullable = true)
 |    |    |-- Rock Music: long (nullable = true)
 |    |    |-- Rogue-like: long (nullable = true)
 |    |    |-- Rogue-lite: long (nullable = true)
 |    |    |-- Roguelike Deckbuilder: long (nullable = true)
 |    |    |-- Roguevania: long (nullable = true)
 |    |    |-- Romance: long (nullable = true)
 |    |    |-- Rome: long (nullable = true)
 |    |    |-- Rugby: long (nullable = true)
 |    |    |-- Runner: long (nullable = true)
 |    |    |-- Sailing: long (nullable = true)
 |    |    |-- Sandbox: long (nullable = true)
 |    |    |-- Satire: long (nullable = true)
 |    |    |-- Sci-fi: long (nullable = true)
 |    |    |-- Science: long (nullable = true)
 |    |    |-- Score Attack: long (nullable = true)
 |    |    |-- Sequel: long (nullable = true)
 |    |    |-- Sexual Content: long (nullable = true)
 |    |    |-- Shoot 'Em Up: long (nullable = true)
 |    |    |-- Shooter: long (nullable = true)
 |    |    |-- Shop Keeper: long (nullable = true)
 |    |    |-- Short: long (nullable = true)
 |    |    |-- Side Scroller: long (nullable = true)
 |    |    |-- Silent Protagonist: long (nullable = true)
 |    |    |-- Simulation: long (nullable = true)
 |    |    |-- Singleplayer: long (nullable = true)
 |    |    |-- Skateboarding: long (nullable = true)
 |    |    |-- Skating: long (nullable = true)
 |    |    |-- Skiing: long (nullable = true)
 |    |    |-- Sniper: long (nullable = true)
 |    |    |-- Snooker: long (nullable = true)
 |    |    |-- Snow: long (nullable = true)
 |    |    |-- Snowboarding: long (nullable = true)
 |    |    |-- Soccer: long (nullable = true)
 |    |    |-- Social Deduction: long (nullable = true)
 |    |    |-- Software: long (nullable = true)
 |    |    |-- Software Training: long (nullable = true)
 |    |    |-- Sokoban: long (nullable = true)
 |    |    |-- Solitaire: long (nullable = true)
 |    |    |-- Souls-like: long (nullable = true)
 |    |    |-- Soundtrack: long (nullable = true)
 |    |    |-- Space: long (nullable = true)
 |    |    |-- Space Sim: long (nullable = true)
 |    |    |-- Spaceships: long (nullable = true)
 |    |    |-- Spectacle fighter: long (nullable = true)
 |    |    |-- Spelling: long (nullable = true)
 |    |    |-- Split Screen: long (nullable = true)
 |    |    |-- Sports: long (nullable = true)
 |    |    |-- Stealth: long (nullable = true)
 |    |    |-- Steam Machine: long (nullable = true)
 |    |    |-- Steampunk: long (nullable = true)
 |    |    |-- Story Rich: long (nullable = true)
 |    |    |-- Strategy: long (nullable = true)
 |    |    |-- Strategy RPG: long (nullable = true)
 |    |    |-- Stylized: long (nullable = true)
 |    |    |-- Submarine: long (nullable = true)
 |    |    |-- Superhero: long (nullable = true)
 |    |    |-- Supernatural: long (nullable = true)
 |    |    |-- Surreal: long (nullable = true)
 |    |    |-- Survival: long (nullable = true)
 |    |    |-- Survival Horror: long (nullable = true)
 |    |    |-- Swordplay: long (nullable = true)
 |    |    |-- Tabletop: long (nullable = true)
 |    |    |-- Tactical: long (nullable = true)
 |    |    |-- Tactical RPG: long (nullable = true)
 |    |    |-- Tanks: long (nullable = true)
 |    |    |-- Team-Based: long (nullable = true)
 |    |    |-- Tennis: long (nullable = true)
 |    |    |-- Text-Based: long (nullable = true)
 |    |    |-- Third Person: long (nullable = true)
 |    |    |-- Third-Person Shooter: long (nullable = true)
 |    |    |-- Thriller: long (nullable = true)
 |    |    |-- Tile-Matching: long (nullable = true)
 |    |    |-- Time Attack: long (nullable = true)
 |    |    |-- Time Management: long (nullable = true)
 |    |    |-- Time Manipulation: long (nullable = true)
 |    |    |-- Time Travel: long (nullable = true)
 |    |    |-- Top-Down: long (nullable = true)
 |    |    |-- Top-Down Shooter: long (nullable = true)
 |    |    |-- Touch-Friendly: long (nullable = true)
 |    |    |-- Tower Defense: long (nullable = true)
 |    |    |-- TrackIR: long (nullable = true)
 |    |    |-- Trading: long (nullable = true)
 |    |    |-- Trading Card Game: long (nullable = true)
 |    |    |-- Traditional Roguelike: long (nullable = true)
 |    |    |-- Trains: long (nullable = true)
 |    |    |-- Transhumanism: long (nullable = true)
 |    |    |-- Transportation: long (nullable = true)
 |    |    |-- Trivia: long (nullable = true)
 |    |    |-- Turn-Based: long (nullable = true)
 |    |    |-- Turn-Based Combat: long (nullable = true)
 |    |    |-- Turn-Based Strategy: long (nullable = true)
 |    |    |-- Turn-Based Tactics: long (nullable = true)
 |    |    |-- Tutorial: long (nullable = true)
 |    |    |-- Twin Stick Shooter: long (nullable = true)
 |    |    |-- Typing: long (nullable = true)
 |    |    |-- Underground: long (nullable = true)
 |    |    |-- Underwater: long (nullable = true)
 |    |    |-- Unforgiving: long (nullable = true)
 |    |    |-- Utilities: long (nullable = true)
 |    |    |-- VR: long (nullable = true)
 |    |    |-- VR Only: long (nullable = true)
 |    |    |-- Vampire: long (nullable = true)
 |    |    |-- Vehicular Combat: long (nullable = true)
 |    |    |-- Video Production: long (nullable = true)
 |    |    |-- Vikings: long (nullable = true)
 |    |    |-- Villain Protagonist: long (nullable = true)
 |    |    |-- Violent: long (nullable = true)
 |    |    |-- Visual Novel: long (nullable = true)
 |    |    |-- Voice Control: long (nullable = true)
 |    |    |-- Volleyball: long (nullable = true)
 |    |    |-- Voxel: long (nullable = true)
 |    |    |-- Walking Simulator: long (nullable = true)
 |    |    |-- War: long (nullable = true)
 |    |    |-- Wargame: long (nullable = true)
 |    |    |-- Warhammer 40K: long (nullable = true)
 |    |    |-- Web Publishing: long (nullable = true)
 |    |    |-- Well-Written: long (nullable = true)
 |    |    |-- Werewolves: long (nullable = true)
 |    |    |-- Western: long (nullable = true)
 |    |    |-- Wholesome: long (nullable = true)
 |    |    |-- Word Game: long (nullable = true)
 |    |    |-- World War I: long (nullable = true)
 |    |    |-- World War II: long (nullable = true)
 |    |    |-- Wrestling: long (nullable = true)
 |    |    |-- Zombies: long (nullable = true)
 |    |    |-- e-sports: long (nullable = true)
 |    |-- type: string (nullable = true)
 |    |-- website: string (nullable = true)
 |-- id: string (nullable = true)

Out[4]: (55691, 2)
```

* *Part 2*:

Examples of macro analysis results, like the number of games per languages or the number of games released by year.

![games_languages](Graphes_macro/nb_games_per_languages.png) ![games_year](Graphes_macro/released_per_years.png)

* *Part 3*:

Examples of genres analysis, like the most lucrative genre or the number of games by genres.

![genres_lucrative](Graphes_genres/most_lucrative_genre.png) ![games_genre](Graphes_genres/nb_game_per_genre.png)

* *Part 4*:

Example of platform analysis, like the games per platforms.

![game_platform](Graphes_platforms/games_per_platform.png)

## Acknowledgments

* Thanks for Jedha and its instructors for the lectures, exercises and all the work.






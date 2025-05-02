---
layout: project
status: 1
title: Football - Discord Bot
order: 7

type: fa-cogs
typeTitle: Demo

source: fa-male
sourceTitle: Personal Project

tools:
    Neovim: Neovim_logo.svg
    HTML: HTML5Icon.svg
    Chrome: ChromeIcon.svg
    Firefox: FirefoxIcon.svg

lang: icon-rust
langTitle: Rust

description: A new iteration on my football pool website. This time using Discord's API in order to automate the process.
images:
    - /images/projs/DiscordBot_0.png
    - /images/projs/DiscordBot_1.png
    - /images/projs/DiscordBot_2.png
---

Growing up, my family had an interest following the American football league NFL. We would each have a favorite team and tried to predict the teams that would win their match each week.

As time went on, more and more people got included in this circle of predictions after some people at my dad's workplace started to also be interested. We started trying to keep score of who was in the lead and what next surprising results would occur during the season.

I have good memories of this time, but I do remember that a lot of the work going into keeping track of the scores, winners, etc was very manual. Messages between members of the pool were written on a Geocities website edited manually after the messages were communicated to the website admin through email.

In highschool, I wanted to bring the pool back but I was also studying programming. I thought there was surely a way for me to combine my passion of programming and the fun of predicting NFL game winner while also spending less time on manual tasks of organization. This is where multiple passes were made to incrementally make the process better and better.

The most recent of these iteration is controller by a Discord Bot that adds some commands to automate the process of making predictions and reporting scores after a week of activity. Discord was chosen in order to keep the process closely linked to a place where the poolers can also banter with eachother.

The current tech loop I am using looks like this

- Discord bot
    * implemented in Rust
    * using Serenity Discord API crate
- Tiny web app for picks
    * using expressJS
    * let's the poolers have a nice interface to make picks
- SQLite database
    * locally stored on the server running the bot and the web app
    * aware of the scaling issues; not an issue for our small group
    * would need to look into a different solution for a full public release
    * was very helpful for development (local db vs. prod db)

During the 2024-2025 off-season, I just added a new feature where one match throughout the week will be selected as the featured match where poolers will have to also predict a total score over/under. I will keep this page updated if I can think of more interesting features to add for the future seasons.

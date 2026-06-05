# APLvent of Code

[Advent of Code](https://adventofcode.com/) solutions written in [APL](https://en.wikipedia.org/wiki/APL_(programming_language)) (Dyalog).

The main purpose of this repo is to **have fun and learn APL**, not to win leaderboards or write the most optimal code. Expect plenty of comments that read like a learning diary, the occasional brute-force solution, and a steadily shrinking ratio of comments to glyphs as I get more comfortable with the language.

## Why APL?

I found out about APL after watching a [video](https://www.youtube.com/watch?v=uYFRnsMD9ks) by Conor Hoekstra ([codereport](https://github.com/codereport) on GitHub). It was ostensibly about algorithms in C++23, but the most interesting parts were really about APL.

I was immediately intrigued and read up on it. APL had a big influence on R, which I love — although these days I mostly use Pandas, very much a spiritual successor to R. I decided to give it a try, and Advent of Code seemed like a good place to start.

I work in the [Dyalog RIDE](https://github.com/dyalog/ride) IDE and use [Link](https://dyalog.github.io/link/3.0/) to keep the workspace and the source files on disk in sync.

Thanks to Link, every APL function lives in its own file: `.aplf` files are functions and `.aplo` files are operators. A day's directory becomes a namespace (e.g. `day05`), with `Part1` / `Part2` as the entry points and any supporting functions alongside them.

## Usage

```apl
   ⍝ Set up Link for the year you're currently working on
   ]LINK.Create # ./2025

   ⍝ Use the Run function to execute a solution for a specific day.
   ⍝ The data read from ./Data/dayXX.txt is passed as the argument to dayXX.PartY.
   ⍝ Use the left argument to specify which part to run.
   1 Run 5    ⍝ Executes day05.Part1
   Run 5      ⍝ Same as above — left argument defaults to 1
   2 Run 10   ⍝ Executes day10.Part2

   ⍝ While working on a solution, use ReadData to load a given day's input
   data ← ReadData 8

   ⍝ To start working on a new day, either create a dayXX directory (outside the IDE),
   ⍝ or create a new namespace to have the IDE create it for you
   'day11' ⎕NS ''

   ⍝ Create/edit Part1 (or type the name and press Ctrl+Enter):
   )ED day11.Part1
```

`Run` (`Run.aplf`) builds the day name, makes sure the namespace exists, and dispatches to the requested part with that day's input already loaded via `ReadData` (`ReadData.aplf`).

## Useful Resources

- [APLcart](https://aplcart.info/) - A repository of APL idioms
- [APL Wiki](https://www.aplwiki.com/)
   - [APL built-ins](https://aplwiki.com/wiki/Template:APL_built-ins) - This is a template that's embedded at the bottom of many pages, but it's actually a good reference on its own.
   - [Function composition](https://aplwiki.com/wiki/Function_composition) - A useful reference for all your Tacit programming needs.
- [Dyalog ](https://www.youtube.com/@DyalogLtd) YouTube Channel
   - [Train Spotting in Dyalog APL](https://www.youtube.com/live/Enlh5qwwDuY) - Don't know what the fork you're doing? This is the video that made forks and function trains in general click for me.
   - [Inline Tracing in Dyalog](https://www.youtube.com/watch?v=UM-ahvEpLew) - A useful tool for debugging APL and a great way to learn.
- [Dyalog User Meetings](https://www.youtube.com/@DyalogUserMeeting) YouTube channel 
- Conor Hoekstra's [code_report](https://www.youtube.com/@code_report) YouTube channel - Plenty of interesting videos on APL and other array languages.

----

A note on AI usage: I used Claude Code to help write the first version of this README, but everything else is 100% pure, hand-written, artisanal code. I'm here to have fun and learn. Nothing else. 
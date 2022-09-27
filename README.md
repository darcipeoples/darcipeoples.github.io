# Darci Peoples

## Game bots & solvers

### "Operation Gumball" (Mastermind) Bot

I created a Python bot to automatically beat the game Operation Gumball. Operation gumball is a code guessing game (similar to Mastermind and Wordle). The bot makes use of Donald Knuth's five guess minimax Mastermind algorithm[^1], adapted for Operation Gumball. The bot is completely autonomous, needing no human input. It is able to input mouse and keyboard movements and interpret screen output to play an entire 30 level game.

![Operation Gumball game](./data/gumball-game.gif)

[^1]: <a href="https://www.cs.uni.edu/~wallingf/teaching/cs3530/resources/knuth-mastermind.pdf" target="_blank">https://www.cs.uni.edu/~wallingf/teaching/cs3530/resources/knuth-mastermind.pdf</a> 

### Logic Puzzle Solver
I created a Python script that's capable of solving any Puzzle Baron logic puzzle. A logic puzzle provides a set of clues and categories. The player must use logical deduction to determine what entities correspond to what categories. To use the script, the user must transcribe each clue. E.g. "Opal played 1 game before Gail" turns into `[Player.Opal].games = [Player.Gail].games - 1`. And also provide units for any ordinal categories so these strings can be converted to numbers (e.g. "$5 thousand" --> `5000`).

Future plans for the project include adding an online UI for ease of use. And perhaps to automatically transcribe clues into a format the program can understand using heuristics and/or NLP derived from the 30k+ puzzles already scraped from the site.

A second, simpler bot can solve any puzzle up to 4x5 in size given a puzzle URL. It does this by brute force checking of board hashes against the solution hash given in the game html. This solver requires only the URL of the puzzle and no transcription of puzzles clues.

![Logic Puzzle game](./data/logic-game.png)

### Wordle Solver

Using much of the same tactics as the Operation Gumball solver, my Wordle bot can solve World with 100% success rate. It uses a minimax algorithm to optimize for the best outcome (most elimiations) in the worst case (worst response coloring) each turn. It's recommended first word is "ARISE". This work came about before the rise in Wordle bots & optimal algorithms that have since determined "SALET" to be the best first guess via Information Theory.

Future work could include adding a UI instead of command line interface and utilizing Information Theory to reduce the number of average guesses required.

<img src="./data/wordle-game.png" alt="Wordle game" height="500"/>
<img src="./data/wordle-bot.png" alt="Wordle bot" height="500"/>

### "Draw My Thing" (Skribbl.io, Sketchful.io) Solver

I wrote a bot to spit out possible solutions for a given a partial word clue (e.g. "-um-k=n" --> "pumpkin"). Optimizations include progressively narrowing the possible word list (instead of starting from square one as each letter is revealed). This was my very first game bot which I made in high school, and I think it's a great way to get into the hobby.

"Draw My Thing", "Sketchful.io", and "Skribbl.io" are games in which players try to guess what someone is drawing as letters of the prompt are progressively revealed. In the future, this could better assist in Hangman by suggesting the best next guess based on remaining words. Other future work could include making a UI or browser extension.

![Sketchful game](./data/sketchful-game.png)

### "Picnic" (Snake) bot

"Picnic" is a snake-like game wherein you collect food until you run into a wall or your own ever-lengthening trail of ants. My bot complete a hamiltonian cycle of the board in order cover every square and achieve the highest score (on Easy). The bot cannot complete a game "Hard" difficulty because the Python screenshotting and keystroke libraries are unable to keep up with the requisite reaction times.

![Picnic game](./data/picnic-game.gif)

### "Wordtwist" (Ruzzle, Word Hunt, Boggle) solver

Wordtwist is a Puzzle Baron game in which players are given a grid of letters and must create words by chaining adjacent letters. My Python solver takes in the text board and outputs the list of words, ranked in descending order of points. It finds these solutions via depth-first search (DFS) of the board and backtracking when a given partial path has no more possible words.

A second, more cheaty (and arguably, less fun) solver takes advantage of the underlying exposed APIs to simply fetch the list of solution words for a given board.

![Wordtwist game](./data/wordtwist-game.gif)

### "Where's Wacky" (Memory Card Game) bot

"Where's Wacky" is an online memory card game. My Python bot parses the cards on the screen and with perfect memory, clears boards in no time.

![Where's Wacky game](./data/wacky-game.gif)

### "Booger Gets an A" bot

In "Booger Gets an A", the player must click tiles that add to a given sum to eliminate them before the screen fills with tiles. My Python bot automatically parses the board & desired sum and simulates mouse presses to achieve superhuman scores.

![Booger Gets an A game](./data/booger-game.gif)

### "Circuits" (network puzzle) solver

"Circuits" is a Puzzle Baron network puzzle in which you try to connect all lightbulbs to the central battery (without any cycles) by rotating the grid cells. My Python bot takes as input a board configuration and outputs the rotations to perform on each cell. It finds this solution by recursively applying restrictions of each cell's neighbors (e.g. to start, a wire end shouldn't point at an edge) until there is only one possible rotation per cell. During the search we also ensure there will only be one connected component (so all bulbs will touch battery) and that there are no cycles.

![Circuits game](./data/circuits-game.gif)

### "Ringers" solver
I wrote a bot to solve the "Ringers" word puzzle. My first attempt at the program used brute force. Still, I was able to write & run the program in less time than it took to solve 5 such puzzles manually. I've since updated the algoritm to use backtracking and it can now generate and solve a puzzle of any size in sub-second time (up to puzzles with 100 words of length 20).

**Game description:**
> Each of the five Ringers is composed of five rings. Use your imagination to rotate the ring so that you spell four 5-letter words reading from the outside to the insite when all the five rings are aligned correctly.

**Example board:**
<img src="./data/ringers-game.png" alt="Ringers game" height="300" width="300"/>

**Example solution:**
FANCY, LLAMA, DOUBT, BROWN, SALAD

## Woodworking

### Geometric Coaster Set

These coasters are my current favorite woodworking creation, but boy, were they time-consuming to make. I had an idea of what I wanted to make and the folks and the wood working shop were so helpful in making it a reality! I really like the end result and how the different woods catch the light.

These coasters are made of scrapwood; I think redwood, walnut, cherry, and maple. Each is made of 18 isosceles triangles. I cut 0.5 inch strips on the table saw then cut each triangle out with the miter saw. Then I sanded every triangle to ensure accurate angles and a snug fit. I glued sets of 3 traingles together to make a larger equilateral triangles & glued 6 of those together to make each hexagon (after sanding edges again). Each glue-up was held in place with rubber bands and a weight on top to keep it flat. Once glued up, I sanded glue off of the edges with the belt sander and taped them on plywood to send through the drum sander. I then hand sanded and raised the grain. I finished them with a coat of shellac followed by several coats of water-based polyeurathane and also stuck cut cork on the bottoms.

I cannot count how many hours these coasters took to make. But it was a fun time and I'm not against making them again. If I made them again, I'd probably avoid using the miter saw to cut the individual triangles; the pieces kept flying off or burning, even with a sacrificial fence and stop block. I'd like to make a jig to speed up triangle cutting or make it more consistent to avoid edge sanding before glue-ups. Or I could even use the CNC. Another option would be to cut long isosceles triangle prisms (strips), then just glue 18 of those together and slice the coasters off like bread. This would however make _end-grain_ coasters which may not catch the light as nicely. Also, when finishing, I'd use more coats of finish or make sure not to sand off as much between coats. Some coasters already have dents from being dropped, so a thicker finish could help them last longer.

![Geometric coasters](./data/coasters.jpg)

### Infinity Cube

This infinity cube is meant to look like one continuous piece of wood. It's based off of a metal table I had seen online. It makes a good desk trinket & is surprisingly sturdy.

To make the infinity cube, I used scrap walnut wood. I cut it into 0.75" wide strips on the table saw, then 12 2.5" and 6 1.75" lengths on the bandsaw. I sanded each piece up to 220 before glueing them together (using a makeshift glue rig at home; bring out the heavy bottles and coasters for spacers 😆). I finished with a few coats of satin water-based polyeurathane using a foam brush, sanding between coats (likely too much). If I made this again, I might try a layer of shellac before the layer of poly to better bring out the wood. The proportions did turn out nicely.

![Wooden infinity cube](./data/infinity-cube.jpg)

### Scrap Wood Cutting Board

This cutting board was my first finished woodworking creation. It's made out of scrap wood; the middle strip is walnut and the others might be cherry and maple (not sure).

To make it, I trued up the boards, glued them together, planed it down, cut off the rough ends, and used a drill press to start the handle. I shaped the handle with a rasp and did lots of sanding (manual and not) to get it all feeling nice. I did raise the grain & sand once again. To finish it, I used mineral oil, just for a few hours.

This is a face-grain cutting board, so I'm not comfortable cutting on it, but it can be used as a cheese or serving board since it's food safe. I look forward to making an end-grain cutting board in the future.

![Cutting board](./data/cutting-board.jpg)

## Other Programming Projects

### Reddit BDI

Reddit BDI is a webapp to estimate a social media user's depression severity using their post & comment history. The app fetches the user's past comments and posts and feeds these through an ML model to predict responses to the Beck's Depression Inventory[^2] and thus estimate their corresponding depression severity. The model was trained on the data of 90 users provided by the CLEF eRisk 2021 Workshop. The site also provides mental health resources & allows users to submit their true BDI results for potential improvement of the model. The app was created using React, Python, Flask, TensorFlow, pushshift.io, and the Google Cloud Platform.

**Visit the site:** <a href="https://reddit-bdi.uc.r.appspot.com" target="_blank">https://reddit-bdi.uc.r.appspot.com</a>

**Project report:** <a href="./data/reddit-bdi-report.pdf" target="_blank">reddit-bdi-report.pdf</a>

![Reddit BDI](./data/reddit-bdi.png)

[^2]: (Beck, A. T., Steer, R. A., & Brown, G. (1996). _Beck Depression Inventory–II_ [Database record]. APA PsycTests. <a href="https://doi.org/10.1037/t00742-000" target="_blank">https://doi.org/10.1037/t00742-000</a>)

### grok.date

<a href="https://grokdating.web.illinois.edu" target="_blank">grok.date</a> is a dating site intended for "geeks" (gamers, redditors, coders, etc.). It lets users import profile data from other social media (e.g. their subreddits) for easier account setup and transparent interest sharing. The app also has interest-based icebreakers and direct messages. The app was built using React, the Reddit API, Firestore, and cPanel.

**Visit the site:** <a href="https://grokdating.web.illinois.edu" target="_blank">https://grokdating.web.illinois.edu</a>

**About the site (video):** <a href="https://www.youtube.com/watch?v=FZoiCHPYWBE" target="_blank">https://www.youtube.com/watch?v=FZoiCHPYWBE</a>

![grok.date](./data/grok-date.png)

### Bike Sharing data analysis and narrative visualization

In this narrative data visualization, I explore how weather, time of year, and time of day impact London bike share frequency. I also created a multiple linear regression model to predict bike sharing frequency based on these seasonal conditions, providing potentially useful insights for bike & scooter sharing companies and transport authorities.

**Narrative Visualization:** <a href="https://darcipeoples.com/bike-sharing-viz/" target="_blank">https://darcipeoples.com/bike-sharing-viz/</a>

**Data Analysis Report:** <a href="./data/bike-share-report.pdf" target="_blank">bike-share-report.pdf</a>

![Bike Sharing visualization](./data/bike-sharing-viz.png)

### Pixel Art Generator
This program takes as input an image to turn into pixel art and an available color pallete. It can be used for different mediums like Perler/fuse beads or in-game creations (e.g. in a sandbox game like Terraria or Minecraft, by providing the available block palette).

<img src="./data/pixel-art-in.png" alt="Pixel Art Generator input" width="400"/>
<img src="./data/pixel-art-out.png" alt="Pixel Art Generator output" width="400"/>

![Pixel Art Generator output](./data/pixel-art-dist.png)


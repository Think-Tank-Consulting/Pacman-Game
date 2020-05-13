<h1>Artificial Intelligence (Winter 2020)</h1>
<hr></hr>

<h2>Project Assignment 1: Pacman agent</h2>
<hr></hr>

For those of you not familiar with Pacman, it's a game where Pacman (the yellow circle with a mouth in the above figure) moves around in a maze and tries to eat as many food pellets (the small white dots) as possible, while avoiding the ghosts (the other two agents with eyes in the above figure). If Pacman eats all the food in a maze, it wins.

<p align="center"> 
<img src="https://rb.gy/ws1sl6" alt="Animated gif pacman game" style="max-width:50%;">
</p>

<p align="center"> 
<img src="DFS.gif" alt="Animated gif DFS Algorithm" style="width:10px; height:10px;">
</p>

<h2>Overview</h2>
In this project, the Pacman agent will find paths through his maze world, both to reach a particular location and to collect food efficiently. I implemented general search algorithms such as depth-first, breadth-first, uniform cost, and A* search algorithms which are used to solve navigation problems in the Pacman world.

<h2>Project Files Description</h2>
<ul>
  <li><b>search.py</b> - Where all of the search algorithms reside.</li>
  <li><b>searchAgents.py</b> - Where all of the search-based agents reside.</li>
  <li><b>pacman.py</b> - The main file that runs Pacman games. This file also describes a Pacman GameState types.</li>
  <li><b>game.py</b> - The logic behind how the Pacman world works.</li>
  <li><b>util.py</b> - Useful data structures for implementing search algorithms.</li>
</ul>

<h3>Some other supporting files</h3>
<ul>
  <li><b>graphicsDisplay.py</b> - Graphics for Pacman.</li>
  <li><b>graphicsUtils.py</b> - Support for Pacman graphics.</li>
  <li><b>textDisplay.py</b> - ASCII graphics for Pacman.</li>
  <li><b>ghostAgents.py</b> - Agents to control ghosts.</li>
  <li><b>keyboardAgents.py</b> - Keyboard interfaces to control Pacman.</li>
  <li><b>layout.py</b> - Code for reading layout files and storing their contents.</li>
  <li><b>autograder.py</b> - Project autograder.</li>
  <li><b>testParser.py</b> - Parses autograder test and solution files</li>
  <li><b>testClasses.py</b> - General autograding test classes.</li>
  <li><b>test_cases/</b> - Directory containing the test cases for each scenario.</li>
  <li><b>searchTestClasses.py</b> - Project specific autograding test classes.</li>
</ul>

<h2>Introduction</h2>
<p>You are able to start the game by typing the following at the command line:</p>
<pre><code>$ python pacman.py</code></pre>

<p>You can see the list of all options and their default values via:</p>
<pre><code>$ python pacman.py -h</code></pre>
<i>Note that all of the commands that appear in this project also appear in <code>commands.txt</code>, for easy copying and pasting.</i>

<h2>Scenario 1: Finding a Fixed Food Dot using Depth First Search</h2>
I have Implemented the depth-first search (DFS) algorithm in the depthFirstSearch function in <code>search.py</code>.
<p>The Pacman will quickly find a solution via running following commands:</p>
<pre><code>$ python pacman.py -l tinyMaze -p SearchAgent</code></pre>
<pre><code>$ python pacman.py -l mediumMaze -p SearchAgent</code></pre>
<pre><code>$ python pacman.py -l bigMaze -z .5 -p SearchAgent</code></pre>

<h2><a id="user-content-hw1-search" class="anchor" aria-hidden="true" href="#hw1-search"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>HW1 Search</h2>
<ul>
<li>DFS, BFS, UCS, ASTAR, ASTAR heuristic</li>
</ul>
<pre><code>$ python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=dfs
$ python pacman.py -l bigMaze -p SearchAgent -a fn=bfs -z .5
$ python pacman.py -l bigMaze -p SearchAgent -a fn=ucs
$ python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic
</code></pre>
<ul>
<li>Corner problem, Corner heuristic</li>
</ul>
<pre><code>$ python pacman.py -l mediumCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
$ python pacman.py -l mediumCorners -p AStarCornersAgent -z 0.5
</code></pre>
<ul>
<li>Eating all the dots</li>
</ul>
<pre><code>$ python pacman.py -l trickySearch -p AStarFoodSearchAgent
</code></pre>
<blockquote>
<p>for more information, check <a href="https://github.com/jasonwu0731/NTU-AI-Fall2016/blob/master/Pacman/hw1-search/Project1.html">here</a> for details</p>
</blockquote>
<h2><a id="user-content-hw2-multi-agent" class="anchor" aria-hidden="true" href="#hw2-multi-agent"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>HW2 Multi-Agent</h2>
<ul>
<li>ReflexAgent:
A capable reflex agent will have to consider both food locations and ghost locations to perform well.</li>
</ul>
<pre><code>$ python pacman.py --frameTime 0 -p ReflexAgent -k 2
$ python pacman.py -p ReflexAgent -l openClassic -n 10 -q
</code></pre>
<ul>
<li>MinimaxAgent:
Write an adversarial search agent in the provided MinimaxAgent class stub in multiAgents.py</li>
</ul>
<pre><code>$ python pacman.py -p MinimaxAgent -l minimaxClassic -a depth=4
</code></pre>
<ul>
<li>AlphaBetaAgent:
Make a new agent that uses alpha-beta pruning to more efficiently explore the minimax tree.</li>
</ul>
<pre><code>$ python pacman.py -p AlphaBetaAgent -l trappedClassic -a depth=3 -q -n 10
</code></pre>
<ul>
<li>Expectimax:
ExpectimaxAgent is useful for modeling probabilistic behavior of agents who may make suboptimal choices.</li>
</ul>
<pre><code>$ python pacman.py -l smallClassic -p ExpectimaxAgent -a evalFn=better -q -n 30
</code></pre>
<h2><a id="user-content-hw3-reinforcement-learning" class="anchor" aria-hidden="true" href="#hw3-reinforcement-learning"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>HW3 Reinforcement Learning</h2>
<p>In this project, you will implement value iteration and Q-learning. You will test your agents first on Gridworld (from class), then apply them to a simulated robot controller (Crawler) and Pacman.</p>
<pre><code>$ python gridworld.py -m
</code></pre>
<ul>
<li>Value Iteration: an offline planner, not a reinforcement learning agent, and so the relevant training option is the number of iterations of value iteration it should run (option -i) in its initial planning phase.</li>
</ul>
<pre><code>$ python gridworld.py -a value -i 5
</code></pre>
<ul>
<li>Q-Learning: Write a Q-learning agent, which does very little on construction, but instead learns by trial and error from interactions with the environment through its update(state, action, nextState, reward) method.</li>
</ul>
<pre><code>$ python gridworld.py -a q -k 100 
</code></pre>
<ul>
<li>Q-Learning and Pacman</li>
</ul>
<pre><code>$ python pacman.py -p PacmanQAgent -x 2000 -n 2010 -l smallGrid  
</code></pre>
<ul>
<li>Approximate Q-Learning: Implement an approximate Q-learning agent that learns weights for features of states, where many states might share the same features.</li>
</ul>
<pre><code>$ python pacman.py -p ApproximateQAgent -a extractor=SimpleExtractor -x 50 -n 60 -l mediumGrid
</code></pre>
<h2><a id="user-content-hw3-bonus-ghostbusters" class="anchor" aria-hidden="true" href="#hw3-bonus-ghostbusters"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>HW3-Bonus Ghostbusters</h2>
<p>In this project, you will design Pacman agents that use sensors to locate and eat invisible ghosts. You'll advance from locating single, stationary ghosts to hunting packs of multiple moving ghosts with ruthless efficiency.</p>
<pre><code>$ python busters.py -l smallHunt -p GreedyBustersAgent -n 10 --frameTime=0 &nbsp;
</code></pre>
<h2><a id="user-content-credits" class="anchor" aria-hidden="true" href="#credits"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Credits</h2>
<ul>
<li>This is the homework project for the course COMP 6721 - Artificial Intelligence (Winter 2020), at Concordia University</li>
<li>Author: Mohammad Amin Shamshiri</li>
</ul>
</article>


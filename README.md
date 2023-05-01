Download Link: https://assignmentchef.com/product/solved-ch231a-assignment12-shortest-path-algorithm
<br>
Your friend (who has not taken an ”Algorithms and Data Structures” course) asks you for help on implementing an algorithm for finding the shortest path between two nodes <em>u </em>and <em>v </em>in a directed graph (possibly containing negative edge weights). The friend proposes the following algorithm:

<ol>

 <li>Add a large constant to each edge weight such that all weights become positive.</li>

 <li>Run Dijkstra’s algorithm for the shortest path from <em>u </em>to <em>v</em>.</li>

</ol>

Prove or disprove the correctness of the above algorithm to find the shortest path (note that in order to disprove, you only need to give a counterexample).

<h1><strong>Problem 12.2 </strong>Optimal Meeting Point</h1>

You are trying to meet your friend who lives in a different city than you and you want to meet in a city that is between where either of you live. Time is limited and you are trying to minimize the time spent traveling. So, where exactly should you meet?

You are given a graph <em>G </em>with nodes <em>V </em>= {0<em>,…,n </em>−1} that represent the cities and edges <em>E </em>that represent streets connecting the cities directly. The edges are associated with the distance <em>d</em>(<em>e</em>), which is the time needed to travel between two cities. You are given your own city <em>p </em>and your friend’s city <em>q </em>with <em>p,q </em>∈{0<em>,…,n </em>−1}.

Implement an algorithm that finds the target city <em>m </em>in which you and your friend should meet in order to minimize travel time for both of you (you drive towards your meeting city simultaneously, so if you travel for <em>x </em>minutes and your friend travels for <em>y </em>minutes, then you will want to minimize max(<em>x,y</em>)). The graph is given to you with an adjacency matrix, where each entry <em>x<sub>ij </sub></em>represents the time (in minutes) that it takes to travel from city <em>i </em>to city <em>j</em>. Naturally, the indices are the nodes. The algorithm should return the target city <em>m </em>∈{0<em>,…,n </em>−1}. The prototype of the corresponding function should be similar to:

int find_meetup_city(int[][] adj_matrix, int your_city, int friend_city);

<h1><strong>Problem 12.3 </strong>Number Maze</h1>

Consider a puzzle that consists of a <em>n </em>× <em>n </em>grid where each field contains a value <em>x<sub>ij </sub></em>∈ N. Our player starts in the top left corner of the grid. The goal of the game is to reach the bottom right corner with the player.

<em>Rules of the game</em>: On each turn, you may move your player up, down, left or right. The distance by which the player moves in a chosen direction is given by the number of its current cell. You must stay within the board (you cannot go off the edge of the board).

<em>Example</em>: If your player is on a square with value 3, then you may move either three steps up, down, left or right (as long as you do not leave the board).

<ul>

 <li>(2 points) Represent the problem as a graph problem. Formalize it by determining what is represented as the nodes and as the edges.</li>

 <li>(4 points) Implement the class PuzzleBoard similar to class declaration shown below.</li>

 <li><strong>Bonus </strong>(4 points) Implement an algorithm that returns the minimum number of moves required to solve this problem. If there is no solution, your algorithm should determine this fact.</li>

</ul>

class PuzzleBoard { private:

// your choice public:

// Subpoint (b)

PuzzleBoard(int boardSize, int[][] fields = null);

/<sup>∗ </sup>constructor should create the graph (as you defined it in subpoint (a) with the values from fields. If fields is null, then initialize the fields of the board with random values between 1 and boardSize-1. <sup>∗</sup>/ bool makeMove(int direction);

/<sup>∗ </sup>makes the move (if valid), direction is 0 for up, 1 for right, 2 for down, 3 for left. Returns true if the move was valid, false otherwise. <sup>∗</sup>/ bool getResult();

/<sup>∗ </sup>Returns false if game is not over yet, true if puzzle was solved <sup>∗</sup>/ std::ostream &amp;operator&lt;&lt;(std::ostream &amp;os, PuzzleBoard const &amp;m);

/<sup>∗ </sup>in Python, this is the __str__ method. <sup>∗</sup>/

// Subpoint (c) int solve();

/<sup>∗ </sup>returns the minimum number of moves needed to solve the puzzle, and -1 if it is not solvable. <sup>∗</sup>/

}
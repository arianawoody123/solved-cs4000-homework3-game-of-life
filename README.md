Download Link: https://assignmentchef.com/product/solved-cs4000-homework3-game-of-life
<br>
In the 1970’s, John Conway developed a game with very simple rules that produces amazingly complex patterns — The Game of Life. Conway’s original Game of Life is played on a 2dimensional grid of cells. The game starts with some of the cells being “alive” and the remaining cells being “dead.” The game is played in rounds, where each round depends on the values of the cells in the previous round.

In each successive round, the value of a cell is determined by the values of its 8 neighboring cells from the previous round. If four or more of a cell’s neighbors are alive, then that cell dies because of overpopulation. If zero or one of the cell’s neighbors are alive, then that cell dies of loneliness. If two or three of a cell’s neighbors are alive, then that cell survives (if it was alive previously). Finally, a cell is born if exactly 3 of its neighbors are alive. These are the only rules in the Game of Life.

Conway’s rules can produce strangely intricate patterns. For example, consider the action of three living cells in a row. This pattern will “blink” forever if left alone.

<table width="576">

 <tbody>

  <tr>

   <td width="150">


    <table width="144">

     <tbody>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

     </tbody>

    </table></td>

   <td width="58"></td>

   <td width="158">


    <table width="144">

     <tbody>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

     </tbody>

    </table></td>

   <td width="58"></td>

   <td width="152">


    <table width="144">

     <tbody>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

      <tr>

       <td width="48"></td>

       <td width="48"></td>

       <td width="48"></td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

Figure 1: A blinker

<h1>Project</h1>

In Conway’s game of life, the 2 dimensional world is infinite. For this project, we will simulate Conway’s Game of Life over a finite 2 dimensional grid. Our grids will be finite and square

(<em>n </em>× <em>n</em>). So, in this case, the 8 neighbors of any grid cell (<em>i,j</em>) will be

<ol>

 <li>(<em>i </em>+ 1( mod )<em>n,j</em>)</li>

 <li>(<em>i </em>− 1) mod <em>n,j</em>)</li>

 <li>(<em>i </em>− 1) mod <em>n,j </em>+ 1 mod <em>n</em>)</li>

</ol>

1

<ol start="4">

 <li>(<em>i </em>− 1) mod <em>n,j </em>− 1 mod <em>n</em>)</li>

 <li>(<em>i </em>+ 1) mod <em>n,j </em>+ 1 mod <em>n</em>)</li>

 <li>(<em>i </em>+ 1) mod <em>n,j </em>− 1 mod <em>n</em>)</li>

 <li>(<em>i,j </em>+ 1 mod <em>n</em>)</li>

 <li>(<em>i,j </em>− 1 mod <em>n</em>)</li>

</ol>

For positive values, the meaning of x mod y is clear. For negative values (e.g., -1), the value that you want to compute is not a%b, but (b-a)%b. So, for example, -1 % 10 = (10-1)% 10 = 9. In general, (n+i+/-1) mod n will give you the value you desire.

For your project, you will create a class GameOfLife with at least one public member function

vector&lt;vector&lt;int&gt; &gt; SimulateLife(vector&lt;vector&lt;int&gt; &gt; &amp;board, int life_cycles)

that returns the 2 dimensional grid (1== alive, 0 = dead) after life_cycles generations.

The original “board” will have some cells (with a value 2) that are eternal, i.e., they live forever. This slight modification to Conway’s game makes this version a bit more interesting.

<h1>Sequential Version</h1>

Implement the class GameOfLife without parallelism. Your code should run reasonably fast. For example, my code on a 100 × 100 grid, using 1000 iterations (original.dat, 1000_iters.dat) took 1.2 seconds.

<h1>Parallel Version Using C++ Threads</h1>

Implement a second version of GameOfLife that uses threads in C++ to achieve a faster solution. Your solution should be at least 75% efficient on a 4 core machine. Make your code as clean as possible (consider using the future class, etc.). Also, this version may require process synchronization. (See lecture #10.)
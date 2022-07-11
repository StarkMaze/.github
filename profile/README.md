<h1 align="center">StarkMaze💫</h1
<h4 align="center">Built with ❤️ during the <a href="https://matchboxdao.com/">MatchboxDAO</a> Hackathon (3nd-10th July 2022)</h2>
<br>
<br>

## Description

StarkMaze is a mini recurring maze game build on <a href="https://starknet.io/">StarkNet</a> ! everyday a new labyrinth will be generated. Player have to solve the daily maze as quickly as possible. at the end of his game, an nft corresponding to the path he has traveled will be generated. The player can share his score directly on twitter.

## Installation

We have 3 repository: <br>
`starkmaze-contracts`             -> Repo of our differents Smart Contract <br> 
`starkmaze-frontend`              -> Repo of our final site w/maze generation on-chain <br>
`starkmaze-frontend-Gen-onChain`  -> Repo of a test with off-chain generation of the maze <br>




## On-chain game computation

We decided to build a fully on-chain game. It mean that our maze generation algorithm will be coding and executing on-chain. 
First of all, we'll use depth first search to generate a perfect maze. A perfect maze is a maze with only one path between any two cells. Since there is only one path between any two points you can represent a perfect maze as a tree. Then use both depth first search and breadth first search to solve the maze. 

## 1- Maze generation

Depth First Search (DFS) :

Depth-first search (DFS) is an algorithm for traversing or searching tree or graph data structures. The base of the algo is to starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.


Our DFS Algorithm in pseudocode :

1) Start at a random cell. (For now we decided to start all the time at top left)
2) Mark the current cell as visited, and get a list of its neighbors.
3) For each neighbor, starting with a randomly selected neighbor
4) If that neighbor hasn't been visited, remove the wall between this cell and that neighbor, and then recurse with that neighbor as the current cell.

Functions already implemented :

| Functions                     | Objectives |
| ----------------------------- | ------------- |
| ```generate_maze()```         | Generate maze. | 
| ```_cell_neighbors()```       | Return the only neighbors that don't have downed walls. | 
| ```_walls_bitwise_and()```    | Check that the neighbor doesn't have any walls knocked down. |
| ```_cell_in_bounds()```       | Check that the current cell is already inside the maze. |

## 2- Maze solving
COMING SOON

## 3- Movements

For movements, we have in our smart contract defined 4 functions (move_up, move_down, move_left, move_right) that we call each time a user performs a movement. The next step is to group each movement and use the multicall in order to have the transactions grouped

## 4- Recurring game

For the management of the recurring generation of the maze, we have decided to use the <a href="https://docs.yagi.fi/">Yagi Finance</a> solution which will allow us to automate the generation of the maze every day
We have started the implementation but we are waiting for the return of their team in order to be able to automate everything with them.

## 5- Next step

We will continue this project and go to the end, we have discussed a lot with many people who gave us valuable advice for the rest of the project.

Next features: <br>
 Finish on-chain generation of maze <br>
 Implement NFT with good path
 Add on-chain stopwatch
 Multicall function with all move
 Change UI
 

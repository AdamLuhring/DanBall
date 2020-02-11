DanBall is a game played on a graph with a given number of nodes randomly connected. You play by providing a function which takes the graph's state as its input and returns a move as its output.

The game's state is provided to your function as an object with the following properties:
-numberOfNodes: An integer representing the number of nodes in the graph
-areNodesConnected[a][b]: A two-dimensional array with boolean values for whether two nodes are connected (whether a player can move from one to the other)
-isNodeRuledOut[a]: A one-dimensional array with boolean values for whether a node is ruled out for future travel
-whereArePlayers[a]: A one-dimensional array with the node each player is currently on
-whoseTurnIsIt: An integer representing which player's turn it is

Responses are given as an object literal with one or two properties:
-ruleOutOrMove (required): A string with either "ruleOut" (to rule out the node the player is on from future travel) or "move" (to move to a connected node)
-moveTo (use if ruleOutOrMove is set to "move"): Integer representing the node to move to

The game continues until a player loses by providing a move which:
-Is not properly formatted
-Attempts to move to a node the player cannot reach from their current location
-Attempts to move to a ruled-out node
-Attempts to rule out an already ruled-out node

Project roadmap:
+Draw game state each step
+Process responses
 -Check that response object was provided
 +Check for formatting
  +Inclusion of correct properties
  +Check that ruleOurOrMove is a string
  -Check that moveTo is an integer
 +Rules processing
  +Can only rule out non-ruled-out nodes
  +Can only move to connected nodes
  +Cannot rule out already ruled-out node
  +Cannot move to where other player is
  +Cannot move to current node
 -Ensure # of moves does not exceed 100 (declare tie)
+Tournament
 +Set up new round after each game
  +Two players
  -Pick from more than two strategies
 +Tabulate results
  +Two players' scores displayed
  -Table of how more than two strategies did against each other
-UI
 -Controls to set number of matches to play through
 -Controls to adjust speed of play
 -Controls to pause/resume play
 -Controls to step through game's history
  -Capture history
  -Add controls
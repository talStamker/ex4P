In this task we will convert the task in JAVA to PYTHON and therefore we will use 3 main classes A class of a graph A class of its algorithm and a class of node
We will detail each of them:
Node: 
Params: 
•	str pos
•	float x
•	float y
•	float z
•	float d
•	Node dadi
•	Int id
Explanation:
Pos is what we ger from json file, x, y, z are the geolocation, d, dadi are the params of Dijkstra's Algorithm it will help us to apply it.
Function:
•	Get and set for all the params
•	Copy for graph and graph algo constructors
•	Equal for the test of DiGraph
DiGraph:
Params:
Dictionary v
Dictionary outE
Dictionary inE
Int sizeOfE
Int numberOfChanges
Explanation:
We will build a DICTINARY of V so that we can return it in the get_all_v function.Built DICTIONARY of DICTIONARY for both outgoing and incoming functions we will save the size of the sides and the number of changes so we can give them in the appropriate functions
Function:
v_size-we will return v size
e_size- we will return the param sizeOfE
get_all_v- we will return v
all_out_edges_of_node- we will use outE and return the dictionary in place id1
all_in_edges_of_node-we will use inE and return the dictinary in place id1
get_mc- we will return numberOfChanges
add_edge-we will check if v has key like id1 or id2 f and if id2 is in the dictionary in outE in place id1 first. Then we will add to outE and inE and add 1 to numberOfChange and sizeOfE
add_node-we eill check if v has a key like id if not we will add it to node and open dictionary in outE and inE respectively and add 1 to number of change
remove_node- we will use outE and inE to remove the relevant and update sizeOfE and numberOfChanges
remove_edge-we will check if v has the key of id1 and id2 and if out E has a edge like we get and if not we will remove the edge from outE and inE
str- we will return string like json file for save file and for main
GraphAlgo:
Params:
DiGraph graph
Dictionary v
FWA fwa
Explanation:
Graph- The graph on which the algorithms are performed, fwa we will explain it in center function, v is graph.v
Function:
load_from_json- we will call to json.load and add all the information to our graph
save_to_json-we will cal self.graph.__str__and turn it to dictionary and call to dumps 
shortest_path- we will use Dijkstra's Algorithm: Dijkstra(G,s) for each v  V d[v] = ; (v)=NULL; d[s] = 0; Q = V; while (Q  ) u = ExtractMin(Q); for each e leaving u relax(e).And build relax function which update d and dadi if u.d+w<v.d
TSP- we will use 2 function nearestN and isDone. NearestN will check the nearest neighbor,isDone will check if we pass all the node. And we will start from all the node to try to arive all the node and chose the fast one.
centerPoint- we call for function in FWA
FWA:
Params:
DiGraph gra
List keys
Dictionary v
List mat
List rowNxt
Explanation:
Gra- for using it in algorithms, keys-graph.v keys, v- graph.v,mat rowNxt -for using belmanFord's .
We will use belmanFord's algorithm to find the center we eill pass all the result and choose the smallest weight
plot_graph- we will use matplotlib first of all we will find the min point and max point of the graph ten we will update all the node which doesn’t have pos to be closer to min or max and then we will update min and max and for all node we will use the function scatter and text and for all edge we will use arrow function
test:
test of graph:
function:
test__size_-we will add and remove nodes then we wil check if the nodes were add and remove
test__node-
we will add node then check if it has been added and we will add node that already exist. 
Test_Edge- We will remove some node and we will check if the node has been removed .we will remove edge that doesn’t exist or it's node doesn’t exist.
test__mc__getAllV- we will add some nodes then check if the nodes is in v. then we will remove some nodes add ande remove edges and check if the numberOfChanges is correct
test__outE__inE
we will add some nodes and edges and check if outE and inE are up to date.
test_shortPath
we will build one short path and one long path and will check that we get the short
test_center
we will build graph which has a lot of path and check if we get the correct node with correct distance 
test_TSP
we will build graph which has a lot of path and check if we get the correct node with correct distance and will check if we get the shortest path that visit all the nodes we sent and his distance.
test_save_load
we will build graph save it to file and take another graph which has no nodes and load from fail and will check if the graphs are even
test_plot
we will load from A1 to our graph and will call to plot__graph() and will see if we get the correct graph.

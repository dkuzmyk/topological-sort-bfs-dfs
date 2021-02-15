# topological-sort-bfs-dfs
class:  graph  *  * 
desc:   class for representing directed graphs.  
Uses the adjacency list representation.  
*  * key concepts:  *  *
- Each vertex is identified by a string AND by an integer ID:  
  o strings are convenient for the outside world -- we can give vertices meaningful real-world names like Chicago and Peoria 
  o On the other hand, refering to vertices with simple integer IDs 0..|V|-1 is convenient and efficient for algorithm implementation of many algorithms. 
ref:  see the read_file function (which reads edges as string pairs).  *  *   
- mapping between vertex names and vertex-IDs: the graph class has a data member called _name2id which is an unordered map from strings (vertex names) to integers (corresponding   vertex ID). 
- Key data structures and types: 
  vertices:  The graph class also contains a data member called vertices. It is the core of the adjacency list representation and is where most of the action is!  
  It is a vector of type vertex. It is indexed by vertex ID. 
  vertex struct:  within a vertex struct there are four data members which capture what we need to know about a vertex:  
      id:  integer id associated with vertex (not used very often...)  
      incoming:  a vector of incoming edges (edges for which this vertex is the destination vertex).  The edge struct is the element type of the vector (see below).                     outgoing:  a vector of outgoing edges (edges for which this vertex is the source vertex).
      name:  the string name associated with the vertex.  This lets us map from vertex ID to vertex name. edge struct: this struct captures what we need to know about an edge in    the context of an adjacency list representation.  There are two data members: vertex_id: this is the id of the "other" vertex.  If an edge struct is part of a vector of           outgoing edges, then vertex_id refers to the DESTINATION vertex of the edge; if it is part of a vector of incoming edges, then  *                 vertex_id refers to the           SOURCE vertex of the edge. weight:  this is a floating point number giving the weight of the edge.  It defaults to 1.0 and is not relevant for all operations you might want       to perform on a graph.

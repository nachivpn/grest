# grest
grest provides an REPL interface to run gremlin queries on a neo4j server via the the [neo4j-gremlin plugin](https://github.com/thinkaurelius/neo4j-gremlin-plugin/).  

## Installation

### Requirements: 

* Ruby [2.0]

* rlwrap package [0.42] - Can be installed using yum, brew or from [here](https://github.com/hanslub42/rlwrap)

* python [2.7.6] 

* Neo4j [gremlin plugin](https://github.com/thinkaurelius/neo4j-gremlin-plugin) installed and running on the Neo4j instance

### Instructions:

* Download [Zip](https://github.com/nachivpn/grest/archive/master.zip)

* Unzip the contents

* Navigate to the directory
    ``` cd grest/ ```
* Ensure grest has executable permissions
    ```chmod +x grest```

* Create a symbolic link on the symbolic link
    ``` ln -s $PWD/grest /usr/bin/grest ``` 

    
##Usage

```
 Nachi@MBP:workspace $ grest 127.0.0.1:7474     //ip:port of neo4j instance
 
 gremlin [127.0.0.1:7474]> g.loadGraphML("https://raw.githubusercontent.com/tinkerpop/gremlin/2.5.0/data/graph-example-2.xml")
 {
    "success": true
 }

 gremlin [127.0.0.1:7474]> g.V().has("name","MONA").outE
 {
    "results": [
        {
            "_id": 33491,
            "_inV": 4851,
            "_label": "followed_by",
            "_outV": 4841,
            "_type": "edge",
            "weight": 1
        },
        {
            "_id": 33490,
            "_inV": 4968,
            "_label": "followed_by",
            "_outV": 4841,
            "_type": "edge",
            "weight": 1
        },
        {
            "_id": 33493,
            "_inV": 4842,
            "_label": "written_by",
            "_outV": 4841,
            "_type": "edge"
        },
        {
            "_id": 33492,
            "_inV": 4885,
            "_label": "sung_by",
            "_outV": 4841,
            "_type": "edge"
        }
    ],
    "success": true
}
 
 
```

##REPL

The REPL utility has been forked from [REPL by Defunkt](https://github.com/defunkt/repl)

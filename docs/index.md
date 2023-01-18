# Ocean End-To-End (E2E)
The following list briefly explains the steps which the agent takes:

- Once this agent is run, it starts off by deploying a new pool. 
- After deploying the pool it goes on to deploy an algorithm
- Makes the dataset available for Compute-To-Data (C2D)
- Submits a C2D job
- Download the job results 

[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggVERcbiAgIEFbU3RhcnQgQWdlbnRdIC0tPiBCW0RlcGxveSBQb29sXVxuICAgQiAtLT4gQ1tEZXBsb3kgQWxnb3JpdGhtXSBcbiAgIEMgLS0-IERbTWFrZSBEYXRhc2V0IEF2YWlsYWJsZSBmb3IgQzJEXVxuICAgRCAtLT4gRVtTdWJtaXQgQzJEIEpvYl1cbiAgIEUgLS0-IEZbRG93bmxvYWQgUmVzdWx0c10iLCJtZXJtYWlkIjp7InRoZW1lIjoiZGVmYXVsdCJ9LCJ1cGRhdGVFZGl0b3IiOmZhbHNlLCJhdXRvU3luYyI6dHJ1ZSwidXBkYXRlRGlhZ3JhbSI6ZmFsc2V9)](https://mermaid-js.github.io/mermaid-live-editor/edit/#eyJjb2RlIjoiZ3JhcGggVERcbiAgIEFbU3RhcnQgQWdlbnRdIC0tPiBCW0RlcGxveSBQb29sXVxuICAgQiAtLT4gQ1tEZXBsb3kgQWxnb3JpdGhtXSBcbiAgIEMgLS0-IERbTWFrZSBEYXRhc2V0IEF2YWlsYWJsZSBmb3IgQzJEXVxuICAgRCAtLT4gRVtTdWJtaXQgQzJEIEpvYl1cbiAgIEUgLS0-IEZbRG93bmxvYWQgUmVzdWx0c10iLCJtZXJtYWlkIjoie1xuICBcInRoZW1lXCI6IFwiZGVmYXVsdFwiXG59IiwidXBkYXRlRWRpdG9yIjpmYWxzZSwiYXV0b1N5bmMiOnRydWUsInVwZGF0ZURpYWdyYW0iOmZhbHNlfQ)

### `eightballer/ocean:0.1.0` Skill

The behaviours of this skill is what dictate the whole flow which the agent goes through.
There are 3 classes that define the behaviours of this skill `OceanC2DBehaviour`, `OceanDataAccessBehaviour` and `OceanDemoBehaviour`.
5 states are available for the agent to go through are already mentioned above. It's worth noting that the agent is can only be on one of those states at once.
The states are split into two classes `OceanC2DBehaviour` and `OceanDataAccessBehaviour`. 
`OceanC2DBehaviour` handles the first 4 states, whereas `OceanDataAccessBehaviour` handles the last one.
`OceanDemoBehaviour` is responsible for handling the switch between the two above-mentioned classes.

### `eightballer/ocean:0.1.0` Connection
This connection acts as a translation layer between the agent and the Ocean network. 
The main task of this connection is to act as a wrapper for the `ocean_lib` library, that is responsible for the actual communication with the ocean network.


### `eightballer/ocean:0.1.0` Protocol
This protocol is in place to allow for communication between the different components of the agent, in this case between the above mentioned connection and skill.


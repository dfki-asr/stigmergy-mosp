# Stigmergy-based Minimize Number of Open Stacks example

This is a Linked-Data based solver for the Minimize Number of Open Stacks Problem.
The repository consists of the following contents:

 1. *model* : Example instances of the problem of varying complexity
 2. *queries* : Queries that encode agent behavior of increasing complexity
 3. *postman* : Postman collection of ready-to-use queries

## Usage:

The Postman collection is designed to be executed against a triple store instance that is running on localhost, port 3030 . The queries assume the *model* data to be hosted by a dataset "mosp", with the triple store offering a SPARQL API endpoint at http://localhost:3030/mosp/ .

Import the Postman collection under */postman/* .
Make sure that a triple store with a dataset "mosp" is available under the given route (or adapt routes in the Postman queries accordingly).

Initialize the demo via (Routes referring to routes in Postman collection):
1. Initialization / Reset with X classes : erases all data in the mosp dataset on the remote and, and inserts X classes of products as RDF classes
2. Initialization / Insert X Y : Inserts Y fixed orders over a set of X product classes

Execute the demo by repeating the following steps (Routes referring to routes in Postman collection):
1. /\<agentModel\>/MoveAgentToOrder : Sets agent to the next order according to preference (random walk, by number of markers, by intensity of marker, depending on model)
2. /\<agentModel\>/Produce : Produces a product of the current order
3. /\<agentModel\>/Close Orders: Counts number of stacks currently open, and closes finished orders.

The effect of the different action can be inspected directly on the dataset after every step.
 

# Acknowledgements

This work has been supported by the German Federal Ministry for Education and Research(BMBF) as part of the MOSAIK project (grant no. 01IS18070-C)

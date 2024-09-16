# Network-measur

## Network Efficiency and Transformation

Assume that `{𝑙𝑖𝑗}` is the transformed weighted matrix and `{𝑑𝑖𝑗}` is the shortest path matrix.

### Efficiency Calculation

The efficiency \( E(G) \) of a graph \( G \) is defined as:

\[ E(G) = \frac{\sum_{i \neq j} \frac{1}{𝑑𝑖𝑗}}{𝑁(𝑁 - 1)} \]

where \( 𝑑𝑖𝑗 \) is the shortest path distance between nodes \( i \) and \( j \), and \( N \) is the number of nodes in the graph.

Since \( E(G) \) ranges from 0 to infinity, we define the ideal network where the shortest path distance is equal to the weight between nodes (i.e., the network is fully connected). The ideal efficiency \( E(G_{ideal}) \) is given by:

\[ E(G_{ideal}) = \frac{\sum_{i \neq j} \frac{1}{𝑙𝑖𝑗}}{𝑁(𝑁 - 1)} \]

The normalized value of efficiency is obtained by:

\[ \text{Normalized Efficiency} = \frac{E(G)}{E(G_{ideal})} \]

This normalized value varies from 0 to 1. If the normalized value of efficiency exceeds 1, it indicates that one of the constraints is not satisfied.

### Constraints and Transformation

We initially assumed:

\[ 𝑑𝑖𝑗 \geq 𝑙𝑖𝑗 \quad \text{and} \quad \frac{1}{𝑙𝑖𝑗} \geq \frac{1}{𝑑𝑖𝑗} \]

However, this implies:

\[ \frac{1}{𝑑𝑖𝑗} \geq \frac{1}{𝑙𝑖𝑗} \]

which means the triangle inequality is not satisfied.

To address this, I transformed all weights based on the maximum value in the initial adjacency matrix `{𝑤𝑖𝑗}`.

#### Transformation

Transformation: 

\[ t = \max({𝑤𝑖𝑗}) + 1 \]
\[ {𝑙𝑖𝑗} = t - {𝑤𝑖𝑗} \]

For three nodes \( i \), \( j \), and \( k \) forming a triangle, we expect:

\[ {𝑙𝑖𝑗} \leq {𝑙𝑗𝑘} + {𝑙𝑖𝑘} \]

Substituting the transformation:

\[ t - 𝑤𝑖𝑗 \leq t - 𝑤𝑗𝑘 + t - 𝑤𝑖𝑘 \]

Thus, the value of \( t \) must satisfy:

\[ 𝑤𝑗𝑘 + 𝑤𝑖𝑘 - 𝑤𝑖𝑗 \leq t \]

We know that:

\[ 𝑤𝑗𝑘 + 𝑤𝑖𝑘 - 𝑤𝑖𝑗 \leq 2 \times \max({𝑤}) - \min({𝑤}) \]

Therefore, the transformation should be within the range:

\[ 2 \times \max({𝑤}) - \min({𝑤}) \leq t \]

The initial transformation does not satisfy this constraint.

# Algorithm Workflow Diagram

This `README.md` explains the architecture represented in the flowchart. The architecture is designed to demonstrate the step-by-step workflow of a pathfinding algorithm, such as **A* (A-star)**. Below are the detailed steps:

---

## **Workflow Steps**

### 1. Initialization
- **Start Node**: 
  - The algorithm begins with a specified start node.
  - This node is added to the **Priority Queue** for processing.
  
- **Initialize g_score and f_score**:
  - `g_score`: Represents the cost from the start node to the current node.
  - `f_score`: Estimated total cost (`g_score` + heuristic).
  - These scores are initialized for all nodes:
    - Start node: `g_score = 0`, `f_score = heuristic(start)`.
    - Other nodes: `g_score = ∞`, `f_score = ∞`.

---

### 2. Main Loop
- **Dequeue Node**:
  - The node with the **lowest f_score** is dequeued from the Priority Queue and set as the *Current Node*.

- **Check Goal**:
  - If the current node is the **Goal Node**, the algorithm terminates successfully:
    - The path is constructed.
    - A success message is returned.

- **Expand Neighbors**:
  - If the current node is not the goal, the algorithm explores its **neighbors** (adjacent nodes).

---

### 3. Neighbor Processing
For each neighbor of the **Current Node**:
1. **Calculate g_score and f_score**:
   - Compute:
     - `g_score`: Tentative cost from the start node to the neighbor.
     - `f_score`: `g_score + heuristic(neighbor)`.

2. **Update Priority Queue**:
   - If the new `f_score` is lower than the previously recorded `f_score` for the neighbor:
     - Update the neighbor's scores.
     - Add or update the neighbor in the **Priority Queue**.

3. **Push Neighbor to Queue**:
   - Push the neighbor into the queue for further exploration.

---

### 4. Post-Processing
- **Mark Node as Visited**:
  - After processing all neighbors, mark the current node as visited.

- **Queue Empty**:
  - If the Priority Queue becomes empty and the goal has not been found:
    - The algorithm terminates with a failure.

---

### 5. Visualization
- **No Path Found**:
  - If no path is found, display a failure message.

- **Visualize Path**:
  - If a path is found:
    - Construct and visualize the path on the grid.

- **Update Grid UI**:
  - Update the user interface with the final path or grid status.

---

## **Diagram Overview**
Below is the diagram representing the architecture of the algorithm.

*(Insert Diagram Here)*

---

## **Technologies Used**
- **Algorithm**: A* (A-star) or similar heuristic-based pathfinding algorithm.
- **Data Structures**: 
  - Priority Queue for node selection.
  - Graph representation for nodes and edges.
- **Visualization**: Updates to the grid UI for user feedback.

---

## **How to Use**
1. Clone the repository and set up the project.
2. Refer to the implementation files:
   - Algorithm logic is in `pathfinding_algorithm.py`.
   - Visualization logic is in `visualizer.py`.
3. Run the application:
   ```bash
   python main.py

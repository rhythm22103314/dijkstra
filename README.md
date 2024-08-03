# dijkstra
Sure! Let’s break down and document the functionality of each function in your code for the Dijkstra's Algorithm simulation using OpenGL and GLUT.

### Main Functions and their Roles

1. **`int computeDistance(struct node a, struct node b)`**
   - **Purpose**: Computes the Euclidean distance between two nodes `a` and `b`.
   - **Parameters**: 
     - `struct node a`: The first node.
     - `struct node b`: The second node.
   - **Returns**: Integer value representing the distance between nodes.

2. **`int noRepeat(int x, int y)`**
   - **Purpose**: Checks if a click at coordinates `(x, y)` is within the radius of an existing node. If so, it selects the node; otherwise, it creates a new node.
   - **Parameters**:
     - `int x`: X-coordinate of the click.
     - `int y`: Y-coordinate of the click.
   - **Returns**: `1` if a new node should be created, `0` otherwise.

3. **`void getPerpendicularCoordinates(int *x, int *y)`**
   - **Purpose**: Calculates perpendicular coordinates from the midpoint of a line segment to place the text (distance) label.
   - **Parameters**:
     - `int *x`: Pointer to X-coordinate of the midpoint.
     - `int *y`: Pointer to Y-coordinate of the midpoint.

4. **`void writeDistance(char *text, int x, int y)`**
   - **Purpose**: Writes the distance between nodes at specified coordinates.
   - **Parameters**:
     - `char *text`: The text to be displayed.
     - `int x`: X-coordinate for the text.
     - `int y`: Y-coordinate for the text.

5. **`void writeLabel(char text, int x, int y)`**
   - **Purpose**: Writes a single character label on a node at specified coordinates.
   - **Parameters**:
     - `char text`: The label to display.
     - `int x`: X-coordinate for the label.
     - `int y`: Y-coordinate for the label.

6. **`void drawCircle(float cx, float cy, float r, float num_segments, char colorCharacter)`**
   - **Purpose**: Draws a circle with a given radius and color at coordinates `(cx, cy)`.
   - **Parameters**:
     - `float cx`: X-coordinate of the circle's center.
     - `float cy`: Y-coordinate of the circle's center.
     - `float r`: Radius of the circle.
     - `float num_segments`: Number of segments (lines) to approximate the circle.
     - `char colorCharacter`: Determines the color of the circle and if it should have a label.

7. **`void drawSquare(int x, int y)`**
   - **Purpose**: Draws a square at coordinates `(x, y)`. The function is defined but not used in the code.

8. **`void getMidPoint(int *midX, int *midY)`**
   - **Purpose**: Computes the midpoint of a line segment connecting two nodes.
   - **Parameters**:
     - `int *midX`: Pointer to the midpoint's X-coordinate.
     - `int *midY`: Pointer to the midpoint's Y-coordinate.

9. **`void drawLine(char color)`**
   - **Purpose**: Draws a line between two selected nodes and labels the distance between them.
   - **Parameters**:
     - `char color`: Determines the color of the line (e.g., 'N' for normal, 'R' for red, 'D' for default).

10. **`void myMouse(int btn, int state, int x, int y)`**
    - **Purpose**: Handles mouse input for creating nodes, drawing lines, and selecting source/destination nodes.
    - **Parameters**:
      - `int btn`: Mouse button used.
      - `int state`: Mouse button state (down or up).
      - `int x`: X-coordinate of the mouse click.
      - `int y`: Y-coordinate of the mouse click.

11. **`void myReshape(GLsizei w, GLsizei h)`**
    - **Purpose**: Adjusts the viewport and projection matrix when the window size changes.
    - **Parameters**:
      - `GLsizei w`: New window width.
      - `GLsizei h`: New window height.

12. **`void myInit()`**
    - **Purpose**: Initializes OpenGL settings including viewport, projection, and clear color.

13. **`void display_hello()`**
    - **Purpose**: Displays instructions for the user on how to interact with the simulation.

14. **`void myDisplay()`**
    - **Purpose**: Clears the screen and displays instructions for the user.

15. **`void fixAdjMatrix()`**
    - **Purpose**: Initializes the adjacency matrix with a high value (99999) to represent no connection between nodes.

16. **`void beginDijkstra(unsigned char key, int x, int y)`**
    - **Purpose**: Starts Dijkstra's algorithm when the Enter key is pressed and ensures that source and destination nodes are selected.
    - **Parameters**:
      - `unsigned char key`: Key pressed.
      - `int x`: X-coordinate of the key event.
      - `int y`: Y-coordinate of the key event.

17. **`int getMinimumDistanceNode(int *distanceFromSource, int *selected)`**
    - **Purpose**: Finds the node with the minimum distance from the source that has not yet been selected.
    - **Parameters**:
      - `int *distanceFromSource`: Array of distances from the source node.
      - `int *selected`: Array indicating which nodes have been selected.
    - **Returns**: The index of the node with the minimum distance.

18. **`void routeNodes(int n1, int n2)`**
    - **Purpose**: Draws a line between two nodes, marking the path found by Dijkstra's algorithm.
    - **Parameters**:
      - `int n1`: ID of the first node.
      - `int n2`: ID of the second node.

19. **`void delay(int number_of_seconds)`**
    - **Purpose**: Introduces a delay in milliseconds.
    - **Parameters**:
      - `int number_of_seconds`: Number of seconds to delay.

20. **`void dijkstra()`**
    - **Purpose**: Implements Dijkstra's shortest path algorithm to find the shortest path from the source node to the destination node. Updates the adjacency matrix and visualizes the process.
    - **Parameters**: None directly, but uses global variables like `sourceNode`, `destinationNode`, `adjMatrix`, and `nodes`.

### General Structure

- **Initialization**: `main()` sets up the GLUT environment and initializes the adjacency matrix.
- **Rendering and Interaction**:
  - **Rendering**: `myDisplay()` and related functions handle drawing and updating the screen.
  - **Interaction**: `myMouse()` processes user input for creating nodes and selecting nodes for paths.
- **Algorithm Execution**: `beginDijkstra()` starts the Dijkstra’s algorithm when the Enter key is pressed, and `dijkstra()` performs the actual algorithm.
- **Utility Functions**: Include distance calculations, drawing utilities, and delay functions.

Each function is carefully designed to handle specific tasks such as rendering, user input, and algorithm execution. The separation of concerns allows for a modular design where each function has a single responsibility.

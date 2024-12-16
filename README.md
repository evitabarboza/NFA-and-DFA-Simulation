
---

# NFA to DFA Conversion, DFA Simulation, and FSM Diagram Generator

## Overview

This project provides a solution for:

1. **Converting a Non-deterministic Finite Automaton (NFA) to a Deterministic Finite Automaton (DFA)**: It simulates the conversion process using the subset construction algorithm.
2. **Simulating the DFA**: It allows users to simulate the DFA with a given input string and check if it is accepted or rejected.
3. **Visualizing the FSM Diagram**: It generates a graphical representation of the DFA using the `graphviz` library to display states, transitions, and accepting states.

The project is built using Python and leverages `tkinter` for the GUI and `graphviz` for diagram generation.

## Features

- **Interactive GUI**: Provides input fields for defining the NFA and DFA components like states, alphabet, start state, accepting states, and transitions. Users can visualize and simulate both NFA and DFA.
- **NFA to DFA Conversion**: Converts an NFA to a DFA using the subset construction algorithm.
- **DFA Simulation**: Simulates the DFA with a given input string and checks if the string is accepted or rejected.
- **FSM Diagram**: Generates a state machine diagram of the DFA, representing the states and transitions visually.
- **Error Handling**: The program identifies and handles common input errors like invalid transitions or state configurations.

## Requirements

To run the project, you need to have the following libraries installed:

- `tkinter` (for GUI)
- `graphviz` (for FSM diagram generation)

### Installation Instructions

1. Install Python from the [official website](https://www.python.org/downloads/).
2. Install the required libraries using `pip`:

   ```bash
   pip install graphviz
   ```

   If you're using an IDE like PyCharm, make sure to include the necessary libraries in the project dependencies.

3. The `graphviz` executable (for rendering diagrams) should be installed on your machine. You can follow the installation instructions from [here](https://graphviz.gitlab.io/download/).

## How to Use

### Step 1: Start the Program

Run the Python script:

```bash
python nfatodfa.py
```

### Step 2: Enter the Required Inputs

The GUI will display input fields where you can enter:

- **States**: Comma-separated list of states in the NFA (e.g., `q0,q1,q2`).
- **Alphabet**: Comma-separated list of symbols in the alphabet (e.g., `0,1`).
- **Start State**: The start state of the NFA (e.g., `q0`).
- **Accepting States**: Comma-separated list of accepting states (e.g., `q2`).
- **Transitions**: Comma-separated list of transitions in the format `state,symbol,next_state` (e.g., `q0,0,q1;q1,1,q2;q2,0,q2`).
- **Input String**: A string to test the DFA simulation (e.g., `011`).

### Step 3: Simulate NFA to DFA Conversion

Click on the **Simulate NFA to DFA** button. This will:

- Convert the NFA to a DFA using the subset construction algorithm.
- Process the input string through the DFA to check whether it is accepted or rejected.
- Generate a FSM diagram of the DFA.

### Step 4: Simulate the DFA

Click on the **Simulate DFA** button after entering the DFA components (states, alphabet, transitions, etc.). This will:

- Allow you to simulate the DFA with any input string you provide.
- Show the result (whether the input string is accepted or rejected by the DFA).

### Step 5: View Results

The following results will be displayed:

- **FSM Diagram**: A PNG image of the DFA, showing the states and transitions.
- **DFA Simulation Result**: Whether the input string is accepted or rejected by the DFA.

### Example

1. **States**: `q0,q1,q2`
2. **Alphabet**: `0,1`
3. **Start State**: `q0`
4. **Accepting States**: `q2`
5. **Transitions**: `q0,0,q1;q1,1,q2;q2,0,q2`
6. **Input String**: `011`

After clicking the button, the program will display the DFA diagram and indicate whether the string `011` is accepted or rejected.

## Code Explanation

### `simulate_nfa_to_dfa` Function
This function converts an NFA to a DFA using the subset construction algorithm. It creates new DFA states that correspond to sets of NFA states, and transitions are defined for each subset based on the NFA's transitions.

### `generate_fsm_diagram` Function
This function uses the `graphviz` library to generate a graphical representation of the DFA. It creates nodes for each state and edges for each transition, highlighting accept states with double circles.

### DFA Simulation
The DFA simulation is handled by a state transition table, which stores the transitions for each state and symbol in the DFA. The simulation processes the input string and checks whether the DFA reaches an accepting state by the end of the string.

### GUI Components
- **Input Fields**: For defining states, alphabet, start state, accepting states, transitions, and input string.
- **Buttons**: 
  - **Simulate NFA to DFA**: Converts the NFA to a DFA and generates the FSM diagram.
  - **Simulate DFA**: Simulates the DFA for a given input string and provides feedback on acceptance.

## Troubleshooting

- **Graphviz not found**: If the program fails to generate the diagram, ensure that Graphviz is installed and available in your system’s PATH. Check this by running `dot -version` in the terminal.
- **Invalid Transitions**: Ensure transitions are formatted correctly (`state,symbol,next_state`) and separated by semicolons.
- **DFA Simulation Issue**: Make sure that all DFA states and transitions are correctly defined. Invalid input strings or missing transitions can cause simulation errors.

## License

This project is open-source and can be modified and distributed under the terms of the MIT License.

## GitHub Repository

You can find the source code and contribute to the project on GitHub:

[**NFA-and-DFA-Simulation**](https://github.com/evitabarboza/NFA-and-DFA-Simulation)

---

Feel free to fork, modify, and contribute to the project. If you encounter any issues or have suggestions for improvements, please open an issue on the GitHub repository.
# LangGraph BMI Calculator

A simple BMI (Body Mass Index) calculator built using LangGraph, demonstrating state management and workflow orchestration.

## Overview

This project showcases how to use LangGraph to create a stateful workflow for calculating BMI. The application uses LangGraph's `StateGraph` to manage state transitions and execute a BMI calculation workflow.

## Features

- **State Management**: Uses LangGraph's `StateGraph` to manage BMI calculation state
- **Typed State**: Implements a `BMIState` TypedDict for type safety
- **Workflow Orchestration**: Demonstrates node addition and edge connections in LangGraph
- **BMI Calculation**: Calculates BMI using the standard formula: BMI = weight(kg) / height(m)²

## Project Structure

```
langgraph_project/
├── 1_Bmi-Calculator.ipynb    # Jupyter notebook with BMI calculator implementation
├── main.py                   # Main Python script
├── pyproject.toml            # Project dependencies and configuration
├── uv.lock                   # Lock file for dependency management
└── README.md                 # This file
```

## Installation

### Prerequisites

- Python 3.13 or higher
- uv (recommended) or pip for package management

### Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd langgraph_project
```

2. Install dependencies using uv:
```bash
uv sync
```

Or using pip:
```bash
pip install -e .
```

## Usage

### Running the BMI Calculator

The BMI calculator can be run in two ways:

#### 1. Jupyter Notebook
Open `1_Bmi-Calculator.ipynb` in Jupyter and run the cells to see the BMI calculation workflow in action.

#### 2. Python Script
Run the main script:
```bash
python main.py
```

### BMI Calculator Workflow

The BMI calculator workflow consists of:

1. **State Definition**: Defines a `BMIState` with weight, height, and calculated BMI
2. **BMI Calculation Node**: A function that calculates BMI from weight and height
3. **Graph Construction**: Creates a StateGraph with nodes and edges
4. **Workflow Execution**: Invokes the workflow with initial state

### Example Usage

```python
# Define initial state
initial_state = {'weight_kg': 80, 'heigh_m': 1.73}

# Execute workflow
final_state = workflow.invoke(initial_state)
print(final_state)
# Output: {'weight_kg': 80, 'heigh_m': 1.73, 'bmi': 26.73}
```

## Dependencies

- **langgraph**: Core workflow orchestration framework
- **langchain**: LangChain framework for LLM applications
- **langchain-openai**: OpenAI integration for LangChain
- **dotenv**: Environment variable management

## BMI Categories

The calculated BMI can be interpreted using standard categories:

- **Underweight**: BMI < 18.5
- **Normal weight**: BMI 18.5-24.9
- **Overweight**: BMI 25-29.9
- **Obese**: BMI ≥ 30

## Development

### Project Configuration

The project uses `pyproject.toml` for configuration and dependency management. Key dependencies include:

- `langgraph>=0.6.8`: For state graph workflows
- `langchain>=0.3.27`: For LLM framework integration
- `langchain-openai>=0.3.34`: For OpenAI model integration

### Adding Features

To extend the BMI calculator:

1. Add new state fields to `BMIState`
2. Create new calculation functions
3. Add nodes to the graph using `graph.add_node()`
4. Connect nodes with edges using `graph.add_edge()`

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

For questions or issues, please open an issue in the repository.

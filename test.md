# Introduction to Streamlit

Streamlit is an open-source framework that allows you to create web applications for data science and machine learning projects with minimal effort. It lets you convert Python scripts into shareable web apps quickly.

## Installation

To get started with Streamlit, you need to have Python installed on your machine. You can install Streamlit using pip:

```bash
pip install streamlit
```

## Running a Streamlit App

You can create a Python script (e.g., `app.py`) and run your Streamlit app with the command:

```bash
streamlit run app.py
```

This command will start a local server, usually at `http://localhost:8501`.

## Basic Structure of a Streamlit App

Here's a simple example to get you started.

### Example 1: Hello Streamlit

Create a file named `hello_streamlit.py` and add the following code:

```python
import streamlit as st

st.title("Hello, Streamlit!")
st.write("Welcome to your first Streamlit app.")
```

### Running the App

Run the app using the command:

```bash
streamlit run hello_streamlit.py
```

## Adding Widgets

Streamlit provides several built-in widgets to make your app interactive.

### Example 2: Slider and Text Input

Modify `hello_streamlit.py` to include a slider and text input:

```python
import streamlit as st

st.title("Hello, Streamlit with Widgets!")

# Slider
number = st.slider("Select a number", 0, 100)
st.write(f"You selected: {number}")

# Text input
user_input = st.text_input("Enter some text")
st.write(f"You entered: {user_input}")
```

## Displaying Data with Charts

Streamlit can also display charts and data frames.

### Example 3: Line Chart

You can visualize data using charts. Here's how to add a simple line chart:

```python
import streamlit as st
import pandas as pd
import numpy as np

st.title("Line Chart Example")

# Create a DataFrame
data = pd.DataFrame(
    np.random.randn(20, 3),
    columns=['a', 'b', 'c']
)

# Display the line chart
st.line_chart(data)
```

## Using Caching for Performance

You can use the `@st.cache` decorator to cache expensive computations.

### Example 4: Caching Data

```python
import streamlit as st
import pandas as pd

@st.cache
def load_data():
    # Simulate a time-consuming loading process
    return pd.DataFrame({
        'x': range(1, 101),
        'y': range(1, 101)
    })

st.title("Cached Data Example")

data = load_data()
st.write(data)
```

## Layouts and Columns

You can structure your app using different layouts. For example, using columns:

### Example 5: Using Columns

```python
import streamlit as st

st.title("Columns Example")

col1, col2, col3 = st.columns(3)

with col1:
    st.header("Column 1")
    st.button("Button 1")

with col2:
    st.header("Column 2")
    st.button("Button 2")

with col3:
    st.header("Column 3")
    st.button("Button 3")
```

## Conclusion

Streamlit allows you to create interactive web applications with minimal effort. You can implement widgets, display charts, and create complex layouts easily. As you become more familiar with Streamlit, you can explore additional features such as file uploads, state management, and building custom components.

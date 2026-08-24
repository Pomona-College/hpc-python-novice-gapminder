---
title: "Instructor Notes"
---

## Workshop Overview

This workshop introduces learners to data visualization and programming with Python using the Gapminder dataset. Participants will learn fundamental Python concepts while building practical data analysis and visualization skills. The Gapminder data provides an engaging, real-world context for exploring economic indicators (GDP per capita), life expectancy, and population trends across countries and time periods.

The workshop uses Jupyter notebooks as the primary learning environment and introduces learners to pandas for data manipulation and matplotlib for visualization. By the end of the workshop, participants will be able to write Python scripts to analyze datasets, create publication-quality plots, and understand fundamental programming concepts like variables, loops, functions, and scope.

## Episode Timing and Structure

The workshop consists of 20 episodes organized into logical learning blocks:

**Getting Started (Episodes 1-5):**
- Episode 1 (Run & Quit, 30 min): Jupyter basics and environment setup
- Episode 2 (Variables, 45 min): Variable assignment, naming conventions
- Episode 3 (Types & Conversion, 45 min): Data types and type conversion
- Episode 4 (Built-in Functions, 40 min): Functions like print(), len(), type()
- Episode 5 (Coffee Break, 15 min): Break time

**Core Python Concepts (Episodes 6-10):**
- Episode 6 (Libraries, 45 min): Importing and using libraries (pandas, matplotlib)
- Episode 7 (Reading Tabular Data, 50 min): Loading CSV files with pandas
- Episode 8 (Data Frames, 50 min): Working with DataFrames and selecting data
- Episode 9 (Plotting, 50 min): Creating plots with matplotlib
- Episode 10 (Lunch, 60 min): Lunch break

**Advanced Programming (Episodes 11-20):**
- Episode 11 (Lists, 40 min): Lists and indexing
- Episode 12 (For Loops, 45 min): Iteration and automation
- Episode 13 (Conditionals, 50 min): if/else statements
- Episode 14 (Looping Data Sets, 50 min): Combining loops with data analysis
- Episode 15 (Coffee Break, 15 min): Break time
- Episode 16 (Writing Functions, 55 min): Function definition and parameters
- Episode 17 (Scope, 40 min): Variable scope and namespaces
- Episode 18 (Style, 30 min): Code style and best practices
- Episode 19 (Wrap-up, 20 min): Review and next steps
- Episode 20 (Feedback, 10 min): Feedback collection

**Total Workshop Duration:** Approximately 6-7 hours of instructional time (with breaks)

## Teaching Tips and Best Practices

### Environment Setup
- Ensure Jupyter is running smoothly before the workshop starts. Test it with the Gapminder data file.
- Have Python and required packages (pandas, matplotlib, numpy) installed and verified.
- Provide clear instructions for accessing Jupyter (locally or via the HPC OnDemand portal if running on Sagehen).

### Engagement Strategies
- Use the Gapminder dataset as a motivating narrative. Students often find it interesting to explore GDP and life expectancy trends.
- Encourage students to explore the data themselves during exercises. Let them ask questions like "Which country had the biggest growth?" or "How has life expectancy changed?"
- Break code into small, manageable chunks. Don't show an entire function all at once.
- Live code along with students. Type out examples rather than copying/pasting.
- Ask questions to check understanding: "What do you think will happen if we run this code?"

### Pacing
- Episode 1 is crucial for environment comfort. Spend extra time here if needed.
- Episodes 6-9 are the payoff: students see visible results with plots. This is motivating.
- Episodes 12-14 can feel abstract. Use concrete examples from the Gapminder data.
- The function episodes (16-17) are often where students struggle. Use lots of examples and practice.

### Accessibility
- Use a large font size in Jupyter (18pt+ for visibility).
- Read code aloud as you type to help auditory learners.
- Encourage questions and create a safe environment for mistakes.
- Pair novices with more experienced learners if possible.

## Common Pitfalls and How to Address Them

### 1. **Indexing Off-by-One Errors**
Students often forget that Python uses 0-based indexing.
- **Teaching Tip:** Explicitly count: "Index 0 is the first item. Index 1 is the second item." Write it out visually on the board.
- **Demo:** Show `my_list = [10, 20, 30]` and access each element: `my_list[0]`, `my_list[1]`, `my_list[2]`.

### 2. **Confusion Between Variable Assignment and Comparison**
Students mix up `=` (assignment) and `==` (comparison).
- **Teaching Tip:** Refer to `=` as "gets" (x gets 5) and `==` as "equals" (x equals 5?).
- **Demo:** Show both in context: `x = 5` vs. `if x == 5: print("yes")`.

### 3. **Forgetting to Import Libraries**
Students try to use pandas or matplotlib without importing them.
- **Teaching Tip:** Emphasize that import statements must be at the top of the script/notebook.
- **Demo:** Show the NameError that results from forgetting an import, then fix it.

### 4. **Column Selection Confusion**
Students struggle with selecting columns from DataFrames.
- **Teaching Tip:** Use both methods: `df['column_name']` and `df.column_name`.
- **Demo:** Load the Gapminder data and show: `gapminder['country']` vs. `gapminder.country`.

### 5. **Function Scope Misunderstandings**
Variables defined inside functions are not accessible outside.
- **Teaching Tip:** Use color or diagrams to show scope boundaries.
- **Demo:** Define a function, show that variables inside don't exist outside, contrast with global variables.

### 6. **Loop Logic Errors**
Students don't understand how loop variables update or how break/continue work.
- **Teaching Tip:** Use print statements to trace loop execution.
- **Demo:** Add `print()` statements inside loops to show each iteration.

## Demonstration Suggestions

### Live Coding Examples

**Example 1: Loading and Exploring Gapminder Data (Episode 6-8)**
```python
import pandas as pd
gapminder = pd.read_csv('gapminder-data.csv')
print(gapminder.head())
print(gapminder.describe())
print(gapminder[gapminder['year'] == 2007].sort_values('lifeExp', ascending=False).head())
```

**Example 2: Creating Your First Plot (Episode 9)**
```python
import matplotlib.pyplot as plt
import pandas as pd

gapminder = pd.read_csv('gapminder-data.csv')
gapminder_2007 = gapminder[gapminder['year'] == 2007]

plt.figure(figsize=(10, 6))
plt.scatter(gapminder_2007['gdpPercap'], gapminder_2007['lifeExp'], s=gapminder_2007['pop']/1e6, alpha=0.5)
plt.xlabel('GDP per Capita ($)')
plt.ylabel('Life Expectancy (years)')
plt.title('Life Expectancy vs. GDP per Capita (2007)')
plt.xscale('log')
plt.show()
```

**Example 3: Loop with Data (Episode 12-14)**
```python
for year in gapminder['year'].unique():
    year_data = gapminder[gapminder['year'] == year]
    print(f"Year {year}: Average Life Expectancy = {year_data['lifeExp'].mean():.1f}")
```

**Example 4: Writing a Data Analysis Function (Episode 16-17)**
```python
def analyze_country(country_name):
    """Analyze trends for a specific country."""
    country_data = gapminder[gapminder['country'] == country_name]
    print(f"GDP growth: {country_data['gdpPercap'].min()} to {country_data['gdpPercap'].max()}")
    print(f"Life expectancy: {country_data['lifeExp'].min()} to {country_data['lifeExp'].max()}")
    return country_data

analyze_country('China')
```

### Interactive Challenges

1. **Episode 9 Challenge:** "Create a scatter plot of population vs. life expectancy. What patterns do you see?"
2. **Episode 12 Challenge:** "Write a loop that prints each country's name from the 2007 data."
3. **Episode 16 Challenge:** "Write a function that takes a country name and returns the most recent life expectancy value."

## Materials and Resources

- **Gapminder Dataset:** Included in the episodes, typically a CSV file with columns: country, continent, year, lifeExp, pop, gdpPercap.
- **Jupyter Notebook:** Pre-configured notebooks for each episode are available.
- **Code Snippets:** All examples from episodes are executable and can be copied/pasted.

## Troubleshooting Checklist

- [ ] Jupyter is accessible and responsive
- [ ] Python packages installed: pandas, matplotlib, numpy
- [ ] Gapminder CSV file is in the correct location
- [ ] Students can create new notebook cells and run code
- [ ] Plots display correctly in the notebook
- [ ] File system access works (for reading CSVs)

## Wrap-Up and Next Steps

In the final episodes, encourage students to:
1. Explore the data further on their own
2. Try creating new plots or analyses
3. Refer to pandas and matplotlib documentation
4. Practice writing their own functions
5. Consider using these tools in their own research

Provide resources for continuing learning:
- Official pandas documentation: https://pandas.pydata.org/docs/
- Matplotlib tutorials: https://matplotlib.org/stable/tutorials/
- Python official tutorials: https://docs.python.org/3/tutorial/

## Assessment and Feedback

Consider using the feedback session (Episode 20) to gather:
- Which episodes were most challenging?
- Did the pace feel appropriate?
- What would you like to learn next?
- Would you recommend this workshop to colleagues?

Use this feedback to refine the workshop for future offerings.

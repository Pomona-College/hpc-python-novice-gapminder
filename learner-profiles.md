---
title: Learner Profiles
---

## Typical Participants

### Profile 1: Biology Graduate Student Analyzing Comparative Data
**Name:** Sarah Kim
**Background:** 2nd year PhD student in comparative biology, working in a Pomona College biology lab and storing project files on Sagehen at `/bigdata/lab/biolab/`

**Motivation:**
- Analyzing species biodiversity data across continents (and a side project on the Bernard Field Station Cecil Sagehen population)
- Has 50+ CSV files with country-level GDP and health data
- Needs to combine, visualize, and analyze relationships
- Advisor expects publication-ready plots and is requesting that Sarah's notebooks run unchanged on Sagehen via OnDemand

**Experience:**
- Comfortable with basic statistics and scientific thinking
- Recently completed intro programming course (used Python basics)
- Can write simple for loops and if statements
- No experience with data visualization
- Never used pandas or matplotlib

**Pain Point:**
"I have all this data in spreadsheets, but I don't know how to load it into Python or make plots that look professional. My advisor showed me matplotlib plots online, and they looked great, but I have no idea where to start."

**Expected Outcome After Workshop:**
- Load CSV files with pandas
- Create publication-quality plots with matplotlib
- Manipulate and filter dataframes
- Combine multiple datasets
- Save plots in publication-ready formats

**Preference:** Will use Jupyter Notebook on the Pomona OnDemand portal at https://ondemand.hpc.pomona.edu, signed in with her Pomona DUO MFA at https://duo.pomona.edu

---

### Profile 2: Psychology Researcher Building Data Processing Scripts
**Name:** James Okonkwo
**Background:** Postdoc in the Pomona College psychology department

**Motivation:**
- Processing behavioral experiment data (reaction times, accuracy) from Pomona undergraduate participants
- Runs 20+ experiments per year, scheduled across the academic calendar
- Wants to automate plotting and statistical summaries so weekly figures are produced as a SLURM batch job on Sagehen HPC
- Currently uses Excel, wants to move to Python

**Experience:**
- Familiar with R and basic statistics
- Some Python programming experience
- Can write functions and basic scripts
- Never used pandas or matplotlib
- Has moderate data handling needs

**Pain Point:**
"I can write Python code, but I don't know how to work with data tables in Python. I also don't know how to make the plots my papers require without hours of manual work in Illustrator."

**Expected Outcome After Workshop:**
- Use pandas for data manipulation and filtering
- Create multiple plot types (scatter, bar, line)
- Automate plot creation for batch processing
- Understand when to use different plot types
- Customize plots for publication

**Preference:** Will use Jupyter Notebook, may write standalone Python scripts later

---

### Profile 3: Environmental Science Undergraduate Learning Research Skills
**Name:** Alex Patel
**Background:** Junior undergrad in environmental analysis at Pomona College, doing fieldwork at the Robert J. Bernard Biological Field Station

**Motivation:**
- Starting undergraduate research project on climate and agriculture
- Needs to learn data visualization for research reports for an environmental analysis senior thesis
- Planning to pursue graduate study in environmental science
- First real programming experience for science; will use the Sagehen HPC cluster for any analyses too large for a laptop

**Experience:**
- Beginner programmer (some high school CS, intro college course)
- Took basic statistics class
- Comfortable with spreadsheets
- No prior experience with Python scientific libraries
- Enthusiastic but anxious about coding

**Pain Point:**
"I know what data I want to analyze, but I don't know how to turn a CSV file into a plot. I'm worried the code will be too complicated for me."

**Expected Outcome After Workshop:**
- Load and explore CSV data
- Create basic plots (scatter, line, histogram)
- Understand when to use matplotlib vs. pandas plotting
- Gain confidence in Python for research
- Know where to find help and examples online

**Preference:** Will use Jupyter Notebook with lots of examples and step-by-step guidance, launched through the Pomona OnDemand portal so Alex never has to install Python locally

---

## Common Learner Characteristics

### What They Know
- Basic Python syntax (variables, loops, conditionals)
- How to open files in a code editor
- Basic statistics (mean, standard deviation)
- What data visualization is and why it matters

### What They Don't Know
- How to load CSV files into Python
- How pandas DataFrames work or when to use them
- How to create plots beyond simple matplotlib calls
- How to customize plots for publication
- How to work with multiple datasets together
- Best practices for data visualization

### What They Value
- **Clear examples:** Want to see real, working code they can modify
- **Practical application:** Need solutions to their actual research problems
- **Quick results:** Want to see plots early in the workshop
- **Publication quality:** Need plots suitable for papers and presentations
- **Flexibility:** Prefer tools that work across different types of data

### What They Worry About
- **"Will this be too technical?"** "Can I actually do this?"
- **"How do I debug code?"** "What if something breaks?"
- **"Will I understand data frames?"** "They sound complicated"
- **"Are there better tools?"** "Should I use R instead?"
- **"How do I make professional-looking plots?"** "My plots look ugly"

---

## Design Philosophy

This workshop is designed for **researchers who have data and want to visualize and analyze it in Python**, not for programming language specialists.

Key assumptions:
- Participants can read and write basic Python code
- Participants have real data they want to work with
- Participants value practical skills over theory
- Participants may not have computer science background

The workshop emphasizes:
- **"How do I load MY data?"** not "how do CSV files work?"
- **"How do I make MY plot?"** not "how does matplotlib rendering work?"
- **"What plot type should I use?"** by showing examples
- **"Can I make it publication-quality?"** through customization
- **"What's the minimum code I need?"** to avoid overwhelming examples

By day's end, participants should have either:
1. Created publication-quality plots from their own or provided data, OR
2. Clear understanding of the pandas/matplotlib workflow for their data

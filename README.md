# Degrees of Separation - Breadth-First Search (BFS)

## Overview
This program determines the number of "degrees of separation" between two actors based on the movies they have starred in. It finds the shortest path connecting two actors by identifying the sequence of movies that links them.

## Background
Inspired by the Six Degrees of Kevin Bacon game, this program models the problem as a graph search. Each actor represents a node, and edges are defined by shared movie appearances. The goal is to find the shortest path between two given actors using **breadth-first search (BFS)**.

## Usage
To run the program, use:
```sh
python degrees.py [directory]
```
where `[directory]` is either `small` (for quick tests) or `large` (for the full dataset).

**Large dataset directory can be downloaded from this [link](https://drive.google.com/drive/folders/1dAZzqmJ-qkg73bd2cbqw6n4OWWxeI86l?usp=sharing).**

### Example:
```sh
$ python degrees.py large
Loading data...
Data loaded.
Name: Emma Watson
Name: Jennifer Lawrence
3 degrees of separation.
1: Emma Watson and Brendan Gleeson starred in Harry Potter and the Order of the Phoenix
2: Brendan Gleeson and Michael Fassbender starred in Trespass Against Us
3: Michael Fassbender and Jennifer Lawrence starred in X-Men: First Class
```

## Data Structure
- `people.csv` – Contains unique person IDs, names, and birth years.
- `movies.csv` – Contains unique movie IDs, titles, and release years.
- `stars.csv` – Establishes actor-movie relationships.

## Implementation Details
The program follows these steps:
1. **Load Data** – Parses CSV files into dictionaries for fast lookup.
2. **User Input** – Accepts two actor names.
3. **Find Shortest Path** – Uses **BFS** to determine the shortest connection.
4. **Output Result** – Displays the sequence of movies linking the two actors.

### Shortest Path Algorithm
The function `shortest_path(source, target)`:
- Uses a **queue** to explore actors level by level.
- Tracks visited actors to prevent cycles.
- Stops when the target actor is found, returning the shortest path.

## Edge Cases Handled
- Returns `None` if no connection exists.
- Handles multiple actors with the same name by prompting clarification.
- Outputs a path of length `0` if the source and target are the same.

## License
This project is for educational purposes and follows Harvard's CS80's AI curriculum.

## Acknowledgments
- CS80 AI Course for the dataset and project inspiration.



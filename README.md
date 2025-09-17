# D&D 5e Spellbook Network Analysis 🧙‍♂️✨

This project uses Python to transform the Dungeons & Dragons 5th Edition spellbook into an interactive network graph. The goal is to visualize the hidden relationships between all 554 spells in the dataset, based on which character classes have access to them. The final visualization reveals the "core" of multi-class magic—the spells that are so versatile they are shared across a wide range of magical practitioners.



---
## Key Findings & Analysis
This project analyzes the interconnectedness of the D&D spell list to distinguish between highly specialized spells and universally shared magic.

The most significant finding was that the spell network is **extremely dense by nature**. An initial analysis connecting spells that share **at least one** character class created an unreadable graph of nearly 100,000 (99045) connections. To uncover a meaningful structure, the connection rule was iteratively tightened. After testing a rule of 3+ shared classes, the final, most insightful model was built using a rule where an edge is only created between two spells if they are shared by **four or more classes**.

This final rule filtered the network down from a tangled "hairball" to a clear, interpretable structure of **554 nodes (spells)** and **1,644 core edges**. These connections represent the "superhighways" of the magic system, linking the spells that are truly fundamental to the D&D universe.

By coloring each spell by its school of magic, we can also see which schools (like Transmutation and Abjuration) are more widely distributed across classes, versus those that are more specialized.

---
## Tech Stack & Data Source
* **Language:** **Python** was used for all data processing and analysis.
* **Environment:** **Google Colab** provided an interactive, browser-based notebook for development.
* **Data Manipulation:** The **`pandas`** library was essential for loading the spell data and cleaning it into a usable format.
* **Graph Analysis:** The **`networkx`** library was used to construct the graph, adding spells as nodes and creating the connections between them.
* **Interactive Visualization:** The **`pyvis`** library transformed the networkx graph into a beautiful and interactive HTML file, using the **ForceAtlas2** physics engine to improve the layout.
* **Data Source:** The project uses the **Dungeons & Dragons Spell Listing** dataset from Kaggle, which can be found here: [D&D Spells Dataset](https://www.kaggle.com/datasets/mrpantherson/dndspells).

---
## What I Learned
This project was a practical lesson in transforming a complex dataset into a clear and insightful story.
The most important takeaways were:
* **Iterative Analysis:** The initial analysis is often just a starting point. The key insight emerged from iteratively refining the graph's connection rules—testing thresholds of 1, 3, and finally 4 or more shared classes—to filter out statistical noise and reveal a meaningful structure.
* **Data Storytelling:** Simply plotting the data wasn't enough; applying a distinct color to each school of magic was essential for making the final graph interpretable.
* **Algorithm Application:** A common visualization problem (a dense "hairball" graph) was solved by applying a more suitable layout algorithm. Implementing the **ForceAtlas2** physics engine with a repulsive gravity setting was crucial for untangling the network and creating a readable final product.

---
## Project Key: Classes, Schools & Colors
This project analyzes the relationships between the spells available to the following D&D 5e classes:
* **Classes:** Artificer, Bard, Cleric, Druid, Paladin, Ranger, Sorcerer, Warlock, and Wizard.

The spells in the visualization are colored according to their school of magic, based on the following key:
* **Abjuration:** `#00bfff` (Deep Sky Blue)
* **Conjuration:** `#ff4500` (OrangeRed)
* **Divination:** `#ffffff` (White)
* **Enchantment:** `#ff69b4` (Hot Pink)
* **Evocation:** `#dc143c` (Crimson)
* **Illusion:** `#9932cc` (Dark Orchid)
* **Necromancy:** `#006400` (Dark Green)
* **Transmutation:** `#ffd700` (Gold)

---
## How to Run
1.  **Set up the environment:** Open the notebook in Google Colab.
2.  **Upload Data:** Upload the D&D spell dataset file (e.g., `dnd-spells.csv`).
3.  **Install Libraries:** Run the installation cell to ensure `pyvis` is installed.
    ```
    !pip install pyvis
    ```
4.  Execute the notebook cells to load the data, build the graph, and generate the final visualization.
5.  **Download the Output:** The final cell will save an HTML file (e.g., `spell_network.html`). Download this file from the Colab file browser.
6.  **View:** Open the downloaded HTML file in your local web browser to explore the interactive graph.

---
## Images of Visualised data
<img width="757" height="680" alt="Screenshot 2025-09-18 003250" src="https://github.com/user-attachments/assets/56eda123-80a5-4562-baee-327c7aa533a3" />

<img width="719" height="684" alt="Screenshot 2025-09-18 010022" src="https://github.com/user-attachments/assets/90428c2d-fbfd-4460-bc05-2bbac2c81933" />


<img width="1067" height="738" alt="Screenshot 2025-09-18 010112" src="https://github.com/user-attachments/assets/5f3f5bba-ce25-43b0-b2dd-38a5501b825a" />


<img width="736" height="730" alt="Screenshot 2025-09-18 010034" src="https://github.com/user-attachments/assets/2b8df7c0-b811-46ca-96d0-0e74e5015a0e" />



Spells with fewer than 4 common classes
<img width="1664" height="505" alt="image" src="https://github.com/user-attachments/assets/b55c3023-b117-41e0-817e-5692fbf490b1" />



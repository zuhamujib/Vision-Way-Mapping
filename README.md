# Vision-Way-Mapping
VisionWay-Mapping is a mapping software developed as part of the ECE297 Software Communication and Design course at the University of Toronto (2024).

![Screenshot (452)](https://github.com/zuhamujib/Vision-Way-Mapping/assets/123215280/2f483678-82a2-4df7-9180-4dea6e3a5c74)

## Overview
This project leverages the OpenStreetMap API and OSM database to extract and display important geographical information for various cities worldwide. It is entirely written in C++, utililzing the gtk libraries and glade for the user interface and focuses on implementing advanced pathfinding algorithms for efficient route planning.

Our map is specifically designed for individuals with low vision and color blindness. Explore the tailored features we’ve implemented for accessibility below. 

## Features
### Colour Themes
Our application supports three distinct color themes to enhance accessibility and user experience:
- Default Theme: The standard theme with a balanced color palette.
- ![Screenshot (439)](https://github.com/user-attachments/assets/4a8418a9-3435-4d7b-9e56-69e74863d979) 
Colorblind Mode: Optimized for red-green colorblind users, ensuring all interface elements are easily distinguishable. 
- ![Screenshot (438)](https://github.com/user-attachments/assets/f2bb1eee-4e09-4c91-bf04-c7895397ad05)
 Night Mode: A high-contrast theme using shades of white, black, and grey to reduce eye strain in low-light environments.

This is a snippet of how night mode looks like:
![Screenshot (307)](https://github.com/user-attachments/assets/89025858-ddfa-42f4-b86d-933884bbc54e)

You can switch between these themes using the dedicated buttons located in the sidebar. Each button is marked with a unique, descriptive icon, making it easy to navigate and select your preferred color theme.

### Subways
You can toggle the subway display using the dedicated button in the sidebar, represented by a subway icon. This feature shows the different subway stations across the city along with their names. To avoid overcrowding the map, by default subway stations are only visible when zoomed in to a detailed level.

![Screenshot (299)](https://github.com/user-attachments/assets/93514a4e-3a11-4904-807f-7af5dac1cb10)

### Text-to-Speech
Our app provides a text-to-speech feature that is activated when you click on intersections. This allows for auditory feedback, ensuring that important location information is accessible to users with visual impairments.

### Auto Zooming
When searching for intersections between two streets or finding the shortest path between locations, the map automatically zooms in or out to display all intersections or the complete route. The view is adjusted to ensure the entire path is visible within the user’s screen, enhancing navigation and clarity.

![VNC - mujibzuh@ug165](https://github.com/user-attachments/assets/92743543-9782-4c4d-90c7-1c099fe021c4)

## Pathfinding Algorithms
Our GIS system enables users to find all intersections between two streets by entering the street names into the top two search bars and clicking the corresponding button to display common intersections. Additionally, users can search for the shortest path between two intersections by entering the street names for both intersections into search bars 1 and 2, and 3 and 4 respectively, then toggling the appropriate button to highlight the optimal path between them. This intuitive interface simplifies navigation and pathfinding across the city.

![Screenshot (449)](https://github.com/user-attachments/assets/111af897-1dce-4517-a558-5c166e1e4063)

### Dijkstra's Algorithm: Shortest Path Between Two Intersections
In this implementation, Dijkstra’s algorithm was applied to efficiently compute the shortest path between two intersections. A key modification to the standard approach involved accounting for turning penalties, where each turn incurs a 15-second delay. This required careful consideration of the direction of travel between intersections, ensuring that the algorithm not only minimized distance but also optimized for travel time. By incorporating this real-world constraint, the solution provides a more accurate and practical navigation experience.

![Screenshot (437)](https://github.com/user-attachments/assets/ef7bc10a-e1dd-4995-a386-cbe8b5731e41)

### Travelling Salesman Problem
To tackle the TSP within the GIS system, we employed a combination of multi-Dijkstra’s, greedy heuristics, and dynamic programming techniques. This multi-faceted approach enabled us to handle the complexity of managing multiple depots, pickup, and drop-off locations. The multi-Dijkstra's method facilitated efficient route planning, while the greedy heuristic provided a fast initial solution. Dynamic programming was then used to further optimize the route, minimizing the total travel cost. As a result, our solution outperformed the Intermediate TA algorithm, demonstrating an advanced level of problem-solving and algorithmic efficiency.

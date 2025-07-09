# capstone_project


Brief Overview of the Project

Urban parking spaces suffer from inefficiency when prices remain static despite changes in demand throughout the day. This project builds a real-time dynamic pricing engine for 14 parking lots using real-world features like occupancy, traffic, vehicle type, and special events. The goal is to optimize price based on real-time demand using a 3-stage modeling pipeline:

Model 1: Linear pricing based on occupancy

Model 2: Demand-function-based pricing

Model 3: Competitive pricing with spatial proximity and rerouting suggestions


The project also simulates data in real time using Pathway, and visualizes outputs using Bokeh.



Tech Stack Used

Tool	Purpose

Python	Core logic and feature processing
Pandas	Data manipulation and preprocessing
NumPy	Numerical calculations and vector operations
Pathway	Real-time stream processing & simulation
Bokeh	Real-time interactive visualization
Colab	Development and testing environment
(Optional) Mermaid	For architecture diagramming


 Project Architecture Diagram 

![WhatsApp Image 2025-07-09 at 20 44 18_d5d4face](https://github.com/user-attachments/assets/ed557722-4366-4b2e-9f80-355ba000d549)



Project Architecture and Workflow Explanation

1. Data Ingestion

The dataset contains real-time features (occupancy, queue, traffic, vehicle type) for 14 lots over 73 days.

Data is time-sorted and ingested using Pathway to simulate live streaming.



2. Model Pipeline

Model 1: Uses a simple linear function with occupancy/capacity to increase or decrease prices.

Model 2: Uses a weighted demand function based on occupancy, queue, traffic, special day, and vehicle type.

Model 3 (optional): Adds spatial awareness by computing proximity to nearby lots and adjusting prices based on competitor behavior.



3. Real-Time Simulation (Pathway)

Simulates incoming data in chronological order.

Each time step updates prices and optionally routes vehicles.



4. Pricing Engine

Applies selected model logic.

Updates prices in real time with constraints: minimum 0.5x base price, maximum 2x.



5. Visualization

Bokeh is used to plot price changes over time.

Interactive comparison between different lots and models.



6. Export

Outputs are saved as CSV.

Plots and data are embedded in a final Google Colab notebook.



Other Relevant Documentation & Notes

Base Price: $10 for all lots

Feature Normalization: Essential for demand function stability

Assumptions:

Capacity does not change

Traffic and events are external and known in advance

Demand is responsive in short intervals (30 mins)


Next Steps:

Tune weights (α, β, etc.) using historical trends

Add feedback mechanism for rerouting in Model 3

Enhance Bokeh dashboard for user interaction

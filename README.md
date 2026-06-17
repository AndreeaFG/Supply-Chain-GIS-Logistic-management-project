Supply Chain GIS Simulation for Berlin

Overview

This project models and simulates an urban supply chain network for the city of Berlin using AnyLogic and GIS (Geographic Information Systems) integration. The simulation focuses on order generation, delivery operations, resource allocation, and logistics performance analysis in a realistic urban environment.

Project Structure
Phase 1 – Supply Chain Analysis

The conceptual design of the supply chain includes:
- Three-Environment Diagram illustrating interactions between:
  - Internal resources (warehouse, trucks, logistics personnel, GIS system)
  - Near external factors (suppliers and retailers)
  - Far external factors (economic conditions, regulations, technological developments)
- SWOT Analysis identifying:
  - Strengths
  - Weaknesses
  - Opportunities
  - Threats
- Fishbone Diagram analyzing the root causes of delivery delays
- Logistics Flow Diagram describing the movement of products throughout the supply chain.

Phase 2 – GIS Distribution Network

The first simulation model was developed using GIS maps in AnyLogic.
Main features:
- Central distributor located in Berlin using real geographic coordinates (52.5200, 13.4050)
- GIS visualization of the distribution network
- 15 retailers imported from an Excel file and positioned on the map using latitude and longitude data
- Real-world geographic representation of supply chain entities.

Phase 3 – Truck Movement Simulation

The model was extended by introducing truck agents responsible for deliveries.
Main features:
- Fleet of 5 trucks
- Statechart-based truck behavior
- Real-road movement using GIS routes
- Automatic travel between distributor and retailers
- Delivery cycle including:
  - AtDistributor
  - MovingToRetailer
  - MovingToDistributor
- Order generation event executed periodically
- Initial unloading delay modeled using a triangular distribution.

  Results:
- Visual truck movement on the GIS map
- Automated delivery operations
- Delivery time evaluation
- Functional logistics flow simulation.
  
Phase 4 – Order Management System

The supply chain logic was expanded through the introduction of product orders and dynamic truck allocation.
Main features:
- Retailers generate orders periodically
- Order quantities vary randomly between 10 and 20 units
- New ProductOrder agent introduced
- Automatic selection of available trucks
- Message-based communication between agents
- Prevention of null-destination errors when all trucks are busy
- Each truck stores and processes its assigned order.

Main Agents:
Distributor - Maintains the list of active orders and acts as the central distribution point
Retailers - 15 retailers that periodically generate delivery requests
Trucks - 5 delivery vehicles responsible for transporting orders
ProductOrder - Non-visual agent containing: Order quantity, Destination retailer.

The model now simulates a complete order-delivery process instead of simple truck movement.

Phasee 5 – Realistic Unloading Operations

The final stage focused on increasing operational realism.
Improvements:
- Removal of the simple unloading delay
- Introduction of a dedicated Unloading state in the Truck statechart
- Integration with AnyLogic Process Modeling Library
- Explicit unloading workflow: Enter, Service (Unloading), Exit
- Message-based synchronization using the "unloaded" signal
- Limited unloading resources through a forklift resource pool
- Queue formation and congestion effects.

Resource Constraints
A forklift resource pool with capacity 1 was introduced to simulate limited unloading equipment and realistic bottlenecks.

Dynamic Unloading Time
Unloading duration depends on order size: Unloading Time = Order Quantity × 10 minutes.
This allows larger orders to require longer processing times, improving simulation realism.

Technologies Used
- AnyLogic
- GIS Maps
- Agent-Based Modeling
- Statecharts
- Process Modeling Library
- Java
  

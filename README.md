# Eurobot 2025: Hyperion Robotics Mechanism Replica

## Project Overview
This repository contains a 3D CAD model replicating the core mechanisms of the "Hyperion Robotics" robot designed for the 2025 edition of Eurobot. 

**Important Note on Project Scope:** Due to time constraints, this project focuses *exclusively* on mimicking the complex kinematics and mechanical movements of the original robot. The main chassis, electronics drawer, battery housing, and cable management have been neglected in favor of perfecting the primary game-playing mechanisms. 

The primary goal was to ensure the mechanical interactions (lifting, grabbing, and deploying) mirror the functionality seen in Hyperion's 2025 robot while remaining 3D-printable with minimal supports. Additionally, because the original robot features a highly symmetrical design, modeling only one side of the robot's mechanisms was sufficient to demonstrate its complete functionality and kinematics.

## Project Structure
*   `/CAD_Files` - Contains the 3D models of the mechanisms (designed for minimal supports and easy 3D printing).
*   `/Screenshots` - Contains visual demonstrations of the mechanisms in action, specifically detailing the deployment rotations.
*   `README.md` - Project documentation.

## Core Mechanisms

The robot's movement and scoring abilities are driven by three main subsystems:

### 1. The Elevator System
The elevator is the central vertical translation unit, responsible for raising and lowering both the top grabbing arm and the bottom lifting arm.
*   **Design:** The system utilizes two distinct pairs of lead screws (front and back).
*   **Actuation:** Each pair is connected by a timing belt and driven by a stepper motor located on one side of the elevator assembly.
*   **Functionality:** 
    *   The **back pair** of screws controls the height of the *Grabbing Mechanism*.
    *   The **front pair** of screws controls the height of the *Lifting Mechanism*.

### 2. The Grabbing Mechanism
This mechanism is located at the top and is responsible for lifting one of the platforms so that side lifters can slide two columns underneath it, effectively assembling a two-level tribune.
*   **Actuation:** Powered by a servo motor driving a double rack and pinion mechanism.
*   **1200mm Perimeter Rule Compliance:** To fit within the starting perimeter limits, the entire assembly is mounted on a rotating bar. 
*   **Deployment:** 
    *   *Pre-match:* The mechanism is manually tucked inside the robot's perimeter and held securely in place by a servo motor. 
    *   *Match Start:* The retaining servo releases the hold. Gravity allows the mechanism to swing outward 90 degrees until it hits a physical stopper screw. 
    *   *In-game:* The mechanism is held in its deployed, rigid state by both gravity and the weight of the objects it picks up.
    *   *(See the `/Screenshots` folder for a visual breakdown of this deployment sequence).*

### 3. The Lifting Mechanism
Located lower on the robot, this system combines platform-lifting arms with column-hugging holders equipped with built-in electromagnets. 
*   **Functionality:** Both the arms and the electromagnet holders are raised and lowered simultaneously using the front screws of the main elevator. 
*   **Purpose:** This mechanism lifts an already-assembled two-level tribune and raises it high enough to place on top of another base, creating a complete three-level tribune.
*   **Deployment:** Just like the Grabbing Mechanism, the Lifting Mechanism utilizes the same gravity-drop rotation principle. It remains tucked in prior to the match to satisfy the 1200mm perimeter rule and automatically deploys into position once the match begins.

## Future Improvements (To-Do)
If this project is expanded in the future, the following elements from the original specifications need to be integrated:
*   A complete main chassis.
*   A deployable electronics drawer for the Raspberry Pi, Lidar, and custom boards.
*   A designated, impact-resistant battery box (for a LiPo 3S).
*   Proper routing and cable management.
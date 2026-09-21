# CCS 3209 — Week 1 Laboratory Work

## Introduction, Overview and Simulation Tools

This laboratory introduces the basic concepts of **simulation and modelling**, with a focus on **Discrete-Event Simulation (DES)**.

The practical uses a student service centre as a case study to demonstrate system components, conceptual modelling, manual simulation, Python implementation, performance analysis and experimentation.

---

## Objectives

The objectives of this practical were to:

- Identify the main components of a simulation system.
- Construct a conceptual model of a service system.
- Perform a manual discrete-event simulation.
- Calculate simulation performance measures.
- Implement the simulation model in Python.
- Compare Python results with manual calculations.
- Investigate the effect of changing service times.
- Relate the practical to the simulation study process and simulation tools.

---

## Part A — System and Conceptual Model

### Student Service Centre

The system consists of a student service centre with **one service officer**.

Students arrive at different times for services such as registration assistance, fee enquiries and document processing. If the service officer is busy, students wait in a **FIFO queue**. After receiving service, the student leaves the system.

### System Components

| Component | Description |
|---|---|
| Entity | Student |
| Entity Attributes | Arrival time and service/request type |
| Resource | One student service officer |
| Queue | One FIFO queue for students waiting for the service officer |
| Events | Student arrival, service start, service completion and departure |
| State Variables | Number of students in the queue and service officer status |

### Process Flow

```text
Student Arrival
      ↓
Check Service Officer
      ↓
   Officer Busy?
    ↙       ↘
  Yes        No
   ↓          ↓
FIFO Queue  Begin Service
   ↓          ↓
   └──────→ Complete Service
                ↓
            Departure
```
# Part B — Manual Discrete-Event Simulation

## Student Service Centre

The student service centre has one service officer. Students arrive at different times and require service. If the officer is busy, students wait in a **FIFO queue** until the officer becomes available.

## Input Data

| Student | Arrival Time | Service Time |
|---|---:|---:|
| S1 | 0 | 4 |
| S2 | 2 | 3 |
| S3 | 4 | 5 |
| S4 | 5 | 2 |
| S5 | 9 | 4 |
| S6 | 12 | 3 |
| S7 | 14 | 2 |
| S8 | 18 | 4 |

## Calculation Formulas

```text
Service Start = max(Arrival Time, Previous Completion Time)

Completion Time = Service Start + Service Time

Waiting Time = Service Start − Arrival Time

Time in System = Completion Time − Arrival Time
```
# Part C — Python Implementation

## Objective

The objective of Part C was to implement the student service-centre simulation in Python and compare the program results with the manual calculations from Part B.

## Input Data

The original service times were:

```text
[4, 3, 5, 2, 4, 3, 2, 4]
```
# Part D — Simulation Study and Tools

## Task 9 — Simulation Study Process

The practical was related to the main stages of a simulation study.

```text
| Simulation Study Stage | Application in the Practical |
|---|---|
| **Problem Formulation** | Studied the performance of a student service centre with one service officer and a FIFO queue. |
| **Data Collection** | Used the provided arrival times and service times for eight students. |
| **Conceptual Modelling** | Identified students as entities, the service officer as the resource, the FIFO queue, events and state variables. |
| **Implementation** | Implemented the conceptual model using Python. |
| **Verification and Validation** | Compared the Python results with the manual calculations. |
| **Experimentation** | Increased service times to investigate their effect on system performance. |
| **Output Analysis** | Calculated average waiting time, maximum waiting time, average time in system and percentage of students who waited. |
| **Recommendation** | Used the results to understand the effect of service-time changes on waiting and congestion. |
```
## Task 10 — Simulation Tools

```text
| Tool / Approach | Suitable Use | Advantage | Limitation |
|---|---|---|---|
| **Python with SimPy** | Process-based discrete-event simulation models such as queues and service systems. | Flexible and can be extended using Python and other libraries. | Requires programming knowledge. |
| **Arena / Simio** | Discrete-event simulation models involving queues, services and resources. | Provides specialised simulation features for modelling and analysing systems. | Licensing and deployment considerations may apply. |
```
### Preferred Approach

For a larger and more complex service-centre model, **Python with SimPy** was selected because it provides flexibility for extending the model through programming and allows integration with Python tools for data analysis and visualisation.

#  Dynamic Staff Allocation in Supermarkets Using Integer Programming

This project implements a **Hybrid Rolling-Horizon Multi-Skill Integer Programming (MILP)** model with **Lagrangian-Assisted Decomposition** and **Greedy Repair** for **real-time supermarket staff allocation**.

It is based on insights from the research paper:
> _Dynamic Staff Allocation in Supermarkets Using Integer Programming_ (Uploaded by user)

---

##  Overview

Supermarkets experience dynamic variations in customer demand throughout the day. Traditional static staff scheduling often fails to adapt to these fluctuations, leading to inefficiency and unfair workload distribution.

This project introduces a **real-time optimization framework** that dynamically reallocates staff while balancing:
- Customer demand coverage  
- Employee fairness  
- Labor cost efficiency  
- Skill and shift constraints  

---

##  Key Features

- **Rolling-Horizon Optimization:** Replans every short interval (e.g., 15 minutes) with new demand.  
- **Multi-Skill Pooling:** Employees can switch between roles such as cashier, stock, or customer service.  
- **Fairness Optimization:** Ensures balanced workload via a lexicographic minimax objective.  
- **Lagrangian Decomposition:** Divides the problem by department for faster computation.  
- **Warm-Start + Greedy Repair:** Reuses prior solutions to reduce solving time and maintain stability.  
- **Operational Constraints:** Includes shift limits, rest periods, and skill compatibility rules.

---

##  Model Formulation

The MILP minimizes a weighted objective function:

\[
\text{Minimize: } W_1 \times \text{max\_deviation} + W_2 \times \text{uncovered\_demand} + W_3 \times \text{cost}
\]

Subject to:
- Coverage constraints  
- Single-task-per-slot limits  
- Skill compatibility  
- Minimum/maximum working hours and rest constraints  

---

##  Project Files

| File | Description |
|------|--------------|
| `staff_allocation.py` | Main Python script implementing the MILP and Lagrangian-based optimization. |
| `requirements.txt` | Python dependencies for the project. |
| `README.md` | Project documentation. |

---

##  How to Run

### Clone the Repository
```bash
git clone https://github.com/<your-username>/dynamic-staff-allocation.git
cd dynamic-staff-allocation

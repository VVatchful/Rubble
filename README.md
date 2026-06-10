# Rubble
A system that aims for efficiency and aims to benefit warehouse and inventory workers by making the consolidation process easier in the warehouse


**Stakeholders & users**

1. Who executes the move list — a picker, a dedicated consolidation worker, a shift lead assigning tasks?
   - This tool is ideal for anyone who needs appropriate consolidation but is tired of manually printing locations to move to and from, meaning the stone age is no more!
     
2. Who *approves* the moves? Would a manager want to veto individual moves? Does your output need a "skip" affordance?
   - Anyone can approve or ignore a move, but the goal is to keep inventory and items grouped together, so it is in the best interest to follow the planner.

3. If this ran at your old warehouse, what's the first objection a coworker would raise?
   - Too much time to implement in an actual warehouse? Most warehouses are massive understably. However, this is a tool that aims to have an effect over time and to achieve optimal SKU and bin choices to improve workflow efficiency by consolidating movements.

**Costs & benefits**

4. Moving from one bin to another can take lots of time and is often one of the last things being taken care of inside the warehouse. Having a target of pulling 90 tires an hour shouldn't be hard; it should be as easy as possible! Having to move across the warehouse to multiple bins for the same tire is unnecessary, and that is what this problem aims to solve. Turning a 10-15 min to 5 min.
   
5. What does one consolidation *save*? A scattered SKU costs extra travel on every future pull. 
   - Consolidating a bin saves a ton of future time and effort when it comes to inbound shipments and future pullers. The potential for time savings is huge when it comes to picking the total number of tires at a certain time/cutoff or meeting strict deadlines for a specific transfer load going out the next day.
     
6. When is a move NOT worth it? Construct three concrete examples (e.g., 1 tire of a dead SKU scattered far away). Your engine must decline these.
    - A move is not typically worth it if the number of tires exceeds the amount of space in a given bin, calling that SKU within that time frame.
    - moving a high-count SKU in order to fit another high-count SKU
    - Moving to a bin requires a mixed full bin to be emptied. In this case, the bin will be sorted before SKUs are moved into it.
 
**Scope & differentiation**

7. Commercial WMS systems do "slotting optimization," and why Rubble is better.
   - ABC Analysis: Categorizes inventory by sales velocity or pick frequency. Fast-moving items (A-items) go in the most accessible spots, while slow-moving items (C-items) go in deeper storage
   - Golden Zone Placement: Stores the highest-demand or heaviest products at ergonomic heights (waist to shoulder level) to increase pick speeds and reduce worker fatigue.
   - Fixed vs. Dynamic Slotting: Fixed slotting assigns each SKU a permanent location. Dynamic slotting uses software to recalculate optimal placements continuously based on real-time data.
   - **Rubble inherently aims to incorporate the same practices, but adds an ML layer that adjusts tires based on season, throughput, and counts to save time on pulls.**
     
8. What's explicitly OUT of scope for v1? Write the cut list now (e.g., multi-floor, labor scheduling, real-time re-slotting, receiving optimization).
   - This is ultimately just a demo aiming to create an example of how much more effectively it is to keep the warehouse in orderly condition and create an easier working environment for warehouse workers and the like.
 
**Metrics**

9. Fragmentation Percentage analysis and plan of action
    - Fragmentation is one of our most important metrics. It demonstrates what our current warehouse looks like and compares it to what it could look like. Efficiency is the goal, and having a metric to indicate whether fragmentation is occurring is either a good or bad sign and needs to be handled.
      - In order for fragmentation to be a good indicator, we need to establish guardrails that are mandatory to follow. Due to warehouse fragmentation being inevitable, if an aisle is 100% full, there will be some fragmentation, and it has to be determined whether it is better to adjust and move to overflow or move something out before moving something in.
   
### 0.2 Design exercise — the napkin ROI
 
On one page, estimate: if your old warehouse ran this weekly, how many labor-hours of consolidation would it cost, and how many picker-hours would it save? Use your own floor numbers. Even rough math here is interview gold — almost no candidate does it.
 
### 0.3 Pitfalls
- Skipping this phase. Everything downstream (cost model, stopping rules, evaluation) depends on answers here.
- Picking "fragmentation" as the north star without tying it to time/money. Fragmentation is a proxy; travel time is the real cost.
### 0.4 Deliverables
- `notes/00-framing.md`: all answers, one-liner, metric choices, napkin ROI, cut list.
### 0.5 Done when
You can give a 60-second pitch AND answer "why is this hard?" without mentioning code.

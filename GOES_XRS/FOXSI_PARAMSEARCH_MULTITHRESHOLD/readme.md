# Incorporating Multiple Thresholds into the Parameter Search

Attempting a parameter search that moves away from a single trigger and cancellation condition, and moves to incorporating multiple thesholds that must be met at each new GOES point. In the future, this idea could also incorporate EVE.

### Brain dump of what needs to change: 
---
- general changes: 
	 - Cancellation condition will now be edited to say where it got cancelled. Potential solution would just be changing the "cancelled?" column to 0 (no cancellation), 1 (first thresh), 2, etc. 
	 - Recall should maybe be reconsidered. Now, there is nothing to show on the PR curve that we are cancelling too much on an early trigger. It might be good to have things like PR curves but with cancelling at different thresholds. 
	 - flare categorization matrix would also change into having a few more columns. Could keep a refined version that is the same as what exists now for a simpler option as well.
- `run_paramsearch.py` changes: 
	 - Need to now have an array for each threshold. Will want to keep these separate for the future so that I can try different combos of things for each threshold! I could see this going a few ways, because the thresholds could be dependent on each other enough that I need to do a huge run each time... definitely time to get this on the MSI. 
	 
### Timing of the new simulated launch: 
---
3 minute latency + 30 second discussion + 3 minute countdown

**Minute -1: data that surpasses trigger comes in**
 - discussion begins with the goal of starting the count so that a new datapoint comes in at the 30ish second mark. For the simulation, assume we discuss for 30 seconds then. 
 
**Minute 0: the count begins**
 - at the 30 second mark, new datapoint 1 comes in, and we have **cancellation 1** to surpass. 
 
**Minute 1: two minutes left of count**
 - at the 1:30 mark, new datapoint 2 comes in and we have **cancellation 2** to surpass.
 
**Minute 2: one minute left of count**
 - at the 2:30 mark, new datapoint 3 comes in and we have **cancellation 3** to surpass.
 
**Minute 3: we launch!**

Therefore, we have the trigger and 3 cancellation thresholds. 
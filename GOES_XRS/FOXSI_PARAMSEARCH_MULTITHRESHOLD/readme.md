# Incorporating Multiple Thresholds into the Parameter Search

Attempting a parameter search that moves away from a single trigger and cancellation condition, and moves to incorporating multiple thesholds that must be met at each new GOES point. In the future, this idea could also incorporate EVE.

### Brain dump of what needs to change: 
---
- general changes: 
	 - Cancellation condition will now be edited to say where it got cancelled. Potential solution would just be changing the "cancelled?" column to 0 (no cancellation), 1 (first thresh), 2, etc. 
	 - Recall should maybe be reconsidered. Now, there is nothing to show on the PR curve that we are cancelling too much on an early trigger. It might be good to have things like PR curves but with cancelling at different thresholds. s
- `run_paramsearch.py` changes: 
	 - Need to now have an array for each threshold. Will want to keep these separate for the future so that I can try different combos of things for each threshold! I could see this going a few ways, because the thresholds could be dependent on each other enough that I need to do a huge run each time... definitely time to get this on the MSI. 
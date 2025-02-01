# Uncommon VHDL Process Sensitivity List Bug

This repository demonstrates a subtle but impactful bug in VHDL related to process sensitivity lists. The bug involves a missing sensitivity list element, which leads to the process not updating under certain conditions.

## Bug Description
The `bug.vhdl` file contains a VHDL entity and architecture.  The process inside the architecture intends to register the `data_in` value to `data_out` on each rising edge of the clock. However, the process' sensitivity list only includes `clk`.  If `data_in` changes without a simultaneous `clk` edge, the process will not update the internal signals, leading to incorrect output.
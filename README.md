For the given design, create an assertion module containing the required assertions given below.
Bind the assertion module to the testbench top, execute the simulation, and share the simulation results along with a screenshot of the waveform/output. 


Question 1: Reset Verification
Write SystemVerilog Assertions (SVA) to verify that after an active-low reset:
•	b_wptr is reset to zero. 
•	g_wptr is reset to zero. 
•	full is deasserted. 
•	b_rptr is reset to zero. 
•	g_rptr is reset to zero. 
•	empty is asserted. 
________________________________________
Question 2: Write Pointer Increment
Write an assertion to verify that the binary write pointer increments by one on every rising edge of wclk when:
•	w_en = 1 
•	full = 0 
Otherwise, the write pointer should remain unchanged.
________________________________________
Question 3: Read Pointer Increment
Write an assertion to verify that the binary read pointer increments by one when:
•	r_en = 1 
•	empty = 0 
Otherwise, the read pointer should not change.
Question 4: Full Flag Detection
Write an assertion to verify that whenever
g_wptr_next ==
{~g_rptr_sync[PTR_WIDTH:PTR_WIDTH-1],
 g_rptr_sync[PTR_WIDTH-2:0]}
the full flag is asserted on the next write clock.
________________________________________
Question 5: Empty Flag Detection
Write an assertion to verify that whenever
g_wptr_sync == g_rptr_next
the empty flag becomes high on the next read clock.
________________________________________
Question 6: No Write When FIFO is Full
Write an assertion to verify that if
full == 1
then
•	memory is not written. 
•	binary write pointer does not increment. 
•	Gray write pointer remains unchanged. 
________________________________________
Question 7: No Read When FIFO is Empty
Write an assertion to verify that if
empty == 1
then
•	binary read pointer does not increment. 
•	Gray read pointer remains unchanged. 
________________________________________
Question 8: Pointer Stability
Write assertions to verify that when:
w_en = 0
the write pointer remains stable.
Similarly, verify the read pointer remains stable when
r_en = 0
________________________________________
Question 9: Data Integrity
Write an assertion that verifies:
Every data written into the FIFO is eventually read out in the same order.
This property should ensure FIFO ordering.
________________________________________
Question 10: Simultaneous Read and Write
Write assertions to verify that simultaneous read and write operations occurring on different clocks do not incorrectly assert both full and empty.

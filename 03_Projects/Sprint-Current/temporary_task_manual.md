
As you know, over the past couple of days we have been working on the **alignment overlap resolution algorithm**. I have attached a **diff file** that contains all the changes we made. Please go through this diff carefully and make sure you understand the code that has been implemented.

The next step is to **write unit tests for these functionalities**. Please review the **tests folder** and add the necessary tests in `test_grid.py`.

When writing the tests, try to **reuse existing utilities and helpers already present in the repository**. For example, there are functions such as `generate_data` and `generate_pid_graph` that we could potentially use for constructing test scenarios. In `test_grid.py` there are also functions for creating **distorted or parallel graphs**, which might be useful as well.

Ideally, we should construct test graphs that simulate **semi-overlapping or overlapping symbols within a segment**.

To keep things simple, it would be sufficient to:

- create **one segment** (either vertical or horizontal), and
    
- test the overlap resolution logic on that segment.
    

Specifically, we should write tests for the following methods:

- `_resolve_overlaps_in_segment`
    
- `_shift_segment_to_resolve_overlap`
    
- `resolve_segment_overlaps`
    

Please make sure the tests are **concise, clear, and simple**. Avoid overengineering and **reuse as much of the existing code and utilities in the repository as possible**.
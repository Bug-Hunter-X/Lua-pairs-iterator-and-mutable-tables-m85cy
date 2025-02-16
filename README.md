# Lua pairs iterator and mutable tables

This repository demonstrates a potential issue with Lua's `pairs` iterator when dealing with tables that are modified during iteration.  The `bug.lua` file contains code that recursively iterates a nested table.  If the table structure is altered during the iteration (elements added or removed), the iterator might skip elements or behave unpredictably.

The `bugSolution.lua` file offers a possible workaround.  Instead of directly modifying the table during iteration, changes should be made in a separate step after the iteration is complete.  This ensures that the iterator will consistently traverse all elements present at the start of the iteration. 

**Potential Solutions:**

*   Iterate through a copy of the table to avoid modification issues.
*   Track changes and apply them after iteration.
*   Consider alternative iteration methods (like `ipairs` if applicable) that are less sensitive to structural changes during iteration.

This example highlights the importance of carefully managing table modifications during iteration to avoid unexpected results.
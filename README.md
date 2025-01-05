# Tailwind CSS Flexbox Rounding Error

This repository demonstrates a common, yet subtle bug in Tailwind CSS when using fractional width classes within flexbox containers.  The issue stems from rounding errors that can cause unexpected gaps or overlaps in layout.

## Bug Description

The problem is that `w-1/2` doesn't always translate to exactly 50% width due to floating-point arithmetic.  This can lead to subtle visual discrepancies, especially when combined with flexbox.

## Solution

Several solutions are possible:

*   **Use `flex-grow`:** Instead of fixed widths, let the flex items grow to fill the available space evenly using `flex-grow`. This is generally the cleanest and most robust solution.
*   **Use decimal widths:** If you require precise control, use decimal widths for more granular control e.g. `w-[49.99%]`. 
*   **Parent width constraints**: Ensure the parent container has a defined width (e.g. using `w-full`, `w-[500px]`, etc) to avoid unpredictable behaviour caused by the parent's width being unknown or calculated flexibly

This repository demonstrates both the problem and the solutions.  See `bug.html` and `solution.html` for code examples.
# testplace
Placement Drive **POSSIBLE WORKS**


### Approach of the Program 

1. **Read JSON Files:**  
   - The program reads two JSON files (`testcase1.json` and `testcase2.json`) that contain data in different number bases.

2. **Parse the JSON Data:**  
   - It extracts values from the JSON file using the `JSONParser` and converts them into a usable format.

3. **Extract Keys (`n` and `k`):**  
   - `n` represents the total number of data points.  
   - `k` is the number of points needed for interpolation.

4. **Extract and Convert (x, y) Pairs:**  
   - Each data point consists of:
     - `x`: The x-coordinate (integer).
     - `y`: A value stored in different number bases (binary, octal, decimal, etc.).
   - The program converts `y` from its base to a decimal value using `BigInteger`.

5. **Store the Points in a List:**  
   - Each `(x, y)` pair is stored in an **ArrayList**.

6. **Sort the Points Based on x-values:**  
   - Sorting ensures interpolation works correctly.

7. **Select First k Points for Interpolation:**  
   - Only `k` points are used to compute the final result.

8. **Apply Lagrange Interpolation Formula:**  
   - Lagrange interpolation is used to find the constant term (secret value).  
   - Formula:  
     \[
     P(0) = \sum_{i=0}^{k-1} y_i \prod_{j=0, j \neq i}^{k-1} \frac{(0 - x_j)}{(x_i - x_j)}
     \]
   - This formula helps reconstruct the hidden constant term.

9. **Print the Computed Secret Value:**  
   - The final constant term is printed for each JSON file.

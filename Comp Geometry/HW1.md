1. 
   - To calculate the area of a triangle, we can use the Trapezoid method. Essentially, making a trapezoid between the horizontal axis and two points on a polygon, for every sequential two points in a polygon, will compute its area, as long as going in one direction produces negative area. To upload the condition that points in a counterclockwise direction produce positive area, we will make the left direction positive, and vice versa for right. We can define the formula for the signed area of this type of trapezoid with polygonal points $p_1$ and $p_2$ as
   $$Area = \frac{(p_{1y} + p_{2y})}{2}(p_{1x} - p_{2x})$$
   With $p_1$ being the leftmost point and $p_2$ being the rightmost point to produce a positive area.
   To apply this to a triangle, assume we have points $A$, $B$, and $C$. We can define our area as
   $$Area = \frac{(A_y + B_y)}{2}(A_x - B_x) + \frac{(B_y + C_y)}{2}(B_x - C_x) + \frac{(C_y + A_y)}{2}(C_x - A_x)$$
   To calculate twice the area, just multiply the formula by 2.
   $$2 \cdot Area = (A_y + B_y)(A_x - B_x) + (B_y + C_y)(B_x - C_x) + (C_y + A_y)(C_x - A_x)$$
   Now we can expand terms
   $$2 \cdot Area = A_yA_x - B_yB_x - A_yB_x + B_yA_x + B_yB_x - C_yC_x - B_yC_x + C_yB_x + C_yC_x - A_yA_x - C_yA_x + A_yC_x$$
   and simplify
   $$2 \cdot Area = A_yB_x - B_yA_x + B_yC_x - C_yB_x - C_yA_x + A_yC_x$$
   This is the formula we were given, and so we can now prove the second part. 
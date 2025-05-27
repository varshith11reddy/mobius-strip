# mobius-strip
calculation of surface area and edge length along with visualization

functionality of code:

1) Import
    numpy- mathematical calculations
    simpson- Numerical Integration
    matPlotLib - 3D visualization

2) Class MobiusStrip Initialization
   R - radius of the Mobius strip’s center circle
   w - width of the strip
   n - resolution (number of sample points)
   u - array of parameter values along the strip length (0 to 2π)
   v - array of parameter values across the strip width (-w/2 to w/2)
   meshgrid(U, V) - create 2D grids of parameters for surface computation
   computes 3D coordinates (X, Y, Z) of the Mobius strip surface

3) Method compute_mesh
   calculates X, Y, Z coordinates of the Mobius strip using parametric equations
   uses cosine and sine functions of parameters U and V (as per formula)
   returns 3D mesh arrays representing the surface

4) Method surface_area
   calculates gradients (partial derivatives) of X, Y, Z with respect to parameters u and v
   computes cross product of tangent vectors to find surface element area
   calculates infinitesimal area elements dA as the magnitude of the cross product
   integrates dA over the entire parametric domain using double Simpson’s rule
   returns total surface area approximation

5) Method edge_length
   computes 3D coordinates along one edge of the Möbius strip (at v = w/2)
   calculates differences between consecutive edge points to find segment lengths
   sums segment lengths to estimate total edge length of the strip

6) Method plot
  sets up a 3D figure and axis using matplotlib
  plots the Möbius strip surface with a smooth plasma colormap and no edge lines
  removes axes for clean visualization
  displays the 3D plot window

7) Execution block (if __name__ == "__main__":)
  creates a MobiusStrip instance with specified parameters
  prints calculated surface area and edge length formatted to 4 decimals
  calls the plot method to visualize the strip

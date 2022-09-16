# Tasmania-Conservation-Prioritization
We provide the supplementary plots of the case study at Tasmania Island for our paper titled "Prioritization via Parametric Optimization". The data for this case study is retrieved from [R package prioritizr](https://cran.r-project.org/web/packages/prioritizr/vignettes/tasmania.html).

The Tasmania Island is divided into 1130 zones, and the cost of protecting each site is visulized below. There are 62 species of interests, we pick two representative species and visulize its' distribution over the entire map. Notice that different species may spread out over different regions of the map, which brings ectra difficulty for the work of conservation planning. We target to protect 17% of the total amount for each species. 

<table align="center">
   <tr>
     <td align="center">Planning Cost</td>
     <td align="center">Species Distribution</td>
   </tr>
   <tr>
      <td><img src="https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/Cite_Cost.png" width = 400px></td>
      <td><img src="https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/Feature_Plot.png" width = 400px></td>
  </tr>
</table>

Among the thousand zones, 257 lock-in zones that have already been protected, and we aim to protect more zones under a progressively revealed budget uniformly ranges from 8700 to 9600. We implement scenario-wise optimization method, optimal prioritization method, heuristic prioritization method, forward-greedy method and backward-greedy method on this problem，and visulize the relative penalty of disconnectivity and shortfall for the later four methods over the first method as follows.

<table align="center">
   <tr>
     <td align="center">Relative Penalty</td>
   </tr>
   <tr>
      <td><img src="https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/Relative_Cost.png" width = 500px></td>
  </tr>
</table>

We plot below the evolution of protected sites when budget increases for all methods. The lock-in zones are marked by color index 2, the protected zones are marked by color index 1 and the unprotected zones are marked by color index 0. (Please refresh the page if the gifs don't play in sync.)


<table>
  <tr>
    <td align="center">Scenario-Wise Optimization Method</td>
    <td align="center">Optimal Prioritization Method</td>
    <td align="center">Heuristic Prioritization Method</td>
  </tr>
  <tr>
    <td><img src = "https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/ScenOptAnimation.gif" width = 300px></td>
    <td><img src = "https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/OptPrioAnimation.gif" width = 300px></td>
    <td><img src = "https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/HeuPrioAnimation.gif" width = 300px></td>
   </tr> 
</table>

<table align="center">
   <tr>
     <td align="center">Forward-Greedy Method</td>
     <td align="center">Backward-Greedy Method</td>
   </tr>
   <tr>
      <td><img src="https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/ForGreedyAnimation.gif" width = 300px></td>
      <td><img src="https://github.com/ConservationPrioritization/Tasmania-Conservation-Prioritization/blob/main/BackGreedyAnimation.gif" width = 300px></td>
  </tr>
</table>

Note that the solution from scenario-wise optimization method is not nested, which indicates the solution is not suitable for implementation under the progressively revealed budget enviroment. The optimal prioritization method, produce a nested solution and at the same time, always has a satisfying performance in every scenario. In constrast, it is hard for the greedy methods to balance the trade-off between the penalty of disconnectivity (require the protected zones to be connected) and shortfall to the protection target of all species (require the protected zones to be scattered). We investigate the cost component of disconnectivity and shortfall in the objective function, and find that our prioritization method outperforms the forward-greedy method regarding both penalties. The backward-greed method provides a more concentrated solution, showing a smaller penalty of disconnectivity compared to our method, but at the price of significantly higher shortfall cost. 

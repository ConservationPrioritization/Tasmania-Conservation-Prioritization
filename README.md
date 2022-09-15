# Tasmania-Conservation-Prioritization
We provide the supplementary plots of the case study at Tasmania Island for our paper titled "Prioritization via Parametric Optimization". The data for this case study is retrieved from [R package prioritizr](https://cran.r-project.org/web/packages/prioritizr/vignettes/tasmania.html).


We also plot the selected zones under different methods at an intermediate stage with budget $9100$. As shown in Figure \ref{fig:planning_CR_uniform}, both optimal and heuristic prioritization methods largely mimic the pattern of selected zones under the scenario-wise optimal solution, but leaves sufficient spaces to re-optimize the conservation plan when the budget changes. Note that the species are sparsely distributed over the island (cf. Figure \ref{fig:case_CR}(b)), and hence it is hard for the greedy methods to balance the trade-off between the penalty of disconnectivity (require the protected zones to be connected) and shortfall to the protection target of all species (require the protected zones to be scattered). We investigate the cost component of disconnectivity and shortfall in the objective function, and find that our prioritization method outperforms the forward-greedy method regarding both penalties. The backward-greed method provides a more concentrated solution, showing a smaller penalty of disconnectivity compared to our method, but at the price of significantly higher shortfall cost.


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

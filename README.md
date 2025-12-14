# Third Down Performance Analysis of the NFL  
**Will Schreyer**

## 1. Introduction
In American football, third downs are the most strategically significant situations because they serve as pivotal points where drives are either extended or stopped. Third downs are more constrained than early downs, when offenses can use all of their tactical choices. The high pressure of the circumstance highlights both execution and error; the defense is completely aware of the offensive goal, and the yardage needed is clear. Because of these factors, third-down plays offer a particularly useful perspective for assessing team trends, long-term patterns in play-calling behavior, the dependability of individual players, and the impact of environmental factors like wind and temperature.

This study examines third-down outcomes, strategic evolution, and the relationship between performance and external variables using NFL play-by-play data from 2010 to 2025 from the **nflfastR** database.

The nflfastR dataset offers structured, high-resolution data on every NFL play, including yards-to-go, play type, game context, environmental descriptors, EPA (Expected Points Added), and other advanced metrics. The dataset includes **339 variables per observation** and approximately **746,000 plays** between 2010 and 2025. Weather data was standardized into quantitative bins for wind and temperature. Third downs were divided into three categories:
- **Short:** ≤ 3 yards  
- **Medium:** 4–6 yards  
- **Long:** 7+ yards  

The analysis followed four phases:
1. Play-calling trends by distance and time  
2. Third-down conversion outcomes  
3. Environmental impacts on strategy and execution  
4. EPA-based comparisons of offensive and defensive efficiency  

---

## 2. Evolution of Third-Down Play Calling
A central question in NFL analytics is whether third-down strategy has evolved over time. 
**Figure 1** 
(“Number of Runs vs. Passes on 3rd Down by Distance”) illustrates play-calling volume from 2010 to 2025.
![“Number of Runs vs. Passes on 3rd Down by Distance”](results/passvsrunbyyear.pdf)

Passing overwhelmingly dominates **medium and long** third downs, accounting for roughly **85–90%** of plays in long-yardage situations across most seasons. Run frequency steadily declines in these categories, reflecting a league-wide shift toward pass-heavy offenses driven by improved quarterback play, spread concepts, and rule changes favoring receivers.

In **short-yardage** situations, however, recent seasons show a clear increase in rushing attempts. Since the emergence of the Philadelphia Eagles’ *“tush push”* in 2021 and the rise of dual-threat quarterbacks, teams have deliberately re-emphasized quarterback power and interior run concepts. This marks a strategic shift away from earlier pass-dominant short-yardage approaches.

---

## 3. Longitudinal Third-Down Conversion Trends
While play-calling preferences have changed, conversion rates tell a different story. 
**Figure 2** 
(“NFL 3rd Down Conversion Rates Over Time by Distance”) shows conversion percentages from 2010 to 2025.
![“NFL 3rd Down Conversion Rates Over Time by Distance”](results/passvsrunconversionbyyear.pdf)

- **Short yardage:** consistently highest (≈ 55–70%)  
- **Medium yardage:** stable around the mid-40% range  
- **Long yardage:** persistently lowest (≈ 20–30%)  

Despite major strategic evolution, conversion rates remain remarkably stable. This suggests that defensive adaptations largely offset offensive innovation, preserving the inherent difficulty of third-down situations.

---

## 4. Play-Calling Efficiency by Play Type
**Figure 3** 
(“Proportion of Runs vs. Passes Completed on 3rd Down by Distance”) compares conversion efficiency by play type.
![“Proportion of Runs vs. Passes Completed on 3rd Down by Distance”](results/passvsrunconversionbyyard.pdf)

Passing clearly outperforms rushing in **medium and long** yardage scenarios. In **short yardage**, however, the gap between rushing and passing success has narrowed in recent seasons. Rushing efficiency rises notably after 2018, coinciding with the adoption of power-based short-yardage packages and quarterback-run designs.

Overall, passing remains essential at longer distances, while rushing has regained strategic value in short-yardage situations.

---

## 5. Temperature Effects on Third-Down Performance

### 5.1 Temperature and Play Calling
**Figure 4** 
(“Effect of Temperature on 3rd Down Play Calling”) shows that temperature has minimal influence on play selection in medium and long yardage, where passing remains dominant across all temperature bins.
![“Effect of Temperature on 3rd Down Play Calling”](results/temppropofplaycalls.pdf)

In short-yardage situations, teams slightly reduce passing in cold conditions and rely more on rushing, likely due to ball-handling and footing concerns. However, these effects are modest.

### 5.2 Temperature and Conversion Rates
**Figure 5** 
(“Effect of Temperature on 3rd Down Conversion Rate”) 
![“Effect of Temperature on 3rd Down Conversion Rate”](results/tempthirddownconversionrate.pdf)

indicates that:
- Long-yardage conversions are largely temperature-invariant  
- Medium-yardage passing declines slightly in extreme cold  
- Short-yardage passing dips in cold weather, while rushing weakens in extreme heat  

Overall, temperature affects execution more than strategy, and its total impact is limited.

---

## 6. Wind Effects on Third-Down Performance

### 6.1 Wind and Play Calling
Wind introduces a disruptive force on passing. 
**Figure 6** 
![“Effect of Wind on 3rd Down Play Calling”](results/windpropofplays.pdf)
(“Effect of Wind on 3rd Down Play Calling”) shows that while passing remains dominant in medium and long yardage, run frequency increases noticeably in strong and severe wind—especially in short-yardage situations.


### 6.2 Wind and Conversion Rates
**Figure 7** 
![“Effect of Wind Speed on 3rd Down Conversion Rate”](results/windthirddownconversionrate.pdf)
(“Effect of Wind Speed on 3rd Down Conversion Rate”) reveals a clear linear decline in **passing conversion rates** as wind speed increases. Medium-yardage passing is particularly sensitive to wind, while rushing efficiency remains largely unaffected.

Wind emerges as the most impactful environmental variable affecting both strategy and execution.

---

## 7. Team-Level EPA Analysis
EPA provides a context-aware efficiency metric.  
- **Figure 8:** Team Offensive vs. Defensive Third-Down EPA (2010–2025)  
- **Figure 9:** Same metric for the 2025 season  

Most teams cluster near league average, with few excelling on both offense and defense. Long-term performance reflects organizational identity more than season-specific variation. Teams rarely sustain elite third-down efficiency on both sides of the ball.

---

## 8. Player Reliability Analysis Using Empirical Bayes
Raw conversion percentages can be misleading, especially with small samples. **Figure 10** applies **Empirical Bayesian (EB) shrinkage**, combining player data with the league-average conversion baseline (~45%).

For example, a 12-for-20 (60%) performer shrinks to an EB estimate of **52.5%**, reflecting uncertainty. Players are ranked using **95% confidence lower bounds**, rewarding consistency over volatility.

Key findings:
- **2025 most reliable:** Justin Herbert  
- **2025 least reliable:** Travis Hunter  
- **2010–2025 most reliable:** Josh Allen  
- **2010–2025 least reliable:** Jonathan Mingo  

EB modeling produces more stable and meaningful player evaluations.

---

## 9. Conclusion
Third-down performance provides a powerful lens into NFL strategy, execution, environmental effects, and organizational identity. Despite major shifts in play-calling—especially increased passing—conversion rates have remained remarkably stable from 2010 to 2025. Wind has a significant and measurable impact on both strategy and success, while temperature plays a minor role.

EPA analysis shows that teams rarely excel on both offensive and defensive third downs simultaneously, reinforcing the idea that third-down efficiency reflects long-term structural tendencies rather than short-term randomness. Overall, the core dynamics of third downs—pressure, constraint, and strategic importance—remain resilient despite evolving tactics and increasingly sophisticated analytics.

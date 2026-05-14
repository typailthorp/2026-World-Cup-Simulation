# 2026-World-Cup-Simulation

A machine learning and simulation project that predicts international football match outcomes and simulates the 2026 FIFA World Cup.

Link to project: [Add your GitHub repo link here]

---

## How It's Made:
**Tech used:** Python, Pandas, NumPy, Scikit-learn, Matplotlib

This project combines historical international match data with FIFA rankings to build a predictive model and simulate a full tournament structure.

I first cleaned and merged match data with ranking data, ensuring that each match used only the most recent available rankings at the time to avoid data leakage. I then engineered features such as rank differential, points differential, and recent team form.

Using these features, I trained a classification model to predict match outcomes (home win, away win, draw). The model achieved approximately 56% accuracy, outperforming a baseline of ~47%.

I then used the model’s predicted probabilities to simulate the 2026 World Cup:
- Simulated group stage results using a points-based system  
- Built a realistic knockout bracket, including third-place qualification  
- Ran 1,000 Monte Carlo simulations to estimate win probabilities  

The results showed that teams like France, Spain, and Argentina emerged most frequently as tournament winners, while also highlighting the high level of uncertainty in knockout competitions.

---

## Optimizations

- Replaced a greedy third-place assignment approach with a global assignment method to ensure valid tournament brackets  
- Used time-aware merging (`merge_asof`) to prevent future data leakage  
- Refactored simulation logic to separate group stage and knockout stages for clarity and reusability  

---

## Lessons Learned:

This project reinforced how important data preparation is in building reliable models. Handling time correctly (ensuring no future data leaked into predictions) was one of the most critical parts of the pipeline.

I also gained a deeper understanding of how feature engineering impacts model performance, particularly when working with limited or noisy data. Adding features such as recent form and goal differential helped capture more realistic team performance.

Finally, building the tournament simulation highlighted how small modeling assumptions can significantly impact results, especially in systems with high uncertainty like sports outcomes.

This project pushed me to think beyond just model accuracy and focus on building a complete, end-to-end analytical system.

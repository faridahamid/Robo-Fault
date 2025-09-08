# 📑 Full Figure Index with Descriptions (51 Figures)

---

## 1. Imputation Comparisons (Null Handling)

1. **Imputation comparison – Current_J0**  
   Shows how different null-filling methods (KNN, Linear, MissForest) handle missing values in Current_J0.  
   ![Figure 1](J0.png)

2. **Imputation comparison – Current_J1**  
   Same as above, focused on Current_J1. Highlights small differences between methods.  
   ![Figure 2](cj1.png)

3. **Imputation comparison – Current_J2**  
   Null handling for Current_J2; MissForest tends to better preserve natural fluctuations.  
   ![Figure 3](cj2.png)

4. **Imputation comparison – Current_J3**  
   Shows effects of filling nulls on Current_J3’s dynamic range.  
   ![Figure 4](cj3.png)

5. **Imputation comparison – Current_J4**  
   Comparison of three strategies on Current_J4.  
   ![Figure 5](cj4.png)

6. **Imputation comparison – Current_J5**  
   Final joint current; null handling preserves extreme swings.  
   ![Figure 6](cj5.png)

7. **Imputation comparison – Temperature_T0**  
   Different fills for T0 temperature; smoother interpolation visible.  
   ![Figure 7](T0.png)

8. **Imputation comparison – Temperature_J1**  
   Same comparison for J1 temperature; temperatures drift more slowly.  
   ![Figure 8](tj1.png)

9. **Imputation comparison – Temperature_J2**  
   Highlights how each method handles rare nulls in J2 temps.  
   ![Figure 9](tj2.png)

10. **Imputation comparison – Temperature_J3**  
    Null-handling impact on J3 temps.  
    ![Figure 10](tj3.png)

11. **Imputation comparison – Temperature_J4**  
    Comparison across J4 temperature sensor.  
    ![Figure 11](tj4.png)

12. **Imputation comparison – Temperature_J5**  
    Null handling for J5 temp values.  
    ![Figure 12](tj5.png)

13. **Imputation comparison – Speed_J0**  
    Null handling on J0 speed, shows linear interpolation vs KNN smoothing.  
    ![Figure 13](sj0.png)

14. **Imputation comparison – Speed_J1**  
    Effect of fills on J1 speed series.  
    ![Figure 14](sj1.png)

15. **Imputation comparison – Speed_J2**  
    Speed profile with null handling methods compared.  
    ![Figure 15](sj2.png)

16. **Imputation comparison – Speed_J3**  
    Shows interpolation artifacts vs KNN smoothing for J3 speeds.  
    ![Figure 16](sj3.png)

17. **Imputation comparison – Speed_J4**  
    Comparison of filled values for J4 speeds.  
    ![Figure 17](sj4.png)

18. **Imputation comparison – Speed_J5**  
    Filling strategies compared on J5 speeds.  
    ![Figure 18](sj5.png)

19. **Imputation comparison – Tool Current**  
    Null-filling impact on tool current, important for fault analysis.  
    ![Figure 19](tc.png)

---

## 2. Data Balance & Distribution

20. **Balance of Grip Lost**  
    Bar chart showing class imbalance between grip-lost and normal cycles.  
    ![Figure 20](1.png)

21. **Balance of Protective Stop**  
    Distribution of cycles with/without protective stops.  
    ![Figure 21](2.png)

---

## 3. Correlation & Feature Relationships

22. **Numeric Correlation Heatmap (basic)**  
    Heatmap of correlations; clusters indicate redundancy among features.  
    ![Figure 22](3.png)

23. **Numeric Correlation Heatmap (annotated)**  
    Same as above but with coefficients; helps in feature selection.  
    ![Figure 23](4.png)

24. **Temperature_T0 vs Temperature_J1 Correlation**  
    Scatter plot; shows near-linear correlation between two sensors.  
    ![Figure 24](5.png)

---

## 4. Tool Current vs Failures

25. **Tool Spikes per Cycle vs Grip Loss**  
    Cycles with grip-loss often have more spikes in tool current.  
    ![Figure 25](6.png)

26. **Tool Spikes per Cycle vs Protective Stop**  
    Protective stops correspond to increased current variability.  
    ![Figure 26](7.png)

27. **Tool Current Across Cycles with Faults**  
    Mean & max tool current trends with faults marked.  
    ![Figure 27](8.png)

28. **Tool Current Variability Across Cycles**  
    Std deviation per cycle; fault cycles more unstable.  
    ![Figure 28](9.png)

29. **Rolling Trend of Tool Current**  
    20-cycle rolling mean smooths trend; shows gradual drifts.  
    ![Figure 29](10.png)

30. **Tool Current vs Fault Rate**  
    Correlates higher average current with higher rolling fault rates.  
    ![Figure 30](11.png)

31. **Distribution of Tool Current Mean (Protective Stop)**  
    Stop cycles slightly shift distribution lower.  
    ![Figure 31](12.png)

32. **Distribution of Tool Current Mean (Grip Loss)**  
    Grip-loss cycles skew distribution compared to normal.  
    ![Figure 32](13.png)

---

## 5. Joint Currents

33. **Mean Currents per Joint (Protective Stop)**  
    J1 & J2 currents higher during stops.  
    ![Figure 33](14.png)

34. **Mean Currents per Joint (Grip Loss)**  
    Grip loss correlates with reduced J2/J3 current.  
    ![Figure 34](15.png)

35. **Time-Series Mean Currents per Joint (J0–J5)**  
    Cycle-level current per joint with fault markers.  
    ![Figure 35](16.png)

36. **Boxplots of Joint Currents**  
    Distribution of joint currents with outliers.  
    ![Figure 36](17.png)

37. **Joint Current Asymmetry (Forward–Backward)**  
    Direction imbalance visible in J2 & J3.  
    ![Figure 37](18.png)

38. **Joint Current Asymmetry split by Grip Loss**  
    Grip-loss cycles show stronger asymmetries.  
    ![Figure 38](19.png)

---

## 6. Joint Speeds

39. **Mean Speeds per Joint (Protective Stop)**  
    Stops correspond to reduced J2 & J3 speeds.  
    ![Figure 39](20.png)

40. **Mean Speeds per Joint (Grip Loss)**  
    Grip-loss linked with slower J2/J3 speeds.  
    ![Figure 40](21.png)

41. **Boxplots of Joint Speeds**  
    Speed distributions with extreme outliers.  
    ![Figure 41](22.png)

---

## 7. Motion Abruptness & Power

42. **Motion Abruptness (Acceleration Std) – Protective Stop**  
    Stops show higher abruptness in J2.  
    ![Figure 42](23.png)

43. **Motion Abruptness (Acceleration Std) – Grip Loss**  
    Grip-loss shows sharper accelerations.  
    ![Figure 43](24.png)

44. **Total Effort (Current × Speed) – Protective Stop**  
    Power consumption higher in J2 during stops.  
    ![Figure 44](25.png)

45. **Total Effort (Current × Speed) – Grip Loss**  
    J2 again dominates during grip-loss.  
    ![Figure 45](26.png)

---

## 8. Timing & Lag Analysis

46. **Average Lead/Lag (Current vs Speed)**  
    Shows phase differences; J0 & J4 shift timing during stops.  
    ![Figure 46](27.png)

47. **Within-Cycle Correlation (Temperature vs Power)**  
    Weak but noticeable correlation in J1 & J2.  
    ![Figure 47](28.png)

48. **Best Thermal Lag per Sensor**  
    Heat buildup delays of 5–10s observed.  
    ![Figure 48](29.png)

49. **Peak Temp–Work Correlation**  
    Strongest correlations at J2 and T0.  
    ![Figure 49](output.png)

---

## 9. Temperatures

50. **Mean Joint Temperatures over Time**  
    Temps rise gradually during operations.  
    ![Figure 50](output2.png)

51. **Boxplots of Joint Temperatures**  
    J4/J5 consistently hotter; outliers visible.  
    ![Figure 51](early_placeholder_20.png)

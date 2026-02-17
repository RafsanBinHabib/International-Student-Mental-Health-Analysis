# 🌏 International Student Mental Health Analysis

A data analysis project exploring the relationship between length of stay and mental health outcomes among international university students in Japan.

---

## 📋 Project Overview

This project analyzes survey data from a Japanese international university (2018) to investigate how the duration of stay affects mental health indicators among international students. The study examines three key metrics:
- Depression (PHQ-9 test scores)
- Social connectedness (SCS test scores)  
- Acculturative stress (ASISS test scores)


## 🎯 Key Findings

The analysis reveals interesting patterns in how the length of stay correlates with mental health metrics:

| Stay (Years) | Student Count | Avg Depression | Avg Social Connectedness | Avg Acculturative Stress |
|--------------|---------------|----------------|-------------------------|-------------------------|
| 10 | 1 | 13.00 | 32.00 | 50.00 |
| 8 | 1 | 10.00 | 44.00 | 65.00 |
| 7 | 1 | 4.00 | 48.00 | 45.00 |
| 6 | 3 | 6.00 | 38.00 | 58.67 |
| 5 | 1 | 0.00 | 34.00 | 91.00 |
| 4 | 14 | 8.57 | 33.93 | 87.71 |
| 3 | 46 | 9.09 | 37.13 | 78.00 |
| 2 | 39 | 8.28 | 37.08 | 77.67 |
| 1 | 95 | 7.48 | 38.11 | 72.80 |


## 📊 Data Description

The dataset includes the following key variables:

| Field | Description |
|-------|-------------|
| `inter_dom` | Student type (International/Domestic) |
| `stay` | Length of stay in years |
| `todep` | Depression score (PHQ-9 test) |
| `tosc` | Social connectedness score (SCS test) |
| `toas` | Acculturative stress score (ASISS test) |
| `age` | Student age |
| `academic` | Academic level (Undergraduate/Graduate) |
| `japanese_cate` | Japanese language proficiency |
| `english_cate` | English language proficiency |


## 🔍 Analysis Methodology

### Tools Used
- **PostgreSQL** for data querying and analysis
- SQL aggregations and statistical functions

### Key SQL Query
```sql
SELECT 
    stay, 
    COUNT(*) AS count_int, 
    ROUND(AVG(todep), 2) AS average_phq, 
    ROUND(AVG(tosc), 2) AS average_scs, 
    ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```

## 📈 Insights
- Sample Distribution: Most international students (95) have a stay duration of 1 year
- Depression Patterns: Average depression scores range from 0 to 13, with longer stays showing varying impacts
- Social Connectedness: Scores remain relatively stable across different stay durations (32-48 range)
- Acculturative Stress: Shows interesting variations, peaking at mid-length stays (4-5 years)


## 🎓 Context
This analysis is based on a 2018 survey conducted at a Japanese international university. The original study found that international students have a higher risk of mental health difficulties compared to the general population, with social connectedness and acculturative stress being key predictors of depression.


## 💡 Future Work
Potential extensions to this analysis:
- Compare international vs domestic student mental health metrics
- Analyze the impact of language proficiency on mental health outcomes
- Investigate the correlation between age and mental health scores
- Time-series analysis of mental health trends over stay duration


## 📝 License
This project is for educational purposes. Please cite the original study when using this data.


## 🙏 Acknowledgments
- Original study and data collection team at the Japanese International University
- DataCamp for project inspiration and structure
- PostgreSQL community for excellent documentation


## 📬 Contact
- [LinkedIn profile](https://www.linkedin.com/in/rafsanbinhabib23/)
- [Read my Blogs](https://medium.com/@rafsanbinhabib23)
  
---

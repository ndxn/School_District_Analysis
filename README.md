# School District Analysis

## Introduction
After completing and presenting the school district analysis to Maria, it was discovered that there were anomalies with the test scores of the 9th grade class at Thomas High School. At Maria's direction, this new analysis removes the scores from the data but includes the student record in the analysis. This process includes replacing all the test values from the subset with the NaN, the numerical datatype that represents undefined or unrepresentable. 

Because the instructions were to retain the students in the analysis, the arithmetic means will be calculated using the Python ```mean()``` function instead of the NumPy ```nanmean()``` function. 

## Analysis
It has been noticed that removing the test scores of the 9th grade students at Thomas High School has impacted the results throughout the analyses conducted. Relevant tables from the revised analysis, with the reading and math test scores and resultant calculated passing rates, as well as corresponding tables from the original analysis have been provided below. The general trend is that average scores and percent-passing rates see a decline when the potentially-anomalous scores are included in the analysis. Discussion of this will follow at the end of this document.  


### District Summary

The district summary aggregates all the data across all schools and grades to deliver a global view of the performance of the district. Tables 1a and 1b show the after and before analysis.

**Table 1a.** District Summary after Removal of Test Scores
|    |   Total Schools | Total Students   | Total Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|---:|----------------:|:-----------------|:---------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
|  0 |              15 | 39,170           | $24,649,428.00 |                 78.9 |                    81.9 |               74 |                  85 |                  64 |

**Table 1b.** District Summary before Removal of Test Scores
|    |   Total Schools | Total Students   | Total Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|---:|----------------:|:-----------------|:---------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
|  0 |              15 | 39,170           | $24,649,428.00 |                   79 |                    81.9 |               75 |                  86 |                  65 |

As can be seen from the above tables, dropping the scores from the THS 9th grade class results in lower average scores across the district. The reading scores are lower, but within the tolerance of the rounding function. However, the percentage of students passing the reading exam is lower with the scores omitted.

In short, all metrics appear worse with the THS scores removed. This indicates that the THS 9th grade scores were higher than the overall average. This could indicate that THS is a higher performing school or that there are other anomalies in the testing data. 

### School Summary

For the school summary analyisis, the data  Thomas High School has been filtered out as the remainder of the high schools are not impacted by the change to the calculated scores at THS. These tables, after and before the removal of the scores, are provided below.

**Table 2a.** Thomas High School Record from School Summary DataFrame after Removal of Test Scores
|                               | Thomas High School   |
|:------------------------------|:---------------------|
| School Type                   | Charter              |
| Total Students                | 1635                 |
| Total School Budget           | $1,043,130.00        |
| Per Student Budget            | $638.00              |
| Average Math Score            | 83.35093696763202    |
| Average Reading Score         | 83.89608177172062    |
| % Passing Math                | 66.91131498470948    |
| % Passing Reading             | 69.66360856269112    |
| % Overall Passing             | 65.07645259938838    |
| Spending Ranges (Per Student) | $630-644             |
| School Size                   | Medium (1000-2000)   |

**Table 2b.** Thomas High School Record from School Summary DataFrame before Removal of Test Scores
|                               | Thomas High School   |
|:------------------------------|:---------------------|
| School Type                   | Charter              |
| Total Students                | 1635                 |
| Total School Budget           | $1,043,130.00        |
| Per Student Budget            | $638.00              |
| Average Math Score            | 83.4183486238532     |
| Average Reading Score         | 83.84892966360856    |
| % Passing Math                | 93.27217125382263    |
| % Passing Reading             | 97.30886850152906    |
| % Overall Passing             | 90.94801223241589    |
| Spending Ranges (Per Student) | $630-644             |
| School Size                   | Medium (1000-2000)   |

For THS, across the board, the scores in both subjects are lower as the percentage passing, as measured individually as well as aggregated. What should be noted about this data is that, while the average scores barely change--for all metrics, the average scores are in the range of 83--the percentage of pupils passing drops from the range of percents in the 90s to the range of percents in the 60s. This would indicate that there were sufficient enough scores in the middle, yet passing range to buffer what must be a large number of scores within the removed data that were under the passing threshold of 70.

### School Rankings

The overall ranking of schools shows what might be the most drastic of impacts associated with the removal of the 9th grade testing--without the data, THS drops significantly in ranking by overall passing rates. The tables below are the top 10 rankings.

**Table 3a.** Ranking of High Schools based on Performance After Removal of Test Scores
|                     | School Type   |   Total Students | Total School Budget   | Per Student Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------------|:--------------|-----------------:|:----------------------|:---------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Cabrera High School | Charter       |             1858 | $1,081,356.00         | $582.00              |              83.0619 |                 83.9758 |          94.1335 |             97.0398 |             91.3348 |
| Griffin High School | Charter       |             1468 | $917,500.00           | $625.00              |              83.3515 |                 83.8168 |          93.3924 |             97.139  |             90.5995 |
| Wilson High School  | Charter       |             2283 | $1,319,574.00         | $578.00              |              83.2742 |                 83.9895 |          93.8677 |             96.5396 |             90.5826 |
| Pena High School    | Charter       |              962 | $585,858.00           | $609.00              |              83.8399 |                 84.0447 |          94.5946 |             95.9459 |             90.5405 |
| Wright High School  | Charter       |             1800 | $1,049,400.00         | $583.00              |              83.6822 |                 83.955  |          93.3333 |             96.6111 |             90.3333 |
| Shelton High School | Charter       |             1761 | $1,056,600.00         | $600.00              |              83.3595 |                 83.7257 |          93.8671 |             95.8546 |             89.8921 |
| Holden High School  | Charter       |              427 | $248,087.00           | $581.00              |              83.8033 |                 83.815  |          92.5059 |             96.2529 |             89.2272 |
| Thomas High School  | Charter       |             1635 | $1,043,130.00         | $638.00              |              83.3509 |                 83.8961 |          66.9113 |             69.6636 |             65.0765 |
| Bailey High School  | District      |             4976 | $3,124,928.00         | $628.00              |              77.0484 |                 81.034  |          66.6801 |             81.9333 |             54.6423 |
| Ford High School    | District      |             2739 | $1,763,916.00         | $644.00              |              77.1026 |                 80.7463 |          68.3096 |             79.299  |             54.2899 |

**Table 3b.** Ranking of High Schools based on Performance before Removal of Test Scores
|                     | School Type   |   Total Students | Total School Budget   | Per Student Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------------|:--------------|-----------------:|:----------------------|:---------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Cabrera High School | Charter       |             1858 | $1,081,356.00         | $582.00              |              83.0619 |                 83.9758 |          94.1335 |             97.0398 |             91.3348 |
| Thomas High School  | Charter       |             1635 | $1,043,130.00         | $638.00              |              83.4183 |                 83.8489 |          93.2722 |             97.3089 |             90.948  |
| Griffin High School | Charter       |             1468 | $917,500.00           | $625.00              |              83.3515 |                 83.8168 |          93.3924 |             97.139  |             90.5995 |
| Wilson High School  | Charter       |             2283 | $1,319,574.00         | $578.00              |              83.2742 |                 83.9895 |          93.8677 |             96.5396 |             90.5826 |
| Pena High School    | Charter       |              962 | $585,858.00           | $609.00              |              83.8399 |                 84.0447 |          94.5946 |             95.9459 |             90.5405 |
| Wright High School  | Charter       |             1800 | $1,049,400.00         | $583.00              |              83.6822 |                 83.955  |          93.3333 |             96.6111 |             90.3333 |
| Shelton High School | Charter       |             1761 | $1,056,600.00         | $600.00              |              83.3595 |                 83.7257 |          93.8671 |             95.8546 |             89.8921 |
| Holden High School  | Charter       |              427 | $248,087.00           | $581.00              |              83.8033 |                 83.815  |          92.5059 |             96.2529 |             89.2272 |
| Bailey High School  | District      |             4976 | $3,124,928.00         | $628.00              |              77.0484 |                 81.034  |          66.6801 |             81.9333 |             54.6423 |
| Ford High School    | District      |             2739 | $1,763,916.00         | $644.00              |              77.1026 |                 80.7463 |          68.3096 |             79.299  |             54.2899 |
While long and potentially cumbersome, it is important to notice that, if the scores of THS's 9th grade class are dropped from the analysis, the school drops from 2nd to 8th. This finding should be concerning for both district and THS officials.

### Analysis of Math and Reading Scores by Grade

The following charts illustrate, by subject, the after and before scores by grade level at all schools in the district. When the average score by grade and the passing rates are calculated and the scores are removed, it should be noted that the result are the same NaN numeric data type. 

**Table 4a.** Math Scores after Removal of Test Scores
|                       |   9th |   10th |   11th |   12th |
|:----------------------|------:|-------:|-------:|-------:|
| Bailey High School    |  77.1 |   77   |   77.5 |   76.5 |
| Cabrera High School   |  83.1 |   83.2 |   82.8 |   83.3 |
| Figueroa High School  |  76.4 |   76.5 |   76.9 |   77.2 |
| Ford High School      |  77.4 |   77.7 |   76.9 |   76.2 |
| Griffin High School   |  82   |   84.2 |   83.8 |   83.4 |
| Hernandez High School |  77.4 |   77.3 |   77.1 |   77.2 |
| Holden High School    |  83.8 |   83.4 |   85   |   82.9 |
| Huang High School     |  77   |   75.9 |   76.4 |   77.2 |
| Johnson High School   |  77.2 |   76.7 |   77.5 |   76.9 |
| Pena High School      |  83.6 |   83.4 |   84.3 |   84.1 |
| Rodriguez High School |  76.9 |   76.6 |   76.4 |   77.7 |
| Shelton High School   |  83.4 |   82.9 |   83.4 |   83.8 |
| Thomas High School    | nan   |   83.1 |   83.5 |   83.5 |
| Wilson High School    |  83.1 |   83.7 |   83.2 |   83   |
| Wright High School    |  83.3 |   84   |   83.8 |   83.6 |

**Table 4b.** Math Scores after Removal of Test Scores
|                       |   9th |   10th |   11th |   12th |
|:----------------------|------:|-------:|-------:|-------:|
| Bailey High School    |  77.1 |   77   |   77.5 |   76.5 |
| Cabrera High School   |  83.1 |   83.2 |   82.8 |   83.3 |
| Figueroa High School  |  76.4 |   76.5 |   76.9 |   77.2 |
| Ford High School      |  77.4 |   77.7 |   76.9 |   76.2 |
| Griffin High School   |  82   |   84.2 |   83.8 |   83.4 |
| Hernandez High School |  77.4 |   77.3 |   77.1 |   77.2 |
| Holden High School    |  83.8 |   83.4 |   85   |   82.9 |
| Huang High School     |  77   |   75.9 |   76.4 |   77.2 |
| Johnson High School   |  77.2 |   76.7 |   77.5 |   76.9 |
| Pena High School      |  83.6 |   83.4 |   84.3 |   84.1 |
| Rodriguez High School |  76.9 |   76.6 |   76.4 |   77.7 |
| Shelton High School   |  83.4 |   82.9 |   83.4 |   83.8 |
| Thomas High School    |  83.6 |   83.1 |   83.5 |   83.5 |
| Wilson High School    |  83.1 |   83.7 |   83.2 |   83   |
| Wright High School    |  83.3 |   84   |   83.8 |   83.6 |

**Table 4c.** Reading Scores by Grade after Removal of Test Scores
|                       |   9th |   10th |   11th |   12th |
|:----------------------|------:|-------:|-------:|-------:|
| Bailey High School    |  77.1 |   77   |   77.5 |   76.5 |
| Cabrera High School   |  83.1 |   83.2 |   82.8 |   83.3 |
| Figueroa High School  |  76.4 |   76.5 |   76.9 |   77.2 |
| Ford High School      |  77.4 |   77.7 |   76.9 |   76.2 |
| Griffin High School   |  82   |   84.2 |   83.8 |   83.4 |
| Hernandez High School |  77.4 |   77.3 |   77.1 |   77.2 |
| Holden High School    |  83.8 |   83.4 |   85   |   82.9 |
| Huang High School     |  77   |   75.9 |   76.4 |   77.2 |
| Johnson High School   |  77.2 |   76.7 |   77.5 |   76.9 |
| Pena High School      |  83.6 |   83.4 |   84.3 |   84.1 |
| Rodriguez High School |  76.9 |   76.6 |   76.4 |   77.7 |
| Shelton High School   |  83.4 |   82.9 |   83.4 |   83.8 |
| Thomas High School    | nan   |   83.1 |   83.5 |   83.5 |
| Wilson High School    |  83.1 |   83.7 |   83.2 |   83   |
| Wright High School    |  83.3 |   84   |   83.8 |   83.6 |

**Table 4d.** Reading Scores by Grade before Removal of Test Scores
|                       |   9th |   10th |   11th |   12th |
|:----------------------|------:|-------:|-------:|-------:|
| Bailey High School    |  81.3 |   80.9 |   80.9 |   80.9 |
| Cabrera High School   |  83.7 |   84.3 |   83.8 |   84.3 |
| Figueroa High School  |  81.2 |   81.4 |   80.6 |   81.4 |
| Ford High School      |  80.6 |   81.3 |   80.4 |   80.7 |
| Griffin High School   |  83.4 |   83.7 |   84.3 |   84   |
| Hernandez High School |  80.9 |   80.7 |   81.4 |   80.9 |
| Holden High School    |  83.7 |   83.3 |   83.8 |   84.7 |
| Huang High School     |  81.3 |   81.5 |   81.4 |   80.3 |
| Johnson High School   |  81.3 |   80.8 |   80.6 |   81.2 |
| Pena High School      |  83.8 |   83.6 |   84.3 |   84.6 |
| Rodriguez High School |  81   |   80.6 |   80.9 |   80.4 |
| Shelton High School   |  84.1 |   83.4 |   84.4 |   82.8 |
| Thomas High School    |  83.7 |   84.3 |   83.6 |   83.8 |
| Wilson High School    |  83.9 |   84   |   83.8 |   84.3 |
| Wright High School    |  83.8 |   83.8 |   84.2 |   84.1 |

Another takeaway from this data is that, even before the scores are removed, THS's average scores are within the range of typical for the data set. 

### Analysis of Scores by Per-student Spending

**Table 5a.** Scores by Per-stuednt Spending after Removal of Test Scores

The spending per pupil at THS is $638. In the tables below, note the row for the $630-644 bin, the second highest of the per pupil spending rates.
| Spending Ranges (Per Student)   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| <$584                           |                 83.5 |                    83.9 |               93 |                  97 |                  90 |
| $585-629                        |                 81.9 |                    83.2 |               87 |                  93 |                  81 |
| $630-644                        |                 78.5 |                    81.6 |               67 |                  77 |                  56 |
| $645-675                        |                 77   |                    81   |               66 |                  81 |                  54 |
**Table 5b.** Scores by Per-student Spending before Removal of Test Scores
| Spending Ranges (Per Student)   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| <$584                           |                 83.5 |                    83.9 |               93 |                  97 |                  90 |
| $585-629                        |                 81.9 |                    83.2 |               87 |                  93 |                  81 |
| $630-644                        |                 78.5 |                    81.6 |               73 |                  84 |                  63 |
| $645-675                        |                 77   |                    81   |               66 |                  81 |                  54 |

Within the parameters of the rounding function, the average test scores remain the same. However, when the data from THS is removed, the overall passing rates, the passing math rate, and the passing reading rates take a hit from 63%, 73%, adn 84%, respectively, to 56%, 67%, and 77%.

# Analysis of Scores by School Size
With 1635 students, THS is firmly in the middle bin by student body size. As such, the bin labeled Medium (1000-2000) is where any changes to the data would be located.
**Table 6a** Scores by School Size after Removal of Test Scores
| School Size        |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:-------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Small (<1000)      |                 83.8 |                    83.9 |               94 |                  96 |                  90 |
| Medium (1000-2000) |                 83.4 |                    83.9 |               88 |                  91 |                  85 |
| Large (2000-5000)  |                 77.7 |                    81.3 |               70 |                  83 |                  58 |

**Table 6b** Scores by School Size before Removal of Test Scores
| School Size        |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:-------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Small (<1000)      |                 83.8 |                    83.9 |               94 |                  96 |                  90 |
| Medium (1000-2000) |                 83.4 |                    83.9 |               94 |                  97 |                  91 |
| Large (2000-5000)  |                 77.7 |                    81.3 |               70 |                  83 |                  58 |

Similar trends to the analysis by spending per pupil are evident in the analysis of scores by school size. With the way the data was removed from the set, there are no changes to the average scores within the rounding limits. However, there are drops of about 6% in the passing rates when the scores from THS are removed.

### Analysis of Scores by School Type

The final comparative analysis is between the types of school within the district--the district-operate schools and charter schools. As THS is a charter school, any difference by school type will be noted in the charter school column.

**Table 7a.** Scores by School Type after  Removal of Test Scores
| School Type   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Charter       |                 83.5 |                    83.9 |               90 |                  93 |                  87 |
| District      |                 77   |                    81   |               67 |                  81 |                  54 |

**Table 7b. Scores by School Type after Removal of Test Scores**
| School Type   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Charter       |                 83.5 |                    83.9 |               94 |                  97 |                  90 |
| District      |                 77   |                    81   |               67 |                  81 |                  54 |

Once again, there is a significant change in the passing rates. Even though the average scores do not show a difference, within the data analysis, the average scores to drop slightly in a range that does not get reflected in the rounded data.

## Conclusions

From the analysis, it becomes clear that the scores from the 9th grade class at THS buoyed the average scores by subject, the passing rate by subject, and the overall passing rates, no matter what way the data is sliced. Because THS accounts for 1635 of the over 30,000 records, the changes to the average scores are miniscule but the impact to the passing rate is quite high. A reason for this outcome could be that the scores were maniuplated to give a higher-than-average passing rate while keeping the average scores for the school within the range of normal as to avoid arousing suspicion of auditors.

This seems likely and John Oliver would have some choice words to say about this particular charter school.
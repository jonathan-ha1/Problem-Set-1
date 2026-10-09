# Problem Set 1: The Cost of Living Brief

ECON 3916, Applied Machine Learning for Economists

A household price index for a single parent working an hourly job, compared to the official CPI from 2019 to 2024.

## Finding

From 2019 to 2024, living costs for a single parent working an hourly job at the employer went up about 25.9%, compared to 22.7% for the CPI. That means the CPI doesn't overstate what these workers face. If anything, it understates it by about 3 points. The household used here is a single parent who rents a two-bedroom apartment, drives to work, and has a kid in full-time daycare. Rent and daycare are more than half of their budget, and both went up faster than prices in general. The CPI is based on what the average household buys, which looks pretty different from this budget.

The employer could be right about some workers. If someone doesn't spend much on rent or daycare, their costs probably went up less than the CPI. But the workers a starting wage is meant to attract are more like this household, and their costs went up faster than the CPI.

The confidence level would be moderate because the result held up when the budget shares were changed around, and the official data didn't have any missing months between 2019 and 2024. The weak spots are that the 2019 and 2024 prices for this household are estimates, not the employer's actual numbers, and the official data is national, not local. A good idea would be to check local rent and daycare prices before settling on a wage.

## Checking the AI's code

When the code changes one category's weight, it has to rescale the others so the weights still add up to 1. If that step were wrong, every result on the chart would be off. To check it, I first confirmed that the code's base index of 125.93 matched what my own laspeyres() function gives. Then I looked at each category's line at its actual weight, like Rent at 0.38, and all seven came back to 125.93. That shows the other weights were rescaled correctly. The code also worked with all seven of my categories, even though the prompt said six.

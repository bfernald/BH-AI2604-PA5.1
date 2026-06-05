# BH-AI2604-PA5.1
PA 5.1 Will the Customer Accept the Coupon?
[Jupyter Notebook](https://github.com/bfernald/BH-AI2604-PA5.1/blob/main/prompt.ipynb)

## Introduction

We had 3 key problems to address
1. Identify data issues and decide how to address them
2. Identify the participant characteristics that make Bar Coupon acceptance most likely
3. Identify the participant characteristics that make To Go Coupon acceptance most likely

## Investigate the dataset for missing or problematic data.

* Missing Data
  * Car column is mostly null (only 108 non-null) and the five unique values.
  * The purchase-history columns contain the rest of the nulls (Bar, Coffee, Togo, and Restaurants x2)
    * 605 rows total
    * 108-217 rows per column

* Problem Data
  * Car appears to be a text entry field with few entries and no consistency in content. I.e. low data quality

* Decisions & Actions
  * Drop the column 'car'
  * Drop the null rows from the purchase-history columns (< 5%)
  * Fix column 'passanger' by renaming to correct spelling (passenger with an e)

## Investigate the Bar Coupons

Based on these observations, I hypothesize that age <br>
and bar regularity are the primary drivers of Bar Coupon acceptance.

## Investigate the To Go Coupons

Using the bar coupon example as motivation, you are to explore one of the other coupon groups and try to determine the characteristics of passengers who accept the coupons. 

Today I will explore the acceptance of "Carry out & Take away" coupons. <br>
 * I'll use "To Go" (or "togo" in the code) as shorthand for "Carry out & Take away"
 * I will investigate how Age, Passenger, Time of Day, Weather, and Direction (Same) determine the characteristics of passengers who accept coupons.

### Age as a determinant for To Go coupon acceptance
 * While there are more participants in the 21-30 year old and 50-plus brackets, acceptance rates across all ages are between 71.8% and 77.1%, a range of only 5.3 percentage points. There does not appear to be a significant pattern based on the current age groupings.

Let's see if having children makes a difference.

### Having Children as a determinant for To Go coupon acceptance
* Wow. Nearly identical acceptance rates whether or not children are in the family.

Let's see if marital status makes a difference.

### Marital Status as a determinant for To Go coupon acceptance
* While the acceptance rate is consistently high, there's a small increate in acceptance for single individuals, and a big 10 percentage point bump for widowed individuals.

### Passengers as a determinant for To Go coupon acceptance
* Acceptance rates for all categories are high, but there seems to be a slight penalty for having Kids in the car. Intuition tells me there might be an issue of distraction in the Kids as passengers case.

### Time of Day as a determinant for To Go coupon acceptance
* Again, the acceptance rates are high, and there is a boost towards the end of the day (presumably toward dinner time).
* Further investigation could break this boost out to see if there is a lunch and dinner split. Lunch is difficult to measure as the 2PM bucket may include both lunch and dinner. Smaller buckets would give a clearer picture of trends during the day.

### Weather as a determinant for To Go coupon acceptance
* Again, the acceptance rates are high.
* I'm surprised to see Snowy come out ahead of Rainy for acceptance.
* Sunny leads the way, 5% better than Snowy, and a whole 15% better than Rainy

### Direction of Travel as a determinant for To Go coupon acceptance
* There something here as driving in the opposite direction gives a 5% higher acceptance rate than driving in the same direction.
* Most coupons are offered to drivers in the opposite direction.
* Is this because of offer timing, visible signage on the road, or some other metric that correlates with direction? All possible areas for further investigation.

## Conclusion
* Being single (including widowed), with friends, and ahead of dinner time are the big indicators of higher To Go coupon acceptance.
* That said, most coupons are accepted, and as long as it isn't rainy you can expect a 70% acceptance rate from most individuals for To Go food.

### Recommendations and Next Steps
* Rather than looking at who accepts a coupon, let's look at how coupons can shift behavior for participants.
* Advertisers are looking to influence behavior when they buy advertising like coupons.
* Here are some scenarios to investigate:
  * How coupon offerings make activities more attractive to participants.
  * How coupon offerings make specific advertisers more attractive to participants.
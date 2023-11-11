I used Morgan Mendis' colab script to prompt OpenAI
I used Amanda Shih's combined csv from xsv demo
repurposed colab:
https://colab.research.google.com/drive/1jQtxF2hxMBknwFMvMVwskrgSvtgQICaJ?usp=sharing

Goal: -find the best time to host special events/happy hour
	-to increase revenue and promote business
	-find the slowest period to boost traffic during slow times
      
My prompt:
```
agent.run("what are the slowest periods of the day"
          "periods to be 4 hours long"
          "use 'opened' and '# of guests'"
          "return example 20231011 1000-1400: <numberofguests>"
          "i need the 4-hr-periods for everyday don't forget to include calendar date"
          "seperate by days of the week"
          "group by week day"
          "only one period for one day"
          "then give me the average for each day from the findings")
```
most promising looking answer before OpenAI started to bug out:

```
  - Monday: 09:00-13:00, Average Guests: 9.33
  - Tuesday: 00:00-04:00, Average Guests: 2.39
  - Wednesday: 00:00-04:00, Average Guests: 6.03
  - Thursday: 00:00-04:00, Average Guests: 12.20
  - Friday: 00:00-04:00, Average Guests: 12.64
  - Saturday: 00:00-04:00, Average Guests: 15.87
  - Sunday: 12:00-16:00, Average Guests: 29.53
```

I also wanted to run the same prompt for the busiest period for comparison.
```
agent.run("what are the busiest periods of the day"
          "periods to be 4 hours long"
          "use 'opened' and '# of guests'"
          "return example 20231011 1000-1400: <numberofguests>"
          "i need the 4-hr-periods for everyday don't forget to include calendar date"
          "seperate by days of the week"
          "group by week day"
          "only one period for one day"
          "then give me the average for each day from the findings")
```
Output was being very inconsistent as well

observation: the data is probably incorrect. I did a quick scan and didn't find any opened orders at 12A-4A. I suspect the business is not open during those hours.

Conclusion: OpenAI is not the best tool for this, but potential is promising. It's better to use tools that can manipulate the data more directly for the time being.



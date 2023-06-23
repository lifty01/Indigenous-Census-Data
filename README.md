# LHL-Capstone-Project
Final Capstone Project for Lighthouse Labs (DA)

## Project/Goals
The project is a culmination of the skills and knowledge learned throughout the bootcamp. I was free to select any kind of topic and to treat it whichever way I wanted, as long as it pertained to data analytics.
The topic I settled on was First Nation groups in Canada. I didn't really have a clear direction or question I wanted to answer, but I knew that I mostly just wanted to explore the topic and see what I could find out after having pulled and acquired the data from the Canadian government’s statistics and census website. However, I did know that I wanted to use Python to clean the data I would find, and then load that data into Tableau to create some visualisations.

## Process
Initially wanting to get the geographic locations of all or most reservations across Canada and then find the population numbers for each, I started to explore the website for the data. I was not able to find the data that I had initially wanted but I did find data for ancestry/heritage of different groups, income statistics, group populations that lived on or off a reservation and schooling levels of different populations, as well as employment statistics. I started from the latest census year (2021) and worked my way down, but after the data started to get less and less consistent between years, I stopped at 2016 (2 census years total for each dataset).
After gathering my data, I loaded the files into a Python notebook and cleaned up the data. After it was clean, I proceeded to join them but ultimately decided to leave them scattered across tables because inner joins removed too much of the data and outer joins connected the data, but had too many NULL values to be relevant.
Once I had my clean datasets, I ran a statistical model to see if there was a link between the number of people that had singular or mixed ancestry and if they lived on a reservation or not.
After the statistical model, I loaded the datasets into Tableau and started creating graphs to get more insights about population trends among First Nations groups.

## Results
Statistical Model: I decided to run the independent variables of “homogenous ancestry” and “heterogenous ancestry” against the dependent variables “on reserve” and “off reserve”. Basically trying to see if there is a link between the number of people with either single or mixed ancestry from a specific First Nation group versus the number of people of that group living on or off a reservation.
The fit of the model isn’t great. The R-squared values are pretty low, sitting at around 11-13%, so it can’t really predict much of the variance of the data. The p-values are also high and higher than the 0.05 threshold so the data can’t be considered significant. Although one interesting thing from the results is the negative coefficient when testing the number of people with heterogeneous ancestry against the number of people off a reservation. This tells us that the more people have mixed ancestry, the less people (of that group) are off the reservation, therefore on the reservation. It could lead to implications that despite having mixed ancestry from different groups, there may be a strong sense of community encouraging people to remain on reservations.

             On reserve      Off Reserve
Adjusted R2: -0.112             0.137
p-values:     0.636/0.703       0.123/0.290
coefficient:  0.0032/0.0095     0.0517/-0.1283

When it comes to the visualisations made via Tableau, a simple one I made was to see the evolution of the population of certain groups. So for example, the “Cree” First Nation and the Métis grouping has mostly had a stable population between 2016 and 2021, but the Mi’kmaq group population has declined within the same time. Another example is the Métis grouping also had the highest income statistics between First Nations in general and Inuits. Also, when comparing the proportion of populations located on or off a reservation, it can be easily noticed that for the Qalipu Mi’kmaq First Nation, a heavy majority seems to be living off reservation.
All these visualisations lead to questions such as what are the factors driving people off or onto a reservation? What are the social and living conditions there? Why is income so much higher among people of the Métis group? What is driving population decline across different groups? They basically are giving insights on what sort of questions we should be asking to better research issues and phenomena going on with First Nations across Canada.

## Challenges
I ran into quite a few issues when working on the project. Initially, I had wanted to focus on a geographical component and combine that with census/population information to analyse location information of reservations and access to other services such as medical, education, etc. However, I scrapped the idea when not having any luck finding geographical data that matches the census data, which led me to focus on information I could find solely from the census/statistics data. I also had to limit my data to 2 census years, as the data found throughout the years would not match for specific topics (income, education, ancestry, reservation status). And even then, the information from those 2 census years was not consistent or cohesive across the same topics for both years or between different topics from the same year. Because of this, joining the data after having cleaned it seemed pointless as I would have ended up with a dataset of very few rows/entries, which is why I decided to keep the data tables separate from each other. The joining problem reappeared when I transferred my data into Tableau. I couldn’t join and connect my data without having a few NULL values appear from joins. I could somewhat bypass this issue by creating pivot tables and linking them through that, but it definitely limited the type of relationship I could create with visualisations between data tables.
A big part of the project was trying to find a way to adapt to the dwindling size of the information over the course of it and seeing what information and insights I could salvage from my changing data, and shifting the direction of my project.

## Future Goals
For future goals, I think I’d rather just restart the project from scratch by selecting a different data source and make sure I’d have a more complete set of information after cleaning my data and something that I’d be able to join and play around with comfortably. I definitely would have loved to add an interactivity component to my visualisations Despite this, I think I was still able to adapt well enough to still be able to pose questions and pull insights from the data and graphs. I also think it was a shame that I had to scrap the geographical component of my project, so I would want to take a look at that again and think of other ways I might be able to include it.

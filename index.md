<br>

## Introduction

The Biden Administration Policy Tracking Project is a nonpartisan effort to record, summarize, and visualize policy actions taken by the Biden administration. Policy actions include, but are not limited to: making a statement in support of a given policy, taking administrative action, issuing executive orders, and acting upon legislation.

I started this project with a few different use cases in mind. First, it may be a helpful resource for people who want to stay informed about what the Biden administration is doing policy-wise, but don’t have the time to constantly monitor the news. These users may find it interesting to explore the three interactive dashboards below.

Additionally, the project may be a useful resource for reporters and other policy-focused writers to help keep track of all of the newsworthy actions that the administration has taken in a given policy area. These users may benefit from working directly with the [underlying data](https://docs.google.com/spreadsheets/d/1-fpsf5ETwbPBGUgl85pAY2X2dz3MtTj4dpuXNO_qq4k/edit#gid=0) that I’ve collected, using the filters to drill down on actions by policy category, date, and/or the type of action (e.g., executive, administrative, or legislative).

Further, the dataset as a whole may present unique research opportunities for political scientists, data scientists, and researchers more broadly. These users may prefer to download the full [dataset](https://docs.google.com/spreadsheets/d/1-fpsf5ETwbPBGUgl85pAY2X2dz3MtTj4dpuXNO_qq4k/edit#gid=0) and analyze it as they see fit.

The next section of this page contains a series of visualizations exploring policy actions taken by the Biden administration, along with brief descriptions of each. After that, I discuss the data collection and classification process in more detail. Finally, I close with a brief discussion of the dataset’s strengths and weaknesses.

<br>

## Visualizations

The first dashboard provides a visual representation of policy actions taken by the Biden administration over time. Each observation represents a particular policy action, as described by a headline from a major media outlet (e.g., “Biden Dips Into U.S. Vaccine Supply to Send 20 Million Doses Abroad”). You can see the article’s headline, the outlet that published it, and the date it was published by hovering over an observation. If you want to read more about a particular policy action, you can click on the observation to see a link to the article (a URL that says “Read More” will appear in the tooltip).

Actions are grouped by policy category (e.g., COVID-19, economic policy, or immigration), and are arranged sequentially over time, with actions occurring in the same week stacked vertically. The shape of an observation indicates the type of action taken (e.g., executive, administrative, or legislative). The visualization is dynamic and interactive, allowing you to select/deselect any combination of policy categories or action types using the functionality on the right side of the dashboard.

<iframe seamless frameborder="0" src="https://public.tableau.com/views/Biden_Administration_Policy_Actions/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '2250' scrolling='no' ></iframe>

<iframe seamless frameborder="0" src="https://public.tableau.com/views/Biden_Administration_Policy_Actions_2022/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '2250' scrolling='no' ></iframe>

The second visualization provides a visual representation of the words that have been used most frequently to describe the administration’s policy actions. The size of each word is determined by the number of times it appears in headlines about policy actions in a given policy category. This means that the same word can appear multiple times if it is used frequently in headlines spanning multiple categories (e.g., “Trump” appears under immigration, foreign policy, COVID-19, and more).

The visualization is dynamic and interactive, allowing you to select/deselect any combination of policy categories, and to adjust the minimum term frequency (e.g., only showing words that appear at least 3 times in headlines about a given policy category).

<br>

<iframe seamless frameborder="0" src="https://public.tableau.com/views/BAPA_terms/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '850' scrolling='no' ></iframe>

Finally, the third visualization shows the total count of actions by policy category.

<br>

<iframe seamless frameborder="0" src="https://public.tableau.com/views/Biden_Administration_Policy_Actions_2022/Dashboard2?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '850' scrolling='no' ></iframe>


## Data Collection and Classification

The process of collecting and classifying articles about policy actions is entirely manual. I discover articles in the course of my regular news consumption, decide whether they warrant inclusion, and then classify them by policy category and action type. The criteria I use for inclusion are:

- The action must be policy-related in nature
- The action must receive coverage in a major media outlet
- The action must be taken by, or attributed to, the Biden administration
  - Sometimes this is straightforward (e.g., executive orders signed by President Biden), but other times it’s more of a gray area (e.g., legislative activity on areas the administration has expressed support for, but hasn’t been directly involved in shaping the legislation). When in doubt, I defer to how the article attributes responsibility.

One key component of the classification process is classifying an action by policy category. As part of this process, I assign each action to a single discrete category, selecting the category it is most relevant to. Sometimes this is straightforward (e.g., an executive order about DACA goes in the immigration category), but other times actions may be relevant to a number of categories (e.g., actions aimed at speeding up school reopenings could be assigned to either the COVID-19 or education policy categories). I chose to handle it this way in order to avoid excessive duplication of the same action across categories, but this means that occasionally a category will be missing a relevant action that’s recorded elsewhere. 

The only situations in which I allow for some duplication is on major legislative packages that span many categories. For the American Rescue Plan Act (ARPA), for example, I recorded all major milestones under the COVID-19 policy category, but I also recorded a few articles that focused on a particular aspect of the package in the relevant category (e.g., an article about reforms to the health care system in ARPA is included in the health care category).

The other major component of the classification process is classifying an observation by action type. Here is a description of how I think about the different action types:

- Administrative
  - I use this category to capture actions that are attributed to the Biden administration, but are carried out by a department or agency (as opposed to the Executive Office of the President).
- Executive
  - I use this category to capture executive orders and other actions that come directly from the Executive Office of the President.
- Judicial
  - I use this category to capture legal actions from the Department of Justice.
- Legislative
  - I use this category to capture major actions/milestones in the legislative process (e.g., when the administration lays out their initial legislative proposal, when a bill passes either the House or the Senate, etc.). 
  - I also occasionally use this category to record a piece of legislation under a secondary policy category, if a media organization publishes an article focused on that aspect of the broader legislation (see above discussion about ARPA, for example). 
  - As a result, a piece of legislation may have multiple actions associated with it.
- Legislative (Passed)
  - Because a single piece of legislation may be logged at multiple checkpoints in the prior category, I thought there was value in adding a separate category to mark the final passage of a bill as it’s sent to the President for signature. A piece of legislation will only appear one time, in one policy category, for this action type. The idea is that this category could be used to highlight a succinct list of legislative accomplishments over the course of the administration.
- Military
  - I use this category to capture military actions that are authorized by the president.
- Personnel
  - I use this category to capture formal nominations and appointments, as well as informal personnel choices (e.g., designating Vice President Harris as point person on immigration issues).
- Statements & Plans
  - This is the broadest category, encompassing newsworthy statements from the president or members of the administration, announcements of new plans, high-level goals (e.g., vaccination targets), and more. Plans that are specifically geared toward legislative action in the near-term are counted in the legislative category rather than in this one. 


<br>

## Discussion of Dataset's Strengths and Weaknesses

There are a few aspects of the dataset that I believe make it uniquely valuable for researchers. First, the dataset provides a broader picture of all of the different ways an administration can affect policy than is available from many other datasets. While it’s common to find datasets of [executive orders](https://www.federalregister.gov/presidential-documents/executive-orders) by president, for example, it’s more challenging to find datasets that span all of the different levers by which presidents pursue policy priorities. It is especially challenging to find comprehensive collections of policy actions that are more informal in nature, such as statements in support of a policy.

Additionally, because I only record policy actions that receive coverage in major media outlets, the dataset is curated to only include those actions that are more notable. A dataset that looks at [legislation passed](https://www.congress.gov/advanced-search/legislation) over a president’s term, for example, will inevitably contain bills renaming post offices and various other actions that are not likely to be of interest. Such a dataset will also include pieces of legislation that the president may ultimately sign, but had no role in shaping or shepherding through the legislative process. Mediating the data collection process through news coverage allows me to focus on only the more newsworthy actions, and it takes the decision of whether or not to attribute an action to the administration out of my hands.

Further, the fact that each action has already been assigned a policy category provides significant analytical value. This allows for supervised learning analyses, where a researcher could use the headline text or the text in the article itself (with some additional web scraping) to predict an action’s policy category. Researchers could also use the dataset to develop custom dictionaries of words that are relevant to certain policy areas for use in related analyses.

Of course, the manual nature of the data collection process comes with drawbacks as well. Most notably, this ensures that the dataset will be non-exhaustive. Inevitably, there will be actions that the administration takes that do not receive media coverage, and even more actions that do receive media coverage, but do not come across my radar. This process involves the biases of what the media chooses to cover, the biases baked into social media and search algorithms that determine what articles I discover, and my own biases and shortcomings in filtering and recording actions.

Additionally, my process for classifying an action by policy category and action type is inherently subjective. The way I think about classifying actions along these dimensions will undoubtedly be different than others, and thus may not line up cleanly with other datasets or bodies of work.

<br>

***

<br>

## Housekeeping Notes

The Biden Administration Policy Tracking Project is a nonpartisan effort and does not take a stance on the administration's policy actions.

Additionally, the project is something that I work on in my free time; it is not associated with any organization that I am affiliated with.

If you'd like to reference the project or use the underlying data in your work, please use the suggested citation below:

Green, Andrew, "Biden Administration Policy Tracking Project," 2021-2022, [(https://andygreen-1.github.io/Biden_Administration_Policy_Actions/)](https://andygreen-1.github.io/Biden_Administration_Policy_Actions/). 

<br>

*You can find more information about me and my work [here](https://andykgreen.com/).*


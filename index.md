<br>

## Introduction

<br>

This page contains a series of visualizations tracking policy actions taken by the Biden administration. Actions include, but are not limited to: making a statement in support of a given policy, taking administrative action, issuing executive orders, and acting upon legislation.

<br>

I started this project with two primary use cases in mind:

- To serve as a resource for people who want to stay in the loop with what the new administration is doing policy-wise, but don’t have the time to monitor the news closely week in and week out
- To develop a unique dataset that could be useful to researchers in the future

<br>

In support of these goals, there are four resources that are available on this page:

- “Biden Administration Policy Actions” – the primary dashboard that contains a visual representation of policy actions taken by the Biden administration.
  - Each observation represents an article from a major media organization describing a particular policy action. You can see the article’s headline (which serves as a short description of the action), the outlet that published it, and the date it was published by hovering over an observation. If you click on the observation, a link to the article is provided in the tooltip (“Read More”).
  - Actions are grouped by policy category (e.g., COVID-19, economic policy, immigration, etc.), and the shape indicates the type of action taken (e.g., executive, legislative, judicial, etc.).
  - The visualization is dynamic and interactive, allowing the user to select/deselect any combination of policy categories or action types. 
  - I provide further detail on the process of how actions are collected, organized, and classified in the appendix at the end of this page.
  - The visualization is updated weekly on Sunday.

<br>
- “Word Cloud by Policy Category” – a visual representation of the words that appear in headlines about policy actions taken by the Biden administration, organized by policy category.
  - The size of each word is determined by the number of times it appears in headlines about policy actions in a given policy category (amongst the headlines that are in my dataset). This means that the same word can appear multiple times if it is used frequently in headlines spanning multiple categories (e.g., “Trump” appears under immigration, foreign policy, COVID-19, etc.). 
  - The visualization is dynamic and interactive, allowing the user to select/deselect any combination of policy categories, and to adjust the minimum term frequency (e.g., only showing words that appear at least 3 times in headlines about a given policy category).
  - I provide further detail on the preprocessing steps used to prepare the text data for analysis in the appendix at the end of this page.
  - The visualization is updated weekly on Sunday.

<br>
- “Count of Actions by Policy Category” – a visual representation of the total count of actions by policy category.
  - Further context on how actions are classified into policy categories is available in the appendix at the end of this page.
  - The visualization is updated weekly on Sunday.

<br>
- Spreadsheet of all recorded policy actions, which is the underlying source data for all of the above visualizations.
  - The spreadsheet can be found [here](https://docs.google.com/spreadsheets/d/1-fpsf5ETwbPBGUgl85pAY2X2dz3MtTj4dpuXNO_qq4k/edit#gid=0).
  - The spreadsheet is updated on a daily basis as I come across new articles/actions.

<br>

## Visualizations

<iframe seamless frameborder="0" src="https://public.tableau.com/views/Biden_Administration_Policy_Actions/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '2100' scrolling='no' ></iframe>

<iframe seamless frameborder="0" src="https://public.tableau.com/views/BAPA_terms/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '900' scrolling='no' ></iframe>

<iframe seamless frameborder="0" src="https://public.tableau.com/views/Biden_Administration_Policy_Actions/Dashboard2?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '900' scrolling='no' ></iframe>


### Appendix A: Data Collection and Classification

The process of collecting and classifying articles about policy actions is entirely manual. I discover articles in the course of my regular news consumption, decide whether they warrant inclusion, and then classify them by policy category and action type. This process – as opposed to something more automated – comes with pros and cons. On the plus side, it results in a thorough but curated dataset, where any given action is represented by a single article without significant duplication. Additionally, while the classification into policy categories and action types is necessarily subjective, it’s likely to be far more accurate than would be the case from relying on a machine learning classification model. However, the manual nature of the process means the dataset is inherently non-exhaustive. An action must be deemed significant enough to receive media attention from a major publication, and then it has to be something I come across in the course of my media consumption.

The criteria I use for inclusion are:

- The action must be policy-related in nature (i.e., not purely about politics)
- The action must be taken by, or attributed to, the Biden administration
  - Sometimes this is straightforward (e.g., executive orders signed by President Biden), but other times it’s more of a gray area (e.g., legislative activity on areas the administration has expressed support for, but hasn’t been directly involved in shaping the legislation). When in doubt, I defer to how the article attributes responsibility.
- The action must receive coverage in a major media outlet
  - I generally will not include press releases or other communications directly from the administration. On very rare occasions, I have included press releases from non-media third party groups (e.g., advocacy organizations) if the action was also discussed in major media articles, but the articles didn’t fully characterize the action in a headline. Given the fact that I rely on the headline text to serve as the action description in the dashboard, I often choose articles based on how well the headline describes the action in question.


One key component of the classification process is classifying an action by policy category. As part of this process, I assign each action to a single discrete category, selecting the category it is most relevant to. Sometimes this is straightforward (e.g., an executive order about DACA goes in the immigration category), but other times actions may be relevant to a number of categories (e.g., an executive order limiting evictions during the pandemic could be assigned to either the COVID-19 or housing policy categories). I chose to handle it this way in order to avoid excessive duplication of the same action across categories, but this means that occasionally a category will be missing a relevant action that’s recorded elsewhere. The only situations in which I allow for some duplication is on major legislative packages that span many categories. For the American Rescue Plan Act (ARPA), for example, I recorded all major milestones under the COVID-19 policy category, but I also recorded a few articles that focused on a particular aspect of the package in the relevant category (e.g., an article about reforms to the health care system in ARPA is included in the health care category).

The other major component of the classification process is classifying an observation by action type. Here is a description of how I think about the different action types:

- Administrative
  - I use this category to capture actions that are attributed to the Biden administration, but are carried out by a department or agency (as opposed to the Executive Office of the President).
- Executive
  - I use this category to capture executive orders and other actions that come directly from the Executive Office of the President.
- Judicial
  - I use this category to capture legal actions from the Department of Justice.
- Legislative
  - I use this category to capture major actions/milestones in the legislative process (e.g., when the administration lays out their initial legislative proposal, when a bill passes either the House or the Senate, etc.). I also occasionally use this category to record a piece of legislation under a secondary policy category, if a media organization publishes an article focused on that aspect of the broader legislation (see above discussion about ARPA, for example). As a result, a piece of legislation may have multiple actions associated with it.
- Legislative (Passed)
  - Because a single piece of legislation may be logged at multiple checkpoints in the prior category, I thought there was value in adding a separate category to mark the final passage of a bill as it’s sent to the President for signature. A piece of legislation will only appear one time, in one policy category, for this action type. The idea is that this category could be used to highlight a succinct list of legislative accomplishments over the course of the administration.
- Military
  - I use this category to capture military actions that are authorized by the president.
- Personnel
  - I use this category to capture formal nominations and appointments, as well as informal personnel choices (e.g., designating Vice President Harris as point person on immigration issues).
- Statements & Plans
  - This category is likely the broadest, encompassing newsworthy statements from the president or members of the administration, announcements of new plans, high-level goals (e.g., vaccination targets), and more. Plans that are specifically geared toward legislative action in the near-term are counted in the legislative category rather than in this one. 

<br>

### Appendix B: Preprocessing Steps for the Word Cloud Visualization

I employ a fairly standard set of preprocessing techniques to prepare the text data for the word cloud visualization. Working with just the headline text from each article, I complete the following steps:

- Removing punctuation and symbols
- Removing numbers
- Converting all words to lowercase
- Removing common stopwords (e.g., “and”, “or”, “it”, etc.)

I also remove the word “Biden”, as it appears in virtually every headline. As of now, I am only working with unigrams for the sake of simplicity (i.e., treating every word individually), but may move to including bigrams or trigrams in the future (e.g., treating something like “White House” as a single entity, as opposed to two separate words “White” and “House”).

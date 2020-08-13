# SUMMARY

## **Need for tweet. How open-source developers use Twitter to talk about their GitHub work**

## Who:
### 1. Hongbo Fang, 
### 2. Daniel Klug,
### 3. Hemank Lamba, 
### 4. James Herbsleb, 
### 5. Bogdan Vasilesc

## When:
### Tue 30 Jun 2020 16:00 - 16:10 at MSR:Zoom - Developer Collaboration **Chair(s): Bogdan Vasilescu**

[PAPER LINK](https://cmustrudel.github.io/papers/msr20tweets.pdf "click here to see paper")

[MEDIA LINK](https://www.youtube.com/watch?v=DlXObspmZiI "click here to see media")

## INTRODUCTION:
### This paper is all about a computational approach to cross-link users across Twitter and GitHub. Through qualitative analysis of tweet contents, researchers report on a case study of 786 tweets by open-source developers about GitHub work, combining automatic characterization of tweet authors in terms of their relationship to the GitHub items linked in their tweets. 
### Researcher find that different developer roles tend to have different tweeting patterns when including GitHub links in their tweets. Some repository owners promote their GitHub projects. Some people who follow others on GitHub also tweet about these people’s work, but do not otherwise contribute to those open-source projects. In short in this paper researchers show a case study about the behaviors of people by their tweets regarding Github or their work on it and the urls on their tweets.

## RESEARCH METHODOLOGY:
### In this paper researchers focus on tweets containing links to GitHub since these are more likely to be work-related as opposed to social and, therefore, among the most relevant content on which to study the impact of Twitter activity on software development outcomes.
### Researchers used the heuristic approach to cross-link GitHub and Twitter user accounts, based on mining GitHub user profile pages and personal blogs for explicit URLs pointing to Twitter. They developed two heuristics expected to have relatively high precision: 
### (1) Mining explicit links to Twitter accounts from GitHub user profile pages; 
### (2) Crawling personal websites linked from GitHub user profile pages and mining links to Twitter accounts therein.
### Through, Using a **GHTorrent  MySQL dump**, they compile a list of all GitHub user logins, then use the GitHub API to mine, for each user, their profile page blog URL field. They identify **72,668 GitHub-Twitter** user account pairs.
### Researchers first collected all the tweets returned by the Twitter API for each of the **70,427** users in their  dataset and kept the recent ones, posted between **January1,2018 and July 1,2019**.Among these tweets, they ,then identified those with URLs containing the substring **/github.com/**, for a total of **131,217** tweets. For each GitHub URL, they recorded the repository the URL points to. After they filtered out tweets containing two or more distinct GitHub URLs, to simplify the subsequent qualitative analysis, **129,843** tweets remained.
### Then through GHTorrent, the GitHub API, and the GitHub-Twitter user account map they  characterized the relationship of the tweet author to the GitHub repository referenced in each tweet. By suspecting different tweeting behaviors they distinguished the users into the following:
### • Owner **(36,480tweets,or28%)**:The tweet author owns the repo.
### •	Collaborator **(14,512;11%)**:The tweet author has write access to the repo, i.e., closed others’ issues or pull requests.
### •	Contributor **(20,316;16%)**:The tweet author contributed to the repo pull requests, commits, or issues.
### •	Follower **(7,697;6%)**:The tweet author follows on GitHub any of the repo owner, collaborators, or contributors. 
### •	 Other **(50,838;39%)**:None of the above.

## RESULTS:
### Researchers emerged six major themes from their qualitative analysis:
### •	Question **(20 tweets, or 3%)**. These tweets ask about technical details of a repository, or about an open issue.
### •	Answer **(94 tweets, or 12%)**.these tweets respond to questions by other Twitter users.
### •	Call for Action **(32 tweets, or 4%)**.The authors of these tweets actively seek or request actions from others.
### •	Repository Advertisement **(366 tweets, or 47%)**. Tweets advertising or advocating for the use of the linked repository.
### •	Work Discussion (**129 tweets, or 16%)**. Tweets which are part of a discussion on Twitter.
### •	Information Sharing **(145 tweets, or 18%)**. 
### Tweets which inform the public or specific individuals about the existence of a repository, a file, an issue discussion, or other work-related news.
### Above results shows that the Twitter users tweet about their own repositories, in most cases they  intend to advertise **(66%)** or inform others about related information **(14%)**. Tweeting about the repositories they own rarely happens during work discussion **(9%)** or answering others’ questions **(8%)**, and almost never appears as a question to ask **(<1%)**, or a call for action **(2%)**.

### Cross-linking data across online platforms where open Source developers participate is feasible and it can help provide deeper insights into how the activities of developers on one platform are moderated by the roles they play on the other. The social media activities of developers may also have direct impact on software development out comes, including open-source project success. In this paper researchers provide a large dataset mapping **70,427open-source developer GitHub and Twitter accounts**, as basis for future empirical research in these directions.
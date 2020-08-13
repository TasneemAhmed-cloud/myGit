# SUMMARY
## **Software-related Slack Chats with Disentangled Conversations**

## WHO:
### 1. Preetha Chatterjee,
### 2. Kostadin Damevski, 
### 3. Nicholas A. Kraft, 
### 4. Lori Pollock

## WHEN:
### Tue 30 Jun 2020 16:40 - 16:50 at MSR:Zoom - Developer Collaboration 
**Chair(s): Bogdan Vasilescu**

[PAPER LINK](https://sites.udel.edu/preethac/files/2020/03/MSR20_Data.pdf "click here to see paper")

[MEDIA LINK](https://www.youtube.com/watch?v=iyL3NPa9utg "click here to see media")

## INTRODUCTION :
### In this paper, writers described that how the slack conversations are important and how these conversations of software developers can be disentangled. Writers studies show that , chat communications on Slack contain valuable information, such as descriptions of **code** and specific **APIs**, good programming practices, and causes of common errors. Availability of these types of information in software-related chats suggests these conversations could provide similar support for improving software maintenance tools as what researchers have already leveraged from **emails** and **bug reports**, **tutorials**, and **Q&A** forums.
### This paper presents the first large-scale data set of automatically disentangled software related conversations from the Slack platform.  The information on chat forums like slack is shared in an unstructured and informal manner. There is no sequence and alignment of conversation in chat communications. Chat conversations are also often interleaved, where multiple questions are discussed and answered in parallel by different participants. Therefore, a technique is required to separate or disentangle  the  conversations for analysis by researchers.
### In this paper a dataset of software related developer chat conversation is described. To enable others to process additional Slack transcripts and disentangle them into conversations, they also share the code we used to process daily chat logs, convert them to **XML**, and extract individual conversations from the collected chat transcripts. 

## RESEARCH METHODOLOGY:
### For the purpose of creating a dataset reusable for software developers and maintenance tools, researchers identified groups that primarily discuss software development topics and have a substantial collection of participants. They selected **three programming communities** who have active presence on Slack, and were willing to provide them **API** tokens for download. Within those selected communities, they focused on **four channels** that follow a Q&A format. The channels are advertised on the Web and allow anyone to join, with a joining process only requiring the participant to create a username and a password. Once joined, on these channels, participants can ask or answer any question, as long as it pertains to the main topic.
### For each Slack community, they downloaded all of the discussion data from each channel incrementally, every day for two years **(July2017-Jun2019)**.
### The downloaded chats from Slack were in JSON format. They collected all the downloaded chat transcripts and converted them into **XML format**, in which each message contains a **time stamp**, the **id** of the participant, and the **message text**. During the **JSON** to **XML** file conversion, they only use slack events that correspond to messages, ignoring all other recorded events (e.g., channel joins).In the next step, they obfuscated the participant’s ids for privacy, by replacing the original user names with randomly generated human names. Otherwise, the Slack user ids can be used to retrieve the participant’s e-mail via the channel of origin.
### Finally they run a disentanglement algorithm that is **Elsner and Charniak’s  algorithm**  to produce **XML attributes** that associate identified utterances (i.e., messages) with their corresponding conversations. 
### They also published their code for dataset in an **XML format**. In the disentangled files, each message has **message conversation_id** which is a mark up to associate each message with its corresponding conversation id,  time stamp **ts** in **Epoch format**, anonymized participant names **user**, and the content **text** of the message.

## RESULTS:
### Researcher’s dataset originates from public Slack channels, focusing on conversations that start with a question followed by a discussion with answers. Thus, the content of dataset, resembles Q&A based forums such as Stack Overflow. If others are interested in datasets that represent team dynamics inside an organization, they would need to augment with private conversations. They modified **Elsner and Charniak’s disentanglement algorithm** to account for several features specific to Slack. The code of their modified disentanglement algorithm may need to be adapted to work well on other chat platforms or developer communications. Any changes in disentangled conversations could be handled manually by post processing or by further automation adaptation.
### Moreover, researchers study shows that, along with few links to **Stack Overflow** and  **GitHub Gists**, there were sporadic links to other sites in their dataset. They believe that embedded links on Slack are used in many different contexts, and as such can be mined to provide more context to other data sources (tutorials, Q&A forums), and thus improve or augment developer learning resources.
### This  dataset could be studied to identify ‘hot’ topics of discussion in a programming community  and understand common challenges and misconceptions among developers. The results of these studies would provide guidance to future research in developing software support and maintenance tools. The wide spread use of chat communication platforms such as Slack provides a thriving opportunity to build new conversation based tools and integrations, such as chatbots. Sharing chat datasets such as provided in this paper could potentially facilitate further research on training and designing chatbots for software development activities.


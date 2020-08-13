# SUMMARY

## **Exploring the Security Awareness of the Python and JavaScript Open Source .**

## Who:
### 1. Gábor Antal, 
### 2. Márton Keleti, 
### 3. Péter Hegedűs

## When:
### **Peter Hegedus Dr**  [view email] [v1] Wed, 24 Jun 2020 11:59:36 UTC (206 KB)

[PAPER LINK](https://www.crysys.hu/publications/files/setit/cpaper_szte_AntalKH20msr.pdf "click here to see paper")

[MEDIA LINK](https://www.youtube.com/watch?v=FiWR3WhECzQ "click here to see media")

## INTRODUCTION:
### In this paper researchers examined vulnerability mitigation (i.e. corrective code changes to resolve security vulnerabilities) with in the open-source community and their typical types. For analysis they specifically chose **Python** and **Java Script** open-source projects as these languages are very popular and widely used in many domains today. 
### Researchers made **Software Heritage Graph Dataset**, through which they investigated the commits of these two languages **Python** and **JavaScript** projects collected from public repositories and identified those that mitigate a certain vulnerability in the code. And how quickly they mitigate a newly published security vulnerability.
 ### They identified the types of vulnerabilities referred to in commit messages and compared their numbers with in the two communities. On the other hand, they examined the average time elapsing between the publish date of a vulnerability and the first reference to it in a commit. They found that there is a large intersection in the vulnerability types mitigated by the two communities. 

 ## RESEARCH METHODOLOGY:
 ### Researchers used a very effective heuristics-based approach, similar to those widely used in works related to bug data collection for collecting the vulnerability mitigation commits for Java Script and Python projects from the dataset, which are potentially connected to a public **CVE**  entry. Firstly, they searched for the commits containing the patterns **“CVE-”** , **“CWE-”** , **“NVD-”** in their commit messages using SQL queries, So the community can understand why the given commit is extremely important and urgent to be merged. They created a temporal table called **cve_revs** with **357,757** rows by filtering the revision table.
### After the first filterization, researchers identified the programming language of the project a given commit belongs to for this:
### •	They considered a revision as a Python revision if its root directory contained either _init.py_ or _setup.py_.
### •	Also they considered a revision to be a JavaScript one if its root directory contained either **index.js**, **app.js**, **server.js** as one of these files will most likely be included in the root directory of a Java Script project.

### After this second step filterization they got **3,718** rows for **Python** and **4,136** rows for **JavaScript**, which they stored in two new tables: **cve_revs_py** and **cve_revs_js**, respectively. They analyzed the data collected in these instead of the original revision table.
### After that they extracted the **CVE/CWE IDs** from the commit messages by using Python scripts and pandas, and by regular expressions.
### Researchers focused on the types of vulnerabilities, which can be described by the **CWE** identifier of the security problem category the vulnerability belongs to, for that they  link each **CVE** entries to the corresponding **CWE** categories of the vulnerabilities. To achieve this, they relied on the data provided by the **National Vulnerability Database (NVL)**. Besides the **CWE** group of a **CVE** entry, they also extracted the publishing date, severity, and the base impacts core of every **CVE** entries. Some revisions contained references to **CWE** groups without mentioning any specific **CVE** entries. These revisions were mapped directly to the referenced **CWE** categories.

## RESULTS:
### After all filtering steps, Total number of **3,458** vulnerability mitigation commits (i.e. commit messages containing valid CVE or CWEIDs) for **Java Script** and **2,884** for Python identified to which researchers were able to resolve the corresponding **CWE** security type groups as well.
### In this paper researchers investigated the following two research questions: 
### **RQ1:** What are the typical security vulnerability types the Java Script and Python open-source communities mitigate and how do they relate to each other? 
### **RQ2:** How quickly the JavaScript and Python open-source communities mitigate a  newly published security vulnerability?
### For answer to **RQ1** researchers found that from the total **103** **CWE**, **55** **CWE** types occurred in both JavaScript and Python commit messages, while **32** **CWE** groups were found only in JavaScript projects, while **16** only in Python project.
### The **CWEs** having at least **150** references in either of the analyzed languages are as follows: 
### **• CWE-79:** Improper Neutralization of Input during Web Page Generation (Cross-site Scripting). 
### **• CWE-399:** Resource Management Errors.  
### **• CWE-200:** Information Exposure.  
### **• CWE-20:** Improper Input Validation. 
### **• CWE-264:** Permissions, Privileges, and Access Controls. 
### **• CWE-400:** Uncontrolled Resource Consumption.  
### **• CWE-119:** Improper Restriction of Operations within the Bounds of a Memory Buffer.  
### **• CWE-22:** Improper Limitation of a Path-name to a Restricted Directory.
### For answer to **RQ2**, they analyzed the average number of days elapsing between a mitigation commit date and the publish date of a CVE entry mentioned in that commit.
### Researchers examined that the Python community reacts **1.5-14** times faster to vulnerabilities than the JavaScript community; most of the mitigation commits appear **50 days** or less after the publish date of the corresponding vulnerabilities. In the case of JavaScript, only vulnerabilities from three **CWE** categories enjoy extra care **(CWE-20, CWE-200, CWE400)**, all the others are mitigated after at least 100 days. And vulnerabilities falling into the CWE categories characteristic to Python **(CWE-264, CWE399, and CWE-119)** are mitigated after **200 days** or more.
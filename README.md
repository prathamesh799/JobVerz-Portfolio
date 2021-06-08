# **Jobverz**
Jobverz is a product by **Multiverz**. It is a web and mobile application with a focus of empowering users to reskill and upskill the users. It services users who are looking looking for a job or enhance their skills or change their career. Jobverz provides the user with personal recommendations about skills to pursue and available career opportunities along with learning paths.<br/>

# **Skills Taxonomy**
A skill taxonomy is intended to organize the skills into a hierarchy. A taxonomy  should essentially connects skills to each other so as you move from role to role we have a relatively intelligent view about the skills that you need to become familiar with to get a new job.

Our team worked on developing a skill taxonomy by combining skills data from different data sources such as ONET, SkillsFuture, Nesta, and EMSI.  <br/>
This data would be saved in an organized manner in S3 buckets and API access is provided to other teams.<br/>

---

## **Our work throughout the project.**

### **Sprint-1: Fetch skills from MOOC's**

![image](https://user-images.githubusercontent.com/72140261/121016847-3dd2c600-c7ba-11eb-8a69-a9e38dedf2ee.png)


- To collect skills for developing our skills taxonomy, we scraped skills from courses in MOOC sites like Coursera, LinkedIn Learning, and Udacity from Data Science domain.
- I specifically worked on LinkedIn Learning courses. We extracted all skills related to Data Science domain. 
- We also extracted data from learning paths provided in LinkedIn Learning platform. 
- This data was stored in JSON format.

#### Technologies used
1. Selenium to scrape data from webistes.

### **Sprint-2: Create a unified schema for ONET database**

![image](https://user-images.githubusercontent.com/72140261/121005164-25a87a00-c7ad-11eb-87f9-7f4c92d88206.png)

- ONET database is primary source for occupational information, maintained by US Dept of Labour. It consists extensive data on occupations, their domains, skills and market demand for skills. 
- As part of sprint-2 we studied the database of ONET to identify relevant information for Skills Taxonomy and created a unified schema to represent the data. 
- We mapped job titles to tech skills, and soft skills characterized as Abilities, Skills and Knowledge by ONET database.

#### Technologies used
1. Jupyter Notebooks
2. Pandas, Numpy for data processing

### **Sprint-3: Provided API access for Skills Taxonomy data**
![image](https://user-images.githubusercontent.com/72140261/121008732-f136bd00-c7b0-11eb-87e7-cdac5232eafd.png)

- In order to provide access to Skills Taxonomy data to Engineering team and Integration team we created an API. 
- Amazon S3 buckets were used to store data related to skills and ONET unified schema.
- As part of this sprint we created 2 API calls. 
  1. A GET method to retrieve all job titles present in Skills Taxonomy.
  2. A POST method to get skills related to a particular job title.

#### Technologies used
1. Amazon S3: To store data
2. Amazon API Gateway: To process incoming requests
3. Lambda: To define API calls

### **Sprint-4: Applied string matching algorithms on job titles**
![image](https://user-images.githubusercontent.com/72140261/121017638-20eac280-c7bb-11eb-8e85-7d6d347f9aac.png)

- As job postings tend to have various titles referring to same job title. We had to map aggregated job titles with Skill taxonomy job titles, as job title in Skills Taxonomy have skills mapped to them. 
- Explored various string matching algorithms such as Token set ratio, Token sort, Partial ratio, Normal ratio from PolyFuzz library.
- Finally we used Google's BERT model, as it considers semantic meaning of words rather than string similarity. 
- We achieved 74% accuracy in matching an aggregated job title with a job title present in Skills Taxonomy with BERT model. 

#### Technologies used
1. Jupyter Notebooks
2. Machine Learning(Transfer learning)

### **Sprint-5: Improved accuracy of BERT model by preprocessing aggregated job titles**
- Created a unified schema for Nesta database. 
  - A hierarchy was created with first layer with 6 broad clusters of skills; split into 35 groups, and then split to give 143 clusters of specific skills.
  - Each of the approximately 10,500 skills lives within one of these 143 skill groups.
- Explored public API's and EMSI API to get alternate titles for job titles.
- Manually preprocessed aggregated job titles and applied BERT model, this improved accuracy. Thus proving that unless manual preprocessing is done accuaracy can't be improved beyond 74%. We also identified that the patterns were not uniform enough to perform preprocessing programatically.
<br />

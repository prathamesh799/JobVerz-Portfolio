# **Jobverz**
### Jobverz is a project by **Multiverse** company. Jobverz is a web application oriented towards reskilling and upskilling users. It's focussed to service Governments, Training organizations and Users who are looking to enhance or change their career. 
### In this 8-week project we aim to develop a **Minimum Viable Product (MVP)**.

## **Skills Taxonomy**
### Our team is responsible to create an unified schema from different data sources such as ONET, SkillsFuture, EMSI to map skills with job titles. 
### This data would be saved in an organized manner in S3 buckets and we provided API to access this data by other teams. This would be displayed on front-end.

---

## **Our work throughout the project.**

### Sprint-1: Fetch skills from MOOC's

![image](https://user-images.githubusercontent.com/72140261/121004906-d8c4a380-c7ac-11eb-813c-d740bf887b3c.png)

- As part of developing our skills taxonomy, we started by scraping MOOC sites like Coursera, LinkedIn Learning, and Udacity.
- I specifically worked on LinkedIn Learning courses. We extracted all skills related to Data Science domain. 

#### Technologies used
1. Selenium to scrape data from webistes.

### Sprint-2: Create a unified schema for ONET database

![image](https://user-images.githubusercontent.com/72140261/121005164-25a87a00-c7ad-11eb-87f9-7f4c92d88206.png)

- ONET database is primary source for occupational information, maintained by US Dept of Labour. It consists extensive data on occupations, their domains, skills and market demand for skills. 
- As part of sprint-2 we studied the database of ONET to identify relevant information for skills taxonomy and created a unified schema to represent the data. 
- We mapped job titles to tech skills, and soft skills characterized as Abilities, Skills and Knowledge by ONET database.

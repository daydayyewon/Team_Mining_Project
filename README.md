🍊Beyond the Questions : Strategic Interview Data Analysis
=

## 🏫 Team Member
YoungWoo Cho : [jayjo9](https://github.com/jayjo9)<br/>
Jiho Kang : [hahahohoJIHO](https://github.com/hahahohoJIHO)<br/>
Yewon Kim	: [daydayyewon](https://github.com/daydayyewon)


## 📸 Introduction
This project focuses on analyzing interview texts from seven distinct fields—Design, ICT, Management, Project Management (PM), Public Service, Research & Development (RND), and Sales & Marketing. Using text mining techniques, the goal is to extract and identify critical keywords that are central to each field.


## 📍 Project Objectives
#### - Keyword Extraction
Identify critical keywords from interview texts across seven fields—Design, ICT, Management, PM, Public Service, RND, and Sales & Marketing—using advanced text mining techniques.

#### - Field-Specific Insights
Analyze domain-specific language patterns to better understand each field’s priorities, values, and expectations.

## ⚙️ Technologies Used
- **Programming Language**: R
- **Libraries Used**:
  - Data Processing: dplyr, tidyr, jsonlite
  - Visualization: ggplot2, patchwork, ggraph
  - Text Analysis: tm, tidytext, KoNLP, topicmodels
  - Machine Learning: LDAvis, stm
 
## 📚1) Data load
- Source: [AI hub 채용면접 인터뷰 데이터](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=data&dataSetSn=71592)
- Date: 2022
- Type: json
- Number of data: 67,307
- Institution name
       : ㈜사람과숲, ㈜넥스인테크놀로지
- Description: Convert voice to text of job interview questions and answers and summarize the contents
 
## 🛠️2) Data Preprocessing

-Unnecessary symbol removal
-Morphological analysis and noun extraction: using KoNLP
-Remove one-character word 
-Load Stopword file & Add additional stopwords
![이미지 2024  12  6  오후 9 56](https://github.com/user-attachments/assets/c38967d4-2d8d-4550-b079-577d8ed7f17e)
![이미지 2024  12  6  오후 9 56 (1)](https://github.com/user-attachments/assets/19ef2d45-d841-4ef9-bfaf-04387296b5f6)
- ## Most frequently used in Job interview
![이미지 2024  12  6  오후 9 57](https://github.com/user-attachments/assets/1e9ece33-d0a3-47e1-96a8-8279d5ee7811)

- # Insight
Interview questions appear to focus on evaluating <core competencies> related to actual job performance, such as experience, problem-solving, and stress management. Therefore, interviewees should prepare specific examples of their problem-solving experiences and the lessons learned from them. It also seems important for interviewees to effectively express their psychological resilience, including examples of how they handled <stressful situations>. Based on this data, it is expected to be useful for analyzing question trends by job category or generating tailored question examples.


## 💼 3) Data Analysis
### ☘️ TF-IDF 
![이미지 2024  12  6  오후 10 31](https://github.com/user-attachments/assets/f422f253-1b8c-439d-b7cc-0731a46a7505)

#### 1️⃣ Analysis of Keywords by Job Categor
![이미지 2024  12  3  오전 5 31](https://github.com/user-attachments/assets/cff2cced-7e15-499e-b899-999e0acf3bbf)

#### Insights  
Depending on the key skills emphasized in each role, candidates should prepare experiences and portfolios that demonstrate technical expertise and professional skills. For instance, candidates for design roles should highlight creativity and trend awareness, while those in ICT roles should focus on programming skills and algorithm understanding.

#### 2️⃣ Alysis of key words by Gend
![이미지 2024  12  3  오전 2 46](https://github.com/user-attachments/assets/bf6ad743-f0b1-463b-8988-2a5a840d00a1)

#### Insights
- Female interview questions often focus on social ethics (e.g., corruption, public office) and social media or personal branding (e.g., Instagram, sales). This suggests women may be more associated with roles emphasizing social responsibility and digital marketing.
- Male interview questions tend to focus on technical, economic, and business-related skills (e.g., strengths, profits, welding). This suggests men are more likely to be in roles that prioritize technical expertise and economic outcomes.

#### 3️⃣ Analysis of Key Keywords by Job Experienced
![이미지 2024  12  3  오전 6 05](https://github.com/user-attachments/assets/76bdb4f2-c025-4ab6-8d31-c308a2b49978)

#### Insights
- Experienced candidates should highlight examples of problem-solving and strengths demonstrated in real-world scenarios.
- Inexperienced candidates should showcase adaptability and learning potential through relevant examples.

### ☘️ Topic Modeling
**1️⃣ LDA Model**: Identified latent topics from the dataset to uncover hidden themes.  

### Perplexity Analysis  
**Key Findings:**  
- The lowest perplexity was observed at **k=2**, indicating that the dataset is well-represented with a minimal number of topics.  
- Higher values like **k=3** or **k=4** may offer greater interpretability while maintaining model quality.  

![이미지 2024  12  6  오후 10 55](https://github.com/user-attachments/assets/920ab7cc-5607-4481-88cb-51b83f98382f)

### Results for k = 2 ~ 4
![이미지 2024  12  6  오후 10 54](https://github.com/user-attachments/assets/d84e0cdd-55f0-4aa6-b37d-2ae7eb3a4f10)

**2️⃣ STM Model**: Enhanced topic analysis by integrating metadata such as job roles, gender, and experience.
![이미지 2024  12  6  오후 11 00](https://github.com/user-attachments/assets/eccb29a8-224c-4265-bff8-83074ac5424d)
![이미지 2024  12  6  오후 10 59 (1)](https://github.com/user-attachments/assets/b4fc3a76-528a-4603-a843-75c0ec674c1d)
![이미지 2024  12  6  오후 10 59](https://github.com/user-attachments/assets/087797cc-1bdc-4ed5-bba3-ac174de97046)

### ☘️ Network Analysis
**Network Analysis Step**
**Step 1**: Create Edge List
Iterating Over Pairs of Sentences, Building Edges

**Step 2**: Process Data for Each Category 
Filtering Data, Tokenizing Text, Selecting Word Lists

**Step 3**: Build Networks

**Step 4**: Visualize Networks 
Edges, Nodes, Labels

## Network Analysis Result

![이미지 2024  12  6  오후 11 04 (1)](https://github.com/user-attachments/assets/aeebc453-7b66-43e6-bd1d-78a68871761f)
![이미지 2024  12  6  오후 11 04](https://github.com/user-attachments/assets/8e4c8dcc-38b2-4df1-a760-a15cade20688)


## 🗝️ Key Findings
- **Topic Modeling**: Identified 5 distinct topics, including 'customer feedback' and 'service quality.'
- **Sentiment Analysis**: Majority of the reviews were positive, with 20% indicating critical feedback.
- **Word Frequency**: Common terms included "service," "quality," and "experience," highlighting the importance of user satisfaction.









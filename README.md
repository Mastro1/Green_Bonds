# 🌱 Green Bond Classification

In this project we explore Natural Language Processing techniques to build an accurate classifier that could predict the bond's membership  in one of the four Principles. Moreover, since many of the bonds issued are linked with Sustainable Development Goals (SDGs) we provide a practical interface which allows the user to select the SDGs  they are more interested in, and as a result the bonds and the corresponding reports will be displayed in a dashboard. By offering a systematic tool that could predict the class of a bond according to the four ICMA Principles and an additional  dashboard for SDGs, we aim  to support investors in their decision-making,, foster sustainable finance and the advancement of SDG frameworks.

# 🌍 Contex
Green bonds are debt instruments issued by companies, governments and other organisations to raise capital for projects that have environmental benefits. Despite their incredible success in the recent years, green bonds still suffer from lack of standards. The International Capital Market Association is a global market initiative that promotes the development of the international capital and securities markets and it is currently focusing on green bonds. To shed light on this new bond category, a collection of voluntary frameworks, called the Principles has been created. The Principles outline best practices when issuing bonds serving social and/or environmental  purposes through global guidelines and recommendations that promote transparency and disclosure, thereby underpinning the integrity of the market.. The Principles  also raise awareness of the importance of environmental and social impact among financial market participants, which ultimately aims to attract more capital to support sustainable development.

To this extent, ICMA developed four Product Standards - principles - that go beyond the mere classification of green bonds and more accurately classify the issuance of debt securities for environmental or sustainable purposes  according to four different categories: Green Bonds, Social Bonds, Sustainability Bonds, and Sustainability-Linked Bonds. 

-	Green Bonds are bonds that are issued to raise capital for projects that have environmental benefits. These projects may include renewable energy, sustainable agriculture, clean transportation, and other initiatives that aim to reduce greenhouse gas emissions and protect the environment.

-	Social Bonds are bonds that are issued to raise capital for projects that have social benefits. These projects may include affordable housing, education, healthcare, and other initiatives that aim to improve the wellbeing of individuals and communities.

-	Sustainability Bonds are bonds that are issued to raise capital for projects that have both environmental and social benefits. These projects may include initiatives 	that promote sustainable development and address both environmental and social challenges.

-	Sustainability-Linked Bonds are bonds whose terms are linked to the issuer's sustainability performance. For example, the interest rate on these bonds may be linked to the issuer's progress in meeting certain environmental or social targets.

# 📋 Data
Our data comprises of bond's reports and fact sheets disclosed by companies upon the issuance of the bond, which is then labeled by ICMA  according to one of the four Principles. This information is available at [this ICMA link](https://www.icmagroup.org/sustainable-finance/sustainable-bonds-database/#HomeContent). In order to retrieve this information in a more adapted format to perform classification algorithms, we created a Python notebook (available on the GitHub folder) which extracts the reports directly from the original source present in the Excel file "ICMA-Sustainable-Bonds-Database-151022". In this Section we first establish a local directory with all the files needed to perform our classifications, namely 761 for Green Bonds, 136 for Social Bonds, 233 for Sustainability Bonds and 79 for Sustainability-Linked Bonds. On the GitHub  directory only few reports are available due to storage constraints.Then, we extract the text from all the reports and we encode it as ASCII  to avoid problems that can arise from the different encoding of the files. Finally, we start to clean our data by lowering all cases and deleting stopwords.

# 🏋️‍♂️ Machine Learning Models
In this section we test different machine learning methods (Logistic Regression, K-Nearest Neighbours, etc. ) on different models (full text, sentences, words, etc.). The question we want to answer is: which is the most accurate algorithm  and on which type of model  does it perform the best? 
In the first three models, we want to predict the membership to one of the four Principles by using 1) the full text of the reports, 2) then splitting the text into sentences and finally, 3) into words.  At each step we clean the data differently in order to not loose precious information. For instance, when we analyse words we only delete all the words the include some strange symbols  (e.g., @, ☐, %). 
Next, in Model 4  we want to explore how SDGs could predict the membership to one of the Principles. To do so, we first extract SDGs from the texts by splitting them first in sentences and then finding the sentences that contain the word "sdg", and then we use both words and SDGs together to predict the category.
In Model 5 we perform a deeper data cleaning and we run again the algorithm while in Model 6 we investigate Neural Networks.

# 🔍 Results
After trying numerous machine learning techniques on different models, we can notice that Markov gives the highest accuracy (71%) when applied on the Optimized Words Model (see Table below). This could be explained by the fact that Markov it is explicitly made for text analysis. More in general, we can also conclude that Markov and Naive Bayes tend to give highest accuracy, indeed they are very similar classification methods.  Interestingly, adding SDGs increases the accuracy compared to only words. This could be explained by the fact that certain SDGs tend to belong to one Principle (e.g. Climate Action to Green Bonds). However, this increase was not expected because for many SDGs there is not clear distinction to which Principle they help (e.g., Sustainable Cities and Communities). Finally, the NetModel should be further investigated with different NetModel such as BERT and different NetChain structures to improve its performances.

# 🤖 Conclusion
In conclusion, we were able to successfully classify green bonds using machine learning techniques. The trained classifier can be used to accurately predict the classification of green bonds, which can help investors identify and invest in environmentally friendly projects.

# 📹 Video
Here the [YouTube link](https://youtu.be/ffawJkkhhrc) for the video presentation of the project!



I aim to conduct research on the concept of the stranger **Gharib**in
Arabic Shia hadith and explore its range of meanings and conceptual
associations. To achieve this, I have chosen to conduct an initial
digital analysis of this concept in order to shed light on its semantic
and related themes. I will approach this analysis in three stages: web
scraping, data cleaning, and analysis.
    <!--more-->

### Web scraping

selected the website innoor.ir, which houses a collection of Shia texts,
for my web scraping project. As I was not experienced in handling large
amounts of data, I decided to begin by searching for the keyword
**“Gharib”** using the search tool on noorlib.ir. Then, I used the
**Beautiful Soup** and **Selenium** Python libraries to scrape the web
content from the search results. However, I encountered an issue with
the code snippet “Create column post_links at index 3 based on column
overview_page” in openrefine which did not work for the website.I was
unable to determine the cause of the problem. Then I was seeking
assistance from Stack Overflow and ChatGPT to use Python to perform the
web scraping, as I was already familiar with it. Through a for loop, I
successfully obtained data from all 83 pages.

![](https://github.com/naghsh70/naghsh70.github.io/blob/main/assets/image1.png?raw=true)

### Cleaning

After scraping the data, I found myself faced with a considerable amount
of unclean data, consisting of numbers, URLs, English words, and Persian
words interspersed within the text. Analyzing this data in its current
state was impossible, so I established a set of rules to clean it up.
-First, I prioritized text normalization. To achieve this, I utilized
the pyArabic library to standardize the Arabic letters and remove the
vowels. -Next, I encountered numerous unrelated words and items at the
beginning and end of each hadith, which needed to be eliminated. I
performed this removal process accordingly. -The text was also burdened
with conjunctions and repetitive words. Initially, I employed the
default Arabic stop words list and then manually supplemented it with additional
words.

![](https://github.com/naghsh70/naghsh70.github.io/blob/main/assets/image7.png?raw=true)

-Subsequently, I was left with a cleaned collection of words from the
hadiths. However, the dataset still appeared quite extensive. In order
to focus on the most relevant words, I extracted only those that were
closely associated with the term “Gharib.” As a result, each hadith
contained an average of 20 meaningful words. -Additionally, I
encountered several variations of family words related to “Gharib” that
carried similar connotations. To streamline the analysis, I unified
these variations.

![image7]([C:\Users\znagh\OneDrive\Desktop\doc\image7.png](https://github.com/naghsh70/naghsh70.github.io/blob/main/assets/image7.png?raw=true)

### Analysis:

The analysis stage proved to be the most captivating part of the
project. With the prepared data in hand, I eagerly anticipated the
insights and surprises that the computer could deliver. I employed
several analytical tools to explore the dataset:

Firstly, I utilized the counter library to determine the frequency of
each word. This allowed me to generate a bar chart displaying the word
frequencies.

![Image5](C:\Users\znagh\OneDrive\Desktop\doc\image5.png)

To gain a clearer understanding of the relationships between words,
particularly those associated with “Gharib,” I employed a form of
network analysis. This visualization provided a depiction of the
connections between words. Notably, the word “Gharib” exhibited strong
connections with “Rajol,” “Al-Mu’min,” “Sabīl,” “Al-Shi’a,” “Nas,” and
“Aabir.” Furthermore, some of these words showed connections with each
other, indicating shared thematic elements across certain hadiths. I
employed the networkx, matplotlib.pyplot, and pyvis.network libraries to
create this visualization.

![image4](C:\Users\znagh\OneDrive\Desktop\doc\image4.png)

Moreover, I conducted a simple clustering analysis to explore the
conceptual relationships among word categories, which yielded
fascinating results. This analysis was performed using the
sklearn.cluster library.
![image2](C:\Users\znagh\OneDrive\Desktop\doc\image2.png)

Finally, I uploaded the data to jsLDA and the Voyant tool for further
analysis. The outcomes obtained from all these tools were generally
consistent and provided valuable insights.

![image3](C:\Users\znagh\OneDrive\Desktop\doc\image3.png "image3")

### Challenges

Throughout the project, I encountered several challenges, particularly
during the data cleaning process, which required numerous tests and
iterations to achieve satisfactory results.

-In the web scraping stage, I faced difficulty in identifying the
relevant elements on the website. Consequently, I resorted to extracting
the id attribute value for each element and storing them in a table. I
then had to perform another for loop to extract the individual Hadith
pages based on these ids.

-Working with an Arabic website presented an ongoing struggle to find
the correct codes and libraries that would yield meaningful results for
the analysis. This required continuous searching and experimentation.

-One puzzling issue I encountered was when I entered 833 ids in Python,
but only obtained 133 final results. Unfortunately, I was unable to
determine the exact cause of this discrepancy, leaving me puzzled and
seeking further understanding.

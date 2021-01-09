Opener

What's your favorite kind of music? Do you know what draws you to this genre -- the tempo, the instrumentation, the arrangements, the lyrics? For a lot of fans of country-western music, the lyrics and the stories are what draws them in. This might be different from fans of rock music, who are more turned on by the drum beats and the guitar solos.

In this analysis, I will look at a large corpuses of written discussion about country and rock to see what patterns emerge from the commentary. What do country music fans talk about that rock music fans eschew, and vice versa? Can we divine the topic of the discussion by looking only at the language used by the fans of the two distinct genres?

                        What type of model will be developed?
                        How will success be evaluated?

As certain patterns in the language emerge, can they then inform what is to come in these genres? I believe we can. Pulling oft-repeated words and phrases out a heated discussion amongst fans about current country music releases can easily inform what a country music songwriter might want to address in their next hit! If those words are highly distinct from the words use by fans of rock and roll, the trend is even more salient, as they are clearly nearest and dearest to hearts of the country music fanbase and not the music community at large.

To that end, I will a body of posts from both the country music subreddit and the rock music subreddit to show how the language of the posters itself can reveal the genre about which they are speaking. Beyond that, I will show that certain words lend themselves to this differentiation, and therefore can reveal the most important and interesting topics -- and thus words! -- to followers of each genre.


But Why?

No, I didn't just waste many hours of work to tell country music artists to sing about love, trucks, country, and mama. This analysis digs deep to help musicians, songwriters, and fans alike better understand what themes at the heart of the music they love by dissecting the language they all use to talk about it. The data is drawn from the passionate commentary of the listeners themselves, so it tells an important story that is based on far more than conjecture: a data-driven report on what music fans care about the most.

Better yet, the breakdown is genre specific! Using robust classification algorithms, my analysis shows clearly that armchair rock music critics aren't saying the same thing as their country-western counterparts. While this report examines only two genres, I wholeheartedly believe that it can be applied across all types of music: classical, reggae,

 While there are many applications of this examination, my hope is that this helps artists, producers, venue owners, and music industry execs know what themes are currently resonating with their fan base. This will inform song composition, tour schedules, media market press packs, and so much more!  

If the fans are talking the talk, the musicians can walk the walk -- all supported by data!

The Solution!

With a clear analysis, I will help show the distinctive language being used by fans of different types of musics. In short, this will serve to unite fans and music professionals and help them find integrated ways to produce, market, and disseminate music, so that what the people want is what people get.

Any music

Data Collection

To perform the modeling, I collected actual posts from two very popular and prolific subreddits: [country music](https://www.reddit.com/r/country/) and [rock music](https://www.reddit.com/r/rock/) ("Rock music in all its forms."), which have 24.7K and 46.4K members, respectively. I used the 3000 most recent posts from each subreddit, and they were posted between June 25, 2020 and January 6, 2020. While the raw dataset had 77 features, I decided

Data Cleaning & Pre-Processing

Fortunately, the natural language data coming out of Reddit was fairly clean directly after scraping. I performed the following steps to get my data ready for Exploratory Data Analysis (EDA):

+ Put data into pandas DataFrame
+ Added a new column called `datetime` which converts the UTC time Reddit provides into a human-readable date
+ Added a new column called `merged` which joined the `title` and `selftext` columns that came out of Reddit. (`selftext` is thet body of the post.)
+ Added a column called `label` that would indicate the class of the post
+ Removed special characters, hyperlinks, and some numbers.
+ converted all letters to lowercase
+ Got rid of null values, though there were very few.
+ Created a new column called `tokens` by applying the `RegexpTokenizer(r'\w+')` to the `merged column`
+ Created a new column called  `stemmed` by applying the `SnowballStemmer(language='english')` to the `tokens` column, then joined these back together into a string for a new column called `combo`. I did end up using the `stemmed` or `combo` columns because the stemmed words ended up being detrimental to my interpretation and visualizations, but I did leave them in the DataFrame I used for models.
+ Removed rows in either DataFrame that were longer than 5000 words. This meant dropping two rows from `country` and six from `rock`
+ ... and finally concatenated the till-now separate `country` and `rock` DataFrames into one DataFrame called `country_rock` and converted the values in the `label` column to binary numeric labels 0 and 1.


EDA

I first went back and looked at each of the two original DataFrames in their cleaned but not concatenated. I


Modeling



Evaluation & Analysis
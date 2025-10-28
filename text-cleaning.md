# 🔴 Text cleaning

* <mark style="color:purple;background-color:purple;">**We mostly used libraries like cleantext / nlp-text-clean**</mark>
* <mark style="color:purple;background-color:purple;">**In this we pass the initialize the object ⇒ like lower\_case , remove\_html\_tags , remove\_url, remove\_stopwords , lemmatize**</mark>
* <mark style="color:purple;background-color:purple;">**It internally has pre-defined lemmatizer which one to be used**</mark>
* <mark style="color:purple;background-color:purple;">**We pass text to this cleaner ⇒ get cleaned text**</mark>



<mark style="color:purple;background-color:purple;">**Libraries Used:**</mark>

* <mark style="color:purple;background-color:purple;">**retext ⇒ remove punctuation**</mark>
* <mark style="color:purple;background-color:purple;">**nltk ⇒ remove stopwords, stemming, lemmatization**</mark>
* <mark style="color:purple;background-color:purple;">**.lower**</mark>
* <mark style="color:purple;background-color:purple;">**re ⇒ remove numbers / url  / special characters**</mark>
* <mark style="color:purple;background-color:purple;">**.strip ⇒ remove whitespace**</mark>
* <mark style="color:purple;background-color:purple;">**bs4 ⇒ html tags**</mark>
* <mark style="color:purple;background-color:purple;">**emojitext ⇒ emoji to text**</mark>

| **Operation**                 | **Example**                                                   | **Code Snippet**                                                                                                                                                              |
| ----------------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Remove Punctuation**        | "Hello, World!" → "Hello World"                               | `import retext = re.sub(r'[^\w\s]', '', "Hello, World!")`                                                                                                                     |
| **Convert to Lowercase**      | "NLP is FUN!" → "nlp is fun!"                                 | `text = "NLP is FUN!".lower()`                                                                                                                                                |
| **Remove Numbers**            | "I have 2 cats." → "I have cats."                             | `text = re.sub(r'\d+', '', "I have 2 cats.")`                                                                                                                                 |
| **Remove Extra Whitespaces**  | "Hello World" → "Hello World"                                 | `text = "Hello World".strip()' '.join(text.split())`                                                                                                                          |
| **Remove Stopwords**          | "This is a cat." → "cat"                                      | <p><code>from nltk.corpus import stopwords</code></p><p><code>stop_words = set(stopwords.words('english'))words = [w for w in text.split() if w not in stop_words]</code></p> |
| **Stemming**                  | "running," "runner" → "run"                                   | `from nltk.stem import PorterStemmerstemmer = PorterStemmer()stemmer.stem("running")`                                                                                         |
| **Lemmatization**             | "better" → "good," "running" → "run"                          | `from nltk.stem import WordNetLemmatizerlemmatizer = WordNetLemmatizer()lemmatizer.lemmatize("better", pos='a')`                                                              |
| **Remove HTML Tags**          | `<p>Hello</p>` → "Hello"                                      | `from bs4 import BeautifulSouptext = BeautifulSoup("<p>Hello</p>", "html.parser").get_text()`                                                                                 |
| **Remove URLs**               | "Visit [https://example.com](https://example.com/)" → "Visit" | \`text = re.sub(r'http\S+                                                                                                                                                     |
| **Remove Special Characters** | "Hello @World!" → "Hello World"                               | `text = re.sub(r'[^a-zA-Z0-9\s]', '', "Hello @World!")`                                                                                                                       |
| **Expand Contractions**       | "can't" → "cannot"                                            | `from contractions import fixtext = fix("can't")`                                                                                                                             |
| **Fix Typos**                 | "realy" → "really"                                            | `from textblob import TextBlobtext = str(TextBlob("realy").correct())`                                                                                                        |
| **Replace Emojis**            | 😊 → "smiley face"                                            | `import emojitext = emoji.demojize("😊")`                                                                                                                                     |
| **Standardize Dates**         | "Jan 1st, 2024" → "2024-01-01"                                | `import dateparserdate = dateparser.parse("Jan 1st, 2024").strftime("%Y-%m-%d")`                                                                                              |
| **Handle Negations**          | "I don’t like cats" → "not like cats"                         | Custom Logic:`text = text.replace("don’t", "not")`                                                                                                                            |

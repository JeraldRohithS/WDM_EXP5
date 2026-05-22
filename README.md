### EX5 Information Retrieval Using Boolean Model in Python
### DATE: 
### AIM: To implement Information Retrieval Using Boolean Model in Python.
### Description:
<div align = "justify">
The Boolean model in Information Retrieval (IR) is a fundamental model used for searching and retrieving information from a collection of documents. It operates on the principles of set theory and logic, where documents are represented as sets of terms or words, and queries are expressed as Boolean expressions using logical operators such as AND, OR, and NOT.
  
### Procedure:
1. ***Initialize the BooleanRetrieval class:*** The BooleanRetrieval class is defined to manage the indexing and searching of documents.
2. ***Constructor and Index Initialization:*** The class constructor initializes an empty index to store the inverted index mapping terms to documents.
3. ***Indexing Documents:***
    <p> a) The index_document method is responsible for indexing documents.
    <p> b) Tokenize the text content of documents, converting them into lowercase terms.
    <p> c) For each term in the document, it adds an entry in the index, associating the term with the document ID. </p>
4. ***Fetch Web Page Text:***
    <p>a) The fetch_webpage_text method uses the requests library to fetch content from a given URL.
    <p>b) Extract text content from the fetched HTML using BeautifulSoup.
    <p>c) The extracted text is returned for further processing.
5. ***Boolean Search:***
    <p>a) The boolean_search method performs Boolean searches on the indexed documents.
    <p>b) Tokenize the input query and iterates through its terms.
    <p>c) For each term in the query, it retrieves documents containing that term and performs Boolean operations (AND, OR, NOT) based on the query's structure.

### Program:
```
 # Information Retrieval Using Boolean Model in Python

# Sample Documents
documents = {
    1: "Python is a programming language",
    2: "Information retrieval uses Boolean model",
    3: "Python supports data science and machine learning",
    4: "Boolean model is used in information retrieval"
}

# Convert documents into lowercase word sets
doc_words = {}

for doc_id, text in documents.items():
    words = set(text.lower().split())
    doc_words[doc_id] = words

# Get user query
query = input("Enter Boolean Query (AND / OR): ").lower()

# Split query
query_parts = query.split()

# Extract keywords and operator
word1 = query_parts[0]
operator = query_parts[1]
word2 = query_parts[2]

# Perform Boolean Retrieval
result = []

for doc_id, words in doc_words.items():
    
    if operator == "and":
        if word1 in words and word2 in words:
            result.append(doc_id)

    elif operator == "or":
        if word1 in words or word2 in words:
            result.append(doc_id)

# Display Results
print("\nMatching Documents:\n")

if len(result) > 0:
    for doc_id in result:
        print("Document", doc_id, ":", documents[doc_id])
else:
    print("No matching documents found")
```

### Output:

<img width="480" height="106" alt="image" src="https://github.com/user-attachments/assets/022ccfcd-3ce5-49d6-8c36-c6e3f75b97b0" />


### Result:

Thus the implement Information Retrieval Using Boolean Model in Python is successful/

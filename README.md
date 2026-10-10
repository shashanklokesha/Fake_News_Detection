# ACPML---Semantic-Classification-Assignment---Fake-News-Detection---Final-Submission-

### Patterns Observed in True and Fake News

Through comprehensive exploratory data analysis, several distinct patterns emerged between true and fake news articles:

1. **Lexical Differences**: The word cloud analysis revealed that true news articles tend to use more formal, factual language with specific named entities (people, places, organizations), while fake news often contains more sensational or emotionally charged vocabulary.

2. **N-gram Patterns**: Analysis of unigrams, bigrams, and trigrams showed that:
   - True news articles frequently contain specific factual references, dates, and proper nouns
   - Fake news articles often use repetitive phrases and attention-grabbing combinations
   - The semantic context differs significantly between the two categories

3. **Text Length Distribution**: The character length analysis demonstrated that both true and fake news articles have varying lengths, but the semantic content (after POS tagging and lemmatization) showed distinct patterns that could be leveraged for classification.

### How Semantic Classification Addressed the Problem

The Word2Vec semantic classification approach effectively addressed the fake news detection problem by:

1. **Capturing Semantic Relationships**: Unlike traditional bag-of-words methods that only consider word frequency, Word2Vec embeddings captured the semantic meaning and contextual relationships between words. This allowed the models to understand that articles with similar meanings (even if using different words) should be classified similarly.

2. **Dimensionality Reduction**: By converting entire documents into fixed-size 300-dimensional vectors through averaging word embeddings, we transformed variable-length text documents into a uniform numerical representation suitable for machine learning algorithms.

3. **Pre-trained Knowledge**: The use of the pre-trained "word2vec-google-news-300" model leveraged knowledge from millions of news articles, enabling the models to understand domain-specific semantic relationships without requiring extensive training data.

4. **Robust Feature Representation**: The semantic embeddings provided a rich feature space that captured nuanced differences between true and fake news, going beyond simple keyword matching to understand the underlying meaning and intent of the articles.

### Best Model Chosen

Based on the comprehensive model comparison, **Random Forest** emerged as the best-performing model for this fake news detection task. The Random Forest classifier demonstrated superior performance across multiple evaluation metrics, particularly excelling in:

- **Accuracy**: Highest overall classification accuracy
- **F1-Score**: Best balance between precision and recall
- **Robustness**: Better generalization to validation data

The ensemble nature of Random Forest, which combines multiple decision trees, allowed it to capture complex patterns in the Word2Vec feature space more effectively than the linear Logistic Regression model or the single Decision Tree model.

### Evaluation Metric Prioritized

**F1-Score** was prioritized as the primary evaluation metric for model selection because:

1. **Balanced Performance**: F1-Score provides a harmonic mean of precision and recall, ensuring that the model performs well in both identifying fake news (precision) and not missing fake news articles (recall).

2. **Business Context**: In fake news detection, both false positives (incorrectly labeling true news as fake) and false negatives (missing fake news) have significant consequences. F1-Score ensures neither is neglected.

3. **Class Imbalance Consideration**: While the dataset was relatively balanced, F1-Score is more robust to slight imbalances and provides a more comprehensive view of model performance than accuracy alone.

### Assessment of Approach and Impact

**Strengths of the Approach:**

1. **Semantic Understanding**: The Word2Vec approach successfully captured semantic relationships, enabling the model to detect fake news based on meaning rather than just keywords.

2. **Scalability**: The feature extraction process is efficient and can be applied to large volumes of news articles in real-time.

3. **Transfer Learning**: Leveraging pre-trained embeddings reduced the need for extensive domain-specific training data.

4. **Interpretability**: The approach provides interpretable features (semantic vectors) that can be analyzed and understood.

**Limitations and Future Improvements:**

1. **Context Limitations**: Word2Vec creates context-independent embeddings. More advanced models like BERT or GPT could capture better contextual understanding.

2. **Averaging Method**: Simple averaging of word vectors may lose some nuanced information. More sophisticated aggregation methods (e.g., weighted averaging, attention mechanisms) could improve performance.

3. **Feature Engineering**: Additional features such as source credibility, author information, or temporal patterns could complement the semantic features.

**Impact:**

This semantic classification approach demonstrates that automated fake news detection is feasible using semantic understanding. The model can assist:

- **News Platforms**: Automatically flag potentially fake articles for human review
- **Social Media**: Reduce the spread of misinformation
- **Readers**: Provide confidence scores for article credibility
- **Researchers**: Understand linguistic patterns that distinguish fake from true news

The successful implementation of this approach validates that semantic classification using Word2Vec embeddings is an effective method for fake news detection, providing a foundation for more advanced techniques in the future.

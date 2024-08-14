# Jethro_Framework  

## Related Works & Papers  
### 1. Hybrid methods  
* Hybrid LLM- Cost-Efficient and Quality-Aware Query Routing
* RouteLLM: Learning to Route LLMs with Preference Data
### 2. Cascade methods
* Online Cascade Learning for Efficient Inference over Streams
### 3. Esemble methods
* LLM-BLENDER
### 4. Orchestration
* Apple Intelligence Foundation Language Models

## Hybrid LLM:Cost-Efficient and Quality-Aware Query Routing

1) **Abstract**:  
*Keyword: Hybrid Inference*  
The paper presents a hybrid inference approach that combines large and small language models (LLMs) to optimize cost and maintain response quality. **A router is proposed to assign queries based on predicted difficulty**, allowing for dynamic tuning of quality and cost. Experimental results demonstrate that this approach can reduce calls to large models by up to 40% without significant quality loss.

2) **Problem Formulation**:  
*Keyword: Cost Efficiency*  
The paper addresses the challenges posed by the increasing size of LLMs, which require substantial computational resources and incur high costs for deployment. The need for cost-effective solutions that do not compromise on quality is emphasized.

2-1) **Related Work**:  
*Keyword: Previous Research*  
The advent of LLMs has transformed various fields, but their large sizes lead to significant resource demands. Previous studies have explored smaller models, but they often lag in response quality compared to larger counterparts.

2-2) **Problem Setting**:  
*Keyword: Query Routing*  
The problem is framed around the need to efficiently route queries to either small or large models based on their complexity, aiming to balance cost and quality in LLM deployments.

2-3) **Evaluation Metric**:  
*Keyword: Performance Measurement*  
The evaluation metrics include BART scores and human assessments to measure response quality, alongside cost advantages achieved through routing strategies.

3) **Hybrid Inference**:  
*Keyword: Model Combination*  
The proposed hybrid inference method leverages a router to optimize the selection of models based on query difficulty.

3-1) **Deterministic Router**:  
*Keyword: Rule-Based Routing*  
This router assigns queries based on deterministic rules, using a binary classification approach to decide which model to use for each query.

3-2) **Probabilistic Router**:  
*Keyword: Flexible Routing*  
This router employs a probabilistic approach to assign queries, allowing for more flexible and nuanced routing decisions based on the inherent uncertainty in natural language processing tasks.

3-3) **Probabilistic Router with Data Transformation**:  
*Keyword: Enhanced Routing*  
This variant enhances routing effectiveness by transforming query data, which helps in better distinguishing between easy and hard queries, thereby improving overall routing performance.

4) **Evaluation**:  
*Keyword: Experimental Results*  
The evaluation of the proposed routing strategies shows that they can achieve significant cost savings while maintaining quality, with results indicating a strong correlation between training and testing performance across different model pairs.

5) **Discussion and Conclusion**:  
*Keyword: Future Directions*  
The paper concludes that the hybrid inference approach effectively balances cost and quality in LLM deployments. The findings highlight the potential for significant cost advantages without compromising response quality, paving the way for more efficient use of LLMs in various applications. Future work may focus on improving generalizability and exploring novel evaluation metrics.

### Q&A
#### Query Complexity Calculation
* **Method**: Query complexity is assessed based on the characteristics of the input queries. The complexity can be determined by analyzing various features of the queries, such as:
  - Length of the query (number of tokens or words).
  - Specific keywords or phrases that may indicate difficulty.
  - Historical performance data on similar queries (e.g., response times, accuracy).
  
* **Implementation**: The router uses these features to classify queries into "easy" or "hard" categories, which helps in deciding whether to route them to a small or large model.

#### Training the Router
* **Training Process**: The router is trained using a supervised learning approach where it learns to predict the complexity of queries based on labeled training data. The steps include:
  - **Data Collection**: Gather a dataset of queries along with their corresponding complexity labels (easy or hard).
  - **Feature Extraction**: Extract relevant features from the queries that can help in predicting their complexity.
  - **Model Training**: Use a machine learning model (e.g., logistic regression, neural networks) to train the router on the extracted features and their labels.

* **Loss Function**: The training process typically involves minimizing a loss function that measures the difference between the predicted labels and the actual labels.

#### Dataset Used
* **Dataset**: The paper mentions using a large benchmark dataset of real-world natural language queries and responses for training and evaluation. While the specific dataset is not named in the provided excerpts, it is implied that the dataset contains a diverse range of queries that reflect various complexities and contexts.

본 논문에서 사용한 데이터셋은 다음과 같습니다:

- **Alpace-GPT4**: 4,179개의 예제, GPT-4에서 생성된 응답
- **Dolly-15K**: 1,381개의 예제, 인간이 생성한 응답
- **GPT4All-LAION**: 13,547개의 예제, chatGPT에서 생성된 응답
- **ShareGPT**: 567개의 예제, chatGPT에서 생성된 응답

총 20,000개의 예제가 다양한 출처에서 수집되어 사용되었습니다 [T5].

* **Validation**: A portion of the dataset is used for validation to tune the router's parameters and ensure that it generalizes well to unseen queries.

In summary, query complexity is calculated based on query features, the router is trained using a supervised learning approach on a labeled dataset, and the dataset consists of real-world queries to ensure relevance and applicability.

## My methods



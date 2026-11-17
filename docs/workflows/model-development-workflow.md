
## Model Development & Evaluation Workflow

The following workflow illustrates the end-to-end process of developing and evaluating machine learning models for support ticket classification, including dataset preparation, text representation benchmarking, classical machine learning, multi-task transformer fine-tuning, model comparison, and final model selection for deployment.

```mermaid
flowchart TD
    A["Labeled Support Tickets Dataset<br/>Category / Priority / Sentiment Labels"]
    B["Exploratory Data Analysis"]
    C["Text Cleaning & Preprocessing"]
    D["Train / Validation / Test Split"]

    A --> B --> C --> D

    D --> E["Representative Stratified Training Sample"]
    E --> F["Text Representation Benchmarking<br/>Per Classification Task"]

    F --> F1["Count BoW"]
    F --> F2["TF-IDF"]
    F --> F3["TF-IDF N-grams (1,2)"]
    F --> F4["Word2Vec (Mean Pooling)"]
    F --> F5["Sentence-BERT (Frozen Encoder)"]

    F1 --> G["Same Baseline Classifier<br/>Linear SVM per Task"]
    F2 --> G
    F3 --> G
    F4 --> G
    F5 --> G

    G --> H["Cross-Validation & Performance Comparison"]
    H --> I["Select Best Representation<br/>for Each Task"]

    I --> J["Classical ML Development<br/>Separate Classifiers"]

    J --> J1["Category Classifier"]
    J --> J2["Priority Classifier"]
    J --> J3["Sentiment Classifier"]

    D --> K["Pretrained Language Model"]
    K --> L["Shared Transformer Encoder<br/>+ 3 Task-Specific Classification Heads"]
    L --> M["Joint Multi-Task Fine-Tuning"]

    M --> M1["Category Head"]
    M --> M2["Priority Head"]
    M --> M3["Sentiment Head"]

    J1 --> N1["Category Model Comparison"]
    M1 --> N1

    J2 --> N2["Priority Model Comparison"]
    M2 --> N2

    J3 --> N3["Sentiment Model Comparison"]
    M3 --> N3

    N1 --> O1["Select Category Model"]
    N2 --> O2["Select Priority Model"]
    N3 --> O3["Select Sentiment Model"]

    O1 --> P["Final Evaluation on Untouched Test Set"]
    O2 --> P
    O3 --> P

    P --> Q["Deploy Selected Models"]
    Q --> R["Department Routing Logic<br/>Business Rules - No Separate Model"]

    classDef data fill:#DCEAFE,stroke:#3976B9,color:#17365D
    classDef classical fill:#DDF3E4,stroke:#32945B,color:#174D2C
    classDef deep fill:#EDE3FA,stroke:#8961B5,color:#45276B
    classDef decision fill:#FFF0CE,stroke:#C28B27,color:#624511
    classDef output fill:#D9F0EA,stroke:#278A70,color:#164B3D

    class A,B,C,D,E data
    class F,F1,F2,F3,F4,F5,G,H,I,J,J1,J2,J3 classical
    class K,L,M,M1,M2,M3 deep
    class N1,N2,N3,O1,O2,O3 decision
    class P,Q,R output
```


## End-to-End Support Ticket Processing Workflow

The following workflow illustrates how incoming support tickets are processed, analyzed, prioritized, and routed, followed by policy retrieval, response generation, and human review.

```mermaid
flowchart TD
    A["Customer Submits Support Ticket"] --> B["Ticket Interface"]
    B --> C["Text Preprocessing"]
    C --> D["AI Analysis"]

    D --> E["Category Classification"]
    D --> F["Priority Estimation"]
    D --> G["Sentiment Analysis"]
    D --> H["Information Extraction"]

    E --> I["Department Recommendation"]

    E --> J["Combined Ticket Analysis"]
    F --> J
    G --> J
    H --> J
    I --> J

    J --> K{"Confidence Check"}

    K -->|Low Confidence| L["Flag for Human Review<br/>Display Predictions & Alternatives"]
    L --> M["Agent Reviews & Corrects<br/>Category / Priority / Department"]

    K -->|Sufficient Confidence| N["Retrieve Relevant Company Policies (RAG)"]
    M --> N

    O["Policies & Support Documentation"] --> P["Knowledge Base"]
    P --> N

    N --> Q["Generate Response Draft"]
    Q --> R["Human Agent Review"]

    R --> S{"Agent Decision"}

    S -->|Approve / Edit| T["Send Response"]
    S -->|Reject| U["Manual Handling"]

    T --> V["Store Feedback & Experiment Data"]
    U --> V
```

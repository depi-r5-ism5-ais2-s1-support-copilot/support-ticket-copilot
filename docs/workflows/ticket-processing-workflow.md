## End-to-End Support Ticket Processing Workflow

The following workflow illustrates how incoming support tickets are processed, analyzed, prioritized, and routed, followed by policy retrieval, response generation, and human review.

```mermaid
flowchart TD
    A("Customer Submits Support Ticket") --> B("Ticket Interface")
    B --> C("Text Preprocessing")
    C --> D("AI Analysis")

    D --> E("Category Classification")
    D --> F("Priority Classification")
    D --> G("Information Extraction")

    E --> H("Department Recommendation")

    E --> I("Combined Ticket Analysis")
    F --> I
    G --> I
    H --> I

    I --> J("Confidence Check")

    J -->|Low Confidence| K("Flag for Human Review<br/>Display Predictions & Alternatives")
    K --> L("Agent Reviews & Corrects<br/>Category / Priority / Department")

    J -->|Sufficient Confidence| M("Retrieve Relevant Company Policies (RAG)")
    L --> M

    N("Policies & Support Documentation") --> O("Knowledge Base")
    O --> M

    M --> P("Generate Response Draft")
    P --> Q("Human Agent Review")

    Q --> R("Agent Decision")

    R -->|Approve / Edit| S("Send Response")
    R -->|Reject| T("Manual Handling")

    S --> U("Store Feedback & Experiment Data")
    T --> U
```

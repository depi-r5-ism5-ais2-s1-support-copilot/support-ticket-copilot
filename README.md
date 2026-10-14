# Support Ticket Copilot

An AI-powered platform that helps customer support teams analyze incoming tickets, classify and prioritize requests, extract key information, and recommend the appropriate department. It also assists support agents by preparing response drafts for human review.

## Team Members

| **Name**        | **Role**    |
| --------------- | ----------- |
| Ahmed Youssef   | Team Leader |
| Mohamed Esam    | Team Member |
| Mahmoud Hany    | Team Member |
| Mohamed Mahmoud | Team Member |

## Problem Statement

Customer support teams often receive large volumes of requests covering different issues, such as delivery delays, billing questions, refunds, technical problems, and product complaints. Manually reviewing each ticket, identifying its category and priority, extracting relevant details, and forwarding it to the correct department can be time-consuming and inconsistent. Support agents may also need to search through company policies and documentation before preparing an accurate response.

## Project Objective

Develop an intelligent support assistant that helps organize and analyze customer tickets, recommends their categories, priorities, and responsible departments, extracts useful information, and provides response drafts that agents can review before sending.

## Key Features / Scope

- Collect and prepare a labeled dataset of customer support tickets.
- Perform exploratory data analysis to understand ticket categories, class distributions, and common patterns.
- Clean and preprocess ticket text and prepare a reusable data-processing pipeline.
- Develop a baseline text-classification pipeline using TF-IDF features and classical machine learning models.
- Fine-tune a suitable pretrained language model locally for ticket classification and compare its performance with the classical baseline.
- Predict ticket categories, such as delivery, billing, refund, account access, and technical support.
- Estimate ticket priority and analyze customer sentiment when supported by the available labels.
- Extract relevant details from ticket text, such as order references, product names, and dates, when present.
- Recommend the department or team best suited to handle each ticket.
- Retrieve relevant passages from approved company policies and support documentation using Retrieval-Augmented Generation (RAG) to help ground suggested responses in source material.
- Provide a review workflow that allows agents to inspect, edit, approve, or reject predictions and response drafts.
- Identify uncertain or ambiguous cases and flag them for human review rather than forcing an unreliable prediction.
- Evaluate classification performance using precision, recall, F1-score, macro-F1, and a confusion matrix, as appropriate.
- Analyze misclassified tickets, class imbalance, confidence levels, and response quality.
- Track experiments, model configurations, metrics, and evaluation artifacts.

## Expected Deliverables

- A Python-based customer support ticket assistance system.
- A prepared and documented dataset for the selected ticket categories.
- A reusable text-preprocessing and feature-engineering pipeline.
- Trained classical machine learning baseline models.
- A locally fine-tuned deep learning model and a comparison report.
- Ticket classification, priority estimation, information extraction, and routing recommendations.
- A functional interface for submitting tickets and reviewing analysis results.
- A response-drafting workflow with relevant source references where available.
- An evaluation report containing classification metrics, a confusion matrix, and error analysis.
- Experiment records and technical documentation, including the system architecture and setup instructions.

## Optional Extension

Extend the system to support Arabic or bilingual tickets, add analytics for recurring support issues, and integrate the workflow with a ticket-management platform. These enhancements will depend on available data, development time, and evaluation results.

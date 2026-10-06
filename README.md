# CareerPilot AI

CareerPilot AI is an intelligent career assistance system designed to provide secure, structured, and cost-efficient career guidance.

The project demonstrates how concepts from modern LLM application engineering can be combined into a complete AI pipeline, including model routing, conversation memory, structured outputs, tool execution, security controls, privacy protection, automated evaluation, caching, and cost optimization.

## Project Overview

CareerPilot AI processes career-related requests and automatically determines how each request should be handled.

The system can support multiple career scenarios such as:

- Career path recommendations
- Skill analysis
- CV guidance
- Interview preparation
- Learning roadmaps
- IT and engineering career guidance
- Cybersecurity and networking guidance
- Cloud and AI career recommendations

## System Architecture

The project follows a modular AI pipeline:

User Request  
→ Input Security Guard  
→ PII Detection & Masking  
→ Smart Model Router  
→ Career Service Detection  
→ Career Tools  
→ Structured Response  
→ Output Security Guard  
→ Quality Evaluation  
→ Cost & Performance Monitoring  
→ Final Response

## Core Features

### Smart Model Routing

CareerPilot AI analyzes request complexity and automatically selects between:

- `cheap` model for simple requests
- `flagship` model for complex analysis, comparisons, recommendations, and roadmaps

This approach helps balance response quality, latency, and cost.

### Conversation Memory

The system maintains conversation context so previous interactions can be used when processing new career requests.

### Structured Outputs

Pydantic models are used to validate structured career information such as:

- Career field
- Experience level
- Technical skills
- Target role
- Location
- Confidence score

### Career Tools

CareerPilot includes dedicated career tools for:

- Required skill lookup
- Learning path generation
- Skill-gap analysis

Supported technical career paths include Network Engineering, AI Engineering, Cybersecurity, Cloud Engineering, IT Support, and Software Engineering.

### Security Guard

The system includes an input security layer that detects:

- Prompt injection attempts
- Requests for system instructions
- Security bypass attempts
- Requests outside the career assistant scope

Unsafe requests are blocked before reaching the main processing pipeline.

### PII Detection & Masking

CareerPilot protects sensitive user information before processing.

The system can detect and mask:

- Saudi national IDs
- Saudi mobile numbers
- Email addresses

Example:

`0551234567` → `[SAUDI_PHONE]`

This reduces unnecessary exposure of personal information inside the AI pipeline.

### Output Guard

Generated responses are checked before being returned to the user to reduce the risk of exposing sensitive information.

### Automated Evaluation

A Golden Dataset is used to test expected system behavior across multiple career scenarios.

The evaluation pipeline automatically calculates a quality score and reports passing and failing cases.

### Quality Judge & Regression Gate

CareerPilot includes an automated quality judge and regression gate.

New versions can be compared against a baseline score. A version can be blocked when its quality drops beyond the accepted tolerance.

### Cost Optimization

The system estimates model usage cost in Saudi Riyals (SAR) and tracks simulated latency.

The project also demonstrates caching. Repeated requests can be served from cache with:

- Reduced latency
- Zero additional simulated model cost
- Less unnecessary model processing

Cost values in this educational project are simulated and do not represent official API pricing.

## Final Pipeline

The final demonstration combines the major components into one end-to-end workflow:

1. Validate the user request
2. Detect prompt injection
3. Detect and mask PII
4. Select the appropriate model
5. Identify the requested career service
6. Generate career guidance
7. Validate the output
8. Evaluate response quality
9. Estimate processing cost in SAR
10. Return the protected final response

## Example Scenarios

The final system is tested with multiple request types, including:

- Network Engineering skills
- Network Engineering vs. Cybersecurity
- Cloud Engineering roadmap
- CV improvement
- IT Support interview preparation
- Cybersecurity career guidance
- AI career recommendations
- Requests containing personal information
- Prompt injection attacks
- Out-of-scope requests

## Technologies

- Python
- Google Colab / Jupyter Notebook
- Pydantic
- Regular Expressions (Regex)
- LLM Application Engineering concepts
- Git & GitHub

## Project File

The complete implementation is available in:

`Abdulaziz_Alotaibi__Final_Project.ipynb`

Run the notebook cells sequentially to reproduce the project demonstrations and outputs.

## Author

**Abdulaziz Faiz Alotaibi**  
Computer Engineering Graduate  
Saudi Arabia

## Project Purpose

This project was developed as a practical demonstration of LLM application engineering concepts, focusing on building AI systems that are structured, secure, measurable, and cost-aware.

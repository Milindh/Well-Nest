
Overview

WellNest is a sophisticated healthcare AI system developed as an academic project to demonstrate the integration of enterprise-grade data engineering practices with Generative AI for preventive healthcare education. The system processes over 600,000 healthcare records across 6 datasets, creating 18 feature tables with 630+ engineered features to power intelligent, domain-specific health assessments.Project Goals
Demonstrate Fine-Tuning Expertise: Showcase advanced LLM fine-tuning techniques using Snowflake Cortex
Enterprise Data Engineering: Implement production-grade data pipelines using medallion architecture (Bronze-Silver-Gold)
Practical Healthcare Application: Create natural, conversational patient interactions while maintaining clinical accuracy
Academic Innovation: Bridge the gap between theoretical ML/AI concepts and real-world healthcare applications


Router LLM: Claude Sonnet 4 intelligent query routing
Specialized Models: Fine-tuned Llama 3.1-8B models for each healthcare domain
Two-Stage Processing: Clinical assessment → Conversational translation

Comprehensive Safety Protocols

Emergency Detection: Automated identification of critical health conditions
Crisis Intervention: Immediate resource provision for mental health emergencies
Clinical Disclaimers: Appropriate medical guidance and limitations

Smart Context Features

Semantic Search: Snowflake Cortex Search for relevant medical history
Health Metric Extraction: Automated extraction from conversations
Conversation Summarization: Intelligent summary generation
Long-term Memory: Track health trends and changes over time

Enterprise Data Engineering

Medallion Architecture: Bronze-Silver-Gold layer separation
Data Quality: Comprehensive validation and cleaning pipelines
Feature Engineering: 630+ clinical features across 18 tables
Scalable Design: Built for production-grade performance

Domain-Specific IntelligenceLifestyle Diseases

Diabetes staging (ADA guidelines)
Hypertension classification (ACC/AHA 2017)
Metabolic syndrome risk assessment
Cardiovascular risk scoring (Framingham-style)

Mental Health & Sleep

Depression severity (PHQ-9 style scoring)
Anxiety assessment (GAD-7 style scoring)
Suicide risk screening
Functional impairment evaluation

Technical StackCore Technologies

Data Warehouse: Snowflake (native environment)
Data Transformation: DBT (Data Build Tool)
LLM Fine-tuning: Snowflake Cortex
Application Interface: Streamlit (Snowflake-native)
Semantic Search: Snowflake Cortex Search
Authentication: bcrypt

LLM Models

Router: Claude Sonnet 4 
Specialists: Llama 3.1-8B (fine-tuned via Snowflake Cortex)
Context Window Management: Smart conversation history handling

Installation & Setup
Prerequisites
bash# Required accounts
- Snowflake account with Cortex access
- Python 3.8+
- Git

# Required privileges in Snowflake
- CREATE DATABASE
- CREATE SCHEMA
- CREATE TABLE
- CREATE PROCEDURE
- CORTEX LLM ACCESS
Step 1: Clone Repository
bashgit clone https://github.com/your-username/wellnest.git
cd wellnest
Step 2: Set Up Python Environment
bash# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
Step 3: Configure Snowflake Connection
Create .streamlit/secrets.toml:
toml[snowflake]
account = "your_account"
user = "your_username"
password = "your_password"
warehouse = "WELLNEST_WH"
database = "WELLNEST"
schema = "PUBLIC"
role = "ACCOUNTADMIN"
Step 4: Initialize Database
bash# Run DBT models
cd dbt_project
dbt deps
dbt seed
dbt run
dbt test

# SnappyCAT - Security Navigation and Prompting Platform Cybersecurity Assistance Tool

## Introduction

Welcome to **SnappyCAT**, the **Security Navigation and Prompting Platform for Cybersecurity Assistance**! This project is designed to support cybersecurity professionals, especially beginners, by allowing them to quickly search for and retrieve correct Linux commands and scripts during their work. Whether responding to security incidents, conducting forensic investigations, or managing systems, **SnappyCAT** is here to help.

What makes **SnappyCAT** stand out is its **Real-time Augmented Generation (RAG)** capability, powered by **Pathway**, ensuring that it continuously adapts to changes in its data sources. The data is stored as PDFs in the project’s data folder and can also be connected to external shared storage like Google Drive. This means that any updates made to the PDFs are reflected in real time, enabling users to get up-to-date information without manual interventions.

This entire application is containerized using **Docker**, making it production-ready and easy to deploy across different environments. With **Pathway's** scalable in-memory vector store, **SnappyCAT** provides efficient, real-time responses to user queries, making it a powerful assistant for fast-paced cybersecurity tasks.


## Table of Contents

- [What Problem It Solves](#what-problem-it-solves)
- [Architecture Overview](#architecture-overview)
- [Getting Started](#getting-started)
- [Demo](#demo)
- [Contributing](#contributing)
- [Contact Information](#contact-information)


## What Problem It Solves

Cybersecurity professionals, especially beginners, often struggle to remember the correct Linux commands needed for critical tasks. In time-sensitive situations like responding to security breaches or managing system configurations, the ability to quickly access the right commands is crucial. 

**SnappyCAT** solves this problem by:
- Enabling fast retrieval of Linux commands and scripts, reducing downtime and manual lookup.
- Providing real-time updates from PDFs stored in the project’s data folder, which can be connected to Google Drive for seamless collaboration.
- Offering a **RAG tool** that processes and indexes the latest documents for scalable, memory-efficient querying.

Explore more about how it integrates with Pathway and its capabilities here:
- [Pathway AI Documentation](https://pathway.com/app-templates)
- [Pathway LLM-APP Repository](https://github.com/pathwaycom/llm-app?tab=readme-ov-file#llm-app)


## Architecture Overview

### Pathway
Pathway is the core framework used to power this real-time RAG application. It allows **SnappyCAT** to provide immediate updates to any changes in the PDFs stored in the data folder. Its in-memory scalable vector store is ideal for handling live data and answering user queries based on real-time document changes.

### Docker
The entire application is containerized using Docker, ensuring smooth deployment across different environments. This containerized setup allows **SnappyCAT** to be production-ready with minimal setup effort. All necessary dependencies and configurations are bundled within the Docker container.


### Local Data Folder for Data Ingestion
The PDFs that serve as the knowledge base for **SnappyCAT** are stored in a local data folder within the project directory. Additionally, the system is set up to allow connection with external data sources like shared Google Drives, ensuring that real-time collaboration and updates are reflected instantly in the application.

## Getting Started

### Prerequisites
To get started with **SnappyCAT**, ensure that you have the following installed on your machine:
- Docker
- Pathway


### Installation and Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/tinkerness/SnappyCAT.git
   cd snappycat
2. **Add Api keys**: Add Gemini Api key in .env 
   ```
   GEMINI_API_KEY=*******
3. **Build the Docker Image**:
   ```bash
   docker build -t raggemini .
3. **Run the Application**: Start the application using Docker
   ```bash
   docker run -v "${PWD}/data:/app/data" -p 8000:8000 raggemini
4. **Check the List of Files**: 
   ```bash
   curl -X 'POST' 'http://localhost:8000/v1/pw_list_documents' -H 'accept: */*' -H 'Content-Type: application/json'
5. **Access the Application**: Once the container is running, you can interact with SnappyCAT by sending requests via HTTP POST. 
   ```bash
   curl -X POST 'http://localhost:8000/v1/pw_ai_answer' -H 'accept: */*' -H 'Content-Type: application/json' -d '{ \"prompt\": \"How to change ownership\" }'


## Demo
The following demo video showcases SnappyCAT in action. 

<!-- <video src="results/demo.mp4" controls></video> -->

[demo video](https://github.com/user-attachments/assets/0d735b28-e4da-4f83-82b0-3cc5209650e0)


## Contributing
If you’re interested in contributing, please follow these guidelines:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a detailed description of your changes.


## Contact Information
If you have any questions or would like to collaborate on the project, feel free to reach out!

- Email: [anittasiby002@gmail.com](mailto:anittasiby002@gmail.com)
- GitHub: [tinkerness](https://github.com/tinkerness)

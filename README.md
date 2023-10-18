# End-to-End RAG Pipeline in GCP

Welcome to the End-to-End RAG Pipeline in Google Cloud Platform (GCP) repository! This project provides a comprehensive framework for leveraging the Retrieve-and-Generate (RAG) model within GCP, enabling you to build powerful natural language processing (NLP) applications, such as question answering and document summarization.

## Key Features

- **Data Ingestion**: Easily bring in your text data from various sources and formats into GCP(like pdfs and image files).
- **Retrieval Stage**: Utilize advanced retrieval models to efficiently find relevant documents and passages.
- **Generation Stage**: Leverage state-of-the-art language generation models to produce high-quality answers or summaries.
- **Scalability**: Design your pipeline to handle both small and large datasets with ease.
- **Customization**: Adapt the pipeline to suit your specific NLP use cases.

## Process Flow

- Install all the necessary requirements from requirements.txt
- For initial Index building store all the pdfs in a folder and pass the location in the mentioned location in the notebook.
- Create the Index with a suitable display name
- Create a VPC in the same region as of index and set up the VPC peering.
- Create an Endpoint in the same region as of Index.
- Deploy the index in the created Endpoint.
- Infer the result using Vertex SDK by setting up proper num_neighbors and getting the value against the ID from Bigquery
- Then use the semantic searched value as the context to generate response with proper prompt(present in the last code cell of the notebook)

## Pipeline Creation

- Fetching PDFs and index creation can be encompassed within one Cloud Function.
- Another HTTPs triggered Cloud Function can be used for inference and text generation of the response based on user query.
- Architecture attached below for reference
- ![rag_pipeline_v1](https://github.com/dpsdev14091998/End-to-End-RAG-Pipeline-in-GCP/assets/60086099/85ef99f9-b89a-423e-b61c-a2964496993b)



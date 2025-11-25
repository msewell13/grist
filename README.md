# Self-Hosted Application Stack

This Docker Compose configuration deploys a comprehensive self-hosted application stack.

## Services

### **grist**
Grist is a powerful spreadsheet-database hybrid that lets you organize and analyze data like a spreadsheet, but with the power of a database. It's perfect for managing complex data, creating dashboards, and building custom workflows. Grist combines the familiar interface of spreadsheets with database-like capabilities, making it easy to work with large datasets, create relationships between tables, and build interactive applications.

### **nextcloud**
Nextcloud is your personal cloud storage and collaboration platform. It gives you complete control over your files, documents, photos, and more. Think of it as your own private Dropbox or Google Drive, but hosted on your own server. Beyond file storage, Nextcloud includes features for sharing files with others, syncing across devices, managing calendars and contacts, and collaborating on documents in real-time.

### **collabora-online**
Collabora Online is a full-featured office suite that runs in your web browser. It provides real-time collaborative editing of documents, spreadsheets, and presentations - similar to Google Docs or Microsoft Office Online, but self-hosted. When integrated with Nextcloud, you can create and edit office documents directly in your browser without needing desktop software installed. Multiple people can work on the same document simultaneously, seeing each other's changes in real-time.

### **paperless-ngx**
Paperless-ngx is a document management system that helps you go paperless by digitizing and organizing all your documents. You can scan or upload documents, and Paperless-ngx will automatically extract text using OCR (Optical Character Recognition), tag them, and make them searchable. It's perfect for organizing receipts, invoices, contracts, and any paper documents you want to store digitally. When integrated with Nextcloud, you can easily send documents from your cloud storage directly to Paperless-ngx for processing and archiving.

### **keycloak**
Keycloak is an identity and access management system that handles user authentication and authorization for all your services. Instead of managing separate logins for each application, Keycloak provides single sign-on (SSO) - log in once and access everything. It supports various login methods including username/password, social logins (Google, GitHub, etc.), and can manage user accounts, roles, and permissions across your entire application stack.

### **ollama**
Ollama lets you run large language models (like ChatGPT-style AI) completely on your own hardware. Instead of sending your data to cloud services, Ollama runs AI models locally, giving you privacy and control. You can chat with AI, ask questions, generate text, and use AI capabilities without any data leaving your server. It supports many different AI models that you can download and run locally.

### **anythingllm**
AnythingLLM is an AI assistant that can read and understand your documents. You can upload files, and then have conversations with an AI about the content of those documents. It's like having a smart assistant that has read all your files and can answer questions about them. Perfect for searching through large document collections, summarizing content, or getting answers from your own knowledge base.

### **stirling-pdf**
Stirling PDF is a comprehensive web-based toolkit for working with PDF files. You can merge multiple PDFs into one, split PDFs apart, rotate pages, convert between formats, extract text, and even perform OCR (Optical Character Recognition) to make scanned documents searchable. All of this happens in your browser without needing to install any software.

### **docuseal**
DocuSeal is an open-source alternative to DocuSign for digital document signing. You can create fillable PDF forms, send them to people for signatures via email, and track who has signed and who hasn't. It's perfect for contracts, agreements, forms, and any document that needs signatures. Everything is handled digitally with a clear audit trail of who signed what and when.

### **homarr**
Homarr is a beautiful dashboard that helps you organize and access all your self-hosted services in one place. Instead of remembering different ports and URLs, Homarr gives you a single homepage with quick links to all your applications. You can customize it with widgets, organize services into categories, and see the status of your services at a glance.

### **dashdot**
Dashdot provides real-time monitoring of your server's health and performance. It displays your system's CPU usage, memory consumption, disk space, network activity, and more in an attractive, easy-to-read dashboard. It's like having a system monitor that's always visible, helping you keep an eye on your server's resources and spot potential issues before they become problems.

## Databases

### **grist-db**
PostgreSQL database that stores all of Grist's data including documents, tables, and metadata.

### **kc_postgresql**
PostgreSQL database that stores all of Keycloak's data including user accounts, authentication settings, and security configurations.

### **nextcloud-db**
PostgreSQL database that stores Nextcloud's configuration, user accounts, file metadata, and all app data.

### **docuseal-db**
PostgreSQL database that stores DocuSeal's templates, documents, signatures, and user information.

### **paperless-db**
PostgreSQL database that stores Paperless-ngx's document metadata, tags, and configuration.

## Supporting Services

### **grist-redis**
Redis cache that helps Grist run faster by storing frequently accessed data in memory.

### **grist-minio**
MinIO is an object storage system (similar to Amazon S3) that stores Grist's document snapshots and files. It provides reliable, scalable storage for all your Grist documents with versioning support, so you can recover previous versions of your work.

### **minio-setup**
A one-time setup container that initializes MinIO by creating the necessary storage buckets and configuring versioning.

### **nextcloud-redis**
Redis cache that speeds up Nextcloud by caching frequently accessed data and managing file locks for better performance.

### **paperless-redis**
Redis cache that handles task queuing and background processing for Paperless-ngx document processing.

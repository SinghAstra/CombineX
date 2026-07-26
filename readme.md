# CombineX

**Why This Exists**
Combinex is a comprehensive platform for managing and analyzing software repositories. It provides a centralized hub for users to create, manage, and collaborate on repositories, as well as a robust set of tools for analyzing and summarizing repository data. Combinex aims to streamline the process of managing and understanding complex software systems, making it easier for developers and teams to work together and deliver high-quality software.

**What It Does**

- Provides a secure and scalable platform for managing software repositories
- Offers a range of tools for analyzing and summarizing repository data, including AI-driven analysis and text summarization
- Enables users to create, manage, and collaborate on repositories in a centralized hub
- Provides real-time job updates and manages job logs for efficient data retrieval and caching
- Offers a reusable hook for fetching job logs and a robust foundation for handling and processing different types of responses

**How It's Built**

### 🔐 Authentication (`/apps/api/src`)

The core API infrastructure handles user authentication and repository management, including email communication, user registration, verification, and password recovery. It also provides secure access to job logs and telemetry streams, ensuring proper authentication and authorization for each request.

### 📚 Repository Management (`/apps/web/features/repo`)

This module handles repository creation, deletion, boosting, and ingestion via API calls, and provides reusable hooks for fetching and managing repository data. It also manages repository resync operations and updates the application's data cache accordingly.

### 🧠 AI Processing Pipeline (`/apps/worker/src/ai`)

The core AI processing pipeline handles tasks such as caching Groq SDK clients, managing asynchronous operations, and enforcing retry strategies for transient errors. It also tracks key performance indicators, classifies API errors, and configures AI model settings to optimize input token limits.

### 📊 File Analysis Pipeline (`/apps/worker/src/services`)

This module handles file ingestion, clustering, and summarization, including AI-driven analysis of code files, generation of text summaries, and database updates to reflect file states and summaries. The pipeline also manages job queuing, progress tracking, and completion notifications.

### 📝 Shared Utilities (`/packages/shared/src`)

This directory serves as a centralized hub for shared constants, utilities, and server functionality across the application. It standardizes error codes for authentication, user, repository, and common issues, and provides a centralized interface for logging errors, tracking job progress, and sending telemetry events.

### 📁 Response Schemas (`/packages/shared/src/responses`)

This module serves as a centralized repository for standardized response schemas across the application. It defines data validation and structure for various operations, including repository management, authentication, and job-related data.

### 📁 Data Validation Schemas (`/packages/shared/src/schemas`)

This module serves as a centralized repository for data validation schemas, providing a standardized structure for authentication, repository, API, and job data. It exports schema definitions for user sign-in, sign-up, email verification, password reset, and Google OAuth authentication.

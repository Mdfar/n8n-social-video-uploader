OmniChannel Video Distributor (n8n)

This workflow automates the distribution of video content from a Google Drive folder to multiple social media platforms simultaneously.

Supported Platforms

YouTube: Direct video upload with metadata.

Facebook: Page video posting.

LinkedIn: Professional video sharing.

X (Twitter): Automated tweeting via API.

Instagram/Pinterest: Supported via HTTP Request nodes (included in template logic).

Prerequisites

An active n8n instance (Self-hosted or Cloud).

Developer Accounts and API credentials for:

Google Cloud (Drive & YouTube API)

Meta for Developers (Facebook & Instagram)

LinkedIn Developer Portal

X (Twitter) Developer Portal

Setup Instructions

Import Workflow: Copy the content of workflow.json and paste it into a new n8n workflow.

Credentials: Configure your OAuth2 credentials for each node.

Folder ID: Replace YOUR_GOOGLE_DRIVE_FOLDER_ID in the Trigger node with the specific ID of your source folder.

Activate: Set the workflow to "Active". Any video dropped into the folder will now trigger the multi-platform upload.

Technical Strategy

The workflow uses a Binary Data Pipeline. Once the file is detected and validated as a video, it is downloaded into the n8n environment buffer and passed in parallel to the various platform nodes, ensuring that a failure on one platform doesn't stop the upload to another.
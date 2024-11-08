# PinPoint

Welcome to **PinPoint** – a powerful tool for collecting, organizing, and categorizing your favorite URLs. This platform is designed to make it easy for you to save and access links across various topics and platforms like YouTube, Instagram, and more.

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Getting Started](#getting-started)
4. [Usage](#usage)
   - [Adding URLs](#adding-urls)
   - [Managing Topics](#managing-topics)
   - [Search and Filter](#search-and-filter)
5. [Deployment](#deployment)
   - [AWS Lambda for Metadata Retrieval](#aws-lambda-for-metadata-retrieval)
6. [License](#license)

## Introduction

URL Organizer is a user-friendly, web-based application that helps you store, manage, and categorize URLs. Built with a serverless backend powered by AWS Lambda, S3, and API Gateway, this tool is perfect for individuals and teams looking to organize a high volume of links with ease.

## Features

- **Add and Organize Links**: Save URLs to categorized topics for easy organization.
- **Metadata Extraction**: Automatically retrieves titles and descriptions from URLs (YouTube, Open Graph, etc.).
- **Flexible Filtering**: Filter saved URLs by topic or search by title.
- **Topic Management**: Add, edit, or delete topics to organize links as you like.
- **Dynamic Count Updates**: View real-time counts of saved URLs by topic.
- **Responsive Design**: Enjoy a user-friendly experience on both desktop and mobile devices.
- **Automated Deployment**: Seamless deployment to AWS S3, triggered by GitHub Actions.

## Getting Started

To use URL Organizer, follow these setup instructions:

1. **Clone this repository**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/url-organizer.git
   cd url-organizer
   ```
2. **Install Dependencies**:
- JavaScript libraries are included via CDN links in the project.
- For Lambda-based URL metadata extraction, package requests and beautifulsoup4 with your Lambda function.
3. **Set Up AWS S3 for Hosting**:
- Create an S3 bucket and configure it for static website hosting.
- Ensure the bucket policy allows public read access to the files.
- Use GitHub Actions with your AWS credentials for automated deployment to S3.

## Usage

### Adding URLs

1. Click **Add URL** in the main interface.
2. Enter the URL, select a topic, and provide a description if desired.
3. Click **Save** to add the URL to the selected topic, displaying metadata like title and thumbnail.

### Managing Topics

1. Click **Add New Topic** to create a new category.
2. After entering a topic name, it will appear in the dropdown.
3. Select the topic to view URLs categorized under it.

### Search and Filter

- Use the search bar to find specific URLs by title.
- Filter the list by selecting a topic from the dropdown to view URLs related to that topic only.

## Deployment

Deployment is automated via **GitHub Actions**:

1. Each time a new release is created, the repository’s contents are synced to the S3 bucket.
2. To manually deploy, push a new commit to the `main` branch, and GitHub Actions will handle deployment to S3.

## AWS Lambda for Metadata Retrieval

For metadata retrieval:

- **AWS Lambda** integrates with API Gateway to fetch metadata for URLs.
- The function retrieves Open Graph metadata and YouTube details (title, description), enriching the displayed links.

## License

This project is open source under the MIT License. See the `LICENSE` file for more details.

A Lambda function that uploads AWS service data to a search service for indexing and retrieval.

## Overview

This Lambda function is designed to process and upload AWS service information to a search backend, enabling efficient searching and discovery of AWS services and their capabilities.

## Features

- Processes AWS service data from various sources
- Transforms and normalizes service information for search optimization
- Uploads formatted data to search service endpoints
- Handles batch processing for large datasets
- Provides error handling and retry mechanisms

## Prerequisites

- AWS Lambda runtime environment
- Appropriate IAM permissions for AWS service access
- Search service endpoint configuration
- Required environment variables configured

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `SEARCH_ENDPOINT` | URL of the search service | Yes |
| `AWS_REGION` | Target AWS region | Yes |
| `BATCH_SIZE` | Number of records to process per batch | No |

## Usage

The function is triggered automatically based on configured event sources (S3, EventBridge, etc.) or can be invoked manually through the AWS Lambda console or CLI.

## Error Handling

- Implements exponential backoff for transient failures
- Logs detailed error information for debugging
- Supports partial batch processing with failure isolation

## Monitoring

Monitor function performance and errors through:
- CloudWatch Logs
- CloudWatch Metrics
- AWS X-Ray tracing (if enabled)
# upload-to-search-aws-services
# Indora Labs Indexing & Redaction API

The **Indora Labs API** provides secure, scalable indexing and redaction of **video, audio, and text** across 240+ file types. Built for GovTech compliance and commercial use cases, the API enables transcription, embedding, and policy-driven redaction with per-page/minute pricing.

---

## Features

- **Indexing**
  - Video, audio, and text ingestion  
  - Automatic transcription and text extraction  
  - Embedding generation for semantic search  

- **Redaction**
  - Video: object/frame-based redaction  
  - Audio: voice and sensitive phrase removal  
  - Text: PII and keyword policy redaction  

- **Compliance-Ready**
  - Designed for FOIA/IPRA, CJIS, and enterprise security standards  
  - Efficient storage and vector DB integration  

---

## Authentication

All requests require an API key. Include it in the header:

Authorization: Bearer <YOUR_API_KEY>

# Endpoints

## Indexing

POST /index/text
Index raw text or documents.
Body:

```http
{
  "file_uri": "s3://bucket/file.txt",
  "tenant_id": "abc123"
}
```

POST /index/audio
Transcribe and index audio files.
Body:

```http
{
  "file_uri": "s3://bucket/audio.mp3",
  "tenant_id": "abc123"
}
```

POST /index/video
Extract frames and transcribe audio from video.
Body:

```http
{
  "file_uri": "s3://bucket/video.mp4",
  "tenant_id": "abc123",
  "sample_fps": 10
}
```

## Redaction
POST /redact/text
Redact sensitive terms based on policy.
Body:

```http
{
  "file_uri": "s3://bucket/file.txt",
  "tenant_id": "abc123",
  "policy": ["SSN", "DOB"]
}
```

POST /redact/audio
Remove sensitive audio segments.
Body:

```http
{
  "file_uri": "s3://bucket/audio.wav",
  "tenant_id": "abc123",
  "policy": ["names", "addresses"]
}
```

POST /redact/video
Redact objects or regions in video frames.
Body:

```http
{
  "file_uri": "s3://bucket/video.mp4",
  "tenant_id": "abc123",
  "policy": ["faces", "license_plates"]
}
```

## Response Format
All endpoints return JSON:

```http
{
  "status": "success",
  "job_id": "xyz789",
  "output_uri": "s3://bucket/output/file"
}
```

## Pricing

Text/Audio Indexing: $0.01 per page

Video Indexing: $0.50 per minute

Text/Audio Redaction: $0.01 per page

Video Redaction: $0.50 per minute

## Use Cases
Government: FOIA/IPRA compliance, CJIS redaction

Commercial: discovery, media compliance, call center security

## Getting Started
Sign up for an API key from Indora Labs.

Send your first indexing request.

Retrieve results from your configured output bucket.

## Support
For support, contact support@indoralabs.com or open an issue in this repository.

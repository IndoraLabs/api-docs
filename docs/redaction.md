# Redaction Endpoints

## POST /redact/text
Redacts sensitive terms in text based on policy.  

**Body:**
```json
{
  "file_uri": "s3://bucket/file.txt",
  "tenant_id": "abc123",
  "policy": ["SSN", "DOB"]
}
```

---

## POST /redact/audio
Removes sensitive phrases or speaker segments.  

**Body:**
```json
{
  "file_uri": "s3://bucket/audio.wav",
  "tenant_id": "abc123",
  "policy": ["names", "addresses"]
}
```

---

## POST /redact/video
Blurs or masks objects/regions in video frames.  

**Body:**
```json
{
  "file_uri": "s3://bucket/video.mp4",
  "tenant_id": "abc123",
  "policy": ["faces", "license_plates"]
}
```

# Indexing Endpoints

## POST /index/text
Indexes text files or documents.  

**Body:**
```json
{
  "file_uri": "s3://bucket/file.txt",
  "tenant_id": "abc123"
}
```

---

## POST /index/audio
Transcribes and indexes audio files.  

**Body:**
```json
{
  "file_uri": "s3://bucket/audio.mp3",
  "tenant_id": "abc123"
}
```

---

## POST /index/video
Extracts frames + transcribes audio from video.  

**Body:**
```json
{
  "file_uri": "s3://bucket/video.mp4",
  "tenant_id": "abc123",
  "sample_fps": 10
}
```

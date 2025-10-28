# YouTube Video Downloader API

A simple Flask API that downloads YouTube videos using yt-dlp for transcription purposes.

## Features

- Download YouTube videos (up to 720p quality)
- RESTful API endpoints
- CORS enabled for frontend integration
- Automatic cleanup of temporary files
- Railway deployment ready

## API Endpoints

### Health Check
```
GET /api/health
```
Returns the API status.

### Download Video
```
POST /api/extract-video
Content-Type: application/json

{
  "url": "https://youtube.com/watch?v=VIDEO_ID"
}
```
Downloads a YouTube video and returns metadata with download info.

### Get Video File
```
GET /api/download-video/{request_id}/{filename}
```
Downloads the actual video file.

## Local Development

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Run the server:
```bash
python youtube_api.py
```

The API will be available at `http://localhost:5002` (or `http://localhost:8080` on Railway).

## Railway Deployment

1. Create a new GitHub repository with these files:
   - `youtube_api.py`
   - `requirements.txt`
   - `railway.json`
   - `Procfile`
   - `README.md`

2. Connect the repository to Railway
3. Deploy automatically

Railway will automatically:
- Install Python dependencies from `requirements.txt`
- Run the Flask app using the `Procfile`
- Provide a public URL for the API

## Environment Variables

- `PORT`: The port to run the server on (automatically set by Railway)
- `FLASK_DEBUG`: Set to 'true' to enable debug mode (optional)

## Dependencies

- Flask 2.3.3
- Flask-CORS 4.0.0
- yt-dlp 2023.9.24

## License

MIT License
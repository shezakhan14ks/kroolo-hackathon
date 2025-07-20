# AI Meeting Summarizer - API Setup Guide

Your AI Meeting Summarizer is now fully functional with real API integrations! Follow these steps to configure the required API keys.

## 🔑 Required API Keys

### 1. AssemblyAI (Speech-to-Text)

- **Purpose**: Converts audio files (.mp3, .wav) to text transcripts
- **Free Tier**: 5 hours of transcription per month
- **Setup**:
  1. Go to [https://app.assemblyai.com/](https://app.assemblyai.com/)
  2. Sign up for a free account
  3. Copy your API key from the dashboard
  4. Add it to your `.env` file: `ASSEMBLYAI_API_KEY=your_key_here`

### 2. OpenAI (GPT-3.5 Turbo)

- **Purpose**: Analyzes transcripts to generate summaries and extract action items
- **Cost**: Pay-per-use (very affordable for typical usage)
- **Setup**:
  1. Go to [https://platform.openai.com/api-keys](https://platform.openai.com/api-keys)
  2. Sign up and add billing information
  3. Create a new API key
  4. Add it to your `.env` file: `OPENAI_API_KEY=your_key_here`

## 🚀 Quick Setup

1. **Copy the environment template**:

   ```bash
   cp .env.example .env
   ```

2. **Edit the `.env` file** and add your API keys:

   ```env
   ASSEMBLYAI_API_KEY=your_assemblyai_key_here
   OPENAI_API_KEY=your_openai_key_here
   ```

3. **Restart the development server**:
   ```bash
   npm run dev
   ```

## ✅ Features Now Available

### Audio Processing

- Upload `.mp3` or `.wav` files
- Automatic transcription via AssemblyAI
- Progress tracking during audio processing

### Transcript Processing

- Upload `.txt` files directly
- Upload `.pdf` files (automatic text extraction)
- Instant processing for text files

### AI Analysis

- Smart meeting summarization (3-5 bullet points)
- Automatic action item extraction with:
  - Assigned person
  - Task description
  - Deadline (when mentioned)

### Export & Sharing

- Download results as `.txt` files
- Email sharing functionality
- Formatted output with timestamps

## 🔧 Technical Details

### File Limits

- Maximum file size: 50MB
- Supported audio: `.mp3`, `.wav`
- Supported text: `.txt`, `.pdf`

### Processing Times

- **Text files**: 10-30 seconds
- **Audio files**: 2-5 minutes (depending on length)
- **PDF files**: 15-45 seconds

### Error Handling

- File type validation
- API timeout protection
- Clear error messages
- Retry functionality

## 💡 Usage Tips

1. **Test with the example**: Click "Try Example" to test with sample content
2. **Audio quality**: Clear recordings work best for transcription
3. **Meeting structure**: Meetings with clear speakers and action items produce better results
4. **File naming**: Use descriptive filenames for better organization

## 🛠️ Troubleshooting

### Common Issues

**"AssemblyAI API key not configured"**

- Check your `.env` file has the correct `ASSEMBLYAI_API_KEY`
- Restart the development server after adding keys

**"OpenAI API error"**

- Verify your OpenAI API key in `.env`
- Ensure you have billing set up on your OpenAI account
- Check if you have remaining quota

**"Processing failed"**

- Try a smaller file size
- Check file format is supported
- Verify your internet connection

**Audio not transcribing**

- Ensure audio file is clear and in English
- Try converting to `.mp3` format
- Check file is under 50MB

## 📊 Cost Estimates

### AssemblyAI

- **Free**: 5 hours/month
- **Beyond free**: $0.37/hour

### OpenAI GPT-3.5 Turbo

- **Typical meeting**: $0.01-0.05 per analysis
- **Monthly usage (20 meetings)**: ~$0.20-1.00

**Total monthly cost for typical usage: Under $5**

## 🔒 Security

- API keys are stored in environment variables
- Files are processed in memory (not permanently stored)
- All communication uses HTTPS
- No data is retained after processing

---

Your AI Meeting Summarizer is now ready to transform your meetings into actionable insights! 🚀

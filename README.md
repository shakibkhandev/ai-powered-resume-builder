# AI-Powered Resume Builder

A modern Flask-based web application that generates professional resumes with AI-powered summaries using Google's Gemini 1.5 Flash model.

## Features

- 📝 Create professional resumes in DOCX format
- 🤖 AI-generated professional summaries using Google's Gemini
- 🎨 Clean and professional document formatting
- 📱 RESTful API for easy integration
- 🔄 Automatic document storage and retrieval

## Prerequisites

- Python 3.13 or higher
- Google API key for Gemini AI
- Git (for version control)
- uv (modern Python package installer)

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/ai-powered-resume-builder.git
cd ai-powered-resume-builder
```

2. Install uv if you haven't already:

```bash
pip install uv
```


4. Install dependencies using uv:

```bash
uv pip install -e .
```

Or install dependencies individually:

```bash
uv add flask
uv add python-dotenv
uv add google-generativeai
uv add python-docx
```

4. Create a `.env` file in the root directory and add your Google API key:

```
GOOGLE_API_KEY=your_api_key_here
```

## Usage

1. Start the Flask server:

```bash
uv run main.py
```

2. The server will start at `http://localhost:5000`

3. Use the API endpoints:

### API Endpoints

- `GET /` - Check if server is running
- `GET /health` - Check server health
- `POST /resume` - Create a new resume
- `GET /docs/<filename>` - Download generated resume

### Example POST Request

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "+1 234 567 8900",
  "address": "123 Main St, City, Country",
  "role": "Software Engineer",
  "skills": ["Python", "JavaScript", "Docker", "AWS"],
  "experience": [
    {
      "role": "Senior Developer",
      "company": "Tech Corp",
      "duration": "2020-2023",
      "description": "Led development of cloud-native applications"
    }
  ],
  "education": [
    {
      "degree": "BS Computer Science",
      "institution": "University of Technology",
      "year": "2019"
    }
  ]
}
```

## Project Structure

```
ai-powered-resume-builder/
├── main.py           # Main application file
├── docs/            # Generated resumes storage
├── .env             # Environment variables
├── pyproject.toml   # Project dependencies
├── uv.lock          # Lock file for dependencies
└── README.md        # Project documentation
```

## How It Works

1. The application receives resume data through a POST request
2. If no summary is provided, it uses Google's Gemini AI to generate a professional summary
3. Creates a formatted DOCX document using python-docx
4. Stores the document in the `docs` directory
5. Returns a download URL for the generated resume

## Contributing

1. Fork the repository
2. Create a new branch for your feature:

```bash
git checkout -b feature/your-feature-name
```

3. Make your changes and commit them:

```bash
git commit -m "Add your commit message"
```

4. Push to your fork:

```bash
git push origin feature/your-feature-name
```

5. Create a Pull Request from your fork to this repository

### Contribution Guidelines

- Follow PEP 8 style guide for Python code
- Write meaningful commit messages
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting PR

## License

This project is open source and available under the MIT License.

## Support

For support, please open an issue in the GitHub repository.

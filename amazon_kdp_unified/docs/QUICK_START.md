# 🚀 Quick Start Guide - Amazon KDP Unified Platform

Get up and running in 5 minutes!

## Prerequisites

- Python 3.10+
- pip or conda
- Git

## 1. Installation

```bash
# Clone repository
git clone https://github.com/63pki/bytebot.git
cd bytebot

# Checkout KDP branch
git checkout amazon-kdp-unified

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r amazon_kdp_unified/requirements.txt
```

## 2. Configuration

```bash
# Copy environment template
cp amazon_kdp_unified/.env.example amazon_kdp_unified/.env

# Edit .env with your API keys
nano amazon_kdp_unified/.env
```

**Required API Keys:**
- `OPENAI_API_KEY` - Get from https://platform.openai.com
- `KDP_EMAIL` & `KDP_PASSWORD` - Your Amazon KDP account

## 3. Start Using

### Generate Book Outline

```python
from amazon_kdp_unified.core.content_generation import OutlineGenerator

generator = OutlineGenerator()
outline = generator.generate(
    topic="Python Programming",
    chapters=10
)

print(f"Generated {len(outline)} chapters")
for chapter in outline:
    print(f"  - {chapter['title']}")
```

### Research Keywords

```python
from amazon_kdp_unified.core.market_intelligence import KeywordResearcher

researcher = KeywordResearcher()
keywords = researcher.research_keywords(
    topic="self-help",
    limit=10
)

for kw in keywords:
    print(f"{kw['keyword']}: {kw['search_volume']} searches")
```

### Analyze Niche

```python
from amazon_kdp_unified.core.market_intelligence import MarketAnalyzer

analyzer = MarketAnalyzer()
niche = analyzer.analyze_niche("productivity books")

print(f"Profitability: {niche['profitability_score']}/100")
print(f"Competition: {niche['competition']}")
print(f"Market Size: {niche['market_size']} books")
```

### Format Book

```python
from amazon_kdp_unified.core.formatting import BookFormatter

formatter = BookFormatter()
epub = formatter.markdown_to_epub(
    input_file="my_book.md",
    validate=True
)

print(f"Created: {epub}")
```

## 4. Start API Server

```bash
cd amazon_kdp_unified
python api/main.py
```

Visit: http://localhost:8000/docs

## 5. Common Tasks

### Generate Chapter

```python
from amazon_kdp_unified.core.content_generation import ChapterWriter

writer = ChapterWriter()
chapter = writer.generate(
    chapter_title="Getting Started",
    outline={"key_points": ["Point 1", "Point 2"]},
    word_count=5000
)
```

### Develop Character

```python
from amazon_kdp_unified.core.content_generation import CharacterDeveloper

developer = CharacterDeveloper()
character = developer.generate(
    character_name="John Doe",
    role="protagonist",
    genre="fiction"
)
```

### Validate Format

```python
from amazon_kdp_unified.core.formatting import FormatValidator

validator = FormatValidator()
report = validator.validate_kdp_format("my_book.epub")

if report['is_compliant']:
    print("✅ Book is KDP compliant!")
else:
    print(f"⚠️ Issues: {report['issues']}")
```

## 6. Next Steps

- 📖 Read [Full Documentation](README.md)
- 🔌 Explore [API Reference](API_REFERENCE.md)
- 💡 Check [Examples](../examples/)
- 🤝 Contribute on [GitHub](https://github.com/63pki/bytebot)

## Need Help?

- 📧 Email: support@kdp-unified.dev
- 🐛 [Report Issues](https://github.com/63pki/bytebot/issues)
- 💬 [GitHub Discussions](https://github.com/63pki/bytebot/discussions)

---

**Happy publishing! 🎉**

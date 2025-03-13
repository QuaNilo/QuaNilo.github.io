---
title: "Social Media Scraper(NOOP)"
excerpt: "Leveraged LangChain for data processing and retrieval-augmented generation (RAG), integrating OpenAI's LLM models for contextual understanding..<br/>"
collection: portfolio
---

[Github](https://github.com/QuaNilo/SocialScrapers)

 **Social Scraper** is a Python-based web application that checks the availability of usernames across multiple social media platforms. Utilizing technologies such as Puppeteer Python (Pyppeteer), Flask, and web scraping libraries like Beautiful Soup, this tool provides a unified interface to verify username availability.

## Supported Platforms

The application supports the following social media networks:

- Twitter
- Instagram
- Reddit
- TikTok
- YouTube
- Twitch
- Facebook

## Example Usage

### `/checkall_handle`

- **Methods:** `GET`
- **Parameters:**
  - `handle`: The username to check for availability across all supported platforms.

**Response** 
```json
{
    "data": {
        "facebook": {
            "is_available": "Failure",
            "success": false
        },
        "instagram": {
            "is_available": false,
            "success": true
        },
        "reddit": {
            "is_available": false,
            "success": true
        },
        "tiktok": {
            "is_available": false,
            "success": true
        },
        "twitch": {
            "is_available": false,
            "success": true
        },
        "twitter": {
            "is_available": false,
            "success": true
        },
        "youtube": {
            "is_available": false,
            "success": true
        }
    },
    "success": true
}
```


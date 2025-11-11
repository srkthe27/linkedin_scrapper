# LinkedIn Profile Scraper

A Python-based web scraper that extracts comprehensive profile information from LinkedIn using Selenium WebDriver. This tool automates the process of collecting profile data including basic info, experience, education, skills, and more.

## Features

- 🔐 Automated LinkedIn login
- 👤 Extracts comprehensive profile information:
  - Name, headline, and location
  - About section
  - Work experience (with company and duration)
  - Education details
  - Skills (up to 20 skills)
- 🤖 Human-like behavior simulation to avoid detection
- 📊 Exports data to CSV format
- ⏱️ Built-in delays and random intervals between requests
- 📝 Detailed logging for monitoring scraping progress

## Prerequisites

- Python 3.7+
- Chrome browser installed
- ChromeDriver (compatible with your Chrome version)

## Installation

1. Clone this repository or download the notebook file

2. Install required dependencies:
```bash
pip install selenium python-dotenv
```

## Configuration

1. Create a `.env` file in the same directory as the notebook:
```env
LINKEDIN_EMAIL=your_email@example.com
LINKEDIN_PASSWORD=your_password
```

2. Update the `PROFILE_URL` list in the notebook with the LinkedIn profile URLs you want to scrape:
```python
PROFILE_URL = []
```

## Usage

### Running in Jupyter Notebook

1. Open the notebook:
```bash
jupyter notebook linkedin_profile.ipynb
```

2. Run all cells sequentially, or run them individually:
   - Cell 1: Install dependencies
   - Cell 2: Import libraries and load environment variables
   - Cell 3: Set credentials and profile URLs
   - Cell 4: Define the `LinkedInScraper` class
   - Cell 5: Execute the scraper

### Output

The scraper generates a CSV file named `linkedin_scraped_enhanced.csv` with the following columns:

- `profile_url` - LinkedIn profile URL
- `name` - Full name
- `headline` - Professional headline
- `location` - Location
- `about` - About/summary section
- `exp_title` - First experience title
- `exp_company` - First experience company
- `experience_full` - All experiences (pipe-separated)
- `education` - Primary education
- `education_full` - All education entries (pipe-separated)
- `skills` - Top 10 skills (comma-separated)
- `skills_full` - All skills (comma-separated)

## Key Features Explained

### Human-like Behavior
- Random delays between actions (1-3 seconds)
- Smooth scrolling simulation
- Character-by-character typing for login
- Random wait times between profile scrapes (5-10 seconds)

### Robust Element Detection
- Multiple CSS selector strategies for each element
- Graceful handling of missing elements
- Automatic "Show More" button clicking for expanded content

### Error Handling
- Comprehensive try-catch blocks
- Detailed logging for debugging
- Continues scraping even if individual profiles fail

## Important Notes

### Legal and Ethical Considerations

⚠️ **Important**: This tool is for educational purposes only. When using this scraper:

1. **Respect LinkedIn's Terms of Service**: Automated scraping may violate LinkedIn's Terms of Service
2. **Rate Limiting**: The script includes delays, but excessive scraping may result in account restrictions
3. **Privacy**: Only scrape public profile information
4. **Personal Use**: Use responsibly and ethically
5. **Account Risk**: Your LinkedIn account may be flagged or banned for automated activity

### Best Practices

- Don't scrape too many profiles in a short time
- Use reasonable delays between requests
- Consider using LinkedIn's official API for production use
- Keep your credentials secure (never commit `.env` files)

## Troubleshooting

### Common Issues

1. **ChromeDriver version mismatch**
   - Ensure ChromeDriver version matches your Chrome browser version
   - Download from: https://chromedriver.chromium.org/

2. **Login fails**
   - Verify credentials in `.env` file
   - Check if LinkedIn requires additional verification
   - Try logging in manually first

3. **Elements not found**
   - LinkedIn may have updated their HTML structure
   - Check console logs for specific errors
   - Update CSS selectors if needed

4. **Rate limiting**
   - Increase delays between requests
   - Reduce number of profiles per session
   - Wait before running again

## Logging

The script uses Python's logging module with INFO level by default. Logs include:
- Login status
- Profile scraping progress
- Success/error messages
- Data save confirmations

## Customization

### Adjusting Delays
Modify delay parameters in the class methods:
```python
self.human_delay(min_sec=1, max_sec=3)  # Adjust as needed
```

### Changing Output Format
Modify the `save_to_csv` method to change output format or add fields.

### Adding More Fields
Extend extraction methods to capture additional profile information.

## License

This project is provided as-is for educational purposes. Use at your own risk.

## Disclaimer

This tool is not affiliated with, endorsed by, or connected to LinkedIn Corporation. The authors are not responsible for any misuse of this tool or any consequences resulting from its use.

## Support

For issues or questions:
1. Check the troubleshooting section
2. Review LinkedIn's HTML structure for changes
3. Ensure all dependencies are correctly installed
4. Check logs for specific error messages

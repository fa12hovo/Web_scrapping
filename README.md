# Web Scraping Project

This project is a **Python-based web scraping tool** that uses the `Trafilatura` library to extract and save text content from a list of specified websites. The program is designed to process multiple URLs, extract their main content, and save each website's content to a separate `.txt` file.

## Features
- Fetches HTML content from a list of websites.
- Extracts and cleans main text content using `Trafilatura`.
- Saves extracted content from each website into a unique `.txt` file.

## Getting Started

### Prerequisites
Ensure you have Python installed (version 3.6 or higher recommended). You'll also need to install the following Python libraries:
- `Trafilatura` (for web content extraction)

To install Trafilatura, use:
```bash
pip install trafilatura
```

### Installation
Clone the repository to your local machine:
```bash
git clone https://github.com/your-username/Web_Scraping_Project.git
cd Web_Scraping_Project
```

### Usage
1. **Prepare the List of URLs**: 
   Update the list of URLs in the notebook file (or the provided Python script) by setting the `found_url` variable to contain the URLs you wish to scrape.

2. **Run the Notebook**:
   Open the notebook (`Web_Scrapping_Project.ipynb`) and run each cell to execute the scraping script. 

   Alternatively, you can convert the notebook to a Python script and run it directly:
   ```bash
   jupyter nbconvert --to script Web_Scrapping_Project.ipynb
   python Web_Scrapping_Project.py
   ```

3. **Output**: 
   Each URL's content will be saved to a `.txt` file, named according to the URL structure. These files are saved in the project directory.

### Code Example
Here’s a simplified version of the code to fetch and save content:
```python
from trafilatura import fetch_url, extract

def fetch_website_content(url):
    downloaded = fetch_url(url)
    if downloaded:
        extracted = extract(downloaded)
        return extracted
    else:
        print(f"Failed to download content from {url}")
        return None

found_url = ['https://example.com', 'https://example2.com']

for url in found_url:
    content = fetch_website_content(url)
    if content:
        file_name = f"{url.replace('https://', '').replace('http://', '').replace('/', '_')}.txt"
        with open(file_name, "w", encoding="utf-8") as file:
            file.write(content)
```

### Files
- `Web_Scrapping_Project.ipynb`: Main Jupyter Notebook file containing the web scraping code and instructions for execution.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue for suggestions or improvements.

## License
This project is licensed under the MIT License.

## Acknowledgments
- [Trafilatura Library](https://github.com/adbar/trafilatura) for easy and reliable web content extraction.

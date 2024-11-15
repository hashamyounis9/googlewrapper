# Google Search Scraper API

This is a Flask-based API that scrapes Google search results asynchronously using the `nodriver` package for browser automation and `BeautifulSoup` for HTML parsing. The API returns detailed information about search results, including URLs, titles, site names, and overviews.

## Features

- **Asynchronous Scraping:** Uses `asyncio` and `nodriver` to scrape Google search results efficiently.
- **Headless Browser Automation:** The API runs the browser in headless mode for fast and resource-efficient scraping.
- **HTML Parsing:** Utilizes `BeautifulSoup` to extract and organize data from the HTML content.
- **Customizable Queries:** Allows users to perform Google searches through a simple API endpoint.

## Prerequisites

Before running the API, ensure that you have the following installed:

- Python 3.7 or higher
- `nodriver` package
- `Flask` package
- `BeautifulSoup` package

You can install the required packages using `pip`:

```bash
pip install flask nodriver beautifulsoup4
```

## Getting Started

### Running the API

1. **Clone the repository:**

    ```bash
    git clone https://github.com/hashamyounis9/googlewrapper 
    cd googlewrapper 
    ```

2. **Run the Flask application:**

    ```bash
    python app.py
    ```

    The API will start running on `http://127.0.0.1:5000`.

### API Usage

To use the API, send a GET request to the root endpoint with a `q` parameter, which represents your Google search query.

#### Example Request:

```bash
curl "http://127.0.0.1:5000/?q=python+web+scraping"

[
    {
        "site_url": "https://example.com",
        "result_heading": "Example Title",
        "result_by_site": "Example Site",
        "result_overview": "This is a brief overview of the search result.",
        "site_logo": "https://example.com/logo.png"
    },
    
]
```
### Error Handling

The API includes basic error handling. If something goes wrong, you may receive an error response like the following:

```json
{
    "error": "Some error occurred while performing the query",
    "hint": "Maybe your query is invalid/unclear"
}
```
### Customization

You can customize the scraping behavior by modifying the `scrape` function in `app.py`. For example, you can change the elements being selected or the way the HTML is parsed.

### Sample Query: "Apples"

Here is a sample image result for the query "Apples":

![Sample Image for Apples](/screenshot/Apples.png)

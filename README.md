# Google-dorking-for-downloading-book
from googlesearch import search
import re

# Define your dorking query
query = 'filetype:pdf "rich dad and poor dad"'

# Search Google using the query
results = []
try:
    # Search and fetch PDF links
    for url in search(query, num=10, stop=10, pause=2):
        if re.search(r'\.pdf$', url, re.IGNORECASE):  # Ensure only PDF links are added
            results.append(url)
except Exception as e:
    print(f"An error occurred: {e}")

# Print the found PDF links
for pdf_link in results:
    print(pdf_link)

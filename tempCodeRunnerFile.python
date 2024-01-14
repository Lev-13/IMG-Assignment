import requests
from bs4 import BeautifulSoup

url = 'https://www.91mobiles.com/entertainment/new-movies#:~:text=1%20Drama%2848288%29%202%20Comedy%2828796%29%203%20Thriller%2817860%29%204%20Action%2815276%29,6%20Horror%2814216%29%207%20Documentary%2823601%29%208%20Crime%289150%29%20More%20items'

# Send a GET request to the URL
response = requests.get(url)

# Check if the request was successful (status code 200)
if response.status_code == 200:
    # Parse the HTML content of the page
    soup = BeautifulSoup(response.text, 'html.parser')

    # Find the container(s) that hold the movie information
    movie_containers = soup.find_all('div', class_='movie-container')

    # Open an HTML file in append mode
    with open('mmm.html', 'a', encoding='utf-8') as html_file:
        # Iterate through the movie containers and extract information
        for movie_container in movie_containers:
            # Extract movie details (replace these with the actual tags/classes)
            title = movie_container.find('h2', class_='movie-title').text
            genre = movie_container.find('span', class_='genre').text
            rating = movie_container.find('span', class_='rating').text

            # Write the movie details to the HTML file
            html_file.write(f'<div class="movie">\n')
            html_file.write(f'  <h2>{title}</h2>\n')
            html_file.write(f'  <p>Genre: {genre}</p>\n')
            html_file.write(f'  <p>Rating: {rating}</p>\n')
            html_file.write(f'</div>\n')

    print('Movies added to HTML file successfully.')

else:
    print(f'Failed to retrieve the page. Status code: {response.status_code}')

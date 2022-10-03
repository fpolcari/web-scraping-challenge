# web-scraping-challenge

The instructions for this assignment are divided into three parts: 
1. Scraping 
2. MongoDB and Flask Application
3. Submission 

Part  1: Scraping

I completed my initial scraping using jupyter Notebook, BeautifulSoup, Pandas, and Requests/Splinter.

Then I created a file called `mission_to_mars.ipynb` and used it to complete all of my scraping and analysis tasks. 
We scraped the [Mars News Site](https://redplanetscience.com/) and collected the latest News Title and Paragraph Text. 
Then I visited the URL for the Featured Space Image site [here](https://spaceimages-mars.com) and used Splinter to navigate the site and find the image URL for the current Featured Mars Image, then assigned the URL string to a variable called `featured_image_url`.
I made sure to find the image URL to the full-sized `.jpg` image and saved a complete URL string for this image.

Afterwards, I visit the [Mars Facts webpage](https://galaxyfacts-mars.com) and used Pandas to scrape the table containing facts about the planet including diameter, mass, etc. I also used Pandas to convert the data to a HTML table string.

Mars Hemispheres

Visited the [astrogeology site](https://marshemispheres.com/) to obtain high-resolution images for each hemisphere of Mars.

I found the the image URL to the full-resolution image and save the image URL string for the full resolution hemisphere image and the hemisphere title containing the hemisphere name. Use a Python dictionary to store the data using the keys `img_url` and `title`. Then I appended the dictionary with the image URL string and the hemisphere title to a list.

The second of this challenge included MongoDB and Flask Application

I used MongoDB with Flask templating to create a new HTML page that displays all the information that was scraped from the URLs above.

I started by converting the Jupyter notebook into a Python script called `scrape_mars.py` by using a function called `scrape`. This function executed all of my scraping code from above and return one Python dictionary containing all the scraped data.

Next, I create a route called `/scrape` that will import my `scrape_mars.py` script and call my `scrape` function. Then I stored the return value in Mongo as a Python dictionary. Then I created a root route `/` that will query my Mongo database and pass the Mars data into an HTML template for displaying the data.

Then I created a template HTML file called `index.html` that took the Mars data dictionary and displayed all the data in the appropriate HTML elements. My final page looked like this:
<img width="728" alt="Screen Shot 2022-10-03 at 1 15 27 AM" src="https://user-images.githubusercontent.com/106457512/193506731-e7c25d06-d287-4c27-8c4e-8718970d5967.png">

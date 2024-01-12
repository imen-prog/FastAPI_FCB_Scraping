##FastAPI Facebook Scraper Service Documentation

###Introduction
A dockerized facebook scrapping service using fastAPI.
This FastAPI service allows you to scrape Facebook posts using the facebook_scraper library and store them in a MongoDB database.
###setup
Prerequisites
*Python installed (version 3.7 or higher)
*MongoDB installed and running locally (default port: 27017)
Installation
*Clone the repository:
```bash
git clone https://github.com/imen-prog/FastAPI_FCB_Scraping.git
cd FastAPI_FCB_Scraping
```
*Install dependencies:
```bash
pip install fastapi[all] facebook-scraper pymongo
```
*Set up a .env file with the necessary environment variables:
```bash
MONGO_URI=mongodb://localhost:27017
```
Replace mongodb://localhost:27017 with your actual MongoDB URI.

*Run the FastAPI service:
```bash
uvicorn main:app --reload
```
This will start the FastAPI service on http://localhost:8000.
###Usage
*Scrape Facebook Posts
- Endpoint: /scrap/
- Parameters:
page (str): Facebook page ID or username.
limit (int, optional): Number of pages to scrape (default: 2).
save (bool, optional): Save scraped posts to MongoDB (default: False).
Example:
```bash
curl "http://localhost:8000/scrap/?page=your_page_id&limit=5&save=true"
```
* Get a Specific Post
Endpoint: /post/
Parameters:
post_id (str): ID of the post to retrieve.
Example:
```bash
curl "http://localhost:8000/post/?post_id=your_post_id"
```
*Load Data based on Query Parameters
Endpoint: /load/
Parameters: Any valid MongoDB query parameters.
Example:
```bash
curl "http://localhost:8000/load/?param1=value1&param2=value2"
```
###Additional Information
The service supports automatic reloading with the --reload flag during development. You may remove it in a production environment.



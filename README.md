# News-App

The provided HTML code represents the structure of a web page for a news application. It includes navigation links, a search bar, and a section for displaying news articles. Here's an explanation of the key parts of the HTML structure:

1. **Document Type Declaration (<!DOCTYPE html>)**: This declaration specifies that the document follows the HTML5 standard.

2. **`<html>` Element**: The root element that encapsulates the entire HTML document. The `lang` attribute is set to "en" to indicate that the document is in English.

3. **`<head>` Element**: This section contains metadata about the document, including character encoding, viewport settings, and the document's title. It also links an external stylesheet (`style.css`) for styling.

4. **`<body>` Element**: The main content of the web page is contained within this element.

5. **Navigation (`<nav>`) Section**: This section contains the website's navigation elements, company logo, and search bar.

    - **Company Logo**: An anchor (`<a>`) element with an `onclick` attribute that calls the `reload()` function when clicked. It displays a company logo image.

    - **Navigation Links**: A list of navigation links represented as list items (`<li>`) within an unordered list (`<ul>`). Each navigation link has an `onclick` attribute that triggers the `onNavItemClick()` function with a specific identifier when clicked.

    - **Search Bar**: A search input field (`<input>`) with the ID "search-text" and a search button (`<button>`) with the ID "search-button."

6. **Main Content (`<main>`) Section**: This section is where the news articles will be displayed. It contains a `<div>` element with the ID "cards-container," which will be populated with news cards dynamically.

7. **News Card Template (`<template>`)**: This hidden template defines the structure of an individual news card. It includes an image, a title, a source name and date, and a description. The actual content for these elements will be populated dynamically using JavaScript.

8. **JavaScript File**: The JavaScript file "script.js" is linked at the end of the HTML body. This script is responsible for fetching news data, populating the news cards, and handling user interactions.

Overall, this HTML code provides the basic structure for a news application's front-end. The JavaScript file (script.js) is expected to handle the dynamic functionality, such as fetching news data and updating the webpage with the retrieved articles. The CSS file (style.css) is responsible for styling the elements on the page, but the provided code does not include its content.

`***************************************************************************************************************************************`

## Javascript code explanation

The provided code is for a simple news web application that fetches news articles using the News API and displays them on a webpage. It also allows users to search for news articles based on a query. Here's a breakdown of the Javascript code:

1. **API_KEY**: This is a constant variable that stores the API key required to make requests to the News API. You should replace this with your own API key.

2. **url**: This variable stores the base URL for the News API. Later, the `fetchNews` function will append the search query and API key to this URL.

3. **window.addEventListener("load", ...)**: This event listener is triggered when the web page is fully loaded. It calls the `fetchNews` function with the initial query "India" to load news articles related to India when the page loads.

4. **reload()**: This function reloads the web page when called. It's not used in the provided code.

5. **fetchNews(query)**: This asynchronous function is responsible for fetching news articles from the News API based on the provided `query`. It uses the `fetch` API to make a GET request to the News API with the specified query and API key. Once the response is received, it's converted to JSON, and the `bindData` function is called to display the news articles.

6. **bindData(articles)**: This function takes an array of `articles` and displays them on the webpage. It first clears the content of the `cardsContainer`, which is a DOM element where the news articles will be displayed. Then, it iterates through each article, checks if there is a URL to an image, clones a template card, fills in the data using the `fillDataInCard` function, and appends it to the `cardsContainer`.

7. **fillDataInCard(cardClone, article)**: This function populates the data of an individual news card. It takes a cloned card element and an article object as parameters and sets the image source, title, description, source name, and publication date. It also adds an event listener to the card, allowing users to open the full article in a new tab when clicked.

8. **onNavItemClick(id)**: This function is called when a navigation item is clicked. It fetches news articles based on the provided `id`, which typically represents a category or topic. It also updates the active state of the selected navigation item.

9. **searchButton.addEventListener("click", ...)**: This event listener is triggered when the search button is clicked. It fetches news articles based on the user's query input in the `searchText` input field. It also removes the active state from the currently selected navigation item, if any.

Overall, this code sets up a basic news application that fetches and displays news articles based on user interactions, such as clicking on navigation items and searching for specific news topics. It uses the News API for data retrieval and dynamically updates the webpage with the fetched articles.

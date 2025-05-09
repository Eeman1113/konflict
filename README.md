# Konflict 

**Konflict** is a web-based news digest application designed to curate and display news articles focusing on events and tensions primarily between India and Pakistan. It aggregates content from a wide array of public RSS feeds, filters them based on relevance to the conflict, and presents them in a clean, user-friendly interface.

Visit the live site: [https://eeman1113.github.io/konflict/](https://eeman1113.github.io/konflict/)

## Motivation

This project was born out of a personal need. My girlfriend was finding it challenging to locate a single, consolidated source for news specifically related to the ongoing tensions and conflict dynamics in the region. Konflict aims to address this by providing a focused and easily accessible news digest.

## Key Features

* **Focused News Aggregation:** Gathers news from numerous RSS feeds and specifically filters articles related to India-Pakistan relations, border issues, and regional conflicts.
* **Dynamic Content Display:** Presents news in an easy-to-scan card format, showing title, summary, source, publication date, and an image (with a placeholder if an image is unavailable).
* **Dark Mode:** Offers a toggle for a dark theme, with user preference saved in local storage for persistence across sessions.
* **Auto-Refresh:** Automatically fetches and updates news articles every 2 minutes to provide the latest information.
* **Manual Refresh:** Allows users to manually trigger a news update at any time.
* **Relevant Keyword Filtering:** Utilizes predefined lists of keywords related to geographical locations, conflict terminology, military actions, diplomatic activities, and key entities to ensure the relevance of displayed articles.
* **Responsive Design:** The interface is built with Tailwind CSS, making it adaptable to different screen sizes (desktop, tablet, mobile).
* **Error Handling:** Displays informative messages if news fetching fails or if no relevant articles are found.
* **Modern Aesthetics:** Features a clean, contemporary design with smooth animations and transitions for an enhanced user experience.
* **Accessibility Considerations:** Implements ARIA attributes for better accessibility, such as for the dark mode toggle and loading indicators.

## How It Works

1.  **RSS Feed Aggregation:** The application maintains a list of diverse RSS feed URLs from various news sources.
2.  **Fetching News:** It uses the `rss2json.com` API to fetch data from these RSS feeds. Each feed is fetched asynchronously.
3.  **Content Filtering:**
    * For each fetched article, the title and description are combined.
    * This combined text is then checked against predefined keyword lists:
        * `PRIMARY_ENTITIES_INDIA`: Keywords related to India (e.g., "india", "delhi").
        * `PRIMARY_ENTITIES_PAKISTAN`: Keywords related to Pakistan (e.g., "pakistan", "islamabad").
        * `SPECIFIC_CONFLICT_KEYWORDS`: A comprehensive list of terms associated with conflicts, military, diplomacy, specific locations (e.g., "kashmir", "loc", "ceasefire", "airstrike", "peace talks").
        * `SUPER_SPECIFIC_SINGLE_KEYWORDS`: Highly specific terms that, if present with either an India or Pakistan mention, would qualify an article (e.g., "balakot", "surgical strike").
    * An article is deemed relevant if:
        * It mentions both India and Pakistan entities AND at least one general conflict keyword.
        * OR it mentions either India or Pakistan entities AND at least one super-specific single keyword.
        * OR it mentions either India or Pakistan entities AND at least two general conflict keywords.
4.  **Displaying News:** Relevant articles are sorted by publication date (newest first) and displayed as cards. Each card includes:
    * An image (or a placeholder).
    * Article title.
    * A summarized description (truncated if too long).
    * Source name and publication date.
    * Category tag (derived from feed title or article categories).
    * A link to read the full report on the original source's website.
5.  **User Interface & Experience:**
    * A loading indicator is shown while news is being fetched.
    * An error message is displayed if fetching fails or no relevant articles are found.
    * The dark mode can be toggled via a button in the top-left corner.
    * A manual refresh button is also available.
    * The footer displays the current year and a link to the creator's profile.

## Technologies Used

* **HTML:** Structure of the web page.
* **CSS (Tailwind CSS & Custom CSS):** Styling and layout, including responsive design and dark mode theming.
* **JavaScript:** Core logic for fetching, filtering, and displaying news, handling user interactions, managing dark mode, and auto-updates.
* **RSS2JSON API:** Used to convert RSS feeds into a more manageable JSON format.
* **Google Fonts:** For typography ('Playfair Display' for titles, 'Lora' for body text).
* **Heroicons:** For SVG icons used in buttons.

## RSS Feed Sources

The application utilizes an extensive list of RSS feeds from various international and regional news organizations, including but not limited to:

* Hindustan Times
* Times of India
* BBC News (World/Asia, India)
* Al Jazeera
* The Guardian
* NDTV
* Dawn
* Reuters
* Associated Press (AP News)
* The Hindu
* The News International
* France24
* India Today
* News18
* Indian Express
* Republic World
* Firstpost
* DNA India
* Economic Times (Defence, General)
* Livefist Defence
* The Diplomat (South Asia)
* Force India
* Greater Kashmir
* Kashmir Observer
* The Tribune India
* Daily Excelsior
* Livemint
* Business Standard
* Financial Express
* Jagran
* Amar Ujala
* Navbharat Times
* Punjab Kesari
* PIB (Press Information Bureau, India)
* Ministry of Defence, India (MoD)
* CNN (Asia)
* Zee News
* Aaj Tak
* Times Now
* Asomiya Pratidin
* Mathrubhumi
* ORF Online (Observer Research Foundation)
* IDSA (Institute for Defence Studies and Analyses)
* CLAWS (Centre for Land Warfare Studies)
* The Wire
* Scroll.in
* ThePrint
* Swarajya
* Indian Defence Review
* Defence News India
* Bharat Shakti
* India Strategic
* Daily Kashmir Images
* Rising Kashmir
* Himachal Watcher
* Eastern Mirror Nagaland
* The Quint
* OpIndia
* NewsClick
* The Logical Indian
* The Better India
* Diplomatist
* South Asian Voices
* Gateway House
* IPCS (Institute of Peace and Conflict Studies)
* CPR India (Centre for Policy Research)
* Carnegie India
* VIF India (Vivekananda International Foundation)
* The Citizen
* Countercurrents
* PGurus
* MediaNama
* NE Now
* EastMojo
* Frontier India
* The Kashmir Monitor
* IndiaSpend
* Factly
* Alt News
* Boom Live
* The Databaaz
* Raksha Anirveda
* Defence Aviation Post
* Businessworld (Defence)
* Def Pro Ac
* Defence Capital

*(Note: The application de-duplicates this list to ensure each unique feed URL is fetched only once.)*

## How to Use / View

Simply open the `index.html` file in a modern web browser, or visit the live deployment at [https://eeman1113.github.io/konflict/](https://eeman1113.github.io/konflict/).

No special setup is required as it's a client-side application. An active internet connection is necessary to fetch news updates.

## Disclaimer

This project is for informational and demonstrative purposes only. The news content is aggregated from public RSS feeds and the application does not endorse or verify the accuracy of the articles. All content rights belong to their respective publishers. The filtering mechanism, while designed to be comprehensive, may occasionally miss relevant articles or include marginally related ones.

## Author

Made by **Eeman Majumder** ([poopsvilla](http://linktr.ee/Eemanmajumder)).

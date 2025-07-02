# BrochureGen-AI
Short Description for GitHub Repository: An AI-powered tool that automates the generation of hyper-personalized, engaging digital brochures for Airbnb listings using Large Language Models (LLMs) and web scraping, with multi-language support.



# BrochureGen-AI: AI-Powered Airbnb Brochure Generator

## Project Overview

`BrochureGen-AI` is an intelligent tool designed to revolutionize how Airbnb hosts market their properties. Leveraging the power of Large Language Models (LLMs) and web scraping, this application automates the creation of professional, engaging, and hyper-personalized digital brochures for any Airbnb listing.

From dynamically crafting property descriptions and amenity highlights to suggesting local attractions tailored to specific guest personas, `BrochureGen-AI` ensures your marketing materials resonate directly with your ideal audience, saving hosts valuable time and enhancing their promotional efforts.

## Key Features

* **Intelligent Content Generation:** Automatically writes compelling property descriptions, amenity highlights, welcome messages, FAQs, and calls-to-action based on scraped webpage content.
* **AI-Driven Personalization & Audience Targeting:** Dynamically tailors brochure language, emphasizes specific amenities, and curates local recommendations to appeal to defined guest personas (e.g., "families," "business travelers," "adventure seekers").
* **Multilingual Support:** (Implied from initial prompt - "put it out in different languages") Generates brochures in various languages, expanding reach.
* **Web Scraping Integration:** Gathers initial property information and relevant company/service links directly from specified URLs.
* **Flexible Output:** Produces brochure content in markdown format, easily convertible to digital brochures or print-ready layouts.
* **Iterative Refinement:** Designed to allow user feedback for refining generated content.

## How It Works (High-Level)

1.  **URL Input:** The user provides the main URL of an Airbnb company's website (or a specific property listing page).
2.  **Web Scraping (`Website` class):** The tool scrapes the main landing page for general company information (title, content) and extracts all internal and external links.
3.  **Relevant Link Filtering (LLM):** An LLM (e.g., GPT-4o-mini) analyzes the extracted links, identifies relevant company pages (e.g., "About," "Services," "Help"), and returns them in a structured JSON format.
4.  **Content Aggregation:** The tool then scrapes the content from these identified relevant links, compiling all the pertinent text.
5.  **Brochure Generation (LLM):** The aggregated content, along with the user's specific instructions (e.g., desired tone, target guest persona), is fed into the LLM. The LLM then generates the full brochure content in markdown, adhering to a defined structure and personalization criteria.
6.  **Display:** The generated markdown brochure is displayed, ready for review or further design integration.

## Setup Instructions

To run this project locally or in a Colab environment, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/BrochureGen-AI.git](https://github.com/your-username/BrochureGen-AI.git)
    cd BrochureGen-AI
    ```
2.  **Install Python dependencies:**
    It's recommended to use a virtual environment.
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: `venv\Scripts\activate`
    pip install -r requirements.txt
    ```
    (You will need to create a `requirements.txt` file containing `requests`, `beautifulsoup4`, `python-dotenv`, `openai`, `ipython` (if using notebooks), `markdown`.)

3.  **Set up OpenAI API Key:**
    * Obtain an API key from [OpenAI](https://platform.openai.com/account/api-keys).
    * Create a `.env` file in the project's root directory.
    * Add your API key to the `.env` file:
        ```
        OPENAI_API_KEY='sk-proj-YOUR_ACTUAL_API_KEY_HERE'
        ```

4.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook Untitled.ipynb
    ```

## Usage

Open the `Untitled.ipynb` notebook and execute the cells sequentially.

Key functions to look for:

* `Website(url)`: To scrape webpage content and links.
* `get_links(url)`: Uses an LLM to identify relevant links from a webpage.
* `get_brochure_user_prompt(company_name, url)`: Aggregates scraped content into a prompt for brochure generation.
* `create_brochure(company_name, url)`: The main function to generate and display the brochure.

## Example Output

Below is an example of a brochure generated for Airbnb:

```markdown
# Welcome to Airbnb: Where Your Next Adventure Awaits!

## The Company

Born in 2007 from the brilliant (and somewhat bold) idea of three guests snuggling in a San Francisco living room, **Airbnb** has skyrocketed into a global lodging phenomenon that has over **5 million hosts**. Imagine a world where your next roommate could be a charming local in Paris, a beach bum in Bali, or even a raccoon in someone’s backyard. Kidding! It’s mostly just great hosts and amazing stays. 

### Fun Facts About Airbnb:
- 🏠 **8 million+** active listings worldwide – enough to turn a casual traveler into a seasoned couch connoisseur.
- 🌍 **150,000 cities** and towns – we’ve probably got a home for you on that one little street in the middle of nowhere!
- 🌎 **220+ countries** – yes, even those places you failed geography on!
- 🎉 **2 billion+ guest arrivals**, ensuring every traveler's comfort... and the occasional awkward encounter.
- 💰 **$300 billion+ earned by hosts** – someone’s out there hosting for their 5th yacht!
  
## Company Culture

Team Airbnb doesn’t just talk about "belonging" – they live it! Here, you’ll find fosters of creativity, adventurers, and dare we say, some world-class couch surfers! We value authenticity and uniqueness, just like our listings. Whether you’re in charge of the ad campaign or just making sure the coffee stays warm (you bet it’s craft brews), we embrace a laid-back but driven atmosphere where innovation flows faster than a double-shot espresso.

### Join the Fun!
Wondering about careers at Airbnb? We’re always looking for talented individuals who think outside the box... or maybe they just want to throw a sleeping bag inside it. From staging homes to designing the next big community experience, your adventurous spirit is welcome here, as long as you observe our only rule: **No bringing your pet alligator to work**.

## Unique Stays & Experiences

Why book a standard hotel when you can stay in a treehouse or a castle (seriously)? Whether it’s **mountain cabins**, **beachfront bungalows**, or just about every other unique habitable structure you can think of, there’s an Airbnb for you. Not only do you share a space, but you can also share experiences! Surfing lessons? Check. Cooking with locals? Double check. Karaoke night in the basement? Only if you can hold a tune! 

### Who Stays on Airbnb? 
Everyone! We’ve hosted millionaires on business trips, families on vacation, and even that one couple who really, really wanted to recreate their favorite rom-com in a 200-year-old lighthouse. 

## Become a Host

Tired of paying rent? Want to earn some cash on the side? Why not become a host? You could be the next proud owner of a **Hostial**! (That’s not a real word, but we can dream.) It’s as easy as making some coffee and leaving out cookies — just say who needs cleaning fees?

### FAQ: 
- Q: Do I need to tidy up? 
  - A: Only if you want to avoid the dreaded **bad review**. Vacuuming is a must!
- Q: Can I host my in-laws?
  - A: Absolutely, just ensure you set clear ground rules… and a good bottle of wine!

---

So, why wait? Dive into the **Airbnb** adventure today! Whether you're a traveler looking for a cozy nook or a creative host ready to invite the world, you belong here. 

Let's get you booked or hosted - the adventure of a lifetime awaits! 

**Airbnb: Not just a house, a whole experience!**

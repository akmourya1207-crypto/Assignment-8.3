I’ll complete Assignment 8.3 — Magazine Layout Using Grid Areas with a complete news-style webpage and a separate CSS file. The design will include a header, navigation bar, featured main article, sidebar with trending stories, additional news cards, and a footer, using grid-template-areas to organize the layout.
1. index.html
Create a folder named Assignment-8.3 and save this code as index.html.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 8.3 - The Daily Magazine</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="magazine">

        <!-- Header -->
        <header class="header">
            <div class="logo">THE DAILY<span>.</span></div>
            <p class="tagline">Stories that matter. News that informs.</p>
            <div class="header-date">YOUR DAILY NEWS SOURCE</div>
        </header>

        <!-- Navigation -->
        <nav class="navigation">
            <a href="#home" class="active">Home</a>
            <a href="#latest">Latest News</a>
            <a href="#technology">Technology</a>
            <a href="#lifestyle">Lifestyle</a>
            <a href="#business">Business</a>
        </nav>

        <!-- Main Featured Article -->
        <main class="main-article" id="home">
            <img
                src="https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=1200&q=85"
                alt="Modern workspace with a bright open office">

            <div class="article-content">
                <span class="category">FEATURED STORY</span>
                <h1>How Innovation Is Changing the Way We Live and Work</h1>
                <p class="article-description">
                    Discover how new ideas, digital tools, and changing
                    lifestyles are shaping the world around us and opening
                    doors to new opportunities.
                </p>
                <div class="article-meta">
                    By Editorial Team <span>•</span> 5 min read
                </div>
                <a href="#latest" class="read-more">Read Full Story →</a>
            </div>
        </main>

        <!-- Sidebar -->
        <aside class="sidebar">
            <section class="sidebar-section">
                <h2>Trending Stories</h2>

                <article class="trending-item">
                    <img
                        src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&w=300&q=80"
                        alt="Person using a laptop">
                    <div>
                        <span class="small-category">TECHNOLOGY</span>
                        <h3>Digital Skills for the Next Generation</h3>
                        <small>4 min read</small>
                    </div>
                </article>

                <article class="trending-item">
                    <img
                        src="https://images.unsplash.com/photo-1490645935967-10de6ba17061?auto=format&fit=crop&w=300&q=80"
                        alt="Healthy food arranged on a table">
                    <div>
                        <span class="small-category">LIFESTYLE</span>
                        <h3>Simple Habits for a Healthier Life</h3>
                        <small>3 min read</small>
                    </div>
                </article>

                <article class="trending-item">
                    <img
                        src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&w=300&q=80"
                        alt="Business analytics on a computer screen">
                    <div>
                        <span class="small-category">BUSINESS</span>
                        <h3>Understanding Today's Digital Economy</h3>
                        <small>6 min read</small>
                    </div>
                </article>
            </section>

            <section class="newsletter">
                <h2>Stay Informed</h2>
                <p>Explore stories, ideas, and useful updates every day.</p>
                <a href="#latest">Explore More Stories</a>
            </section>
        </aside>

        <!-- Latest Articles -->
        <section class="latest" id="latest">
            <div class="section-heading">
                <h2>Latest Stories</h2>
                <span>MORE TO EXPLORE</span>
            </div>

            <div class="story-grid">
                <article class="story-card" id="technology">
                    <img
                        src="https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=600&q=80"
                        alt="Electronic circuit board">
                    <div class="story-content">
                        <span class="category">TECHNOLOGY</span>
                        <h3>The Technology Shaping Our Future</h3>
                        <p>
                            A look at the innovations changing how people
                            connect, learn, and solve problems.
                        </p>
                        <small>4 min read</small>
                    </div>
                </article>

                <article class="story-card" id="lifestyle">
                    <img
                        src="https://images.unsplash.com/photo-1470252649378-9c29740c9fa8?auto=format&fit=crop&w=600&q=80"
                        alt="Sunrise over a peaceful landscape">
                    <div class="story-content">
                        <span class="category">LIFESTYLE</span>
                        <h3>Finding Balance in a Busy World</h3>
                        <p>
                            Small changes in everyday routines can help
                            create more time for what matters.
                        </p>
                        <small>3 min read</small>
                    </div>
                </article>

                <article class="story-card" id="business">
                    <img
                        src="https://images.unsplash.com/photo-1460472178825-e5240623afd5?auto=format&fit=crop&w=600&q=80"
                        alt="People collaborating in a modern office">
                    <div class="story-content">
                        <span class="category">BUSINESS</span>
                        <h3>New Ideas for Growing Businesses</h3>
                        <p>
                            Learn how creativity, teamwork, and planning
                            can support long-term growth.
                        </p>
                        <small>5 min read</small>
                    </div>
                </article>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <div class="footer-logo">THE DAILY<span>.</span></div>
            <p>A magazine-style webpage built with HTML and CSS Grid.</p>
            <p class="copyright">© 2026 The Daily Magazine | Assignment 8.3</p>
        </footer>

    </div>

</body>
</html>



2. style.css
Save the following code in style.css in the same folder.

/* Assignment 8.3 - Magazine Layout Using Grid Areas */

/* Basic Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background-color: #f3f4f6;
    color: #222b3a;
    line-height: 1.6;
}

/* Main Magazine Grid */
.magazine {
    width: min(1200px, 94%);
    margin: 25px auto;
    padding: 24px;
    background-color: #ffffff;

    display: grid;

    /* Main article receives more space than the sidebar */
    grid-template-columns: minmax(0, 2fr) minmax(270px, 1fr);

    /* Named grid areas define the page structure */
    grid-template-areas:
        "header header"
        "navigation navigation"
        "main sidebar"
        "latest sidebar"
        "footer footer";

    gap: 24px;
}

/* Header */
.header {
    grid-area: header;
    text-align: center;
    padding: 18px 10px 25px;
    border-bottom: 3px solid #222b3a;
}

.logo {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 43px;
    font-weight: bold;
    letter-spacing: 3px;
}

.logo span,
.footer-logo span {
    color: #d94841;
}

.tagline {
    margin-top: 5px;
    color: #70798a;
    font-size: 14px;
}

.header-date {
    margin-top: 12px;
    font-size: 11px;
    letter-spacing: 2px;
    color: #d94841;
    font-weight: bold;
}

/* Navigation */
.navigation {
    grid-area: navigation;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
    border-bottom: 1px solid #e1e4e9;
    padding: 0 0 15px;
}

.navigation a {
    text-decoration: none;
    color: #343d4d;
    font-size: 14px;
    font-weight: bold;
    padding: 8px 14px;
    border-radius: 5px;
    transition: background-color 0.2s, color 0.2s;
}

.navigation a:hover,
.navigation a.active {
    background-color: #d94841;
    color: #ffffff;
}

/* Main Featured Article */
.main-article {
    grid-area: main;
    min-width: 0;
}

.main-article > img {
    display: block;
    width: 100%;
    height: 300px;
    object-fit: cover;
    border-radius: 6px;
}

.article-content {
    padding-top: 18px;
}

.category {
    display: inline-block;
    color: #d94841;
    font-size: 11px;
    font-weight: bold;
    letter-spacing: 1.5px;
    margin-bottom: 8px;
}

.article-content h1 {
    font-family: Georgia, "Times New Roman", serif;
    font-size: clamp(25px, 3vw, 36px);
    line-height: 1.2;
    margin-bottom: 13px;
}

.article-description {
    font-size: 15px;
    color: #667085;
    margin-bottom: 14px;
}

.article-meta {
    color: #7b8494;
    font-size: 12px;
    margin-bottom: 16px;
}

.article-meta span {
    padding: 0 5px;
}

.read-more {
    display: inline-block;
    color: #d94841;
    font-size: 14px;
    font-weight: bold;
    text-decoration: none;
}

.read-more:hover {
    text-decoration: underline;
}

/* Sidebar */
.sidebar {
    grid-area: sidebar;
    min-width: 0;
    align-self: start;
    border-left: 1px solid #e5e7eb;
    padding-left: 20px;
}

.sidebar-section h2,
.newsletter h2 {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 22px;
    margin-bottom: 18px;
    padding-bottom: 10px;
    border-bottom: 2px solid #d94841;
}

.trending-item {
    display: grid;
    grid-template-columns: 95px minmax(0, 1fr);
    gap: 12px;
    padding: 14px 0;
    border-bottom: 1px solid #e5e7eb;
}

.trending-item img {
    width: 95px;
    height: 90px;
    object-fit: cover;
    border-radius: 5px;
}

.small-category {
    display: block;
    color: #d94841;
    font-size: 10px;
    font-weight: bold;
    letter-spacing: 1px;
    margin-bottom: 5px;
}

.trending-item h3 {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 15px;
    line-height: 1.35;
    margin-bottom: 5px;
}

.trending-item small {
    color: #7b8494;
    font-size: 11px;
}

/* Newsletter Panel */
.newsletter {
    background-color: #f8f1ef;
    padding: 20px;
    margin-top: 25px;
    border-radius: 6px;
}

.newsletter h2 {
    font-size: 20px;
}

.newsletter p {
    color: #667085;
    font-size: 13px;
    margin-bottom: 16px;
}

.newsletter a {
    display: inline-block;
    background-color: #d94841;
    color: white;
    padding: 10px 13px;
    border-radius: 4px;
    font-size: 12px;
    font-weight: bold;
    text-decoration: none;
}

.newsletter a:hover {
    background-color: #b8322b;
}

/* Latest Stories */
.latest {
    grid-area: latest;
    min-width: 0;
    border-top: 2px solid #222b3a;
    padding-top: 20px;
}

.section-heading {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    margin-bottom: 18px;
}

.section-heading h2 {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 25px;
}

.section-heading span {
    color: #d94841;
    font-size: 10px;
    letter-spacing: 1px;
    font-weight: bold;
}

/* Grid for News Cards */
.story-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 18px;
}

.story-card {
    min-width: 0;
    border: 1px solid #e6e8ed;
    border-radius: 6px;
    overflow: hidden;
    transition: box-shadow 0.2s;
}

.story-card:hover {
    box-shadow: 0 5px 16px rgba(0, 0, 0, 0.09);
}

.story-card img {
    display: block;
    width: 100%;
    height: 150px;
    object-fit: cover;
}

.story-content {
    padding: 15px;
}

.story-content h3 {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 17px;
    line-height: 1.35;
    margin-bottom: 8px;
}

.story-content p {
    font-size: 13px;
    color: #667085;
    margin-bottom: 12px;
}

.story-content small {
    color: #7b8494;
    font-size: 11px;
}

/* Footer */
.footer {
    grid-area: footer;
    text-align: center;
    background-color: #222b3a;
    color: #e5e7eb;
    padding: 25px 15px;
    border-radius: 5px;
}

.footer-logo {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 25px;
    font-weight: bold;
    letter-spacing: 2px;
}

.footer p {
    font-size: 12px;
    color: #c4cad4;
    margin-top: 5px;
}

.footer .copyright {
    margin-top: 12px;
    padding-top: 12px;
    border-top: 1px solid #424b5b;
}

/* Tablet Layout */
@media (max-width: 900px) {
    .magazine {
        grid-template-columns: minmax(0, 1.5fr) minmax(230px, 1fr);
        gap: 18px;
        padding: 18px;
    }

    .main-article > img {
        height: 250px;
    }

    .sidebar {
        padding-left: 15px;
    }

    .trending-item {
        grid-template-columns: 75px minmax(0, 1fr);
        gap: 9px;
    }

    .trending-item img {
        width: 75px;
        height: 80px;
    }

    .story-grid {
        grid-template-columns: 1fr;
    }
}

/* Mobile Layout */
@media (max-width: 650px) {
    .magazine {
        width: 100%;
        margin: 0;
        padding: 15px;

        /* Stack the sections vertically on small screens */
        grid-template-columns: minmax(0, 1fr);

        grid-template-areas:
            "header"
            "navigation"
            "main"
            "sidebar"
            "latest"
            "footer";

        gap: 20px;
    }

    .header {
        padding: 15px 5px 20px;
    }

    .logo {
        font-size: 34px;
    }

    .navigation {
        gap: 5px;
    }

    .navigation a {
        padding: 7px 9px;
        font-size: 12px;
    }

    .main-article > img {
        height: 230px;
    }

    .article-content h1 {
        font-size: 28px;
    }

    .sidebar {
        border-left: none;
        border-top: 1px solid #e5e7eb;
        padding: 20px 0 0;
    }

    .trending-item {
        grid-template-columns: 95px minmax(0, 1fr);
    }

    .trending-item img {
        width: 95px;
        height: 85px;
    }

    .story-grid {
        grid-template-columns: 1fr;
    }

    .story-card img {
        height: 200px;
    }
}



3. How to run your assignment

Step 1: Create the project folder

Create a folder named Assignment-8.3 and put both files inside it:
Assignment-8.3

index.html

style.css






Step 2: Open the webpage

Double-click index.html to open it in Chrome. The article images load from Unsplash, so an internet connection is needed.




Step 3: Test the layout

Resize the browser window or press F12 and enable the device toolbar to inspect the mobile layout.



4. How grid-template-areas works
This is the main CSS Grid requirement for your assignment:
grid-template-areas:
    "header header"
    "navigation navigation"
    "main sidebar"
    "latest sidebar"
    "footer footer";


The layout works like this on a desktop screen:
HEADER

NAVIGATION

MAIN ARTICLE
Featured story and image


SIDEBAR
Trending stories


LATEST STORIES


Sidebar continues



FOOTER

Illustration of the desktop grid arrangement.
The main article gets more space because the CSS uses grid-template-columns: minmax(0, 2fr) minmax(270px, 1fr). On smaller screens, the media query rearranges the sections into one column.
5. Submission checklist
- [ ] index.html created.
- [ ] style.css created.
- [ ] Header, navigation, main article, sidebar, and footer displayed.
- [ ] grid-template-areas used to organize the sections.
- [ ] Main article wider than the sidebar on desktop.
- [ ] Desktop and mobile layouts tested.
Assignment 8.3 is ready as a complete code draft. Open it in your browser and verify the layout before submitting.
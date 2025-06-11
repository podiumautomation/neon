# Podium Take Home Project

McMaster-Carr has a [beautiful website](https://www.mcmaster.com/). It’s simply a product catalog, but one that includes over 700,000 parts. Despite the number of items, it’s incredibly easy to find what you’re looking for - within a few clicks even.

No small part of this is due to an excellent data model and squeaky clean data; the parts are broken down into an intuitive hierarchy, each category (and sub-category) has its own set of filter criteria, and every (sub-)category has a high quality photo.

Let’s make a McMaster-Carr for 🪴house plants🪴.

# Data

As our data source, we’ve pulled ~150 indoor plants from the public [Perenual database](https://www.perennials.com/). They're available in the `plants.jsonl` file.

# Goal

Build a web app with the following functionality:

- The home page displays a set of 2 categories
- Each category is a link, and clicking into a category takes us to a new page. On this new page the user sees:
    - 2 sub-categories for the parent
- Each sub-category is a link, and clicking into a sub-category takes us to a new page. On this new page the user sees:
    - A flat list of products in the sub-category
    - A list of 2-3 relevant filters for this sub-category on the left

We’ll support two types of filters:
1. Filters on fields that take on a bounded set of values - i.e. enums
    - Below each filter’s title is a list of the available values. Clicking a value updates the current filter: only products with that value are shown. Clicking again removes the filter value from the query.
    - For example, see [“material” on the left nav of the “thumb screw” sub-category](“material” on the left nav of the “thumb screw” sub-category).
    - The options in the list are dynamic on the current filters – values that are not applicable for any product in the  current result set are excluded. For example, if I [select “brass” as my material](select “brass” as my material), the “thumb screw head shapes” list drops from 6 options to 2. The 4 options that disappeared do not apply to any brass thumb screws.
2. Filters on number fields
    - Again we show the user a list of options, but now each option is a range. Selecting an option applies that range filter: only products with a value in that range are shown.
    - There should never be more than 50 options in this list
    - Again the options are dynamic – only ranges that apply to the existing result set are shown.

# Notes & Guidelines

Submit the result as a GitHub repo, and include a README on how to set up and run the web server.

---

We expect this to take 2-3 hours. Please don’t over-invest — only implement the filters for one sub-category, for example, and don’t sink time into the page styling.

Spend the final hour (or more!) on the README, where you can elaborate on how you would implement parts you don’t have time for, where the existing code can be improved, and how you’d scale this to a production grade app with more (and more complex) data. Think of this like a small tech spec.

---

Please choose between TypeScript, Python, or Elixir as your programming language. Otherwise, use whatever tools and online resources you like.

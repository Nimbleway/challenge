<p align="center"><img src="/assets/banner.png" /></p>

# Welcome to the Nimble X Web Scraping Club AI Challenge

## Introduction

The goal of this challenge will be to both test your skills and introduce you to exciting new technologies that are radically transforming the world of public web data collection.

As part of this challenge, you are encouraged to use Nimble’s Web API to scrape web data, and OpenAI to leverage AI to parse the data you need.

Your credentials for these platforms is available in the welcome email sent at the start of the challenge.

## The Challenge

Many websites have pages that contain lists of items, such as products, people, real-estate listings, etc. The number of items displayed on a page may vary, but often when there are many to display, websites will include pagination links that allow users to browse the items in batches.

Your goal in this challenge is to create an AI-powered web crawler capable of traversing any paginated website and extracting the URLs of the items (products, people, etc.) contained within. Your crawler needs to have broad support for (mostly) any website that has this type of layout, and not be hardcoded for a particular website.

Your crawler will accept an entry URL for a page containing items, will leverage AI to classify which links inside the page lead to relevant pages and keep them while discarding any irrelevant links the page may contain. If the page has a pagination element that leads to more pages, your crawler will traverse the pagination to access the next batch of items and extract those links, and so on for the entire pagination tree.

To accomplish this, you will utilize **[Nimble's Web API](https://docs.nimbleway.com/nimble-api/web-api)** to fetch the websites' HTML content, and **[OpenAI's API](https://platform.openai.com/docs/api-reference/introduction)** to leverage an LLM for parsing the page and filtering out the relevant item URLs and pagination.

The output of your crawler should resemble the following example:

```bash
$ python ./solution.py "https://www.gsmarena.com/samsung-phones-9.php"

https://www.gsmarena.com/samsung_galaxy_f54-12239.php
https://www.gsmarena.com/samsung_galaxy_a24_4g-12176.php
https://www.gsmarena.com/samsung_galaxy_f14-12175.php
https://www.gsmarena.com/samsung_galaxy_m54-12189.php
https://www.gsmarena.com/samsung_galaxy_a54-12070.php
https://www.gsmarena.com/samsung_galaxy_a34-12074.php
...

$ python ./solution.py "https://www.etsy.com/search?q=handmade+furniture"

https://www.etsy.com/listing/965245133/custom-neon-sign-neon-sign-aesthetic
https://www.etsy.com/listing/1203360316/custom-neon-sign-neon-sign-aesthetic
https://www.etsy.com/listing/844235389/essential-wooden-ambience-lamp-home
https://www.etsy.com/listing/1480559129/mid-century-modern-scandinavian-lift-top
https://www.etsy.com/listing/824406862/zen-lamp-handmade-in-bali-wood-rattan
https://www.etsy.com/listing/1425154495/record-player-stand-vinyl-record-storage
...
```

## Rules

1. The input will be a URL string. The output should be a list of URLs leading to the entities that are the subjects of the page.
1. For simplicity, you don't have to scan more than 3 pages if more than 3 are present.
1. Only pagination where the pages are explicitly enumerated is relevant to the challenge. Infinite scrolling pages are out of scope.
1. Using Nimble's Web API is **optional**, but very recommended to avoid being blocked by anti-bots, and to get rendered pages.
1. Using OpenAI's API is **optional**, but very recommended as it is today's leading provider of integration with LLMs.
1. The examples showcase a CLI, but you can wrap the crawler in any way that you prefer such as a server etc.
1. You may use any framework that helps interfacing with your script, such as CLI or server frameworks.
1. You may use any framework useful for interacting with HTML, such as [BeautifulSoup](https://pypi.org/project/beautifulsoup4/#:~:text=Beautiful%20Soup%20is%20a%20library,and%20modifying%20the%20parse%20tree.).
1. The solution must be general and not tailored to any specific site.
1. You can use any programming language. We recommend either Python or Typescript.

## Grading

As long as your crawler works reasonably well within the rules defined above - it will be accepted. Well done!

Once your crawler has been accepted, it will be compared to other accepted crawlers according to the following metrics and guidelines:

- Precision of fetched data
- Compatibility with a diverse array of sources
- Code efficiency and economy
- Crawler performance
- **Bonus**: Output is well structured e.g. CSV, JSON, XML

## Hints

- You can use [this list of paginated websites](https://github.com/Nimbleway/challenge/blob/initial/sites.md) as reference.
- Consider preprocessing the page before sending it to the LLM.
- The GPT 3.5 LLM is good at reading HTML, but you can try converting the page to other formats.
- Some pages require rendering. This can be achieved by passing `render: true` to the request to Nimble's Web API.
- Nimble and OpenAI's APIs have rate limits. If you pass them, you might get an error that is solvable with a retry mechanism.

## Support

In case you have any question or require help, please send an e-mail to challenge@nimbleway.com.

## Submission

When you are ready to submit your solution, please send it to us using the [submission form](https://763p1qm7qkl.typeform.com/to/PDAhOjZ4).

When submitting your solution, include either:

- A link to a git repository containing your solution. Make sure it is public and/or visible to our judges.
- An archive file such as a ZIP or RAR file containing the readable source code of your solution.

In addition, enclosing a README file with instructions on how to run your solution will be appreciated.

By submitting your solution, you agree to [the challenge's terms and conditions](https://www.nimbleway.com/terms-conditions-challenge).

Good luck!

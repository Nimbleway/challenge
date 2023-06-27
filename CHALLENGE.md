# Nimble Challenge

When scraping websites for useful data, a very common type of site to stumble upon is a page containing a list of links to other pages that contain entities (such as products, people, real-estate listings etc.). Often, when the number of entities offered by the website is large, the page will also contain links to more such pages.

In this challenge, you will create an AI-powered web crawler capable of traversing any paginated website and extract URLs leading to the entities contained within, without implementing the logic yourself for each type of page.

Your script will take a URL of a page containing entities, will leverage AI to classify which links inside the page lead to a relevant page and keep it, discarding all unuseful links the page may contain. If the page has a pagination element that leads to more pages, you will traverse them similarly to extract more such URLs.

To accomplish this, you will utilize [**Nimble's Web API**](https://docs.nimbleway.com/nimble-api/web-api) to fetch the websites' HTML content, and [**OpenAI's API**](https://platform.openai.com/docs/api-reference/introduction) to leverage an LLM for parsing the page and deiciding which elements lead to the entities that are the subject of the page, and which lead to pages that might contain more of the entities we're looking for.

Example:

```sh
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

As long as your end solution is working reasonably well within the constraints above - it will be accepted. Well done!

For the purpose of ranking, your solution will be graded according to the following metrics and guidelines:

- Recall and precision of fetched data.
- **Bonus**: Efficiency of solution.
- **Bonus**: Output is well structured e.g. CSV, JSON, XML

## Hints

- You can use [this list of paginated websites](/sites.md) as reference.
- Consider preprocessing the page before sending it to the LLM.
- The GPT 3.5 LLM is good at reading HTML, but you can try converting the page to other formats.
- Some pages require rendering. This can be achieved by passing `render: true` to the request to Nimble's Web API.

## Submission

When you are ready to submit your solution, please send us an email at **challenge@nimbleway.com** from the email with which you've registered, and include either:

- A link to a git repository containing your solution. Make sure it is public and/or visible to our judges.
- An archive file such as a ZIP or RAR file containing the readable source code of your solution.

In addition, enclosing a README file with instructions on how to run your solution will be appreciated.

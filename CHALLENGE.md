# Nimble Challenge

Web pages are generally semi-structured data, where useful data is placed in HTML tags that are easy for a human to parse when rendered in the browser, but don't always make sense to a traditional computer program without a human to guide it.

In this challenge, we are interested in fetching all entities of a certain type from a website.

You are going to implement an AI powered web crawler that can traverse paginated websites of entities and collect their URLs! For this purpose, you have received keys to Nimble's Web API as well as OpenAI's API.

Your script's input will be a web URL, and your script will utilize AI to /_ TODO _/

Example:

```sh
$ python ./solution "https://www.gsmarena.com/samsung-phones-9.php"
```

## Rules

1. Using Nimble's Web API is **optional**.
1. Using OpenAI's API is **optional**, but very recommended.
1. No other third-party API or framework other than an HTTP client can be used for fetching or parsing HTML pages.
1. You may use any framework that helps interfacing with your script, such as CLI or server frameworks.
1. The solution must be general and not tailored to any specific site.
1. Solution must be easy to use. A stand-alone script is acceptable.
1. You can use any programming language.

## Grading

As long as your end solution is working reasonably within the constraints above - it will be accepted. Well done!

For the purpose of ranking, your solution will be graded according to the following metrics and guidelines:

- Recall and precision of fetched data.
- Bonus: Efficiency of solution.
- Bonus: Output is well structured e.g. CSV, JSON, XML

## Hints

## Submission

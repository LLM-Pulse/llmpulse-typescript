
# RedditRow

One row of /dimensions/reddit. Fields depend on view: subreddits (subreddit, citations, unique_authors, positive, negative, neutral, positive_pct, negative_pct, yours, url), authors (author, citations, subreddits, extra_subreddits, leaning, positive, negative, neutral, brands, yours, url), threads (url, title, subreddit, author, subreddit_yours, author_yours, yours, citations, latest_cited_at, upvotes, comments, avg_position, sentiment, archived, posted_at) and breakdowns (breakdown, key, count, pct).

## Properties

Name | Type
------------ | -------------
`subreddit` | string
`author` | string
`url` | string
`title` | string
`citations` | number
`uniqueAuthors` | number
`positive` | number
`negative` | number
`neutral` | number
`positivePct` | number
`negativePct` | number
`yours` | boolean
`subreddits` | Array&lt;string&gt;
`extraSubreddits` | number
`leaning` | string
`brands` | [Array&lt;RedditAuthorBrand&gt;](RedditAuthorBrand.md)
`subredditYours` | boolean
`authorYours` | boolean
`latestCitedAt` | Date
`upvotes` | any
`comments` | any
`avgPosition` | number
`sentiment` | string
`archived` | any
`postedAt` | Date
`breakdown` | string
`key` | string
`count` | number
`pct` | number

## Example

```typescript
import type { RedditRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "subreddit": null,
  "author": null,
  "url": null,
  "title": null,
  "citations": null,
  "uniqueAuthors": null,
  "positive": null,
  "negative": null,
  "neutral": null,
  "positivePct": null,
  "negativePct": null,
  "yours": null,
  "subreddits": null,
  "extraSubreddits": null,
  "leaning": null,
  "brands": null,
  "subredditYours": null,
  "authorYours": null,
  "latestCitedAt": null,
  "upvotes": null,
  "comments": null,
  "avgPosition": null,
  "sentiment": null,
  "archived": null,
  "postedAt": null,
  "breakdown": null,
  "key": null,
  "count": null,
  "pct": null,
} satisfies RedditRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RedditRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)



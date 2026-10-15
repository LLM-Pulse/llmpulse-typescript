
# OwnedMediaRow

One row of /dimensions/owned_media. Fields depend on provider and view: videos (title, url, channel_name, channel_handle, channel_url, video_id, thumbnail_url, views, published_at), channels (key, name, handle, url, avatar_url, unique_videos), posts (url, caption, owner_handle, thumbnail_url, content_type, likes, comments, views, posted_at), profiles (handle, name, url, avatar_url, followers, unique_posts), own_citations (url, citation_date, position, model) and apps (domain, total_responses, rank, global_rank). Every view but own_citations carries citations and yours; videos, channels, posts and profiles carry avg_position.

## Properties

Name | Type
------------ | -------------
`title` | string
`url` | string
`channelName` | string
`channelHandle` | string
`channelUrl` | string
`videoId` | string
`key` | string
`name` | string
`handle` | string
`caption` | string
`ownerHandle` | string
`thumbnailUrl` | string
`avatarUrl` | string
`contentType` | string
`citations` | number
`uniqueVideos` | number
`uniquePosts` | number
`followers` | number
`likes` | number
`comments` | number
`views` | any
`publishedAt` | string
`postedAt` | string
`avgPosition` | number
`yours` | boolean
`citationDate` | Date
`position` | number
`model` | string
`domain` | string
`totalResponses` | number
`rank` | number
`globalRank` | number

## Example

```typescript
import type { OwnedMediaRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "title": null,
  "url": null,
  "channelName": null,
  "channelHandle": null,
  "channelUrl": null,
  "videoId": null,
  "key": null,
  "name": null,
  "handle": null,
  "caption": null,
  "ownerHandle": null,
  "thumbnailUrl": null,
  "avatarUrl": null,
  "contentType": null,
  "citations": null,
  "uniqueVideos": null,
  "uniquePosts": null,
  "followers": null,
  "likes": null,
  "comments": null,
  "views": null,
  "publishedAt": null,
  "postedAt": null,
  "avgPosition": null,
  "yours": null,
  "citationDate": null,
  "position": null,
  "model": null,
  "domain": null,
  "totalResponses": null,
  "rank": null,
  "globalRank": null,
} satisfies OwnedMediaRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)



# K-Pop Release Database with Daily Analytics

This repository contains the results of my data-fetching project focused on K-pop releases. The motivation behind this project is to collect high-frequency time series data—specifically, daily YouTube analytics.

---

## Why K-Pop?

K-pop is a music genre originating in South Korea that blends styles such as pop, hip-hop, and R&B. It differs from Western pop music in several ways—both musically and culturally. One key reason K-pop is particularly well-suited for this kind of project is the intense fan engagement: fans are highly motivated to track new releases, whether to support their favorite artists or to discover new ones.

This enthusiasm leads to the creation of community-driven platforms like [kpopping.com](https://kpopping.com), where users regularly post information about upcoming releases. These platforms provide a valuable, crowd-sourced dataset that can be used to monitor trends and activity.

---

## Data Sources

- **[kpopping.com](https://kpopping.com)** – Used to obtain timely release information. Each release page is created by a community member and may or may not include a valid YouTube link, which could be the main single or another type of video (teaser, trailer, etc.). Each entry also lists an “album date,” which may or may not match the video’s actual release date.

- **YouTube Data API** – Used to fetch both metadata (title, release timestamp) and daily analytics (views, likes, comments). This metadata helps confirm the release date and classify the video (e.g., whether it’s a full music video or a teaser).

---

## Repository Structure

- `releases/` — Contains yearly CSV files with raw data scraped from kpopping.com.
- `video_data/` — Contains metadata for each release, collected from the YouTube API.
- `analytics/` — Stores daily metrics (views, likes, comments). Each year has three CSVs—one per metric.


---

## Considerations

- **Time Range**: I’m currently only tracking analytics for videos released from 2022 onward due to YouTube API quota limitations. 
  - Even though I could request a larger quota, daily tracking is most valuable shortly after a video’s release, when metrics change quickly. Older videos tend to plateau, and a one-time snapshot of their stats is usually sufficient.

<!--
- **Release Dates vs. Analytics Start Dates**:  
  - It is worth noting that the first day a video appears in the analytics dataset does **not** necessarily correspond to its actual release date.  
  To determine the true release date, cross-reference with the corresponding CSVs in `video_data/`.
-->

---

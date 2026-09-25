# Midwest Airbnb Listings: Data Dictionary

**Dataset:** `listings` table in `midwest_airbnb.db` (SQLite), 14,887 rows and 29 columns
**Source:** Inside Airbnb (https://insideairbnb.com/get-the-data/), the detailed `listings.csv.gz` file for each of three regions: Chicago (snapshot 2026-07-20), Columbus (snapshot 2026-07-23), and Twin Cities MSA (snapshot 2026-07-21). Column meanings follow Inside Airbnb's data dictionary and assumptions (https://insideairbnb.com/data-assumptions/).
**Course:** ISA 401, Miami University

> One row is one listing that showed a nightly price on the snapshot date; listings with no price were dropped. Empty cells are stored as SQL `NULL`.

---

## Field Definitions

| Field | Type | Description |
|---|---|---|
| `city` | text | Which Inside Airbnb region the listing came from: `Chicago` (7,439 rows), `Columbus` (2,587), or `Twin Cities` (4,861). The Twin Cities file covers the Minneapolis-St. Paul metro area, not just the two cities. |
| `snapshot_date` | text | Date Inside Airbnb compiled the file, stored as an ISO text string, not a date: `2026-07-20` for Chicago, `2026-07-23` for Columbus, `2026-07-21` for Twin Cities. Every row of a city shares the same value. |
| `id` | text | Airbnb's listing id. Unique across the table (14,887 distinct values). Stored as text even though it looks numeric, so compare it to a quoted string. |
| `name` | text | Listing title as shown on Airbnb (for example "Tiny Studio Apartment 94 Walk Score"). Never empty. |
| `price` | real | Nightly price in U.S. dollars on the snapshot date, with the dollar sign and commas removed. Ranges from 2.56 to 11,412; never `NULL` (rows without a price were dropped). |
| `room_type` | text | Airbnb's four listing categories: `Entire home/apt` (11,652 rows), `Private room` (2,951), `Hotel room` (246), or `Shared room` (38). |
| `host_id` | text | Airbnb's unique identifier for the host that manages the listing. It looks like an integer but it is text |
| `host_name` | text | The name of the host as it appears on Airbnb's website |
| `host_since` | text | This is the date the host joined Airbnb and it is stored as a string in the ISO YYYY-MM-DD format. There are many `NA` values |
| `host_is_superhost` | text | Indicates whether the host is a superhost or not. Values are not booleans, they are stored as text as `t` or `f` |
| `neighbourhood` | text | The neighborhood the listing is located in. This comes from Inside Airbnb's `neighbourhood_cleansed` column |
| `latitude` | double | Geographic latitude of the listing location |
| `longitude` | double | Geographic longitude of the listing location |
| `property_type` | text | The type of property associated with the listing, such as `private room in condo` or `Entire rental unit` |
| `accommodates` | integer | Maximum limit of guests the listing can hold |
| `bedrooms` | double | Number of bedrooms in a listing. May appear as integers but are really a double |
| `beds` | double | Number of beds in a listing. May appear like an integer but are really a double |
| `bathrooms_text` | text | The number of bathrooms and the description of them as shown on Airbnb such as `1 bath` or `2 baths` |
| `minimum_nights` | integer | Minimum amount of nights users can stay at the listing |
| `availability_365` | integer | Number of days the listing was available for during the last 365 |
| `number_of_reviews` | integer | Total number of reviews the listing has received |
| `number_of_reviews_ltm` | integer | Total number of reviews the listing has received in the past 12 months |
| `first_review` | text | Date of the listing's first review as a text string in `YYYY-MM-DD` format |
| `last_review` | text | Date of the listing's most recent review as a text string in `YYYY-MM-DD` format |
| `review_scores_rating` | double | Average review rating of the listing ranging from 0 to 5 |
| `reviews_per_month` | double | The average number of reviews the listing received per month |
| `instant_bookable` | text | Whether the listing can be booked instantly without host approval or not. They are stored as text values `t` and `f` |
| `estimated_revenue_l365d` | double | Estimated revenue generated from the listing in the past 365 days in USD |
| `amenities_count` | int | The number of amenities that are associated with the listing |


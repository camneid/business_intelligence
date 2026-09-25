# Extra Instructions

Rules the LLM follows when it writes SQL for `listings`.

- `price` is the nightly price in U.S. dollars. When the user asks what something costs, use `price` and round money to whole dollars in the answer.
- `host_is_superhost` and `instant_bookable` are the text values 't' and 'f', not boolean values.
- `name` is the name of the listing. If a user types in a name, make sure to look for it case-insensitively so they can find it.
- Ignore rows where the `review_scores_rating` is NULL when calculating average ratings


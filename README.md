# -AVG-game-time-for-Uniq-Use
Overview
This project analyzes the behavior of players on a mobile/online gaming platform from March to December 2022, based on 44,011 records of gaming activity from 216 unique users. The Tableau dashboard focuses on a key engagement metric—average playtime—and its relationship with Battle Pass conversion, age groups, and monthly trends. This is a typical product analytics dashboard for a gaming company, where retention and monetization are directly dependent on time spent in-game.
Business Value
The dashboard answers questions from the product and growth teams:

Is player engagement growing over time?
Which age segments play the most—and in which quarters?
To what extent does the Battle Pass convert active users into paying users?
Are there dips in activity that require a product response?

This allows us to plan content updates, tailor Battle Pass campaign targeting, and make pricing decisions based on real behavior rather than assumptions.
Key Findings and Insights
KPI Dashboard: AVG Hours Per User—310 hours — a high engagement metric,
Battle Pass Conversion—60% — 3 out of every 5 active users purchase the Battle Pass,
Battle Pass Users—129 out of 216 unique users,
Sessions per User—204 — a very active user base.
Over time (bar chart):

A slow start in March—37:11 hours on average
A peak in June—70:56, which may be due to the summer season or the release of new content
After the summer peak, there was a slight decline, followed by a rebound by November (74:40)—this is the “autumn re-engagement” pattern typical of gaming products
December drops to 63:03—the holiday season, players get distracted

Regarding Battle Pass conversion (combo chart):

In March, conversion was 55% with 47 users—a small user base, high engagement among early adopters
Conversion peaked at 79% in April as the audience grew to 82 people
By December, the user base had grown to over 100 people, but the conversion rate dropped to 50% — a typical dilution effect as the audience grows
Overall trend: the audience is growing, while the conversion rate is gradually declining — a signal to improve onboarding for new users.

By age group (heatmap):

Most active age groups: 15–19 and 20–24 — the darkest cells in all quarters
The 25–29 age group also shows good activity, especially in Q3–Q4
Older players (60+) are present but play significantly less
The 80–84 age group has abnormally high values in Q4—possibly a few highly active users.
Logic behind the dashboard
Data source: games_activity_combined.csv — 7 fields:
user_id, activity_date, game_activity_name, total_seconds, language, has_older_device_model, age
Calculated fields that I created:

AVG Hours Per User — total_seconds → converted to hours + aggregated by user_id
Battle Bass Users — COUNT DISTINCT user_id for activities with “Battle Pass”
Battle Bass Conversion — ratio of Battle Pass Users to Unique Users
Sessions per User — COUNT of sessions / COUNT DISTINCT user_id
Age Group — binning the age field into 5-year groups (10–14, 15–19, etc.)
Quarter of activity_date — for heatmap rows.
Visualizations and their logic:
Chart: AVG Time for Unique User
Bar chart by month — Engagement trend?
Unique Users + Battle Pass %
Dual-axis combo (bar + line) — Relationship between audience growth and conversion?
AVG Time for Age Group
Heatmap (quarter × age) — Identify the most valuable segments.
Architectural solutions:

Filters by Activity_date, Age Group, Game name, and Language are implemented via Action parameters—the dashboard is interactive
Measure Names in the combo chart legend allow two scales to be displayed on a single chart without visual clutter
Heatmap with color intensity over time—an intuitive way to compare dozens of segments at once
The KPI block at the top provides instant answers to key questions before diving into the details.

## Dataset
<a href="https://drive.google.com/file/d/1_U4AOIGE_DFEQdPbma6rE5FThWntxMAW/view?usp=sharing">Dataset</a>

## Dashboard
<a href="https://public.tableau.com/views/__3_17536404849610/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link">AVG game time for Uniq Use</a>

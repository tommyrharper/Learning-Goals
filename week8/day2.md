# Day 2

Today it was chosen I would be leader again, for the duration of this sprint. Yes! I love being leader, I don't know why, I guess I aspire to lead, all the people I look up to are leaders so I kind of want to be like them, which is ironically kind of following. Paradoxical hey.

We had our morning scrum meeting, and managed to get a difficult decision through to have a daily afternoon retro in. I faced some resistance from one team member who is quite strong minded, but I made my case and put it down to popular vote and it went through.

Then I spent the rest of the day learning about ruby on rails and how to use it by developing a simple blog application through an online tutorial.

We finished the day with a retrospective, and found a few ways we could improve, including adding story points to all our trello cards, and planning time for our merge requests the next day.


Here is a litte of bit of rails
```ruby
<%= form_with model: @article, local: true do |form| %>
```

local: true stops ajax working, and causes the page to reload. By default local is set to false and ajax works, stopping the page reloading.
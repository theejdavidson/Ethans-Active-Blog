---
layout: post
title:  "My Flatiron Experience So Far"
date:   2020-03-03 16:50:53 -0600
categories: jekyll update
---
Three weeks into [Flatiron School][flatiron-school] and we've hit the ground running with our first project. Using [Ruby's][ruby-lang] ActiveRecord to send GET requests to [PokéAPI][poke-api], an API containing extensive pokémon-related data, we were able to seed our database for tests.


There are several issues that a client faces when making RESTful calls to an API. One that we faced was over-fetching, by making a single GET request we pulled lots of unneeded data. In other cases, the data we needed to fill in info for a given Pokémon required us to write multiple calls per-instance. GraphQL is an open-source query language that aims to solve these sorts of issues.


On Tuesday, March 3rd, I attended a meetup held by ChicagoRuby that discussed GraphQL through the lens of Ruby. The presentation by [Trevor Turk][turk-intro-to-graphql] was a helpful introduction to the tool. He highlighted the importance of security when setting up client access, and gave tips on managing complexity.


The basic premise of GraphQL is to act as a standardized schema for your data. A query, analagous to a GET request, would look something like this:
{% highlight json %}
{
    post {
      title
      body
      author {
        name
      }
    }
  }
{%endhighlight json %}

And the client would recieve a block with values filled like this:
{% highlight json %}
{
  "data": {
    "posts": [
      {
        "title": "John's post",
        "author": {
          "name": "John"
        }
      },
      {
        "title": "Jane's post",
        "author": {
          "name": "Jane"
        }
      }
    ]
  }
}
{% endhighlight %}

Alongside our standard GET requests to the API, I aim to write a small GraphQL schema to test its usability within our app. Keep an eye out for updates!


[turk-intro-to-graphql]: https://github.com/trevorturk/intro-to-graphql-ruby
[poke-api]: https://pokeapi.co/
[ruby-lang]: https://www.ruby-lang.org/en/
[flatiron-school]: https://flatironschool.com/

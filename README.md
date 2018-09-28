### wombat
---

https://github.com/felipecsl/wombat

```ruby
require 'wombat'
Wombat.crawl do
  base_url "https://www.github.com"
  path "/"
  headline xpath: "//h1"
  subheading css: "p.alt-lead"
  what_is({ css: ".one-fourth h4" }, :list)
  links do
    explore xpath: '/html/body/header/div/div/nav[1]/a[4]' do |e|
      e.gsub(/Explore/, "Love")
    end
    features css: '.nav-item-opensource'
    business css: '.nav-item-business'
  end
end

{
  "headline"=>"How people build software"
  "subheading"=>"Millions of developers use Github to build personal projects, support their..."
  "what_is"=>[
    "For everythins you build",
    "A better way to work",
    "Millions of projects",
    "One platform, from start to finish"
  ],
  "links"={
    "explore"=>"Love",
    "features"=>"Open source",
    "business"=>"Business"
  }
}

```


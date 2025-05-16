source 'https://rubygems.org'

gem 'jekyll', '~> 4.2.0'
gem 'webrick', '~> 1.7'
gem 'csv'
gem 'logger'
gem 'base64'
gem 'bigdecimal'

# Core plugins that directly affect site building
group :jekyll_plugins do
    gem 'jekyll-archives'
    gem 'jekyll-diagrams'
    gem 'jekyll-email-protect'
    gem 'jekyll-feed'
    gem 'jekyll-get-json'
    gem 'jekyll-imagemagick'
    gem 'jekyll-jupyter-notebook'
    gem 'jekyll-link-attributes'
    gem 'jekyll-minifier'
    gem 'jekyll-paginate-v2'
    gem 'jekyll-regex-replace'
    gem 'jekyll-scholar'
    gem 'jekyll-sitemap'
    gem 'jekyll-tabs'
    gem 'jekyll-terser', :git => "https://github.com/RobertoJBeltran/jekyll-terser.git"
    gem 'jekyll-toc'
    gem 'jekyll-twitter-plugin'
    gem 'jemoji'

    gem 'classifier-reborn'  # used for content categorization during the build
end

# Gems for development or external data fetching (outside :jekyll_plugins)
group :other_plugins do
    gem 'css_parser'
    gem 'feedjira'
    gem 'httparty'
    gem 'observer'       # used by jekyll-scholar
    gem 'ostruct'        # used by jekyll-twitter-plugin
    # gem 'terser'         # used by jekyll-terser
    # gem 'unicode_utils' -- should be already installed by jekyll
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem 'tzinfo', '~> 1.2'
  gem 'tzinfo-data'
end

# Performance-booster for watching directories on Windows
gem 'wdm', '~> 0.1.1', :platforms => [:mingw, :x64_mingw, :mswin]

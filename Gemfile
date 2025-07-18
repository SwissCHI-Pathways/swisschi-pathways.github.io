source "https://rubygems.org"

gem "jekyll", "~> 4.2.0"
gem "webrick", "~> 1.7"
gem "csv"
gem "logger"
gem "base64"
gem "bigdecimal"
gem "html-proofer", "~> 3.19"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-seo-tag", "~> 2.7"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end
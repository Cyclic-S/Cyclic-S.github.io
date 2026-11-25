# Miscellaneous Notes

## RubyGems mirror

To use the Ruby China mirror instead of the default RubyGems source:

```sh
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
gem sources -l
```

Configure Bundler to use the same mirror:

```sh
bundle config mirror.https://rubygems.org https://gems.ruby-china.com
```

## Troubleshooting

### `No source of timezone data could be found`

Check your `Gemfile` for `tzinfo-data`. If it is already present, make sure its platform list includes the platform you use. For 64-bit Windows with MinGW, for example:

```ruby
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw]
```

If you see `TZInfo::DataSourceNotFound`, you can also remove `Gemfile.lock` and add these dependencies to your `Gemfile`:

```ruby
gem 'tzinfo'
gem 'tzinfo-data'
```

Then run:

```sh
bundle clean
bundle update
bundle install
bundle lock --add-platform x86_64-linux
bundle exec jekyll serve
```

### `cannot load such file -- webrick (LoadError)`

Add the `webrick` dependency:

```sh
bundle add webrick
```

## Git workflow

```sh
git add .
git commit -m "commit"
git pull
git push
```

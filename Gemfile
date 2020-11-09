source 'https://rubygems.org'

gemspec

group :test do
  gem 'rake', '~> 10.0'
  gem 'rspec-its', '~> 1.0'
  gem 'rspec-collection_matchers', '~> 1.0'

  if RUBY_VERSION < '2.0'
    # json 2.x requires ruby 2.0. Lock to 1.8
    gem 'json', '= 1.8'
    # json_pure 2.0.2 requires ruby 2.0, and 2.0.1 requires ruby 1.9. Lock to 1.8.3.
    gem 'json_pure', '= 1.8.3'
    # addressable 2.4.0 requires ruby 1.9.0. Lock to 2.3.8.
    gem 'addressable', '= 2.3.8'
    gem 'diff-lcs', '< 1.3'
    gem 'rspec', '<= 3.4'
  else
    gem 'rspec', '~> 3.0'
    gem 'json'
  end

  if RUBY_VERSION > '1.8'
    # requires ruby 1.9+, on 1.8 we'll fall back to the old regex parsing
    gem 'rspec-json_expectations', '~> 1.4'
  end

  gem 'rubocop', '0.49.1' if RUBY_VERSION > '2.0'
  gem 'simplecov', :require => false if ENV['COVERAGE'] == 'yes'
end

group :development do
  if RUBY_VERSION > '1.9'
    # For Changelog generation
    if RUBY_VERSION >= '2.2.2'
      gem 'github_changelog_generator', :require => false
    else
      gem 'github_changelog_generator', '~> 1.13.0', :require => false
      gem 'rack', '~> 1.0', :require => false
    end

    gem 'pry'
  end
end

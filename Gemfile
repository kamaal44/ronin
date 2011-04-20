source 'https://rubygems.org'

DM_URI = 'http://github.com/datamapper'
DM_VERSION = '~> 1.1.0'
DO_VERSION = '~> 0.10.3'
RONIN_URI = 'http://github.com/ronin-ruby'

gemspec

gem 'data_paths', '~> 0.3.0', :git => 'git://github.com/postmodern/data_paths.git'

# DataMapper dependencies
# gem 'data_objects',       DO_VERSION, :git => "#{DM_URI}/do.git"
# gem 'do_sqlite3',         DO_VERSION, :git => "#{DM_URI}/do.git"
# gem 'dm-do-adapter',      DM_VERSION, :git => "#{DM_URI}/dm-do-adapter.git"
# gem 'dm-sqlite-adapter',  DM_VERSION, :git => "#{DM_URI}/dm-sqlite-adapter.git"
# gem 'dm-core',            DM_VERSION, :git => "#{DM_URI}/dm-core.git"
# gem 'dm-types',           DM_VERSION, :git => "#{DM_URI}/dm-types.git"
# gem 'dm-constraints',     DM_VERSION, :git => "#{DM_URI}/dm-constraints.git"
# gem 'dm-migrations',      DM_VERSION, :git => "#{DM_URI}/dm-migrations.git"
# gem 'dm-validations',     DM_VERSION, :git => "#{DM_URI}/dm-validations.git"
# gem 'dm-serializer',      DM_VERSION, :git => "#{DM_URI}/dm-serializer.git"
# gem 'dm-aggregates',      DM_VERSION, :git => "#{DM_URI}/dm-aggregates.git"
# gem 'dm-timestamps',      DM_VERSION, :git => "#{DM_URI}/dm-timestamps.git"

# Library dependencies
# gem 'ronin-support',	'~> 0.1.0', :git => "#{RONIN_URI}/ronin-support.git"

group :development do
  gem 'rake',         '~> 0.8.7'

  gem 'ore-tasks',    '~> 0.4'
  gem 'rspec',        '~> 2.4'

  gem 'kramdown',       '~> 0.12'
  gem 'ruby-graphviz',  '~> 0.9.10'
  gem 'dm-visualizer',  '~> 0.2.0'
end

group :test do
  adapters = (ENV['ADAPTER'] || ENV['ADAPTERS'])
  adapters = adapters.to_s.gsub(',',' ').split(' ') - ['in_memory']

  DM_ADAPTERS = %w[sqlite3 postgres mysql oracle sqlserver]

  unless (DM_ADAPTERS & adapters).empty?
    adapters.each do |adapter|
      gem "dm-#{adapter}-adapter", DM_VERSION, :git => "#{DM_URI}/dm-#{adapter}-adapter.git"
    end
  end
end

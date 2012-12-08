require 'yaml'

config_file = '_config.yml'
config = YAML.load_file(config_file)

env = ENV['env'] || 'stage'

task :deploy do
  sh "jekyll && rsync -avz --delete #{config['destination']}/ #{config['environments'][env]['remote']['connection']}:#{config['environments'][env]['remote']['path']}"
end

task :launch do
  sh "open #{config['environments'][env]['url']}"
end

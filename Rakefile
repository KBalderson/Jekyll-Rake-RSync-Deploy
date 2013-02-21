require 'yaml'

config_file = '_config.yml'
config = YAML.load_file(config_file)

env = ENV['env'] || 'stage'

task :deploy do
  command = "jekyll && rsync -avz --delete "
  command << "-e 'ssh -p #{config['environments'][env]['remote']['port']}' " unless config['environments'][env]['remote']['port'].nil?
  command << "#{config['destination']}/ #{config['environments'][env]['remote']['connection']}:#{config['environments'][env]['remote']['path']}"
  sh command
end

task :launch do
  sh "open #{config['environments'][env]['url']}"
end

namespace :greeting do 
desc 'outputs hello to the terminal' #this allows us to view a list of available Rake tasks and their descriptions using rake -T command in command line
task :hello do
  puts "hello from Rake!"
end

  desc 'outputs hola to the terminal'
  task :hola do 
    puts "hola de Rake!"
  end
end

namespace :db do 
  desc 'migrate changes to your database'
  task :migrate => :environment do #this creates a task dependency, so we need to define another Rake task to ask for access to the environment file
    Student.create_table
  end
  
  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end
end

task :environment do
    require_relative './config/environment'
  end

desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end
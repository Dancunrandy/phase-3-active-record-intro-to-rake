namespace :greeting do
  desc "Prints hello from Rake!"
  task :hello do
    puts "hello from Rake!"
  end

  desc "Prints hola de Rake!"
  task :hola do
    puts "hola de Rake!"
  end
end

task :console do
  system "irb"
end

namespace :db do
  task :migrate => :environment do
    # code to create the students table in the database
  end

  task :seed => :environment do
    # code to seed the database with dummy data from a seed file
  end
end
task :environment do
  require File.expand_path('config/environment', __dir__)
end
namespace :db do
  task :seed => :environment do
    require 'faker'

    5.times do
      Student.create(
        name: Faker::Name.name,
        email: Faker::Internet.email,
        phone_number: Faker::PhoneNumber.phone_number
      )
    end
  end
end

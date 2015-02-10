require 'rspec/core/rake_task'
require 'rubocop/rake_task'
require 'foodcritic'

# Style tests. Rubocop and Foodcritic
namespace :style do
  desc 'Run Ruby style checks'
  RuboCop::RakeTask.new(:ruby)

  desc 'Run Chef style checks'
  FoodCritic::Rake::LintTask.new(:chef) do |t|
    t.options = {
      :fail_tags => ['any'],
      :tags => ['~FC017']
    }
  end
end

desc 'Run ChefSpec examples'
RSpec::Core::RakeTask.new(:spec)

desc 'Run all style checks'
task :style => ['style:chef', 'style:ruby']
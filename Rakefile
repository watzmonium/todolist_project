require "rake/testtask" # allows access to that Rake::TestTask.new syntax that runs a set of tasks for you
require 'find' # specifically for our find test
require "bundler/gem_tasks" # this adds several default basic tasks to rake!

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

desc 'List files'
task :list do
  Find.find('.') do |path|
    next if path.include?('/.')
    puts path if File.file?(path)
  end
end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end
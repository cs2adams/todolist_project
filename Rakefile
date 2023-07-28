require 'rake/testtask'
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List project files'
task :list do
  files = []

  Find.find(ENV["PWD"]) do |path|
    Find.prune if File.basename(path).start_with?('.')
    files << path if File.file?(path)
  end

  files.map! { |f| f.gsub('/home/cs2adams/todolist_project/', '') }
  puts files
end
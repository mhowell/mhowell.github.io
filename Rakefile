require 'rubygems'
require 'rake'
require 'fileutils'

# Get and parse the date
DATE = Time.now.strftime("%y-%m-%d")

# Directories
POSTS = "_posts"
DRAFTS = "_drafts"

desc "Draft a new post"
task :draft do
  puts "What should we call this post for now?"
  name = STDIN.gets.chomp
  filename = "#{DRAFTS}/{DATE}-#{name}.md"
  FileUtils.touch(filename)

  open(filename, 'a') do |f|
    f.puts "---"
    f.puts "layout: post"
    f.puts "title: \"DRAFT: #{name}\""
    f.puts "---"
  end
end


desc "Startup Jekyll"
task :start do
  sh "jekyll serve --watch"
end

desc "Build site"
task :build do
	sh "jekyll build"
end

task :default => :start
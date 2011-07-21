ROOT = File.dirname(__FILE__)

desc "Genrate the site using the jekyll executable"
task :default do
  system "jekyll"
end

desc "Update the 'published' bit in posts if the post date is today or earlier"
task :update_published do
  require 'rubygems'
  require 'active_support'
  entries.each do |post|
    date = Date.parse(post.scan(/_posts\/(\d{4}-\d{2}-\d{2})/).flatten.first)
    updated = File.read(post).sub(/^published: (false|true)$/, "published: #{(date <= Date.today).to_s}")
    File.open(post, 'w') {|file| file.write(updated) }
  end
end

desc "Create a new post, pass P='The Title' to name the new entry, pass YET=n to postdate by n days"
task :new do
  require 'activesupport'
  postname = ENV['P']
  date     = Date.today + ENV['YET'].to_i
  slug = postname.gsub(/[^a-z0-9\-_\+]+/i, '-').downcase.chomp("-")
  post = "#{ROOT}/_posts/#{date.to_s}-#{slug}.textile"
  File.open(post, 'w') do |f|
    f.write <<-EOS
---
layout: post
title: #{postname}
permalink: #{slug}.html
published: false
author: Jack Danger Canty
author_url: http://jackcanty.com
---

EOS
  end
  system "vim #{post}"
end

def entries
  Dir.glob("./_posts/*")
end

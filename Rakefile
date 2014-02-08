require 'coffee-script'

namespace :js do
  desc "compile coffee-scripts from ./_assets/scripts to ./js"
  task :compile do
    source = "#{File.dirname(__FILE__)}/_assets/scripts/"
    javascripts = "#{File.dirname(__FILE__)}/js/"

    Dir.foreach(source) do |cf|
      unless cf == '.' || cf == '..'
        js = CoffeeScript.compile File.read("#{source}#{cf}")
        open "#{javascripts}#{cf.gsub('.coffee', '.js')}", 'w' do |f|
          f.puts js
        end
      end
    end
  end
end
require 'coffee-script'

desc "compile coffee-scripts from ./_assets/scripts to ./js"
task :compile do
  compile_sass
  compile_coffee
end

def compile_sass
  print 'Compiling SASS... '

  input = "#{ File.dirname(__FILE__) }/_assets/sass/"
  output = "#{ File.dirname(__FILE__) }/css/"

  Dir.foreach(input) do |file|
    unless file == '.' || file == '..'
      system("bundle exec sass #{ input }#{ file } #{ output }#{ file.gsub('.scss', '.css') }")
    end
  end

  puts 'done.'
end

def compile_coffee
  print 'Compiling CoffeeScript... '

  input = "#{ File.dirname(__FILE__) }/_assets/scripts/"
  output = "#{ File.dirname(__FILE__) }/js/"

  Dir.foreach(input) do |file|
    unless file == '.' || file == '..'
      js = CoffeeScript.compile File.read("#{ input }#{ file }")
      open "#{ output }#{ file.gsub('.coffee', '.js')}", 'w' do |f|
        f.puts js
      end
    end
  end

  puts 'done.'
end
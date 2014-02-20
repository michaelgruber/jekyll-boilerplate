desc "compile sass from ./_assets/sass to ./css"
task :compile do
  compile_sass
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
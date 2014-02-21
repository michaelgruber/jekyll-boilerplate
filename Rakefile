INPUT = "#{ File.dirname(__FILE__) }/_assets/sass/"
OUTPUT = "#{ File.dirname(__FILE__) }/css/"

desc "compile sass from ./_assets/sass to ./css"
task :build do
  compile_sass
  system "jekyll build"
end


desc "watch all files for changes"
multitask watch: ['watch:sass', 'watch:jekyll']
namespace :watch do
  task :sass do
    system "bundle exec sass --watch #{ INPUT }:#{ OUTPUT }"
  end

  task :jekyll do
    system "bundle exec jekyll serve --watch"
  end
end

def compile_sass
  print 'Compiling SASS... '

  Dir.foreach(INPUT) do |file|
    unless file == '.' || file == '..' || file[0] == '_'
      system "bundle exec sass #{ INPUT }#{ file } #{ OUTPUT }#{ file.gsub('.scss', '.css') }"
    end
  end

  puts 'done.'
end
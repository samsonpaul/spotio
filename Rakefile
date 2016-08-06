##################################################
# Compile skin sass to build/glue1.css
##################################################

desc "Filter build/glue1.css into Apps"
task :filterdown do
  require 'fileutils'
  puts "\n## Moving glue1.css into Apps"
  status = system("find Apps/. -type d -name 'css' -print0 | xargs -0 -I {} cp build/glue1.css {}")
  puts status ? "Success" : "Failed"
end

desc "Compile Sass to build/glue1.css"
task :compile do
  puts "\n## Compiling Sass"
  status = system("sass skin/glue1.scss:build/glue1.css")
  puts status ? "Success" : "Failed"
  puts "\n## Filtering glue1.css into Apps"
  Rake::Task["filterdown"].invoke
  # status = system("jekyll build")
  # puts status ? "Success" : "Failed"
  puts "\n## Deleting Sass source map"
  status = system("rm -f build/*.map")
  puts status ? "Success" : "Failed"
end

# desc "Notify various services about new content"
#   task :ping => [:pingomatic, :sitemapgoogle, :sitemapbing] do
# end

require 'bundler'

desc "Generate the static files, publish to Status Hero repository"
task "publish" do
  Bundler.require
  puts ""
  system "rm -rf ../statushero/public/api; mkdir ../statushero/public/api"
  puts "Publishing to ../statushero/public/api"
  system "middleman build --clean --build-dir '../statushero/public/api'"
  puts "Finished!"
  puts ""
end

desc "Generate the blog and test the HTML-ness"
task "test" do
  Bundler.require
  raise unless system "middleman build --clean"
  raise unless system "htmlproofer --disable-external --allow-hash-href ./build"
end

task default: [:test]
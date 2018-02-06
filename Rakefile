require 'bundler'

desc "Generate the static files, publish to GitHub"
task "publish" do
  Bundler.require
  puts ""
  system "./deploy.sh"
  puts ""
end

desc "Generate the blog and test the HTML-ness"
task "test" do
  Bundler.require
  raise unless system "middleman build --clean"
  raise unless system "htmlproofer --disable-external --allow-hash-href ./build"
end

task default: [:test]
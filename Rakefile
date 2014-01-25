task :default => [:build]

desc "Build"
task :build do
  puts "Building..."
  system "middleman build --verbose" or exit 1
end

desc "Deploy to S3"
task :s3 do
  puts "Deploying to S3..."
  system "s3_website push --site=build --headless" or exit 1
end

desc "Publish page"
task publish: [:build, :s3]

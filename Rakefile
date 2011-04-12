# Bundler tasks are defined in rakelib/bundler.rake
#
desc "Run specs"
task "spec" do |t|
  CoreComponents.in_each_dir do
    system "rake spec"
  end
end

desc "Run specs using RCov"
task "spec:rcov" do |t|
  CoreComponents.in_each_dir do
    system "rake spec:rcov"
  end
end

desc "Run integration tests. (Requires a running cloud)"
task "tests" do |t|
  system "cd tests; rake tests"
end

namespace "db" do
  desc "Create or update the configured CloudController database"
  task "migrate" do
    system "cd cloud_controller; rake db:create db:migrate"
  end
end
task "migrate" => "db:migrate"

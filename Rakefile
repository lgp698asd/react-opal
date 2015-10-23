Bundler.require
Bundler::GemHelper.install_tasks

require 'opal/rspec/rake_task'
require 'react/source'

Opal::RSpec::RakeTask.new(:default) do |server, task|
  # Need a Phantom polyfill
  es5_path = File.join(RailsAssetsEs5Shim.load_paths[0], 'es5-shim/es5-shim.js')
  task.files = [es5_path, React::Source.bundled_path_for('react-with-addons.js')] + FileList['spec/opal/**/*_spec.rb']
end

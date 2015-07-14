require 'rake/testtask'
require 'rubocop/rake_task'

task default: [:test]

# install asciidoc libxml2-utils xmlto docbook-xsl docbook-xml
desc 'Update manpage from asciidoc file'
task :manpage do
  system('find doc/ -type f -exec a2x -d manpage -f manpage -D man/man1 {} \;')
end

Rake::TestTask.new do |t|
  t.pattern = 'test/**/*_test.rb'
end
task spec: :test

desc 'Execute rubocop'
RuboCop::RakeTask.new(:rubocop) do |t|
  t.options = ['-D'] # display cop name
end

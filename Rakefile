require 'date'

desc 'Create a new draft post'
task :post do
  STDOUT.puts('Whats the title of your post?')
  title = STDIN.gets.chomp

  if title.nil? || title.empty?
    STDOUT.puts('No post name? Aborting...')
    next
  end

  slug = "#{Date.today}-#{title.downcase.gsub(/[^\w]+/, '-')}"

  file = File.join(
    File.dirname(__FILE__),
    '_posts',
    slug + '.markdown'
  )

  File.open(file, 'w') do |f|
    f << <<-EOS.gsub(/^    /, '')
    ---
    layout: post
    title: #{title}
    published: false
    categories:
    ---

    EOS
  end

  system("#{ENV['EDITOR']} #{file}")
  puts("Post \"#{title}\" created successfully!")
end

desc 'List all draft posts'
task :drafts do
  puts `find ./_posts -type f -exec grep -H 'published: false' {} \\;`
end

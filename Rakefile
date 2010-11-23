task :default => ['blacklight:screenshots', 'blacklight:examples']
namespace :blacklight do
   desc 'create blacklight screenshots'
   task :screenshots do
     require 'digest/md5'
     urls = ['http://demo.projectblacklight.org/', 'http://demo.projectblacklight.org/?f%5Bpub_date%5D%5B%5D=2008', 'http://demo.projectblacklight.org/catalog/2008308201']

     urls.each do |url|
       `python bin/webkit2png.py -D images/screenshots -s 0.70 "#{url}"`
     end
   end

   namespace :examples do

   desc 'add a new blacklight example instance'
   task :add do
     require 'digest/md5'

     url = ENV['url']
     name = Digest::MD5.hexdigest(url)
     title = ENV['title'] || '<!-- Add a short caption here -->'
     if false && RUBY_PLATFORM.downcase.include?("darwin")
     print 'Generating screengrabs...' + "\n"
     `python bin/webkit2png.py -o #{name} --clipwidth 532 --clipheight 400 --delay 2 -D images/screenshots -s 0.70 "#{url}"`
     print "-- Preview the automatically generated screenshots and add them to the repository: `git add images/screenshots/#{name}*`" + "\n"
     else
       print "-- Take a screenshot of the example and save a 532x400 PNG image as \"./images/screenshots/#{name}-clipped.png\"" + "\n"
     end

     print "-- Add this line to ./_includes/examples_gallery.html:" + "\n"

     print '<li><a href="' + url + '"><img src="/images/screenshots/' + name + '-clipped.png" /></a><div class="title">' + title + '</div></li>' + "\n"

   end
   end
end

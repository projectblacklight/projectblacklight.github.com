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
   task :examples do
     require 'digest/md5'
     urls = { 'http://demo.projectblacklight.org/?f%5Bpub_date%5D%5B%5D=2008' => 'Generic Blacklight plugin demonstration', 'http://searchworks.stanford.edu/?q=blacklight&search_field=search' => 'Stanford University', 'http://search.lib.virginia.edu/?f%5Bsource_facet%5D%5B%5D=Digital+Library&facets%5B%5D=library_facet&facets%5B%5D=format_facet&facets%5B%5D=recordings_and_scores_facet&facets%5B%5D=recording_format_facet&facets%5B%5D=instrument_facet&facets%5B%5D=music_composition_era_facet&facets%5B%5D=author_facet&facets%5B%5D=language_facet&facets%5B%5D=source_facet&facets%5B%5D=region_facet&facets%5B%5D=subject_facet&portal=music&sort=date_received_facet+desc' => 'University of Virginia', 'http://forward.library.wisconsin.edu/catalog?q=blacklight&qt=search&local=true' => 'University of Wisconsin-Madison', 'http://openvault.wgbh.org/catalog?f%5Bpbcore.title_Series%5D%5B%5D=Vietnam%3A+A+Television+History&q=&style=table&x=3&y=6' => 'Open Vault (WGBH Media Library and Archives)', 'http://historicalstate.lib.ncsu.edu/catalog?f[decade_facet][]=2010s' => 'Historical State (NCSU Libraries)', 'http://nwda.projectblacklight.org/?f[format_facet][]=Postcards' => 'Northwest Digital Archives', 'http://findingaids.library.northwestern.edu/catalog?f%5Brepository_facet%5D%5B%5D=Charles+Deering+McCormick+Library+of+Special+Collections' => 'Archival and Manuscript Collections  (Northwestern University Library)', 'http://www.agnic.org/search?q=&search_field=all_fields&commit=search' => 'Agriculture Network Information Center'}
     s = '<ul class="fader">' + "\n"
     urls.each do |url, title|
       name = Digest::MD5.hexdigest(url)
       `python bin/webkit2png.py -o #{name} --clipwidth 532 --clipheight 400 --delay 2 -D images/screenshots -s 0.70 "#{url}"`
       s += '<li><a href="' + url + '"><img src="/images/screenshots/' + name + '-clipped.png" /></a><div class="title">' + title + '</div></li>' + "\n"
     end
     s += "</ul>"

     File.open('_includes/examples_gallery.html', 'w') { |f| f.write(s) }
   end
end

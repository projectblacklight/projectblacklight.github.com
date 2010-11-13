task :default => ['blacklight:screenshots', 'blacklight:examples']
namespace :blacklight do
   desc 'create blacklight screenshots'
   task :screenshots do
     urls = ['http://demo.projectblacklight.org/', 'http://demo.projectblacklight.org/?f%5Bpub_date%5D%5B%5D=2008', 'http://demo.projectblacklight.org/catalog/2008308201']

     urls.each do |url|
       `python bin/webkit2png.py -D images/screenshots -s 0.70 "#{url}"`
     end
   end
   task :examples do
     urls = ['http://searchworks.stanford.edu/?q=blacklight&search_field=search', 'http://search.lib.virginia.edu/?f%5Bsource_facet%5D%5B%5D=Digital+Library&facets%5B%5D=library_facet&facets%5B%5D=format_facet&facets%5B%5D=recordings_and_scores_facet&facets%5B%5D=recording_format_facet&facets%5B%5D=instrument_facet&facets%5B%5D=music_composition_era_facet&facets%5B%5D=author_facet&facets%5B%5D=language_facet&facets%5B%5D=source_facet&facets%5B%5D=region_facet&facets%5B%5D=subject_facet&portal=music&sort=date_received_facet+desc', 'http://forward.library.wisconsin.edu/catalog?q=blacklight&qt=search&local=true', 'http://openvault.wgbh.org/catalog?f%5Bpbcore.title_Series%5D%5B%5D=Vietnam%3A+A+Television+History&q=&style=table&x=3&y=6' ]

     urls.each do |url|
       `python bin/webkit2png.py --delay 2 -D images/screenshots -s 0.70 "#{url}"`
     end
   end
end

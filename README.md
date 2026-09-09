#Jekyll Site for CMP

The publications page is dynamically generated (i.e. created in the browser) so that it will always reflect the latest faculty publications, provided PubMed is provided with the updated search terms.

To force an update to the publications results when faculty change, you only need to edit `_config.yml` - specifically the `pubmed_link` and `pubmed_rss` variables:

1. Update the PubMed search. Either: 

	- copy the `pubmed_link` url into a browser and update the search terms (it seems this means editing the text string with all the brackets and parentheses)
	- or create a new search from scratch at PubMed. 
	
	Either way, be sure to click 'Search' to get the updated results, and copy the resulting new url from the browser and assign it to `pubmed_link`.

2. Now get the RSS feed version of that search: 

	- In the browser, click on the 'RSS' link/icon right under the search box at the top of the page, select the number of items it should include in the feed (I've chosen 20), and 'Create RSS'.
	- Click on 'XML' link/icon. Copy the url of the page which that loads and assign it to `pubmed_rss`
	
3. OPTIONAL: To change the number of journal articles that are displayed, you will need to change both the PubMed option when creating the RSS feed (step 2) _and_ the value set in `<script>` section of pages/faculty/publications/index.html of the line `feed.setNumEntries(20);`

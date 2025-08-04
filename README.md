Initial repo for codespace trial run on eCFR

<h2>eCFR methods</h2>

<h3>eCFR_API_Wrapper:<h3>
Wrapper utility class with two methods:

 <li>fetch_data - synchronous call to a JSON REST API endpoint</li>
 
 <li>fetch_data_asynch - same but asynch</li> 


eCFR_HouseKeeping:
  fetch_titles_data - helper method to return titles.json from API and populate self.titles.json (fast)

  fetch_agencies_data - helper method to return agencies.json from API and populate self.agencies.json (reasonably fast)
  
  refresh_agencies - fetch agencies.json and write the file 
  
  refresh_titles - check to see if titles.json exists and is <30 days stale. fetch and write otherwise
  
  refresh_title_and_chapter_versions - fetch a single title and chapter versions json from the API and write the file 
  
  load_agency_data - try to load agencies.json from local file else refresh 
  
  load_title_data - try to load titles.json from local file else refresh 
  
  load_title_and_chapter_versions - try to load a single title and chapter versions json from file 
  
  refresh_all_versions_byslug - call refresh_title_and_chapter_versions for all agency slugs
  
 -----https://skylight.digital/careers/career-pathways/digital-transformer/#principal-digital-transformer 
  
  fetch_full_text_byslug - helper method to return full text of a title and chapter from API
  
  refresh_full_text_byslug - check to see if full text exists, if not fetch full text and write the file 
  
  load_full_text_byslug - try to load full text of a title and chapter else refresh 
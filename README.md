Initial repo for codespace trial run on eCFR

<h2>eCFR methods</h2>

<h3>eCFR_API_Wrapper:</h3>
Wrapper utility class with two methods:
 <li>fetch_data - synchronous call to a JSON REST API endpoint</li>
 <li>fetch_data_asynch - same but asynch</li> 


<h3>eCFR_HouseKeeping:</h3>
<p>Helper class to interact with the API endpoints in a structured way</p>
Writes titles, agencies, and full text of title data to disk as JSON and XML
10 methods, in 3 groups: fetch (calls the API), load (reads from file, if file not exists, calls fetch), refresh (check if file exists and is <30 days old, in which case load, else fetch)

<h4>FETCH - call the API</h4>
  <li>fetch_agencies_data - helper method to return agencies.json from API and populate self.agencies.json (reasonably fast) </li> 
  <li>fetch_titles_data - helper method to return titles.json from API and populate self.titles.json (fast) </li>
  <li>fetch_full_text_by_title_and_chapter - helper method to return full text of a title and chapter from API (slow - use asynch) </li>

<h4>LOAD - load from file. If file not found, fetch</h4>
  <li>load_agency_data - try to load agencies.json from local file else refresh</li> 
  <li>load_title_data - try to load titles.json from local file else refresh</li>  
  <li>load_full_text_by_title_and_chapter - try to load a single title and chapter versions json from file</li> 

<h4>REFRESH - check age. if not found or # of stale_days, fetch, else, load</h4>  
  <li>if_fresh - helper function to check the age of a file for staleness</li> 
  <li>refresh_agencies - try to load and confirm < 30 days fetch agencies.json and write the file</li> 
  <li>refresh_titles - check to see if titles.json exists and is <30 days stale. fetch and write otherwise</li>
  <li>refresh_full_text_by_title_and_chapter - fetch a single title and chapter versions json from the API and write the file</li> 
  <li>refresh_full_text_all - fetch all titles from the API and write the files</li> 

  

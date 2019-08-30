### FileType Identification Front End

Using BootStrap and jQuery frameworks, we created a minimal viable frontend for our FileType Identification. The site can be accessed using this [link](ec2-184-72-117-114.compute-1.amazonaws.com).

#### 1) Type of Inputs
This website can take use of several typesof inputs. They are:
  - Single filename query.
  - Multiple filenames queries.
  
#### 2) Using AJAX
After extracting the extensions from queries and verifying the queries to be valid using javascript, the queries were mapped onto one of the services.
  - Single filename on */search/single* with queryExtension parameter
  - Multiple filenames on */search/pagewise/lastpage* with parameters - pageNo and PageSize and JSON body containing list of extension strings and length of the list.

The services return with the JSON object(s) found for the matching extensions which are handled dynamically for the queries. For multiple filenames queries, the page will make use of pagination using page-number and a boolean variable isLastPage (indicating if the page sent over by the services is final) encapsulated in response.  
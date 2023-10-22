Web Scraping Project Judicial Auctions_pandasDFtoImage_Bot_instagram

	OBJECT & FUNCTIONALITY:
The idea of the program is to provide people with information about judicial auctions so that they can become aware of the properties and base prices. 
This could lead to more people showing interest in these assets, benefiting creditors in bankruptcy proceedings or the parties conducting the auctions. 
It would also benefit third parties interested in this information, allowing them to potentially acquire assets close to their homes or of personal interest.

What it does is download judicial notices, filter the data (using web scraping techniques and artificial intelligence), 
create a table, which is then displayed as an image with relevant information (see data.png). 
Subsequently, a bot publishes it on Instagram.

	
	OPERATION EXPLANATION:

The program accesses the page of the Official Gazette of the Argentine Nation.
I used a Python library to scroll to the bottom of the page, displaying all the page's data (Selenium).
I coded it to store in a variable the HTML elements that interest me to later identify the published auctions.
If there is only one published auction, it clicks and accesses the page with information about the corresponding judicial edict.
It then saves the relevant text content in a variable.
If there are more than one auction (similar to the previous case), it enters the first publication and saves the corresponding information in a variable.
But then it clicks on a tab that directs to a page containing only the judicial auctions for the date.

It saves the URL of the mentioned page and closes it.
(I tried to work from the saved URL, but it seemed faster to work on the original official gazette URL from the beginning.)

I created a function that accesses each link and saves the remaining edicts.
In the end, I have a list called "texts" that stores the information from the EDICTS. Each judicial EDICT is an element.
And each element is then processed using a function that uses the OPEN AI API to extract the relevant information.

I define the FUNCTION that processes the edicts with AI.
This function adds relevant information to four lists.
Then, I create a function that converts the lists into dictionaries.
And

create a DataFrame from the dictionaries.
I create an image with a frame that fits the data frame, with the aspect ratio suitable for Instagram.
And it exports it as an image "data.png."

Although I didn't develop it, it was part of the original idea to save geolocation coordinates to generate a map image
locating each auctioned property.

Then I created a bot that logs into Instagram.
And it should upload the photo of the created frame.
However, I have not been able to make this part work properly yet because the HTML path numbers on Instagram change,
so I have left this part at the end of the commented code.

It uploads one photo and then uploads the other one.
END.

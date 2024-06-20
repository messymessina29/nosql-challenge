# nosql-challenge
# Part 1: NoSQL_setup_starter
I only needed help with one section on part 1 of this challenge and that was for changing the data type from string to a decimal. I got most of it correct but I forgot to put a $ in front of $geocode.latitude and $geocode.longitude. I also struggle with the dictionary syntax at times: when to use {}
    Code snippet: establishments.update_many({},[{'$set':
                                {"geocode.latitude": {'$toDouble':"$geocode.latitude"},
                                 "geocode.longitude": {'$toDouble':"$geocode.longitude"}}

# Part 2: NoSQL_analysis_starter
I got through most of this part by myself as well but there were some instances where I needed help from the AI assitant. The dicitonary{} syntax also created some diffculties for me in this part as well. I wasnt sure if we were supposed to hard code the latitude and longitude of Penang Flavours but I ended up filtering the collection to save the variables. I was having trouble just pulling the number out and the AI said to add ['geocode']['latitude'] to the end of my code which got me just the number.
Code Snippet: 
    latitude = establishments.find_one({'BusinessName':'Penang Flavours'},{'geocode.latitude':1,'_id':0})['geocode']['latitude']
    longitude = establishments.find_one({'BusinessName':'Penang Flavours'},{'geocode.longitude':1,'_id':0})['geocode']['longitude']
For the pipeline part, I got through majority of it on my own and only needed a few tweaks from the AI. I wasn't sure how to get the sort to work and I didn't realize that 'count' is the field being used for the descending sort.
Code Snippet:
    # 3. Sorts the matches from highest to lowest
    sort_values = {'$sort': {'count': -1}}
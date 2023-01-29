# Current weather condition reports are different

I am building a weather command line tool and the API that I am calling from is the MET office
because they are the official UK weather reporting institution. Curiously, they do not have a
current weather end point for a location. Only can query for 3 hour intervals or day overview.

This lead me down a bit of rabbit hole checking various sites for the current weather at my
location. I found that they are all slightly different... MET reports 8 degrees, BBC reports 8
as well but bing reports 7 but MET and BBC differ later on at night by a difference of 1 degree.

It looks like that they are not reporting real time information but rather displaying the data for
that hour as the sites display them hourly. There is access to past 24hrs weather but I don't see
weather predictions for an hourly interval.

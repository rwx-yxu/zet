#Google maps API autocomplete does not work well with UK addresses
Google maps is practically the go to maps platform for most users. I
started to use the Google map API recently and noticed that the auto
complete feature for addresses do not return street numbers or post
codes sometimes.

This is because UK post codes are tied to the address at the street
level whereas for Europe for example, the postcode represents a whole
region. This discovery was maddening to uncover because of the
granularity that the Google API returns so it was difficult to get a
straight answer.

Needless to say, do not use Google maps autocomplete API for UK address searches. 
I wasn't aware initially that there are other UK address specific APIs out
there like `postgrid` or `getaddress`. I still think that Googles
distance matrix can still be used so long as you obtain the latitude and
longitude.

Related:

    * (https://stackoverflow.com/questions/52631807/google-maps-autocomplete-doesnt-include-postcodes-in-address-search)
    * (https://getaddress.io)
    * (https://postgrid.co.uk)

Tags

    #api #google #maps #autocomplete

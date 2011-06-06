# Why I Forked Citygrid

To support their version 2 api.  http://docs.citygridmedia.com/display/citygridv2/CityGrid+APIs

You can not run version 1 and 2 gems at the same time.  Why?  Well their documentation says their V1 API will be depreciated at some 
point in time.





# Citygrid

This is a Ruby wrapper for the [CityGrid API](http://developer.citysearch.com/home).

## Installation

As a gem:

    sudo gem install citygrid

    
## Get a Publisher Code

Sign up for a CityGrid Publisher: [http://developer.citygridmedia.com/dashboard/registration](http://developer.citygridmedia.com/dashboard/registration)
    
## Usage

### Instantiate a client

    >> citygrid = Citygrid::Client.new(:publisher => 'your_publisher_code')
    
### or configure once

    >> Citygrid.configure do |config|
    >>   config.publisher = 'publisher'
    >> end
    >> citygrid = Citygrid::Client.new
    
#### Examples

    >> spot = citygrid.search_locations(:what => "roots coffee", :where => "76180", :rpp => 1)
    >> spot.results.location.name
    => "Roots Coffeehouse"
    
    >> spot = citygrid.reviews(:what => "roots coffee", :where => "76180", :rpp => 1)
    >> spot.results.reviews.first.review

    
You can search for locations and events, get reviews, and get business profiles.

## Copyright

Contact me if you have any suggestions and feel free to fork it!

Copyright (c) 2009 Johnny Khai Nguyen, released under the MIT license

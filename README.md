# mpcs51030-2017-summer-final-project-tjlynch15


The name of my app is "Movie Night". The file name is Movie App

The app is universal, but is only functional in portrait orientation.

Data for Now Playing and Top Rated obtained from The Movie DB ("tmdb")
https://www.themoviedb.org/

Data for Theaters (movie times, locations) obtained from Gracenote Developer
http://developer.tmsapi.com/page. **My free subscription limits user to 50 calls per day, and 2 calls per second**.

The app is controlled by a tabview controller

The first tab button selects Now Playing movies. These movies currently playing in theaters per the tmdb database. The view is a tableview that displays a thumbnail image, the movie title, and the release date. Selecting a given cell displays the movie details, including a larger poster image, and a full description of the movie.

The Now playing view has a navigation bar button called "About". Selecting this button will cause a view with instructions for the app to drop down from above. The view shows an html page with instructions. Clicking the close button will cause the about view to rise up out of view.

The second tab button selects Top Rated movies. These are the top rated movies per tmdb. Like Now Playing movies, the view is a tableview that displays a thumbnail image, the movie title, and the release date. Selecting a given cell displays the movie details, including a larger poster image, and a full description of the movie.

The third tab button selects movies playing in theaters within a 5, 10 or 15 mile radius of the user. The default radius is 5 miles, and other options can be selected in Settings. The application asks  permission from the user to obtain the user's current location. The current date is obtained using the NSDate api. Both the coordinates of the user's location, the specified radius, and the current date are inserted into a url used to query the Gracenote Developer database for the movie playing in theaters within the specified radius of the user's location on the current date. The tableview showing the movies has pull to refresh functionality. 

    Selecting a specific movie within the tableview will segue to a tableview of theaters/showtimes for that movie. Selecting the "Tickets" button within a given cell will open a Fandago webpage for purchasing tickets for that movie in the specified theater at the specified time. The ticket button for showtimes playing in the future are blue in color. The ticket button for past showtimes are clear with a black border, and are not enabled.

The fourth tab button selects a map view with a search bar. The search bar is prepopulated with "Theaters near me". Selecting search will display a tableview of theaters near user's current location. Selecting a theater from the tableview will drop a pin at that theater's location in the map view. Selection the pin will show a popup with a car icon and a location description. Selecting the car icon will open the directions function in Apple maps.


Issues/Bugs:

1. Autolayout not working in TheatersTableView and ShowtimesTableView. Did the best I could.


Future Enhancements:

1. Enable user to input zipcode as an alternative to allowing app to use user's location.

2. Allow the user to select a date other than the current date. Would be limited to the current week due to limitations on movie showing information.

3. Provide additional movie information, including director, cast, and rating.


// Attribution: - Casting json
https://stackoverflow.com/questions/30480672/how-to-convert-a-json-string-to-a-dictionary

// Attribution: - Display image from url
https://stackoverflow.com/questions/39813497/swift-3-display-image-from-url

// Attribution: - Map kit, directions
https://www.thorntech.com/2016/01/how-to-search-for-location-using-apples-mapkit/

// Attribution: - Shared networking Present alert if no internet connection
https://stackoverflow.com/questions/26554894/how-to-present-uialertcontroller-when-not-in-a-view-controller

// Attribution: - Creating button in tablleview cell
https://stackoverflow.com/questions/39947076/uitableviewcell-buttons-with-action

// Attribution: - Settings Bundle
https://makeapppie.com/2016/03/14/using-settings-bundles-with-swift/






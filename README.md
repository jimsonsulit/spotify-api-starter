# Getting Started with the Spotify Web API using Python
Get up and running with the Spotify Web API using Python!

This repo contains a small demo application which will authenticate with the Spotify API, list all of a user's playlists,
list all of the tracks for a given playlist, and fetch the audio features for selected tracks in that playlist.
It also allows you to search a track and list out the audio features specifically for that track.

Feel free to fork this jawn and use it for your own hacks and stuff!

**Some handy documentation:**
 - Web API Documentation - https://developer.spotify.com/web-api/
 - Spotipy Documentation - http://spotipy.readthedocs.io/en/latest/

   
## Setup
First, we need to make sure python3, pip, and virtualenv are installed on your system.
To install this stuff, run
```
./setup.sh
source ~/.bashrc
```

Go to https://developer.spotify.com/my-applications and create a new Application.
For the Redirect URI, add `http://localhost/callback` (and don't forget to click "Save) 

From that page, copy your ClientId and your ClientSecret and put them into a file called
`credentials.json` in the root of this repo that looks like this:
```
{
  "client_id": "your-spotify-client-id",
  "client_secret": "your-spotify-client-secret",
  "redirect_uri": "http://localhost/callback"
}
```
For details about how the API authenticates your account with this, see 
https://developer.spotify.com/web-api/authorization-guide/#authorization_code_flow


## Running
To run the out of the box demo, simply run
```
make run
```

Once the program runs, you'll be prompted for your username, and your browser window will open.
Once you log in with Spotify, copy the URL that you're redirected to and paste it into the terminal.

After that, just follow the terminal :)

#### Example Run
```
**************************************************
Spotify Web API Demo App
**************************************************

What is your Spotify username: markster3910


            User authentication requires interaction with your
            web browser. Once you enter your credentials and
            give authorization, you will be redirected to
            a url.  Paste that url you were directed to to
            complete the authorization.

        
Opened https://accounts.spotify.com/authorize?client_id=...


Enter the URL you were redirected to: http://localhost/callback?code=...



******************************
Your Playlists
******************************
  1) An Album a Day Keeps the Doctor Away - spotify:user:markster3910:playlist:5Exd8CXJ9NSrUWhd1iMwXI
  2) Swingin' Electro - spotify:user:markster3910:playlist:2iu5E2EZgfNroIFFzxIyas
  3) Gramatik & Friends - spotify:user:markster3910:playlist:0JrrAohiYpRNYpduglGBZi

Choose a playlist: 1

**************************************************
Tracks in "An Album a Day Keeps the Doctor Away"
**************************************************

  1) Spanish Key - Miles Davis
  2) John McLaughlin - Miles Davis
  3) Miles Runs the Voodoo Down - Miles Davis
  4) Sanctuary - Miles Davis
  5) She Ain’t Right For You - Macy Gra
  6) Waterwheel - Oregon
  7) Witchi-Tai-To - Oregon
  8) El Tren de la Vida - Perujazz, Abraham Laboriel, Alex Acuña
  9) Whoodeeni - De La Soul, 2 Chainz
  10) Nosed Up - De La Soul
  11) You Go Dave (A Goldblatt Presentation) - De La Soul, David Goldblatt

Choose some tracks (e.g 1,4,5,6,10): 1,7,10 

******************************
Audio Features
******************************

  Spanish Key - Miles Davis
    tempo: 106.711
    time_signature: 4
    key: D
    loudness: -7.175
    energy: 0.785
    dancibility: None
    acousticness: 0.489
    instrumentalness: 0.411
    liveness: 0.121
    speechiness: 0.0542

  Witchi-Tai-To - Oregon
    tempo: 146.625
    time_signature: 4
    key: D
    loudness: -17.951
    energy: 0.318
    dancibility: None
    acousticness: 0.657
    instrumentalness: 0.758
    liveness: 0.183
    speechiness: 0.036

  Nosed Up - De La Soul
    tempo: 92.293
    time_signature: 4
    key: C♯/D♭
    loudness: -12.567
    energy: 0.458
    dancibility: None
    acousticness: 0.0835
    instrumentalness: 1.97e-05
    liveness: 0.552
    speechiness: 0.335

Run the program again? (Y/N): n
```
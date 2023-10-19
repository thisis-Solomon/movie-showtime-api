# Movie Showtime API

The Movie Showtime API is a RESTful web service that allows you check out the movie you would want to see or is showing on your prefered Zambian cinemas. This API is based on the data scraped from [mydorpie.com](), a mobile-friendly search platform for Southern Africa that hosts the region's busiest independent movie guide with trailers, load-shedding schedules, weather and more.

You can use this API to:

- Check for malls that have cinemas
- Get information about cinema in a mall, such as name, address, phone number.
- Get information about movies in a cinema, such as title, rating, runtime, and showtimes
- Get additional information about the movie such as genre, duration, stars, directors, release date

## How to use the API and Examples

To use the Movie Showtime API, you need to register for an API key and include it in every request. You can register for a free API key [here]().

The base URL for the API is `https://movieshowtimeapi.cyclic.app/api/`. All requests and responses are in JSON format.

The following endpoints are available:

- `/cinemas`: Returns a list of malls

```json
{
  "count": 3,
  "cinemas": [
    {
      "name": "Arcades Mall"
    },
    {
      "name": "Levy Junction Mall"
    },
    {
      "name": "Manda Hill Mall"
    }
  ]
}
```

`/movies?q=acardes+mall`: Returns details of a specific mall matched cinema name query and movies showing

```json
{
  "movies_in_cinema": {
  "movies_count": 10,
  "cinema_information": [
      {
        "cinema_banner": "https://pics.mydorpie.com/i/cinemas/numetro_logo640.png",
        "address": "Arcades Shopping Centre, Great East Road, Lusaka, Zambia"
      }
    ],
  "movies_showing": [
      {
        "movie_name": "2D - 57 Seconds",
        "movie_poster": "https://pics.mydorpie.com/i/movies/57-Seconds.jpg"
      },
      {
        "movie_name": "2D - The Creator",
        "movie_poster": "https://pics.mydorpie.com/i/movies/The-Creator.jpg"
      },
      {
        "movie_name": "2D - Expendables 4",
        "movie_poster": "https://pics.mydorpie.com/i/movies/Expendables-4.jpg"
      },
    ]
  }
}
```

`movie/{id}`: Returns a specific movie by its ID which is the movie title

```json
{
  "single_movie": {
    "movie_title": "2D - Expendables 4",
    "story_line": "Armed with every weapon they can get their hands on and the skills to use them, The Expendables are the world’s last line of defense and the team that gets called when all other options are off the table. But new team members with new styles and tactics are going to give “new blood” a whole new meaning.",
    "schedule": "Starting times for each show are listed. Popular movies often show on more than one screen on the same day, so start times may be close together.",
    "movie_times": [
      {
        "date": "Tue 17 Oct",
        "times": ["12:15", "17:30"]
      }
    ],
    "disclaimer": "Please note that myDorpie cannot take responsibility for errors or unexpected changes to movie schedules. Cinemas may not update their schedules during load-shedding so it's best to contact the cinema or the mall beforehand if they don't have backup power."
  }
}
```

`movie/details/{id}`: Returns details of a specific movie by its ID which the movie title

```json
{
  "additional_info": {
    "movie_poster": "https://pics.mydorpie.com/i/movieimages/The-Nun-ll.jpg",
    "movie_title": "The Nun ll",
    "category": ["HORROR"],
    "movie_description": "Four years after the events at the Abbey of St. Carta, Sister Irene returns once again and comes face to face with the demonic force Valak, the Nun.",
    "core_stars": [
      "Taissa Farmiga",
      " Jonas Bloquet",
      " Storm Reid",
      " Anna Popplewell",
      " Bonnie Aarons"
    ],
    "release_date": "Fri 8 September 2023",
    "duration": "1 hour 50 minutes",
    "directed_by": ["Michael Chaves"]
  }
}
```

## Feedback
If you have any questions, suggestions, or issues with the Movie Showtime API, please feel free to contact me at [solomonnjobvu1@gmail.com](). I appreciate your feedback and support. Thank you for using the Movie Showtime API! 😊

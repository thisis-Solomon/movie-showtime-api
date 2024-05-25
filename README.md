# Movie Showtime API Documentation
Welcome to the Movie Showtime API, a RESTful web service that provides information about movie showtimes in Zambian cinemas. This API is powered by data scraped from mydorpie.com, a leading mobile-friendly search platform for Southern Africa, offering a comprehensive movie guide, trailers, load-shedding schedules, weather, and more.

## Overview
The Movie Showtime API enables you to:

1. Check for malls that have cinemas.
2. Obtain information about cinemas in a mall, including name, address, and phone number.
3. Retrieve details about movies in a cinema, such as title, rating, runtime, and showtimes.
4. Access additional information about a movie, including genre, duration, stars, directors, and release date.

### Base URL
The base URL for the API is [movieshowtimeapi](https://movie-showtime-api.onrender.com/api). All requests and responses are in JSON format.

### Endpoints
#### 1. /cinemas
**Description:** Returns a list of malls with cinemas.

Example Response:
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

#### 2. /movies?q={mall_name}
**Description:** Returns details of a specific mall matched by cinema name query and movies showing.

Example Response:

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
      }
    ]
  }
}
```

#### 3. /movie/{id}
**Description:** Returns details of a specific movie by its ID (movie title).

Example Response:

```json
{
  "single_movie": {
    "movie_title": "2D - Expendables 4",
    "story_line": "Armed with every weapon they can get their hands on and the skills to use them, The Expendables are the world’s last line of defense...",
    "schedule": "Starting times for each show are listed. Popular movies often show on more than one screen on the same day...",
    "movie_times": [
      {
        "date": "Tue 17 Oct",
        "times": ["12:15", "17:30"]
      }
    ],
    "disclaimer": "Please note that myDorpie cannot take responsibility for errors or unexpected changes to movie schedules..."
  }
}
```

#### 4. /movie/details/{id}
**Description:** Returns additional details of a specific movie by its ID (movie title).

Example Response:

```json
{
  "additional_info": {
    "movie_poster": "https://pics.mydorpie.com/i/movieimages/The-Nun-ll.jpg",
    "movie_title": "The Nun ll",
    "category": ["HORROR"],
    "movie_description": "Four years after the events at the Abbey of St. Carta, Sister Irene returns once again and comes face to face with the demonic force Valak, the Nun.",
    "core_stars": ["Taissa Farmiga", "Jonas Bloquet", "Storm Reid", "Anna Popplewell", "Bonnie Aarons"],
    "release_date": "Fri 8 September 2023",
    "duration": "1 hour 50 minutes",
    "directed_by": ["Michael Chaves"]
  }
}
```

### Conclusion
Explore the Movie Showtime API to seamlessly integrate movie showtime information into your applications and enhance the cinema-going experience for users in Zambia.

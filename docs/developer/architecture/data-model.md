## Data Model Concepts

The data model is centered around the concept of an "album" with associated attributes:

### Core Entities

- **Albums**: The primary entity representing musical releases
- **Artists**: The creators of albums (bands or individual musicians)
- **Years**: The temporal dimension for organizing releases
- **Ratings**: Numerical evaluation of albums on a 0-10 scale

### Key Relationships

- An album is created by exactly one artist
- An album is released in a specific year
- An album receives one rating and one ranking within its release year
- Albums can have special designations (vinyl, EP, live)

### Data Schema

The data schema uses a flat structure with these fields:

- Year: Release year of the album
- Ranking: Position within the release year
- Album: Title of the release
- Artist: Name of the band or musician
- Rating: Numerical score on a 0-10 scale
- Vinyl: Ownership indicator for physical media
- EP: Flag for extended play releases
- Live: Flag for live recordings

# Redline data

Contains data for [Redline game](redline.game). The data here is published to https://redline-dao.github.io/data/ and use for each race.

## Tracks
### Directory [tracks](tracks)

Contains the tracks data,
* [`tracks.csv`](tracks/tracks.csv) - CSV containing all tracks metadata.
  - Track Id
  - Name
  - Location Key - Accuweather location key
  - Country
  - Coords
  - Cell Count
  - Cell Length
  - Sponsor URL
* `{TrackId}.csv` - `{TrackId}` is the ID of the track.
  - Contains cell info for the track

### How to

#### Add a new track
1. Add track row in `tracks/tracks.csv`. Let's say we add this track,
   ```
   bora-bora,Bora Bora island,2349_poi,French Polynesia,16°30′04″S 151°44′24″W,151,100,https://example.com
   ```
2. Create track cells CSV with at least following headers-
   - Angle, TerrainType, Slope, Lane0, Lane1, Lane2, Lane3, Lane4, Lane5
3. Put the file in the repo with name matching the ID of the track in `tracks` directory.
   - `bora-bora.csv`
  
#### Edit an existing track metadata
Just edit track info in `tracks.csv`.
:warning: Avoid changing the ID of the track. If you really have to, make sure to accompanying `{TrackId}.csv`

#### Edit track cells
Edit `{TrackId}.csv` file.

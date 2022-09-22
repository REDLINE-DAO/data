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

## NPC bots

### Directory [npc](npc)

* [`bots.csv`](npc/bots.csv) - One bot NFT address per line
  -	raceType
  -	bots - can be comma separated *enclosed in quotes*

### Last cell should contain bots NFT IDs one will be picked at random.

The table should look like this,

![image](https://user-images.githubusercontent.com/11048263/191680346-d579922b-ca8b-4f0b-a1ca-703ab2aaf4f6.png)

## Prizes

### Directory [prizes](prizes)

* [`prizes.csv`](prizes/prizes.csv) - 
  -	raceType
  -	experience
  -	rewardDAI
  -	tickets
  -	nftPartSkin - can be comma separated *enclosed in quotes*

### Last cell should contain all possible NFT (Template) IDs one will be picked at random.

The table should look like this,

![image](https://user-images.githubusercontent.com/11048263/191680491-f89668f5-9767-4b32-9233-f8870fb33f97.png)

Uses 1st row if race type match is not found.

## Guidelines

After editing CSV files, preview them on GitHub.

Make sure the structure looks legit and there are no errors.

For example,
Errors like this shows up when comma separated values need to be wrapped in quotes.
![image](https://user-images.githubusercontent.com/11048263/191680169-746add31-1df9-46bc-9f7b-6dd30c7266b2.png)

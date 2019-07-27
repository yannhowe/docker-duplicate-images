# A dockerized duplicate image finder by philipbl

Original project [here](https://github.com/philipbl/duplicate-images).

## Quickstart
```
# Clone the project
git clone https://github.com/yannhowe/docker-duplicate-images.git

# Dump your photos into `images-to-dedup`

# Up the mongo DB
cd docker-duplicate-images
docker-compose up -d

# Hash photos and add to MongoDB
cd duplicate-images
pipenv run python ./duplicate_finder.py add ../images-to-dedup/ --db="mongodb://root:example@localhost:27017/"

# Whats in the DB, did it work?
pipenv run python ./duplicate_finder.py show --db="mongodb://root:example@localhost:27017/"
```

## Exploring your photos
```
# Find duplicate images print only
pipenv run python ./duplicate_finder.py find --print --match-time --db="mongodb://root:example@localhost:27017/"

# Find duplicate images with UI
pipenv run python ./duplicate_finder.py find --match-time --db="mongodb://root:example@localhost:27017/"

# Move duplicated images to ./Trash
pipenv run python ./duplicate_finder.py find --delete --match-time --db="mongodb://root:example@localhost:27017/"

# Clear MongoDB
pipenv run python ./duplicate_finder.py clear --db="mongodb://root:example@localhost:27017/"
```
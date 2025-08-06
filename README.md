# scar-fyi
source for wildwizardcreation.com/scar.fyi | a searchable database of all of GoodTimesWithScar's uploaded video transcripts

### Stats
<!-- START_STATS -->
```
Total Videos:
Unqiue Terms: 
Main Channel Videos:
VOD Channel Videos:
Date Range:
```
<!-- END_STATS -->
## CREDITS
this entire project is HEAVILY inspired by [hermits.fyi](https://github.com/etho-fyi/hermits-fyi) and [search.jerma.io](https://github.com/JermaSites/Jerma-Subtitle-Search) and definitely couldn't have been completed without the ability to study their source code and personalized methods!! major thank yous to both projects!!

## DEPENDENCIES

python versions 3.x and Node.js v16+ are supported. other versions and implementations may or may not work correctly.

`minisearch` (the search library) and `yt-dlp` (the video scraper) are required  
`tqdm` (python console progress bar library)  and `cli-progress` (node console progress tracker library) are not

```npm install minisearch cli-progress```

```pip install yt-dlp tqdm```


## Workflow Dissection
the current workflow

- run [a single python script](#) to retrieve the auto-generated subtitles from scar's [main channel](https://www.youtube.com/@GoodTimesWithScar) and [vods channel](https://www.youtube.com/@goodvodswithscar) using [yt-dlp](#)
- the same script runs through [common word replacements](#) to try and clean up the auto-generated slop (and fix hermit name misspellings)
- run [a single node script](#) to generate a temporary .jsonl file
- read the [overall statistics](#) and chunk the index into <25mb .json files.


previous/pre-alpha workflow 

- download the entire [hermits.fyi subtitle dump](https://github.com/etho-fyi/hermits-fyi?tab=readme-ov-file#get-the-subtitles-and-build-a-search-engine-yourself)
- run a python script through the compressed file to single out scar's videos
- decompress only the files found
- run a python script to convert the .pickle files into a single huge .jsonl file
- run the previous version of the [index building script](#) to chunk the index into <25mb .json files

this workflow *does* work but relies too heavily on the absolutely monstrous subtitle dump that only updates once a day and includes *all* of the hermits' subtitle info. while this workflow has been deprecated and i no longer use the hermits.fyi source i still owe them BIG TIME and highly recommend using this starting method if you're looking to learn how to make a similar project.

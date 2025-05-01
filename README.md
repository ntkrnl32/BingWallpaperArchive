# BingWallpaperArchive

[![Bing Wallpaper Scraper](https://www.bing.com/sa/simg/facebook_sharing_3.png)](https://github.com/NT-AUTHORITY/BingWallpaperArchive/actions/workflows/wallpaper.yml)

An automated archive of Bing's daily wallpapers from multiple regions around the world. Started on May 1, 2025.

## Overview

This project automatically collects and archives the daily wallpapers from Bing's homepage across different regions. It uses GitHub Actions to run a daily workflow that fetches the latest wallpapers, stores them in an organized directory structure, and maintains metadata about each image.

## Features

- **Daily Collection**: Automatically fetches new wallpapers every day at midnight UTC
- **Multi-Region Support**: Currently archives wallpapers from 5 regions:
  - United States (en-US)
  - China (zh-CN)
  - Japan (ja-JP)
  - France (fr-FR)
  - Germany (de-DE)
- **Metadata Storage**: Preserves image titles, copyright information, and descriptions
- **Sitemap Generation**: Automatically generates a sitemap.xml for all archived images
- **JSON API**: Provides a wallpapers.json file with metadata for all images

## Directory Structure

```
BingWallpaperArchive/
├── .github/workflows/   # GitHub Actions workflow configuration
├── metadata/            # Metadata files for each workflow run
├── wallpapers/          # The archived wallpaper images
│   ├── en-US/           # United States region wallpapers
│   ├── zh-CN/           # China region wallpapers
│   ├── ja-JP/           # Japan region wallpapers
│   ├── fr-FR/           # France region wallpapers
│   └── de-DE/           # Germany region wallpapers
├── sitemap.xml          # Sitemap of all wallpaper images
└── wallpapers.json      # JSON file with metadata for all images
```

## Image Naming Convention

Images are stored with the following naming pattern:
```
wallpapers/{region-code}/{YYYY-MM-DD}.jpg
```

For example: `wallpapers/en-US/2025-05-01.jpg`

## Metadata Format

The `wallpapers.json` file contains an array of objects with the following structure:

```json
{
  "url": "/en-US/2025-05-01.jpg",
  "title": "A fragrant tradition",
  "copyright": "Plumeria flowers, Hawaii (© Miranda Jans/Getty Images)",
  "region_code": "en-US",
  "description": "",
  "lastmod": "2025-05-01"
}
```

## How It Works

1. A GitHub Actions workflow runs daily at midnight UTC
2. The workflow fetches the current wallpaper from each configured region
3. Images are saved in the appropriate regional directory with the current date as filename
4. Metadata is extracted and stored
5. Sitemap.xml and wallpapers.json are updated
6. All changes are committed and pushed to the repository

## Usage

### Accessing Images

All images are stored in the repository and can be accessed directly via GitHub or through a web server hosting this repository.

### Using the JSON API

The `wallpapers.json` file provides a simple API to access metadata for all archived images. This can be used to build applications or websites that showcase the wallpaper collection.

### Manual Trigger

The workflow can also be triggered manually from the GitHub Actions tab if needed.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- All wallpaper images are copyright of their respective owners as noted in the metadata
- This project is not affiliated with Microsoft or Bing

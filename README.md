# download2release
Download File by URL & Create Release

## Usage

```yaml
name: Test Download
on:
  repository_dispatch:
  workflow_dispatch:
    inputs:
      url:
        description: 'file url'
        required: true
        default: ''
      file_name:
        description: 'file name'
        required: false
        default: ''
jobs:
  Test:
    runs-on: ubuntu-latest
    steps:
      - name: download
        uses: HalfCoke/download2release@v1
        with:
          GITHUB_TOKEN: ${{ secrets.TOKEN }}
          DOWNLOAD_URL: ${{ github.event.inputs.url }}
          FILE_NAME: ${{ github.event.inputs.file_name }}

```

## Parameters

### GITHUB_TOKEN:

Required: true

Description: 'use this to create release'

### DOWNLOAD_URL:

Required: true

Description: 'The download url for file which you want to download'

### FILE_NAME:

Required: false

Description: 'The file name you want to rename for download file'
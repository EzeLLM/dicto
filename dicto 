#!/bin/bash

# Check if a word is provided
if [ $# -eq 0 ]; then
    echo "Usage: $0 <word>"
    exit 1
fi

# The word to look up
word="$1"

# Use curl to fetch the definition from the Free Dictionary API
result=$(curl -s "https://api.dictionaryapi.dev/api/v2/entries/en/$word")

# Check if the word was found
if [[ $result == *"title\":\"No Definitions Found"* ]]; then
    echo "No definition found for '$word'"
    exit 1
fi

# Extract and print the definitions
echo "Definitions for '$word':"
echo "$result" | jq -r '.[0].meanings[] | "- (" + .partOfSpeech + ") " + .definitions[0].definition' 2>/dev/null

# If jq is not installed or fails, use a simpler grep-based approach
if [ $? -ne 0 ]; then
    echo "$result" | grep -oP '(?<="definition":")[^"]*' | sed 's/^/- /'
fi
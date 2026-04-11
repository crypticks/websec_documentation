## Symptom:
Requests contain file paths

## Solutions:
1. Modify the path directly as ../../path_needed
2. If that doesn't work, try raw /path
3. Try ..././..././..././path ( this should make it strip only the inner ../s, and keep the outer ones )
4. URL encode the path, maybe even double encode. 
5. Sometimes the app needs the filepath to start with the expected folder ( /var/www/images/ ). So then concatenate the traversal payload with this.
6. The proper file extension may be expected. Try adding %00 just before a ".pdf" or ".png"


## Prevention
1. Use whitelists for what exactly is permitted from user
2. Avoid taking user inputs altogether if possible. Most code can be reworked for this.
3. Verify that the loaded file is a file that is in the expected location, and not something out of scope
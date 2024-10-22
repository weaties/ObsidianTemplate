There are two main other tools that really make this system really work well.

- [CleanShot](https://cleanshot.com) - Very much worth the $30 they charge for a lifetime license ^a9d489
- [Raycast](raycast.com) This is a super power tool - I _highly_ recommend spending a quick morning going deep on learning how to use this tool.


# Setting up these tools
## Cleanshot
no special setup is required for cleanshot to use this Vault

## Raycast

^0db523

We are going to setup one automation to be able to turn a list of people into links to people.

1. Create the file `attendees.sh` in a script directory on your machine, and make it [executable](https://support.apple.com/guide/terminal/make-a-file-executable-apdd100908f-06b3-4e63-8a87-32e71241bab4/mac)
2. with this as the contents
``` sh

#!/bin/bash

# Required parameters:
# @raycast.schemaVersion 1
# @raycast.title attendees
# @raycast.mode compact

# Optional parameters:
# @raycast.icon 🤖

# Documentation:
# @raycast.description parse atendees from zoom to obsidian links

echo "$(pbpaste)" | tr '\n' '`' \
| sed s/\`\`/\`/g \
| tr '`' '\n' \
| sed s/\(Host\)//ig \
| sed s/\(Co-host\)//ig \
| sed s/\(he.him.his\)//ig \
| sed s/\(he\)//ig \
| sed s/\(he.him.his\)//ig \
| sed s/\(she.her\)//ig \
| sed s/\(,\)//ig \
| while read line;do echo "[[$line]]";done \
| sort \
| uniq \
| pbcopy

```

3. In the [Raycast Settings](https://manual.raycast.com/preferences) go to extensions, and add the directory that you saved `attendees.sh` to the list of directories that raycast looks for attendees in. ![[CleanShot 2024-10-21 at 16.17.38.png]]
4. (optional but helpful) Give your `attendees` command a keyboard alias.


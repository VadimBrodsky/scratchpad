---
layout: post
title: Rename File Extension of All Files in a Folder
category: snippet
tags: bash
---

```bash
for i in *.txt; do
    mv "$i" "${i%.*}.xml"
done
```

via -- [Superuser](http://superuser.com/a/409812)
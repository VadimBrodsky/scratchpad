---
title: "Working With Files: FileUtils Class" 
layout: post
category: ruby
date: 2015-03-05 21:46:04 
---

- Ruby Standard library: `require fileutils`
- `cp`, `copy`
- `mv`, `move`
- `rm`, `remove`
- `cd`, `chmod`, `chown`, `pwd`, `ln`, `touch`, `mkdir`, `rmdir`

```ruby
File.rename('file_to_rename.txt', 'new_file_name.txt')
File.delete('new_file_name.txt')
```

```ruby
require fileutils 		# Ruby built-in library
FileUtils.copy('file_to_copy.txt', 'copied.txt')
```
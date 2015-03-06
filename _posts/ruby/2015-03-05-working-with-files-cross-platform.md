---
title: "Working With Files: Cross Platform" 
layout: post
category: ruby
date: 2015-03-05 21:41:52 
---

- File path separators
  - Unix, Linux, Mac path separator: `/`
  - Windows path separator: `\`
  - The `File.join()` method avoids the OS differences.
- File permissions
  - `chmod`: change permissions on unix.
  - `chown`: change owner on unix.

```ruby
File.join('path', 'to', 'folder', 'file.rb')

# Starting with a blank '' will create a path
File.join('', 'Users', 'vadim', 'Desktop', 'rube_files')
```
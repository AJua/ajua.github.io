---
title: 移除 git submodule
category: Dev
tags: [git]
---

```
mv asubmodule asubmodule_tmp
git submodule deinit asubmodule    
git rm asubmodule
# Note: asubmodule (no trailing slash)
# or, if you want to leave it in your working tree
git rm --cached asubmodule
mv asubmodule_tmp asubmodule
rm -rf .git/modules/asubmodule
```

[how-do-i-remove-a-submodule]( http://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule )

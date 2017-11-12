---
title: 從 json 檔案讀取某一性質
category: Dev
tags: [bash]
---

<!--more-->
### 使用方式

<code>[VAR]=readJson [filename] [key] || exit [code]</code> 其中:

1. <code>[VAR]</code> is a bash variable where you want to assign the result string
2. <code>[filename]</code> is the source JSON file
3. <code>[key]</code> is the identifier
4. <code>[code]</code> is the non-zero error code returned if the value is not found

```bash
function readJson {  
    UNAMESTR=`uname`
        if [[ "$UNAMESTR" == 'Linux' ]]; then
            SED_EXTENDED='-r'
        elif [[ "$UNAMESTR" == 'Darwin' ]]; then
            SED_EXTENDED='-E'
        fi; 

    VALUE=`grep -m 1 "\"${2}\"" ${1} | sed ${SED_EXTENDED} 's/^ *//;s/.*: *"//;s/",?//'`

    if [ ! "$VALUE" ]; then
        echo "Error: Cannot find \"${2}\" in ${1}" >&2;
        exit 1;
    else
        echo $VALUE ;
    fi; 
}
```

參考 [read-json-value-in-bash](http://dailyraisin.com/read-json-value-in-bash/)

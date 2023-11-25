# Description

True or False , htmlentities ( convert special characters to its html entity ) can't be exploited to run XSS payload ?

# Solution

`False`



To prevent from XSS attacks, you just have to check and validate properly all user inputted data that you plan on using and dont allow html or javascript code to be inserted from that form.

Or you can you Use htmlspecialchars() to convert HTML characters into HTML entities. So characters like <> that mark the beginning/end of a tag are turned into html entities and you can use strip_tags() to only allow some tags as the function does not strip out harmful attributes like the onclick or onload.

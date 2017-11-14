Today we’re talking about [subversion](http://subversion.tigris.org/). About how to accomplish a migration from [subversion](http://subversion.tigris.org/) to [git](http://git-scm.com/). Before doing such an import, some preparation is needed. Git needs to know which authors are relevant for your import and how to relate the git checkins to these authors on import.

One thing to prepare is a `authors.txt` file containing all authors that have checked in version in your subversion repository. This file should look like this:
```
rob = Rob Dude <dude@example.com>
someguy = Some Guy <someone@example.com>
```
To archive this layout automagically, just do a subversion log task and parse the required names:
```bash
authors=$(svn log -q | grep -e '^r' | awk 'BEGIN { FS = "|" } ; { print $2 }' | sort | uniq)
for author in ${authors}; do
  echo "${author} = ${author} <${author}@LOCALHOST.NET>" >> authors.txt;
done
```
After executing this handy script on your console the file is created based on your subversion checkin history. Optional you need to edit the file to use the correct emails (`@LOCALHOST.NET`).

Reference:
- [Migrating to git](http://technicalpickles.com/posts/creating-a-svn-authorsfile-when-migrating-from-subversion-to-git/ "Migrating to git") 



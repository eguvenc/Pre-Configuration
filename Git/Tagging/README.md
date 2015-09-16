
## Version Tagging

-----

#### Listing Your Tags

```
$ git tag

v0.1
v1.3
```

#### Creating Tags

```
$ git tag -a v1.4 -m 'my version 1.4'
$ git tag

v0.1
v1.3
v1.4
```

#### Showing Version Changes

```
$ git show v1.4

tag v1.4
Tagger: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Feb 9 14:45:11 2009 -0800

my version 1.4

commit 15027957951b64cf874c3557a0f3547bd83b3ff6
Merge: 4a447f7... a6b4c97...
```

#### Releasing new Version

```
$ git push origin v1.5

Counting objects: 50, done.
Compressing objects: 100% (38/38), done.
Writing objects: 100% (44/44), 4.56 KiB, done.
Total 44 (delta 18), reused 8 (delta 1)
To git@github.com:schacon/simplegit.git
* [new tag]         v1.5 -> v1.5
```
#### Deleting a tag

```
git tag -d v1.5
git push origin :refs/tags/v1.5
```

#### Reverting to a previous version

```
git checkout v1.4

HEAD is now at 560cc31... updates
```

### Tagging Later

You can also tag commits after you’ve moved past them.

Now, suppose you forgot to tag the project at v1.2, which was at the "updated rakefile" commit. You can add it after the fact. To tag that commit, you specify the commit checksum (or part of it) at the end of the command:

```
$ git tag -a v1.2 -m 'version 1.2' 9fceb02
```

### Listing Your Commit History:

```
 $ git log --pretty=oneline

15027957951b64cf874c3557a0f3547bd83b3ff6 Merge branch 'experiment'
a6b4c97498bd301d84096da251c98a07c7723e65 beginning write support
0d52aaab4479697da7686c15f77a3d64d9165190 one more thing
6d52a271eda8725415634dd79daabbc4d9b6008e Merge branch 'experiment'
0b7434d86859cc7b8c3d5e1dddfed66ff742fcbc added a commit function
4682c3261057305bdd616e23b64b0857d832627b added a todo file
166ae0c4d3f420721acbb115cc33848dfcc2121a started write support
9fceb02d0ae598e95dc970b74767f19372d61af8 updated rakefile
964f16d36dfccde844893cac5b347e7b3d44abbc commit the todo
8a5cbc430f1a9c3d00faaeffd07798508422908a updated readme
```

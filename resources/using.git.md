Deleting a tag on a remote (and locally).


You just need to push an 'empty' reference to the remote tag name:

git push origin :tagname
Or, more expressively, use the --delete option (or -d if your git version is older than 1.8.0):

git push --delete origin tagname
If you also need to delete the local tag, use:

git tag --delete tagname
Background

Pushing a branch, tag, or other ref to a remote repository involves specifying "push where, what source, what destination?"

git push where-to-push source-ref:destination-ref
A real world example where you push your master branch to the origin's master branch is:

git push origin refs/heads/master:refs/heads/master
Which because of default paths, can be shortened to:

git push origin master:master
Tags work the same way:

git push origin refs/tags/release-1.0:refs/tags/release-1.0
Which can also be shortened to:

git push origin release-1.0:release-1.0
By omitting the source ref (the part before the colon), you push 'nothing' to the destination, deleting the ref on the remote end.

## tags

*Create an anannotated tag:*
```
$ git tag -a TAG_NAME -m "Published by XYZ for ABC on EFG date." COMMIT_CHECKSUM_VALUE
```

*List tags:*
```
$ git tag
TAG_NAME
```

*See detailed tag info:*
```
$ git show TAG_NAME
tag TAG_NAME
Tagger: GITHUB_ACCOUNT <EMAIL>
...(etc)...
```

*Full tag creation and verification example:*
```
$ git tag -a sub.DelRayPublishing -m "Submitted to Del Ray Publishing." 9fceb02

$ git tag
sub.DelRayPublishing

$ git show sub.DelRayPublishing
tag sub.DelRayPublishing
Tagger: John Gentle <taoteg@gmail.com>
Date:   Mon Feb 9 15:32:16 2009 -0800

version 1.2
commit 9fceb02d0ae598e95dc970b74767f19372d61af8
Author: John Gentle <taoteg@gmail.com>
Date:   Sun Apr 27 20:43:35 2008 -0700

    updated README
...
```

Once the tag is generated for the commit, be sure and enter it into the project.structure.md files under the correct module (reviews/reviews.md, submissions/submissions.md, publications/publications.md) so that you can keep track of it.

However, if you are more comfortable with the command line, you can always look at using git commands: ```$ git tag```.

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

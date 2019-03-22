# git_tag_test
play with git tags

Commands to create this rev history:
```
git init
echo "first feature" > source_code.txt`
git add source_code.txt 
git commit -a -m "first commit"
echo "first feature now working" > source_code.txt
git commit -a
git tag -m "first dev release" dev_1
echo "second feature in dev" >> source_code.txt
git commit -a -m "second feature 1"
echo "second feature appears to work" >> source_code.txt
git commit -a -m "second feature 2"
git push --set-upstream origin master
git push --tags
git checkout dev_1
```
At this point we are in "detached HEAD" state

```
git tag -m "first QA release" qa_1
git push --tags
```
...but we can still create and push new tags that point to the same commit we checked out. `qa_1` is exactly the same code as `dev_1`

```
git checkout master
```
This returns us to a normal non-detached HEAD state and development can continue.

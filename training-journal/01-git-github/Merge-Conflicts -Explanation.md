
## Types of Merges

### 1. FastForward Merge

![Merging a new feature into the main branch when main doesn't have the new changes ](image.png)
"Margin.html"  this is the new feature was addded to the main branch
 

 ### git merge --abort  - Help to doing the abort the last merge

## TAGS

The problem they solve

- Commits are identified by hashes like a3f9c2e. Nobody remembers those. If you shipped your app to users today, how do you later say "the code as it was in that release"?
git tag v1.0                      # lightweight tag
git tag -a v1.0 -m "First release"   # annotated tag (preferred)
git tag                           # list tags
git push origin v1.0              # push one tag
git push origin --tags            # push all tags
git tag -d v1.0                   # delete locally
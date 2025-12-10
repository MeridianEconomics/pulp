# HOW TO UPGRADE MERGE NEW CHANGS IN UPSTREAM

```
git remote -v
git branch
git fetch upstream
git switch floating-patches 
```

Copy the hash of our update:
```
git log
```
In our case this is f162a55dfdf466a49dc9ea98c3e6aee68dcc28a7

Check out the latest version from master:
```
git tag # To get the latest version - You don't actually need this, but it is good to check

git merge upstream/master
```
If there are no merge conflicts, cherry pick using:
```
git cherry-pick f162a55dfdf466a49dc9ea98c3e6aee68dcc28a7
```

If there are merge conflicts, resolve using the editor.
Add any merged files using
```
git add pulp/apis/__init__.py
```

Commit to origin
```
git commit -m<Merge Message>
```

Optionally merge the master branch as well
```
git switch master
git merge upstream/master
git commit -m<Merge Message>
```

push to Meridian Economics 
```
git push
```

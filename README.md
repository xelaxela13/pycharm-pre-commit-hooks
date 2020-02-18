### Pre-commit hooks for PyCharm

1. Settings -> Plugins -> Pre Commit Hook Plugin - install
2. Create a file named pre-commit-hook.sh or pre-commit-hook.bat for Windows, in your project root, exit with non-zero code to 'fail' the commit.
3. chmod a+x pre-commit-hook.sh
4. Settings -> Tools -> Pre Commit Hook
5. Put a path to your script
```
cd ~/PycharmProjects/your-project-folder
docker exec completecase flake8 `git diff HEAD --name-only|grep ".py" || echo "path-to-folder-where-git-init"` || exit 1
``` 

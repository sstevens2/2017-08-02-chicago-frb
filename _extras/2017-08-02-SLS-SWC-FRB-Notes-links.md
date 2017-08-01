## Sarah Stevens' notes for teaching 

### Socrative setup
Go to the link below and enter the following room name -  
[https://b.socrative.com/login/student/](https://b.socrative.com/login/student/)
Room Name: 6HJLONFT  


### NPP Setup
Setup for opening npp from the shell (check first for path variation, see below) to add to .bash_profile:
```
function npp {
    "C:\Program Files (x86)\Notepad++\notepad++.exe" -multiInst -notabbar -nosession -noPlugin "$*";
}
export -f npp;
```
Path variation will probably be the following for 64-bit:
```
function npp {
    "C:\Program Files\Notepad++\notepad++.exe" -multiInst -notabbar -nosession -noPlugin "$*";
}
export -f npp;
```



### Notes for branching

So far we have always been working in one line on our tree (the master branch) but you may want to develop some code but keep your 'master' branch intact.  Lets imagine you are going to write some code that will analyze your files and you don't know if python or bash will be faster.

Make and switch to branch for python code... add some python code...
```
git branch pythondev
git branch
git checkout pythondev
```

 add some python code...
```
git touch code.py
git add code.py
git commit -m "added and tested code.py"
ls
git log --oneline
```

Switch back to master - show that master doesn't have the python code in it...
```
git checkout master
ls
git log --oneline
```

Make and switch to new branch for bash code in one step.. 
```
git checkout -b bashdev
ls
git log --oneline
```

add some fake bash code...
```
touch code.sh
git add code.sh
git commit -m "added and tested code.py"
ls
git log --oneline
```

Switch back to master and merge python version (explain how merging works)
```
git checkout master
git merge pythondev
```

Delete other branches
```
git branch -d bashdev # should get warning
git branch -D bashdev
git branch -d pythondev 
```



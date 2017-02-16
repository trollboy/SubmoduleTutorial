# SubModule Tutorial 
- Step one, checking out this repo, as you have already done.
- You will see that we have a submodule called sampleSubmodule, it contains a file called sample with the number 5 in it.
- The repo sampleSubmodule is currently at 10, so you wish to update it!  you run
```sh
$ git submodule update --init --recursive
```



- Nothing happens.  WTF HAX!!1!!
- No this is expected behavior.  The submodule is pinned to this repo at that specific commit. This keeps people from version jumping.
- Go into the submodule and update manually to the required version (replace `master` with the branch you're wanting):
```sh
$ cd sampleSubmodule/
$ git pull origin master
```

- You will now see that you have the current subModule, but a `git status` shows that `sampleSubmodule` has pending commits.  Why the change? That's because in doing your pull you've updated the official version point for the submodule in this repo.  You can commit and push that:
- 
```sh 
$ git commit sampleSubmodule -m"Updating version!"
```
- Now your ~~co-conspirators~~ collaborators can issue the `git submodule update --init --recursive` and update to the latest approved version.
- To run through this tutorial yourself `fork` this repo or if we know eachother IRL ping me for write access.

Thanks!

 


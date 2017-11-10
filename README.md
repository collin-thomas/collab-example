collaboration tutorial
=======

user 1
------
 1. create repo
 2. mkdir collab-example
 3. cd collab-example
 4. echo "# collab-example" >> README.md
 5. git init
 6. git add README.md
 7. git commit -m "first commit"
 8. git remote add origin https://github.com/nillocftw/collab-example.git
 9. git push origin master
 10. touch index.html
 11. echo "hello world" >> index.html
 12. git commit -am 'added index'
 13. git push origin master

user 2
------
 1. git clone https://github.com/nillocftw/collab-example.git
 2. echo "what is up" >> index.html
 3. git commit -am 'modified index'
 4. git push origin master

user 1
------
 1. git pull origin master
 2. cat index.html

---

commiting changes when repo is out of sync
=======

To start the Remote repo, User1 local repo, and User2 local repo are all up to date.

User1 makes changes to readme.md. User1 then commits and pushes it to the Remote repo.

User2 makes changed to index.html.  User then commits and pushes it to the repo.  However, User2 receives an error when attemping to push.  This is because User2 does not have the updated version of readme.md that User1 pushed earlier.

User2 then does a `git pull origin master`. User2 now has the updated readme.md.  Pulling will not overwrite index.html as the only changes were in readme.md.

 Next User2 runs the `git push origin master` again.  This time the command succeeds. 

At this point the Remote repo has the most up to date version of both readme.md and index.html.

User1 now has to get the most up to date version of index.html.  So User1 runs `git pull origin master` and now has an up to date local repo.

The Remote repo, User1 local repo, and User2 local repo are all up to date.

---

merging scenario
=======

To start the Remote repo, User1 local repo, and User2 local repo are all up to date.

Then User1 makes a change to index.html. User1 then commits the change and pushes it to the Remote repo.

Next User2 makes a change to index.html, but the local copy User2 is modifiying is older than the one that is now on the Remote repo.

User2 commits the change.  Then User2 attempts to push the change, but receives an error saying that it has been "rejected". 

User2 needs to merge their changes.

So User2 runs `git pull origin master` and is then prompted to enter a message to explain why they need to merge.  On a mac/unix/linux this opens vi editor.  Add some text and then do `:wq` to save an exit.

Finally User2 runs `git push origin master` again and the command succeeds.  

The changes have been succesfully merged.

---

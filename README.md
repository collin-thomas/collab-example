collab-example
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
 
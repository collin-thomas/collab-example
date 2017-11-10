# collab-example

# user 1
create repo
mkdir collab-example
cd collab-example/
echo "# collab-example" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/nillocftw/collab-example.git
git push origin master
touch index.html
echo "hello world" >> index.html
git commit -am 'added index'
git push origin master

# user 2
git clone https://github.com/nillocftw/collab-example.git
echo "what is up" >> index.html
git commit -am 'modified index'
git push origin master

# user 1
git pull origin master
cat index.html
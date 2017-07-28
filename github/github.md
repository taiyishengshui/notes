yum install git -y

git init
ssh -T git@github.com

ssh-keygen -t rsa -C "githubaccount"
cat /root/.ssh/id_rsa.pub
git clone git@github.com:youtanhuakai/notes.git

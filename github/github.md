yum install git -y

git init
ssh -T git@github.com

ssh-keygen -t rsa -C "githubaccount"  
cat /root/.ssh/id_rsa.pub  
git clone git@github.com:youtanhuakai/notes.git  
git config --global user.email "email"  
git config --global user.name "githubname"  
误删除找回  
git status
git checkout -- 文件夹/文件    
如有提示错误  
git reset HEAD 文件夹/文件  
git status  
git checkout -- 文件夹/文件  
git status  
ls  

删除暂存区的文件  
git rm 文件名 
删除工作区的文件  
rm 文件名  
同时删除工作区和暂存区的文件  
git rm -f 文件名 
产出暂存区的文件，不删除工作区的文件  
git rm --cached 文件名  
恢复文件    
git log  
git checkout id 文件名 
将所有文件恢复到某个版本  
git reset --hard id
恢复到上一个把版本
git reset --hard HEAD^  
查看恢复记录  
git reflog  

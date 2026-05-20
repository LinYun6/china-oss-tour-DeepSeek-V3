wsl  
cd /  
cd mnt/d/学校教材/开源软件的开发和利用  
git clone https://github.com/deepseek-ai/DeepSeek-V3.git  
cd DeepSeek-V3  
git log --oneline | wc -l  
git log --reverse --oneline | head -5   
git log --format="%b" | grep -i "Co-authored-by:" | sort -u  
git show c8087bd 
git shortlog -sn | head -15
du -sh .git  
ls -la  
git log --since="6 months ago" --oneline | wc -l  
git log --grep="fix" --oneline | head -10  
git show adecc0e  
git show adecc0e --stat
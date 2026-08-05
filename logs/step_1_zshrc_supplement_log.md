**grep -n "interactivecomments" ~/.zshrc**  
**echo 'setopt interactivecomments' >> ~/.zshrc**  
**source ~/.zshrc**  
**grep -n "interactivecomments" ~/.zshrc**  
**setopt | grep interactivecomments**  
**echo hello   # 인라인 주석 테스트**  
**exit**  
  
22:setopt interactivecomments  
23:setopt interactivecomments  
22:setopt interactivecomments  
23:setopt interactivecomments  
24:setopt interactivecomments  
interactivecomments  
hello  

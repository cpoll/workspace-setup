/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install python3
sudo pip3 install ansible


ansible-playbook --connection=local --inventory localhost, ansible/macbook.yml 

# ubuntu_webserver_flask
#Step 1 — Installing the Components from the Ubuntu Repositories

sudo apt update
sudo apt install python3-pip python3-dev build-essential libssl-dev libffi-dev python3-setuptools

#Step 2 — Creating a Python Virtual Environment

sudo apt install python3-venv

mkdir ~/myproject
cd ~/myproject

python3 -m venv myprojectenv

source myprojectenv/bin/activate

#Step 3 — Setting Up a Flask Application

pip install wheel
pip install uwsgi flask

create ~/myproject/myproject.py

create ~/myproject/wsgi.py

#Step 4 — Configuring uWSGI
deactivate
create ~/myproject/myproject.ini


#Step 5 — Creating a systemd Unit File

#create /etc/systemd/system/myproject.service

sudo systemctl start myproject
sudo systemctl enable myproject

sudo systemctl status myproject

#Step 6 — Configuring Nginx to Proxy Requests

#create /etc/nginx/sites-available/myproject

sudo ln -s /etc/nginx/sites-available/myproject /etc/nginx/sites-enabled

sudo nginx -t
sudo systemctl restart nginx


##Debug

#    sudo less /var/log/nginx/error.log: checks the Nginx error logs.
#    sudo less /var/log/nginx/access.log: checks the Nginx access logs.
#    sudo journalctl -u nginx: checks the Nginx process logs.
#    sudo journalctl -u myproject: checks your Flask app’s uWSGI logs.






A
A
B
mkdir Flask
cd Flask/
mkdir venv
python3 -m venv venv
#activate venv
source venv/bin/activate
#install flask
pip3 install flask

#criar hello.py

export FLASK_APP=hello.py

#instalando nginx.
sudo apt-install nginx

#verificando se está no ar.
sudo systemctl status nginx

#tudo pronto
https://medium.com/swlh/deploy-flask-applications-with-uwsgi-and-nginx-on-ubuntu-18-04-2a47f378c3d2
https://www.digitalocean.com/community/tutorials/how-to-serve-flask-applications-with-uswgi-and-nginx-on-ubuntu-18-04

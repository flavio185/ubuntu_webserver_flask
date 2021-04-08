# ubuntu_webserver_flask
sudo apt install python3-pip
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

# bigbluebutton-html5-translation-2.2.35

Audio sharing
How do you start HTML5 custom code?
fairblue is the BBB variant of the HTML5 client by fairkom with features like

Audio share
Translation
Build and install audioshare client
git pull https://git.fairkom.net/chat/fairblue/meet.git

git checkout translation-2.2.31

cd fairblue/bigbluebutton-html5

curl https://install.meteor.com/ | sh

meteor update --allow-superuser --release 1.8

backup settings.yml

mkdir ~/backup

cp /usr/share/meteor/bundle/programs/server/assets/app/config/settings.yml ~/backup/settings.yml

adjust wsUrl in settings.yml

grep "wsUrl" /usr/share/meteor/bundle/programs/server/assets/app/config/settings.yml

vi private/config/settings.yml

sudo systemctl stop bbb-html5

meteor npm install

METEOR_ALLOW_SUPERUSER meteor build --server-only ~/bbb-install

cd ~/bbb-install

sudo tar -xzvf *.tar.gz -C /usr/share/meteor
the packet is exchanged and can then be systemctl restart bbb-html5restarted with. With bbb-conf --restartthere should be no more problems.

Attention: The old HTML5 client will then no longer be available! (would then have to be rebuilt from the repo)

development
First check whether the html5 client is running

bbb-conf --status

Client will exit with

systemctl stop bbb-html5

The new client is in the bigbluebutton-html5 directory and is started in its own parallel session.

cd bigbluebutton-html5
screen #enter drücken beim Startbild von screen
METEOR_ALLOW_SUPERUSER=1 npm start
Strg a+d to leave the attached screen without ending the screen session

Explanation in the BBB documentation

The only difference I recommend is to open a screen session beforehand with 'screen' and to start it with 'METEOR_ALLOW_SUPERUSER = 1 npm start'.

How do you turn off the test code?
The code for audio sharing runs in a screen session. Only one should be running, screen -ri.e. connect to the session and strg+cterminate the running process with . With Strg a+dread aloud the screen. Then start up systemctl start bbb-html5the standard version again with .

Restart of BBB
Due to the code of the audio sharing it can happen that several meteor sessions want to use the same port after a restart, because both html5 clients are switched on. Therefore, first exit the code and start again after the restart, also pay attention to whether the native client is switched on or start the code again.

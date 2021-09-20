## PeerIQ Dev Ops Candidate: Jeremy Donson

#### Links + References
- [Assignment Repo](https://github.com/peeriq/devops-challenge)
- [Working Forked Repo Branch](https://github.com/jeremy-donson/devops-challenge/tree/jeremy-donson-peeriq-devops-challenge)

#### Local Dev Setup

```
cd ~/repos/_py3-flask/
# Forked https://github.com/peeriq/devops-challenge.git
git clone https://github.com/jeremy-donson/devops-challenge.git  
cd ./devops-challenge


curl -s https://bootstrap.pypa.io/pip/2.7/get-pip.py > get-pip.py; python get-pip.py
pip install tox
tox 
:'
  py27: commands succeeded
ERROR:  py37: InterpreterNotFound: python3.7
ERROR:  py38: InterpreterNotFound: python3.8
'
# docker run -it -v $(pwd):/tmp/app -w /tmp/app --rm painless/tox /bin/bash tox # FAILED

# run mongodb locally at standard port
brew tap mongodb/brew; brew install mongodb-community
mongod --config /usr/local/etc/mongod.conf & # To Shutdown mongodb: $ mongo admin --eval "db.shutdownServer()"
mongosh 
# Connecting to:		mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000
# Using MongoDB:		5.0.2
# Using Mongosh:		1.0.6
# Still need to set up mongosh client access control with two users and one database.
# curl -s https://raw.githubusercontent.com/peeriq/devops-challenge/main/data/restaurant.json > restaurant.json
# mongoimport --db test --collection inventory  --authenticationDatabase admin  --drop --file restaurant.json

echo "alias reload='source ~/.bash_profile'\nalias brewup='brew upgrade; brew update; brew cleanup" >> ~/.bash_profile
source ~/.bash_profile
brew doctor ; brewup
brew install asdf direnv
asdf # Error corrected next line: https://github.com/asdf-vm/asdf/issues/428
echo -e "\n. $(brew --prefix asdf)/asdf.sh" >> ~/.bash_profile; reload; asdf
echo 'legacy_version_file = yes' >> ~/.asdfrc

# https://github.com/danhper/asdf-python
asdf plugin-add python
export ASDF_PYTHON_PATCH_URL="https://github.com/python/cpython/commit/8ea6353.patch?full_index=1"
asdf list all python | grep ^3.
asdf install python 3.8.12
echo 'python 3.8.12' >> ~/.tool-versions
python --version  # Python 3.8.12
/Users/admin/.asdf/installs/python/3.8.12/bin/python -m pip install --upgrade pip
python --version


tox
pip install -r requirements.txt

# https://github.com/mongodb/homebrew-brew

export MONGO_URI=mongodb://YOUR_USERNAME:YOUR_PASSWORD@YOUR_MONGO_HOST:YOUR_MONGO_PORT/YOUR_MONGO_DB_NAME
python app.py
curl localhost:8080/api/v1/restaurant | jq
curl localhost:8080/api/v1/restaurant/55f14313c7447c3da705224b | jq

```

#### Challenge Next Steps
- [x] Add SOLUTIONS.md file.
- [x] Create [draft pull request](https://github.com/jeremy-donson/devops-challenge/tree/jeremy-donson-peeriq-devops-challenge).
- [x] [Install](https://github.com/mongodb/homebrew-brew) mongodb locally at standard port; test local app.
- [ ] Bring up mongodb service , set access control, create users and a database; load database
- [ ] export mongodb connect string
- [ ] Bring up app on python 3.8.x @ 0.0.0.0:8080
- [ ] Fix API as instructed.
- [ ] Show API fixed.
- [ ] Dockerize app components
- [ ] Docker compose file
- [ ] Deploy to k8s
- [ ] Then we might return to the varied python versions?

---


- [!!] Due to python 3.9.x installed locally, tox 3.x tests failed.  Venv did not resolve.
- [ ] Resolution: [asdf]() and [direnv](https://direnv.net/)
- [ ] Mongodb: access control, dbadmin, restaurants; load; count; select; insert
- [ ] Dockerize App
- [ ] Dockerize Database + Create App user + Load Data
- [ ] Docker Compose
- [ ] API returns json object instead of json array.
- [ ] Update tox test: https://www.geeksforgeeks.org/how-to-return-a-json-object-from-a-python-function/
- [ ] Github Actions => heroku?gitpod?gce?gke
- [ ] Deploy Using Helm + kubectl
- [ ] Stern to tail pod logs

- [ ] Create pull request + email url to Zvika.
- [ ] Do we prefer python3?
- [ ] Several new python tools@play: asdf, direnv, pipenv, poetry, pipx, other?
  - Several mentioned here: https://towardsdatascience.com/packaging-in-python-tools-and-formats-743ead5f39ee
  - And here: https://www.jwillikers.com/manage-python-dependencies


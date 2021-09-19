## PeerIQ Dev Ops Candidate: Jeremy Donson

#### Links + References
- [Assignment Repo](https://github.com/peeriq/devops-challenge)
- [Working Forked Repo Branch](https://github.com/jeremy-donson/devops-challenge/tree/jeremy-donson-peeriq-devops-challenge)
- [MongoDB Reference](https://www.digitalocean.com/community/tutorials/how-to-set-up-flask-with-mongodb-and-docker)
- [Heroku Flask Mongo Reference](https://github.com/alexeyza/startup-programming/blob/master/past%20semesters/fall%202014/resources/tutorials/heroku%20python%20with%20flask%20mongodb%20shoutout.md)

#### Local Dev Setup
```
git clone https://github.com/peeriq/devops-challenge.git
cd ./devops-challenge
pip install tox
tox
# docker run -it -v $(pwd):/tmp/app -w /tmp/app --rm painless/tox /bin/bash tox

# run mongodb locally at standard port

virtualenv -p python3 .venv
source .venv/bin/activate
pip install -r requirements.txt
export MONGO_URI=mongodb://YOUR_USERNAME:YOUR_PASSWORD@YOUR_MONGO_HOST:YOUR_MONGO_PORT/YOUR_MONGO_DB_NAME
python app.py
curl localhost:8080/api/v1/restaurant | jq
curl localhost:8080/api/v1/restaurant/55f14313c7447c3da705224b | jq

```

#### Challenge Steps
- [x] Add SOLUTIONS.md file.
- [ ] Create sample pull request.
- [ ] Run mongodb locally at standard port; test local app.
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


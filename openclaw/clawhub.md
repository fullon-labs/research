# install clawhub
```bash
dex -u root openclaw-gw bash
npm i -g clawhub
```

# log into clawhub

1. register at clawhub.ai with github oAuth
1. get a login token from clawhub.ai
1. execute the following inside openclaw-gw container
```bash
token=XXXXX
clawhub login --token $token
```
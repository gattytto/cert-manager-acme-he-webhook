# Cert-Manager 

Let's Encrypt DNS-01 challenge solver

for Hurricane Electric free dynamic dns service

Needed .yaml files are in _out folder of this repository.

Dockerfile can be used to build the image in quay/docker-hub, etc...
once built and loaded, the image field is to be edited [here](https://github.com/gattytto/cert-manager-acme-he-webhook/blob/efabef18c815d6193929e80b26cba5ddba41ba93/_out/rendered-manifest.yaml#L215)

Customize ddnskey (obtained from ha.net web ui), mail and dnszones fields in the clusterissuer.yaml before applying, 
same goes for letsencrypt fields like mail and server (for testing with staging servers)

I have added a wait statement in the code because he.net ratelimits requests. 

TODO: add code to delete the challenge dns TXT records from the domain (they are just blanked now)

TODO2: create an operator to automate the ddnskey generation for domains, no api for this available.




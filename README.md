Hello!

Here is the result of my test task. Let me explain the way I went.
I used docker-compose for running a single PolkaDot node and join it to the public Kusama network.
I didn't use exporters from the description of the task for scrape metrics from node because I've found that a PolkaDot instance can export its metrics itself.
There is a preconfigured Prometheus and Grafana with visualization of the node metrics as well. 

So, you can find provisioning tools in the ansible directory. Two playbooks there:
 * `provision.yml` will install all required stuff, such as docker and docker-compose, on your Linux system (I tested everything on Ubuntu 18.04 and there is no specific to adopt playbooks for all distros)
 * `polkadot.yml` will run the node with all required environment
I used `localhost` in all playbooks but it could be changed surely. If you got an error about the wrong interpreter than say ansible to use correct python version: `ansible-playbook polkadot.yml -e 'ansible_python_interpreter=/usr/bin/python3'`

When everything will be done, you can find tools to monitor the node there:
* `http://localhost:3000` -- here is Grafana. Default credentials are `admin / admin`
* `http://localhost:9090` -- here is web UI for Prometheus

I'm ready to answer to any questions :) Thank you!
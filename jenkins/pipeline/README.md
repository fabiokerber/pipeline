# Jenkins Oracle

Requirements:

|Tool    |Link|
|-------------|-----------|
|`Vagrant`| https://www.vagrantup.com/
|`VirtualBox`| https://www.virtualbox.org/

## Lab
```sh
$ git clone --branch oracle https://github.com/fabiokerber/Jenkins
$ cd Jenkins/install_oracle
$ vagrant up
```

## Problem - *‘Jenkins’ doesn’t have label ‘docker-host’*

Solution:<br>

- Install Plugins ▶︎ http://192.168.56.10:8080/manage/pluginManager/available
	- Plugin: nodelabelparameter
	- Plugins: Docker, Docker Commons, Docker Pipeline, Docker API
	- Plugins: Kubernetes, Kubernetes Client API, Kubernetes CLI, Kubernetes :: Pipeline :: DevOps Steps
- Allow Agents ▶︎ http://192.168.56.10:8080/manage/configureSecurity/
	- TCP port for inbound agents: Random
	- SSH Server: Random
- Create node ▶︎ http://192.168.56.10:8080/manage/computer/new
	- Name: jenkins-agent
	- Number of executors: 1
	- Remote root directory: /home/vagrant/agent
	- Labels: linux jenkins-agent docker-host
	- Usage: Use this node as much as possible
	- Launch method: Launch agent by connecting it to the controller
- Agent jenkins-agent ▶︎ http://192.168.56.10:8080/manage/computer/jenkins-agent/
	- shell ▶︎ jenkins-agent
		- echo <secret> > secret-file
		- curl -sO http://192.168.56.10:8080/jnlpJars/agent.jar
		- java -jar agent.jar -jnlpUrl http://192.168.56.10:8080/manage/computer/jenkins%2Dagent/jenkins-agent.jnlp -secret @secret-file -workDir "/home/vagrant/agent"
<br>

## Fix - Port Dockerfile
```diff
- Changed "EXPOSE 3306 33060" ▶︎ "EXPOSE 3306"
```

## Problem - Wrong Variable create_developer.template
```diff
- Changed "<PASSOWRD>" ▶︎ "<PASSWORD>"
```

## Problem - ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
```diff
- 
```

**References:**<br>
https://www.youtube.com/watch?v=99DddJiH7lM&t=442s&ab_channel=CloudBeesTV<br>
https://www.jenkins.io/doc/book/managing/nodes/<br>
https://www.jenkins.io/doc/book/pipeline/jenkinsfile/#string-interpolation<br>
https://www.liatrio.com/blog/building-with-docker-using-jenkins-pipelines<br>
https://stackoverflow.com/questions/48182807/jenkins-use-withcredentials-in-global-environment-section<br>

**Vagrant Plugins**<br>
```
$ vagrant plugin install {vagrant-vboxmanage,vagrant-vbguest,vagrant-disksize,vagrant-env,vagrant-reload}
```
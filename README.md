# Storm-Twitter-Hashtags
It's a course project from [Udacity](https://www.udacity.com/course/real-time-analytics-with-apache-storm--ud381). A stream processing pipeline which performs the real time analysis of top hashtags on Twitter, using [Apache Storm](http://storm.apache.org/).

## Requirements
  * [Vagrant](https://www.vagrantup.com/) - virtual environment manager.
  * [Oracle VM VirtualBox](https://www.virtualbox.org/) - general purpose virtualizer .
  * SSH client, such as [PuTTY](http://www.putty.org/)

## Getting Started
  1. Spin up the VM: `vagrant up`
  2. Using SSH client, SSH `vagrant ssh` <br/>
  2.1. `cd ..`
  3. Run the visualization web server <br/>
  3.1. Inside the VM: `cd /vagrant/viz`<br/>
  3.2. `python app.py`
  4. Package the topology <br/>
  4.1. Inside the VM (open new SSH session): `cd /vagrant` <br/>
  4.2. `mvn clean`<br/>
  4.3. `mvn package` - may take a while the first time.<br/>
  5. Execute the packaged topology <br/>
  5.1. Inside the VM: `cd /vagrant` <br/>
  5.2. `storm jar target/storm-twitter-top-hashtags-0.0.1-SNAPSHOT-jar-with-dependencies.jar storm.TopNTweetTopology`
  6. Live generated results at `http://127.0.0.1:5000`.
  7. Shutdown the VM: `vagrant halt`

## Topology 
![topology](https://cloud.githubusercontent.com/assets/16224847/25064079/1ea5124a-21f3-11e7-9708-22b2e3413ecf.png)

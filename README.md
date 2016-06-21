# Setup Traccar in Amazon Web Services

>Traccar is an open source GPS tracking system for various GPS tracking devices. >System supports more than 80 different communication protocols from popular >vendors. It includes web interface to manage tracking devices online.
- https://www.traccar.org/
>Amazon Web Services, is a subsidiary of Amazon.com, which offers a suite of cloud >computing services that make up an on-demand computing platform. These services >operate from 12 geographical regions across the world.

  - https://aws.amazon.com/

It is very easy to setup traccar in AWS:
  - Goto https://aws.amazon.com/ and create a free account!
  - Provide your ATM card details for authentication.
  - Done! now you can visit AWS management console
  - Under Compute click on EC2 (virtual servers in cloud)
  - Select LAUNCH INSTANCE
  - Tick Free tier only option then find Ubuntu Server 14.04 LTS (HVM) 64bit and click on SELECT
  - Click on REVIEW AND LAUNCH option.
  - LAUNCH
  - Create a new key pair.Give a name and download the '.pem' file.
  - LAUNCH INSTANCES
  - VIEW INSTANCES
  - Download PuTTY and PuTTYgen from http://www.putty.org/
  - Run PuTTYgen
  - Select SSH-2 RSA
  - lOAD >allfiles>choose '.pem' file >save private key > yes > give the same name as that of '.pem' file has >save to '.ppk' file.
  - Run PuTTY
  - Goto AWS and copy Public DNS paste it to PuTTY HostName field
  - set port 22 and connection type to SSH
  - from PuTTY Category >connection >SSH>Auth>Browse '.ppk'>open
  - In PuTTY terminal login as: ubuntu
### Traccar Installation Steps

```sh
$ sudo su
$ wget https://github.com/tananaev/traccar/releases/download/v3.1/traccar-linux-64-3.1.zip
$ sudo apt-get install unzip
$ unzip traccar-linux-64-3.1.zip
$ chmod +x traccar.run
$ sudo apt-get update
$ sudo apt-get install openjdk-7-jre
$ sudo ./traccar.run
```
 - Goto AWS management console>EC2>Instances
 - Now you can see your instance details
 - Find >security groups > launch-wizard >Inbound > Edit > Add Rule >
 - http://postimg.org/image/efy8fhdvt
 - https://postimg.org/image/w4pz73pmx
 - custom TCP rule > TCP > 8082 > Anywhere > 0.0.0.0/0
 - custom TCP rule > TCP > 5055 > Anywhere > 0.0.0.0/0
 - https://postimg.org/image/vppy2kcdj/
 ```sh
 $ sudo /opt/traccar/bin/traccar start
 ```
### Access Website at http:// Public IP:8082/
* username: admin
* password: admin

### Install Mobile Client
  - https://www.traccar.org/client/
  - server address 52.221.230.112
  - server port 5055
  - frequency 1
  - start service

### Congratulation :)
Want to contribute? Great! you are heartly welcome :)

Ready to help @
  - https://plus.google.com/u/0/+leoCj
  - https://twitter.com/leoccjj

# couchbase-yii
Couchbase SDK for Yii2 - Use Couchbase in your Yii project

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist couchbase/yii2-couchbase "*"
```

or add

```
"couchbase/yii2-couchbase": "*"
```

to the require section of your `composer.json` file.


Usage
-----


Configure in application config like the following:

<pre>
'components'=>array(
  'couchbase' => array(
  			'class' => 'CCouchbaseConnection',
  			//dsn of one of the nodes, 
 *      //the php client will determine if there are multiple nodes in the cluster
  			'connectionString' => 'couchbase://127.0.0.1',
  			'username' => 'Administrator',
  			'password' => '',
  			'bucketName' => 'default',
  			'bucketPassword' => ''
  		)
</pre>

Instructions to install couchbase server and PHP client on CentOS/Redhat

Install the couchbase php client:
 
<pre>
sudo nano /etc/yum.repos.d/couchbase.repo
</pre>

copy:
<pre> 
[couchbase]
enabled = 1
name = Couchbase package repository
baseurl = get url from http://docs.couchbase.com/developer/c-2.4/download-install.html
gpgcheck = 1
gpgkey = http://packages.couchbase.com/rpm/couchbase-rpm.key
</pre>

save file

<pre> 
yum install libcouchbase2-core 
yum install libcouchbase-devel 
yum install libcouchbase2-bin 
yum install libcouchbase2-libevent
pecl install couchbase
</pre>

Install couchbase-server:
<pre>
wget get url from http://www.couchbase.com/nosql-databases/downloads
sudo rpm --install couchbase-server-enterprise-3.0.2-centos6.x86_64.rpm
</pre>


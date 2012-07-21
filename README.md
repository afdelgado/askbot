Askbot - Q&A forum
===================

This is my own custom instance of askbot using [the askbot source][ask].

  [ask]: https://github.com/ASKBOT/askbot-devel.git

Install
-------

* Clone this repo
* Install [Vagrant][vag]
* Run `vagrant box add lucid32 https://s3.amazonaws.com/chadoh/lucid-with-ruby19.box`
* In your clone of this repo, run `vagrant up`

Running your local dev Askbot in your browser
---------------------------------------------

Vagrant lets you run a virtual machine within your host system; all of the
python & postgres setup has all been done in the vm you downloaded. To tweak
any of this stuff,

    vagrant ssh

This will ssh you into the headless (no GUI) vm. It's set up so that you land
in the '/vagrant' dir on login, which is a shared directory with the askbot
project in your host system.

To start the askbot server, run

    python manage.py runserver [::]:8000

Port 8000 in the vm is forwarded to port 1111 in the host (look in the
Vagrantfile to see how), so now open your browser and visit 'localhost:1111'.

Configuring Askbot
------------------

You can change a lot of settings from the Askbot GUI. Sign in, and since you'll
be the first user on your system, you can then visit 'localhost:1111/settings'
to see what can be configured.

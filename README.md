TwitterBootstrap Plugin for CakePHP2
====================================

About Bootstrap, from Twitter

[Bootstrap, from Twitter](http://twitter.github.com/bootstrap/)

[twitter/bootstrap - GitHub](https://github.com/twitter/bootstrap)

How to install
--------------

	$ cd YOUR_APP
	$ git submodule add git://github.com/slywalker/TwitterBootstrap.git Plugin/TwitterBootstrap
	$ cd Plugin/TwitterBootstrap
	$ git submodule update --init
	$ cd YOUR_APP
	$ cake twitter_bootstrap.init

TwitterBootstrap.init make symlink css and js files in TwitterBootstrap/webroot.

Controller/AppController.php

	<?php
	class AppController extends Controller {
		public $helpers = array(
 			'Session', 'Html', 'Form',
 			'TwitterBootstrap.BootstrapForm', 'TwitterBootstrap.BootstrapSession'
 		);
	}

Usage
-----

Load CSS

	<?php echo $this->Html->css('/twitter_bootstrap/css/bootstrap.min'); ?>

Load JS

	<?php echo $this->Html->script('/twitter_bootstrap/js/bootstrap-alerts.js'); ?>

Output form input as Bootstrap format

	<?php echo $this->BootstrapForm->input('name'); ?>
	<?php echo $this->BootstrapForm->submit('Submit'); ?>

Output SessionHelper::flash as Bootstrap format

	// SomethingsController
	$this->Session->setFlash(__('The something has been saved'), 'default', array('class' => 'success'));
	$this->Session->setFlash(__('The something could not be saved. Please, try again.'), 'default', array('class' => 'error'));

	// View
	<?php echo $this->BootstrapSession->flash(); ?>

Output Paginate as Bootstrap format

	<?php echo $this->element('pagination', array(), array('plugin' => 'TwitterBootstrap')); ?>
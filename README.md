DokuWiki on OpenShift
=========================
DokuWiki is a standards compliant, simple to use Wiki, mainly aimed at creating documentation of any kind. It is targeted at developer teams, workgroups and small companies. It has a simple but powerful syntax which makes sure the datafiles remain readable outside the Wiki and eases the creation of structured texts. All data is stored in plain text files - no database is required.

More information can be found on the official DokuWiki website at http://www.dokuwiki.org

Running on OpenShift
--------------------

Create an account at http://openshift.redhat.com/

Create a PHP application

       rhc-create-app -a dokuwiki -t php-5.3 -l $USERNAME

NOTE: DokuWiki does not require a database, hence there is no need to add additional catridges such as MySQL.

Add this upstream DokuWiki quickstart repo

    cd dokuwiki/php
    rm -rf *
    git remote add upstream -m master git://github.com/stylesen/dokuwiki-openshift-quickstart.git
    git pull -s recursive -X theirs upstream master

Then push the repo upstream to OpenShift

     git push

Your application is up and running at the following URL:

     http://dokuwiki-$yourlogin.rhcloud.com

Running the install script
--------------------------

Soon after installing DokuWiki in OpenShift, next step is to call the installation script. In order to invoke the script visit the following URL:

     http://dokuwiki-$yourlogin.rhcloud.com/install.php

After entering values in the install page and saving it, we should remove the install.php file which is no longer required. Issue the following command in the command line in order to remove the install.php file.

     cd dokuwiki/php
     git rm install.php
     git commit -a -m 'Remove install.php which is no longer required.'
     git push

Now DokuWiki is ready for business and you can visit and edit contents in the following URL:

    http://dokuwiki-$yourlogin.rhcloud.com

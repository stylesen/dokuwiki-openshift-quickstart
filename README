DokuWiki on OpenShift
=========================
DokuWiki is a standards compliant, simple to use Wiki, mainly aimed at creating documentation of any kind. It is targeted at developer teams, workgroups and small companies. It has a simple but powerful syntax which makes sure the datafiles remain readable outside the Wiki and eases the creation of structured texts. All data is stored in plain text files - no database is required.

More information can be found on the official DokuWiki website at http://www.dokuwiki.org

Running on OpenShift
--------------------

Create an account at http://openshift.redhat.com/

Create a PHP application

       rhc app create -a dokuwiki -t php-5.3

NOTE: DokuWiki does not require a database, hence there is no need to add additional catridges such as MySQL.

Add this upstream DokuWiki quickstart repo

    cd dokuwiki
    git remote add upstream -m master git://github.com/stylesen/dokuwiki-openshift-quickstart.git
    git pull -s recursive -X theirs upstream master

Then push the repo upstream to OpenShift

     git push

Configuring DokuWiki
--------------------

Soon after installing DokuWiki in OpenShift, next step is to change the default values provided (the install script is already run for you with some defaults). In order to change the default values, login to the new instance by visiting the following URL:

     http://dokuwiki-$yourlogin.rhcloud.com/doku.php?do=login

     Username:  admin
     Password:  admin

After login, navigate to 'Edit user' page as follows and change the default values (Do not forget to put a new value for 'Password'):

      Admin -> User Manager -> admin -> Edit user

Once you have changed the default values for admin user, save the changes. Re-login with the new credentials (if you have changed them).

Next step is to change default values for DokuWiki site, which could be done by visiting the following URL:

     http://dokuwiki-stylesen.rhcloud.com/doku.php?id=start&do=admin&page=config

Logout, and visit the following URL, where your new DokuWiki site is up and running:

     http://dokuwiki-$yourlogin.rhcloud.com

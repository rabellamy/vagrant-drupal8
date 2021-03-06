# vagrant-drupal8 #

A plain Vagrant setup script to get Drupal 8 up and running quickly.

## Requirements ##

* A Windows, Linux or Macintosh host machine.
    * On Ubuntu Linux, you'll need to `sudo apt-get install nfs-kernel-server`.
    * On Macintosh, you'll need to run the [OSX GCC Installer][osx-gcc-installer] or install [Xcode][xcode] itself.
    * On Windows, you'll have to change the line in the `Vagrantfile` that says

            config.vm.synced_folder "./data/html", "/mnt/www", :nfs => true

      … to …

            config.vm.synced_folder "./data/html", "/mnt/www"

      **Don't commit this change.**
* [VirtualBox v4.2.x][virtualbox].
* [Vagrant v1.2.7][vagrant].

[osx-gcc-installer]: https://github.com/kennethreitz/osx-gcc-installer
[xcode]: https://developer.apple.com/technologies/mac/#xcode
[virtualbox]: https://www.virtualbox.org/
[vagrant]: http://www.vagrantup.com/

## Usage ##

1. Clone the Vagrant setup files onto your computer somewhere:

        git clone --recursive git@github.com:mparker17/vagrant-drupal8.git

2. Change into the directory you just created.

        cd vagrant-drupal8

3. Clone Drupal 8 into the document root.

        git clone --recursive --branch 8.x http://git.drupal.org/project/drupal.git data/html

4. Start Vagrant.

        vagrant up

5. Map `drupal8.dev` to the virtual machine in the host machine's `hosts` file.

    Most of the time, the following line will work:

        127.0.0.1 drupal8.dev

6. Install Drupal by going to `http://drupal8.dev:8080/install.php` in a web browser.

## Notes ##

* The virtual machine document root is mapped to `data/html` in the repository. This git repository ignores changes to that folder.

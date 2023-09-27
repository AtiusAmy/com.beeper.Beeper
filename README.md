Amy's Beeper flatpak project forked with my customizations since they dont respond to pull requests.

*This will download the LATEST Beeper appimage release. If you are running into issues since Beeper is technically still in open beta, refer to upcoming instruction to revert back a version. Will update later.*

To build and install, do the following:

Install flatpak and git

  - run 'sudo "insert package manager command here" install flatpak git'

As NON-ROOT user:
  - Install Flatpak SDK
    - run 'flatpak install org.freedesktop.Sdk'
    - select the option for version 22.08
    - select 'y' to install
  - Install Flatpak Builder
    - run 'flatpak install org.flatpak.Builder'
    - select 'y' to install
  - Make a build directory in your home folder and go to it
    - run 'mkdir /home/$USER/build && cd /home/$USER/build'
  - Download repository
    - run 'git clone https://github.com/vaparetia/com.beeper.Beeper.git'
  - Change into Beeper directory
    - run 'cd com.beeper.Beeper'
  - Build the package and put into local repo
    - run 'flatpak run org.flatpak.Builder --repo=testing-beeper-repo build-dir com.beeper.Beeper.yaml'
  - Add local repo to flatpak (current $USER only; omit '--user' for system-wide installation)
    - run 'flatpak --user remote-add --no-gpg-verify testing-beeper-repo testing-beeper-repo' 
  - Update flatpak appstream to install
    - run 'flatpak build-update-repo testing-beeper-repo'
  - Install app
    - run 'flatpak install beeper'
    - select 'y'
  - Enjoy your application
    - If things were done right, you should be greeted with Beeper's login screen and follow the screens to log into your instance.

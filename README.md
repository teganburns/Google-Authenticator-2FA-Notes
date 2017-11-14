# Google-Authenticator-2FA-Notes
Notes for setting up Google Authenticator




# Prerequisites

_Google Authenticator App_

Android - https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2

iOS - https://itunes.apple.com/us/app/google-authenticator/id388497605




# Instructions

__WARNING__: It is possible that you may become locked out if there are issues during setup. Therefore it is highly suggested that you have the option to physically access the machine you are installing to in the event that you do become locked out.

1) Clone google-authenticator-libpam repo. `git clone https://github.com/google/google-authenticator-libpam.git`

2) Follow build instructions https://github.com/google/google-authenticator-libpam

```shell
./bootstrap.sh
./configure
make
sudo make install
```

3) Add `ChallengeResponseAuthentication yes` to */etc/ssh/sshd_config*

4) Edit */etc/pam.d/sshd*
```
#auth     required  pam_securetty.so     #disable remote root
auth      include   system-remote-login
account   include   system-remote-login
password  include   system-remote-login
session   include   system-remote-login
auth      required  pam_google_authenticator.so
```




# External Resources

Arch Linux Wiki for Google Authenticator : https://wiki.archlinux.org/index.php/Google_Authenticator
Rate Limiting with UFW : https://wiki.archlinux.org/index.php/Uncomplicated_Firewall#Rate_limiting_with_ufw

# Google-Authenticator-2FA-Notes
Notes for setting up Google Authenticator




# Prerequisites

**Google Authenticator App**

Android - https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2

iOS - https://itunes.apple.com/us/app/google-authenticator/id388497605




# Instructions

__WARNING__: It is possible that you may become locked out if there are issues during setup. Therefore it is highly suggested that you have the option to physically access the machine you are installing to in the event that you do become locked out.

1) Clone google-authenticator-libpam repo.
`git clone https://github.com/google/google-authenticator-libpam.git`

2) Build and install. `./bootstrap.sh && ./configure --prefix=/usr && make && sudo make install`

3) Run `google-authenticator` and follow the setup instructions.

4) Add `ChallengeResponseAuthentication yes` to `/etc/ssh/sshd_config`

5) Add `auth      required  pam_google_authenticator.so` to `/etc/pam.d/sshd`




# External Resources

- Arch Linux Wiki for Google Authenticator : https://wiki.archlinux.org/index.php/Google_Authenticator
- Github repository for Google's google-authenticator-libpam : https://github.com/google/google-authenticator-libpam
- Arch Linux Wiki for Secure Shell ( ssh ): https://wiki.archlinux.org/index.php/Secure_Shell
- Arch Linux Wiki for Rate Limiting with UFW : https://wiki.archlinux.org/index.php/Uncomplicated_Firewall#Rate_limiting_with_ufw

# home-server-docker-compose-stack

## Notes

- Install arch/debian
- Install and start docker-compose, tailscale
- Mount hd - create directories if new
- Update hd permissions
- Start containers
- Set up apps

## Setting up drive

`lsblk`

`sudo mkdir -p /mnt/jellydrive`

`sudo mount /dev/{} /mnt/jellydrive`

`sudo blkid /dev/{}`

`sudo nano /etc/fstab`

add line `{UUID}  /mnt/jellydrive  {filesystem}  defaults  0  0
`

`sudo umount /mnt/jellydrive`

`sudo mount -a`

## Jellyfin
[jellyfin](https://jellyfin.org/) networking is a pain if setting up containerized, so i usually just run it bare metal. this has the added benefit of being higher-available than if it were part of the docker stack since it is independent from docker engine failures

## Other stuff

gnome-remote-desktop or krdp is fine for remoting in if not using a window manager. i dont usually use ssh or vnc for this though you could. since this is headless post-setup, i use [dummy hdmi plugs](https://www.amazon.com/Display-Emulator-Compatible-Windows-fit-Headless/dp/B07C4TWZRM?crid=2C5CXUHNZ35JO&dib=eyJ2IjoiMSJ9.V54_l_dy5H-QDQPGm4g640khueKQbTkZHO0pnffKb_eq9xOtVQIOgpZiIPmrj1uW9pdTFqypB44_TZBpDSjXDZLqZ2kJ9X_jLx2uiAd84ZBVjLWiwsQrZ0BbCD4PBMNTc799ON4r7JqR6Fe6FOmcWmrM8XGDzlUPXEHEyRFhmB0CrxbQCb0IJ5wnNZtFxE1yoT42l3L0pkm89qw3sAFyDMLN2b8gnPURdWhKioowxKA.fIqzOfM-9Cw8DBcypT8JjGmeHxJRA91NmLLIXhSj7-g&dib_tag=se&keywords=dummy+hdmi&qid=1762563652&sprefix=dummy+hdmi%2Caps%2C229&sr=8-9) to get dynamic resolutions across multiple devices

if using gnome, the extension "caffeine" is decent for keeping the os from sleeping

docker shouldnt require file sharing (bind mounts) on linux but if running on other operating systems, you have to add file sharing permissions

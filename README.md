# Ansible Role: bluez

Installs bluez.

## Requirements

None.

## Role Variables

    interfaces_config_file: '/etc/network/interfaces'

Interfaces configuration file.

    kernel_bluetooth_download_urL: http://www.kernel.org/pub/linux/bluetooth/

URL to download bluez from.

    bluez_artifact_version: 5.42

bluez artifact version.

    bluez_artifact_name: "bluez-{{ bluez_artifact_version }}.tar.gz"

bluez artifact name.

    bluez_artifact_dir: "bluez-{{ bluez_artifact_version }}"

bluez artifact directory.

    bluez_artifact_download_url: "{{ kernel_bluetooth_download_urL }}/{{ bluez_artifact_name }}"

bluez download URL.

    uninstall_packages:
    - bluez
    - pi-bluetooth

Packages to be uninstalled before bluez installation.

    packages:
    - libusb-dev
    - libdbus-1-dev
    - libglib2.0-dev
    - libudev-dev
    - libical-dev
    - libreadline-dev

Packages to be installed before bluez installation.

    patch_files:
    - 0001-bcm43xx-Add-bcm43xx-3wire-variant.patch
    - 0002-bcm43xx-The-UART-speed-must-be-reset-after-the-firmw.patch
    - 0003-Increase-firmware-load-timeout-to-30s.patch
    - 0004-Move-the-43xx-firmware-into-lib-firmware.patch

List of patch files.

    firmware_files:
    - BCM43430A1.hcd

Firmware file to be installed.

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - { role: interoberlin.bluez }

## License

GPLv3

## Author Information

This role was created in 2016 by [Florian Schwanz](https://interoberlin.de/).

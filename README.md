<p align="center">
  <img src="https://cdn.svgporn.com/logos/php.svg" width="33%" />
</p>

<h1 align="center">Ansible Role for PHP & Composer</h1>

<p>
  <a href="./LICENSE" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge" />
  </a>
</p>

> This repo contains a Linux-distro agnostic Ansible role that installs PHP + Composer + Composer global packages.

## Requirements

- No additional requirements.

## Notes

- ⚠️ There is no way to install certain PHP version using this role. PHP version depends on your Linux distribution. It's the main idea behind the role: rely only on linux distro repositories.
- ⚠️ The role does not change your profile files (`~/.bash_profile`, `~/.zshrc`, `~/.profile`, or `~/.bashrc`). Make sure you have added the following to the profile file:

  ```bash
  export PATH="$PATH:$HOME/.composer/vendor/bin"
  ```

## Example Ansible Playbook

```yaml
- hosts: 127.0.0.1
  roles:
    - role: ansible-role-php-composer
      vars:
        php_extra_packages:
          - php-mysql
        php_composer_home_dir: '{{ ansible_env.HOME }}/.composer'
        php_composer_install_dir: '/usr/local/bin'
        php_composer_global_packages:
          - squizlabs/php_codesniffer
          - drupal/coder
```

## Author

👤 **Alexander Danilenko**

* Website: https://danilenko.in
* Github: [@alexander-danilenko](https://github.com/alexander-danilenko)
* LinkedIn: [@alexander-danilenko](https://linkedin.com/in/alexander-danilenko)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/alexander-danilenko/ansible-role-php-composer/issues). 

## Show your support

Give a ⭐️ if this project helped you!

## 📝 License

Copyright © 2022 [Alexander Danilenko](https://github.com/alexander-danilenko).<br />
This project is [MIT](./LICENSE) licensed.

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
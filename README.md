# puppet-nvm_nodejs

Localized installation of multiple versions of nodejs via [NVM](https://github.com/creationix/nvm).

Tested to work on 64-bit:

  * Ubuntu Linux

## Parameters
  * `user`    : target user to install node into
  * `version` : must be the full version (format: x.x.x)
  * `home`    : set the target home dir. defaults to `/home/${user}` if skipped

## Usage

Basic:

    class { 'nvm_nodejs':
      user    => 'prod',    # this will create /home/prod automatically
      version => '0.8.22',
    }

    class { 'nvm_nodejs':
      user    => 'jenkins',
      version => '0.8.22',
      home    => '/var/tmp/jenkins',  # explicit home location
    }

## Paths and executables

Once the class was successfully declared, access these variables:

  * `$nvm_nodejs::NODE_PATH` : path to the bin directory
  * `$nvm_nodejs::NODE_EXEC` : full executable path of `node` engine
  * `$nvm_nodejs::NPM_EXEC`  : full executable path of `npm` 

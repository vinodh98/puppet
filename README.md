Puppet Test Repositories
========================

The contents of this repo will be automatically synced to all puppet clients

https://forge.puppetlabs.com/puppetlabs/vcsrepo

```puppet
vcsrepo { "/path/to/repo":
  ensure   => latest,
  provider => git,
  source   => 'git://example.com/repo.git',
  revision => 'master',
}

node "claicinga.cla.temple.edu" {

    notify{"Fix SSH keys !!!":}

    package {"git":
        ensure => "latest",
    }

    # Download the server configurations
    vcsrepo { "/opt/cla":
        ensure   => latest,
        provider => git,
        source   => 'git@github.com:vinodh98/puppet.git',
        revision => 'master',
        require => Package["git"],
    }
}
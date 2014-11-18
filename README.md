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
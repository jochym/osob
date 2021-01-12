# osob
> OpenScience Observatories interface library


The OSOb library provides wrapper for the telescope.org site functionality.

## Install

`pip install osob`

## How to use

The library may be used as standard python module and through several command line utilities: `submit_batch`, `pipeline` etc.

```python
#local
config = configparser.ConfigParser()
config.read(expanduser('~/.config/telescope.ini'))

OSO=Telescope(config['telescope.org']['user'], 
              config['telescope.org']['password'])

reqlst=OSO.get_user_requests(sort='completion')
print(f'Number of users requests: {len(reqlst)}')

OSO.logout()
```

    Number of users requests: 1162


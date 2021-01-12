# osob
> OpenScience Observatories interface library


The OSOb library provides wrapper for the telescope.org site functionality.

## Install

`pip install osob`

## How to use

The library may be used as standard python module and through several command line utilities: `submit_batch`, `pipeline` etc.

```python
config = configparser.ConfigParser()
config.read(expanduser('~/.config/telescope.ini'))

OSO=Telescope(config['telescope.org']['user'], 
              config['telescope.org']['password'])
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-2-29481b3a549e> in <module>
          2 config.read(expanduser('~/.config/telescope.ini'))
          3 
    ----> 4 OSO=Telescope(config['telescope.org']['user'], 
          5               config['telescope.org']['password'])


    ~/Projects/osob/osob/core.py in __init__(self, user, passwd, cache)
         42         self.tout=60
         43         self.retry=15
    ---> 44         self.login()
         45         self.cache=cache
         46 


    ~/Projects/osob/osob/core.py in login(self)
         46 
         47     def login(self):
    ---> 48         log = logging.getLogger(__name__)
         49         payload = {'action': 'login',
         50                    'username': self.user,


    NameError: name 'logging' is not defined


```python
# Not yet implemented
# reqlst=OSO.get_user_requests(sort='completion')
# print(f'Number of users requests: {len(reqlst)}')
```

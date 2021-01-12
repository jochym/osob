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
```




    ['/home/jochym/.config/telescope.ini']



```python
OSO=Telescope(config['telescope.org']['user'], 
              config['telescope.org']['password'])
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-3-a51d20a5967b> in <module>
    ----> 1 OSO=Telescope(config['telescope.org']['user'], 
          2               config['telescope.org']['password'])


    ~/Projects/osob/osob/core.py in __init__(self, user, passwd, cache)
         42         self.tout=60
         43         self.retry=15
    ---> 44         self.login()
         45         self.cache=cache


    AttributeError: 'Telescope' object has no attribute 'login'


```python
# Not yet implemented
# reqlst=OSO.get_user_requests(sort='completion')
# print(f'Number of users requests: {len(reqlst)}')
```

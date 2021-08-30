# OSOb
> OpenScience Observatories interface library


The OSOb library provides wrapper for the telescope.org site functionality. The library provides access and control for the telescope. The functions help with job submission, image retrival and initial analysis. For now this is aimed at variable star observations, but there is nothing prohibiting additional modules intended for different fields (e.g. astrometry).

## Install

`pip install osob`

## How to use

The library may be used as standard python module and through several command line utilities: `submit_batch`, `pipeline` etc. Typical use in your own scripts 

```python
#local
config = configparser.ConfigParser()
config.read(expanduser('~/.config/telescope.ini'))

OSO=Telescope(config['telescope.org']['user'], 
              config['telescope.org']['password'])

reqlst=OSO.get_user_requests(sort='completion')
print(f'Number of users requests: {len(reqlst)}')

print("User folders:")
for f in OSO.get_user_folders():
    cnt = f["count"] 
    if cnt is None:
        cnt = 0
    print(f'{f["name"]:>12} ({f["id"]:>3}): {cnt:>4} items')

OSO.logout()
```

    Number of users requests: 1162
    User folders:
           Inbox (  1): 1162 items
      Favourites (  2):    0 items
         Archive (  3):  447 items
           Trash (  4):   52 items
        Complete (461):   13 items


# Ansible Execution Environment (EE) for Network

Create and activate venv for build
```bash
$ python3 -m venv .venv && source .venv/bin/activate
```

Build command:
```bash
(.venv) $ ansible-builder build -t network-ee
```

### Fix for CryptographyDeprecationWarning

```bash
# Open file
/usr/local/lib/python3.8/site-packages/paramiko/transport.py
# in your preferred editor, find the _cipher_info block and comment out section
# "blowfish-cbc": {
#     "class": algorithms.Blowfish,
#     _cipher_info   "mode": modes.CBC,
#     "block-size": 8,
#     "key-size": 16,
# },
```

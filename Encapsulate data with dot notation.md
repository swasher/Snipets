This functionality already exists in the standard libraries, so I recommend you just use their class.


    >>> from types import SimpleNamespace
    >>> d = {'key1': 'value1', 'key2': 'value2'}
    >>> n = SimpleNamespace(**d)
    >>> print(n)
    namespace(key1='value1', key2='value2')
    >>> n.key2
    'value2'
  
 Adding, modifying and removing values is achieved with regular attribute access, i.e. you can use statements like `n.key = val` and `del n.key`.

To go back to a dict again:

    >>> vars(n)
    {'key1': 'value1', 'key2': 'value2'}
    The keys in your dict should be string identifiers for attribute access to work properly.

Simple namespace was added in Python 3.3. For older versions of the language, argparse.Namespace has similar behaviour.

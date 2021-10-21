Found here https://stackoverflow.com/a/13643355/1334825

Python imports are singleton by nature. When a module is imported multiple times it is only executed the first time. Subsequent imports fetch the module object instance from the globals. More on that here.

shared.py

    class Shared:
      def __init__(self):
        print("Init shared")

      def do_stuff(self, from_mod):
        print("Do stuff from {0}. I am instance {1}".format(from_mod, self))

    shared = Shared()
  
foo.py

    import shared

    shared.shared.do_stuff("foo")

bar.py

    import foo
    import shared

    shared.shared.do_stuff("bar")

repo to help in repro of: https://forum.snapcraft.io/t/localization-of-python-snaps/2066


To repro:

```
dpb@bierstadt:snapcraft-lcall-bug[(master)]$ python3 -m lcall_bug
💩

dpb@bierstadt:snapcraft-lcall-bug[(master)]$ sudo snap install --dangerous ./lcall-bug_0.0.1_amd64.snap
lcall-bug 0.0.1 installed

dpb@bierstadt:snapcraft-lcall-bug[(master)]$ lcall-bug
Traceback (most recent call last):
  File "/snap/lcall-bug/x2/usr/lib/python3.5/runpy.py", line 184, in _run_module_as_main
    "__main__", mod_spec)
  File "/snap/lcall-bug/x2/usr/lib/python3.5/runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "/snap/lcall-bug/x2/lib/python3.5/site-packages/lcall_bug/__main__.py", line 5, in <module>
    sys.exit(lcall_bug.main())
  File "/snap/lcall-bug/x2/lib/python3.5/site-packages/lcall_bug/__init__.py", line 2, in main
    print("""\U0001f4a9""")
UnicodeEncodeError: 'ascii' codec can't encode character '\U0001f4a9' in position 0: ordinal not in range(128)

dpb@bierstadt:snapcraft-lcall-bug[(master)]$ lcall-bug.lcall-fixed
💩

```

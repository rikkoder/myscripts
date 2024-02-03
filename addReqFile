#!/usr/bin/env python3

## create requirements file for python projects that don't maintain it.
## the requirements file thus created may include builtin libs like math, os, etc
## use the following way to install packages instead of pip install -r requirements,
## xargs -n 1 -a requirements.txt pip install
## python venv diectories are excluded so not to reinstall dependencies but if dirnames like 'lib'
## contains internal files then remove it from exclude list.

import os, sys
dir_path = os.path.dirname(os.path.realpath(__file__))
if len(sys.argv) > 1:
    dir_path = sys.argv[1]

libs = set()
internal_files = []

for subdir, dirs, files in os.walk(dir_path):
    if subdir == dir_path:
        internal_files.extend(dirs)

    exclude = ['__pycache__', '.git', 'bin', 'lib', 'lib64', 'include']
    for d in exclude:
        if d in dirs:
            dirs.remove(d)

    for file in files:
        if file[-3:] == '.py':
            if file == __file__.split('/')[-1]:
                continue

            with open(f'{subdir}/{file}') as py:
                lines = py.readlines()
                for line in lines:
                    words = line.split()
                    if len(words) == 0:
                           continue
                    if words[0] == 'import':
                        for lib in words[1:]:
                            libs.update([x.split('.')[0] for  x in lib.split(',')])
                    if words[0] == 'from':
                        libs.add(words[1].split('.')[0])
                py.close()

            internal_files.append(file[:-3])

for file in internal_files:
    if file in libs:
        libs.remove(file)

with open(f'{dir_path}/requirements.txt', 'w') as reqs:
    for lib in libs:
        if lib != 'as':
            reqs.write(f'{lib}\n')
    reqs.flush()
    reqs.close()

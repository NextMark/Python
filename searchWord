#!/usr/bin/python
# -*- coding:utf8 -*-

import os, sys
listonly = False
fileSuffix = ['.java']
     
def visitfile(fname, searchKey):
    global fcount, vcount
    if not listonly:
        if (os.path.splitext(fname)[1] in fileSuffix) and (open(fname).read().find(searchKey) != -1):
			print'%s has %s' % (fname, searchKey)
			fcount += 1
        else:
            pass
    vcount += 1 
    
def visitor(args, directoryName,filesInDirectory):
    for fname in filesInDirectory:                   
        fpath = os.path.join(directoryName, fname)    
        if not os.path.isdir(fpath):                   
            visitfile(fpath,args)
     
def searcher(startdir, searchkey):
    global fcount, vcount
    fcount = vcount = 0
    os.path.walk(startdir, visitor, searchkey)
     
if __name__ == '__main__':
    root=raw_input("type root directory:")
    key=raw_input("type key:")
    searcher(root,key)
    print 'Found in %d files, visited %d' % (fcount, vcount)

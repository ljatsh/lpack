
import os

env = Environment(SHLIBPREFIX = '')
# export LUAJIT=1
if os.environ.get('LUAJIT'):
    print('getjit')
    env.AppendUnique(CPPPATH = ['/usr/local/include/luajit-2.0'])

pack = env.SharedLibrary('pack',
                         'lpack.c',
                         CFLAGS=['-O2', '-Wno-deprecated', '-Wall'],
                         LINKFLAGS = ['-fPIC'],
                         LIBS = ['dl'])

env.Install('/usr/local/lib/lua/5.1', pack)

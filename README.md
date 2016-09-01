
All modules buld with MSVC 2010 and linked against `msvcr100.dll`.
But because it dynamic libraries you can use it for install rocks
with different runtime. Excaption is only for static libraries.
E.g. You can not buld `alien` rocks with different runtime because
libffi is static library. In fact it will be compiled, but you will 
get linker warning.

List of static libraries:
 * libffi

### Install
LuaRocks has hardcoded path `c:\external` where it looking external
dependencies. So you can just clone it in this directory. Or you can
add in your `config.lua`/`config-5.1.lua` e.g.
```Lua
external_deps_dirs = {
    "c:/lua/external/"
}
```
Also to be able find `dll` files you neet add path to `bin` directory to
`PATH` environment variable.

### Some rocks that can be installed

One note. I have to use some patched rockspecs/sources files because they
has some problems on Windows. I puth this files in `rockspecs` directory.

```
Installed rocks:
----------------
alien
   scm-0 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lluv
   0.1.5-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lrexlib-pcre
   2.8.0-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lsqlite3
   0.9.3-0 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lua-cjson
   2.1.0-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lua-curl
   scm-0 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lua-iconv
   7-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
luaexpat
   1.3.0-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
luuid
   20120501-2 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lzlib
   0.4.1.53-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
lzmq
   0.4.3-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
openssl
   scm-1 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
sqlite3
   scm-0 (installed) - c:/Lua/5.1/systree/lib/luarocks/rocks
```
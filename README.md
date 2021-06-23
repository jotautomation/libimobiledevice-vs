# Visual Studio solution & projects for libimobiledevice

This repo is fork from https://github.com/jotautomation/libimobiledevice-vs.

The libimobiledevice project consists of multiple libraries - such as libplist, libusbmuxd
and libimobiledevice.

Each library lives in its own repository, and references the other libraries. By default,
these projects are referenced as Vcpkg packages. This provides great isolation for each library.

This setup can be cumbersome when you're making changes that touch multiple libraries at once,
because you need to make a change, update the dependency, and try again.

This repository contains a Visual Studio solution and projects which allow you to build
all of libimobiledevice at once, using Visual Studio.

## Getting started

You'll need [vcpkg](https://github.com/microsoft/vcpkg) to install dependencies (such as libcurl)
and a couple of repositories to configure your development environment.

To install vcpkg and the dependencies, run:

```
git clone https://github.com/microsoft/vcpkg
vcpkg\bootstrap-vcpkg.bat
vcpkg\vcpkg integrate install
vcpkg\vcpkg install libiconv:x64-windows zlib:x64-windows openssl:x64-windows dirent:x64-windows getopt:x64-windows curl:x64-windows libzip:x64-windows libxml2:x64-windows libusb:x64-windows libusb-win32:x64-windows pthreads:x64-windows readline:x64-windows pcre:x64-windows
```

To get the libimobiledevice source code, run:

```
get-source.cmd
```

You can now open the `libimobiledevice-vs.sln` solution and start compiling libimobiledevice. Note! Select Release and x64 configurations.

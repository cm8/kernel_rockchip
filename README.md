This repo is DEPRECATED and here for reference purpose only,
it may be deleted from github at any time in the future.

For mk802iv instead use e.g.

 mainline kernel (e.g. 5.6) + ite bridge chip code from
 https://github.com/mmind/linux-rockchip/tree/wip/rk3188-lcdc/drivers/gpu/drm/bridge
 
   - copy ite directory, adjust Kconfig and Makefile in drivers/gpu/drm/bridge, so it66121 will show up in menuconfig
   - adjust drmP.h header includes
     - drmP.h was split into multiple headers since 5.0.0-rc2
     - have a look at the updated includes in drivers/gpu/drm/bridge/sii902x.c if you need orientation
   - adjust "struct" to "const struct" to satisfy changed drm header struct declarations
   - merge hdmi fragments in dts/rk3188-radxarock.dts (wip/rk3188-lcdc dts and the one from 5.6 differ!)
 
   - lima module available in 5.6 (mali400/450 kernel module), which has
     not been there when wip/rk3188-lcdc was forked from 5.0.0-rc2
     - https://lists.freedesktop.org/archives/dri-devel/2019-February/206260.html
     - https://gitlab.freedesktop.org/lima/web

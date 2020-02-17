This repo is DEPRECATED and here for reference purpose only,
it may be deleted from github at any time in the future.

See https://github.com/cm8/linux repo for which the steps
outlined below have already been performed.

 mainline kernel plus
 + mmind/linux-rockchip/tree/wip/rk3188-lcdc/drivers/gpu/drm/bridge/ite
 + mmind/linux-rockchip/blob/wip/rk3188-lcdc/arch/arm/boot/dts/rk3188-radxarock.dts
 
   - adjust Kconfig and Makefile in drivers/gpu/drm/bridge
   - adjust drmP.h header includes
     - drmP.h was split into multiple headers
     - for an example refer to updated includes in drivers/gpu/drm/bridge/sii902x.c
   - adjust "struct" to "const struct" to satisfy changed drm header struct declarations
   - merge hdmi fragments into dts/rk3188-radxarock.dts
     - wip/rk3188-lcdc dts and mainline dts differ until at least v5.6-rc2
   - lima mali400/450 kernel module entered mainline in feb 2019
     - wip/rk3188-lcdc missed that module, it was forked before without a lima merge commit thereafter
     - https://lists.freedesktop.org/archives/dri-devel/2019-February/206260.html
     - https://gitlab.freedesktop.org/lima/web

If you don't want to clone the whole repo, you can find
tarballs reflecting official kernel versions supplemented
by it66121 code using https://github.com/cm8/linux/releases.

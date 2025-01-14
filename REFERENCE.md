# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

#### Public Classes

* [`storcli`](#storcli): storcli  Main class, include all other classes.
* [`storcli::configure`](#storcliconfigure): Make any controller settings active

#### Private Classes

* `storcli::install`: This class handles storcli packages and binary link.

## Classes

### <a name="storcli"></a>`storcli`

storcli

Main class, include all other classes.

#### Parameters

The following parameters are available in the `storcli` class:

* [`package_manage`](#package_manage)
* [`package_name`](#package_name)
* [`package_ensure`](#package_ensure)
* [`link_storcli_to`](#link_storcli_to)
* [`configure_settings`](#configure_settings)
* [`controller_autorebuild`](#controller_autorebuild)
* [`controller_rebuildrate`](#controller_rebuildrate)
* [`sync_time_to_controllers`](#sync_time_to_controllers)
* [`controller_use_utc`](#controller_use_utc)
* [`controller_perfmode`](#controller_perfmode)
* [`controller_ncq`](#controller_ncq)
* [`controller_cacheflushinterval`](#controller_cacheflushinterval)
* [`controller_bootwithpinnedcache`](#controller_bootwithpinnedcache)
* [`controller_alarm`](#controller_alarm)
* [`controller_smartpollinterval`](#controller_smartpollinterval)
* [`controller_patrolread_mode`](#controller_patrolread_mode)
* [`controller_patrolread_delay`](#controller_patrolread_delay)
* [`controller_patrolread_rate`](#controller_patrolread_rate)
* [`controller_patrolread_includessds`](#controller_patrolread_includessds)
* [`controller_patrolread_uncfgareas`](#controller_patrolread_uncfgareas)
* [`controller_consistencycheck_mode`](#controller_consistencycheck_mode)
* [`controller_consistencycheck_delay`](#controller_consistencycheck_delay)
* [`controller_consistencycheck_rate`](#controller_consistencycheck_rate)

##### <a name="package_manage"></a>`package_manage`

Data type: `Variant[Boolean, Enum['true', 'false']]`

Whether to manage the storcli package. Default value: value of megaraid['present?'].

##### <a name="package_name"></a>`package_name`

Data type: `Array[String]`

Specifies the storcli package to manage. Default value: ['storcli'].

##### <a name="package_ensure"></a>`package_ensure`

Data type: `String`

Whether to install the storcli package, and what version to install. Values: 'present', 'latest', or a specific version number.
Default value: 'present'.

##### <a name="link_storcli_to"></a>`link_storcli_to`

Data type: `Stdlib::Absolutepath`

The official package puts the binary into /opt/MegaRAID/storcli which isn't usually in `$PATH`.
This module will put a link into another location so the binary is easily found.
Default value: /usr/local/sbin

##### <a name="configure_settings"></a>`configure_settings`

Data type: `Boolean`

Should this class be able to enforce configuration settings on the controllers?
If you've got multiple controllers which should have different configs, you'll want to set this to false.
Default value: true

##### <a name="controller_autorebuild"></a>`controller_autorebuild`

Data type: `Boolean`

Should this controller automatically rebuild arrays
Default value: true

##### <a name="controller_rebuildrate"></a>`controller_rebuildrate`

Data type: `Integer[0, 100]`

Percentage of IO to dedicate to rebuilding an array
Default value: 60

##### <a name="sync_time_to_controllers"></a>`sync_time_to_controllers`

Data type: `Boolean`

Should controller clock be synced with the system clock?
Default value: true

##### <a name="controller_use_utc"></a>`controller_use_utc`

Data type: `Boolean`

Should controller clock use UTC?
Default value: true

##### <a name="controller_perfmode"></a>`controller_perfmode`

Data type: `Integer[0]`

Prioritize IOPS(0) or low latency(1)
Set as an integer should new modes be added
Default value: 0

##### <a name="controller_ncq"></a>`controller_ncq`

Data type: `Boolean`

Should Native Command Queue be enabled?
Default value: true

##### <a name="controller_cacheflushinterval"></a>`controller_cacheflushinterval`

Data type: `Integer[1]`

Time in seconds between cache flushes
Default value: 4

##### <a name="controller_bootwithpinnedcache"></a>`controller_bootwithpinnedcache`

Data type: `Boolean`

Continue booting with data stuck in cache?
Default value: false

##### <a name="controller_alarm"></a>`controller_alarm`

Data type: `Boolean`

Sound alarm when a disk is bad?
Datacenters with lots of hosts and noise may want to disable this.
Default value: true

##### <a name="controller_smartpollinterval"></a>`controller_smartpollinterval`

Data type: `Integer[0, 65535]`

Time in seconds between polling drive SMART errors (0-65535)
Default value: 60

##### <a name="controller_patrolread_mode"></a>`controller_patrolread_mode`

Data type: `Enum['auto', 'manual', 'off']`

Run patrolread either, auto, manual, or off
Default value: auto

##### <a name="controller_patrolread_delay"></a>`controller_patrolread_delay`

Data type: `Integer[0]`

Set the patrolread delay to this many hours
Default value: 336

##### <a name="controller_patrolread_rate"></a>`controller_patrolread_rate`

Data type: `Integer[0, 100]`

Set the patrolread IO percentage
Default value: 30

##### <a name="controller_patrolread_includessds"></a>`controller_patrolread_includessds`

Data type: `Boolean`

Should we patrol SSD devices
Default value: false

##### <a name="controller_patrolread_uncfgareas"></a>`controller_patrolread_uncfgareas`

Data type: `Boolean`

Should we patrol unconfigured areas
Default value: false

##### <a name="controller_consistencycheck_mode"></a>`controller_consistencycheck_mode`

Data type: `Enum['off', 'seq', 'conc']`

One of off, seq, conc
Default value: conc

##### <a name="controller_consistencycheck_delay"></a>`controller_consistencycheck_delay`

Data type: `Integer[0]`

Set the consistencycheck delay to this many hours
Default value: 672

##### <a name="controller_consistencycheck_rate"></a>`controller_consistencycheck_rate`

Data type: `Integer[0, 100]`

Set the consistencycheck IO percentage
Default value: 30

### <a name="storcliconfigure"></a>`storcli::configure`

Configure the storage controllers with the specified settings

#### Parameters

The following parameters are available in the `storcli::configure` class:

* [`configure_settings`](#configure_settings)
* [`controller_autorebuild`](#controller_autorebuild)
* [`controller_rebuildrate`](#controller_rebuildrate)
* [`sync_time_to_controllers`](#sync_time_to_controllers)
* [`controller_use_utc`](#controller_use_utc)
* [`controller_perfmode`](#controller_perfmode)
* [`controller_ncq`](#controller_ncq)
* [`controller_cacheflushinterval`](#controller_cacheflushinterval)
* [`controller_bootwithpinnedcache`](#controller_bootwithpinnedcache)
* [`controller_alarm`](#controller_alarm)
* [`controller_smartpollinterval`](#controller_smartpollinterval)
* [`controller_patrolread_mode`](#controller_patrolread_mode)
* [`controller_patrolread_delay`](#controller_patrolread_delay)
* [`controller_patrolread_rate`](#controller_patrolread_rate)
* [`controller_patrolread_includessds`](#controller_patrolread_includessds)
* [`controller_patrolread_uncfgareas`](#controller_patrolread_uncfgareas)
* [`controller_consistencycheck_mode`](#controller_consistencycheck_mode)
* [`controller_consistencycheck_delay`](#controller_consistencycheck_delay)
* [`controller_consistencycheck_rate`](#controller_consistencycheck_rate)

##### <a name="configure_settings"></a>`configure_settings`

Data type: `Any`

Should this class be able to enforce configuration settings on the controllers?
If you've got multiple controllers which should have different configs, you'll want to set this to false.
Default value: true

Default value: `$storcli::configure_settings`

##### <a name="controller_autorebuild"></a>`controller_autorebuild`

Data type: `Any`

Should this controller automatically rebuild arrays
Default value: true

Default value: `$storcli::controller_autorebuild`

##### <a name="controller_rebuildrate"></a>`controller_rebuildrate`

Data type: `Any`

Percentage of IO to dedicate to rebuilding an array
Default value: 60

Default value: `$storcli::controller_rebuildrate`

##### <a name="sync_time_to_controllers"></a>`sync_time_to_controllers`

Data type: `Any`

Should controller clock be synced with the system clock?
Default value: true

Default value: `$storcli::sync_time_to_controllers`

##### <a name="controller_use_utc"></a>`controller_use_utc`

Data type: `Any`

Should controller clock use UTC?
Default value: true

Default value: `$storcli::controller_use_utc`

##### <a name="controller_perfmode"></a>`controller_perfmode`

Data type: `Any`

Prioritize IOPS(0) or low latency(1)
Set as an integer should new modes be added
Default value: 0

Default value: `$storcli::controller_perfmode`

##### <a name="controller_ncq"></a>`controller_ncq`

Data type: `Any`

Should Native Command Queue be enabled?
Default value: true

Default value: `$storcli::controller_ncq`

##### <a name="controller_cacheflushinterval"></a>`controller_cacheflushinterval`

Data type: `Any`

Time in seconds between cache flushes
Default value: 4

Default value: `$storcli::controller_cacheflushinterval`

##### <a name="controller_bootwithpinnedcache"></a>`controller_bootwithpinnedcache`

Data type: `Any`

Continue booting with data stuck in cache?
Default value: false

Default value: `$storcli::controller_bootwithpinnedcache`

##### <a name="controller_alarm"></a>`controller_alarm`

Data type: `Any`

Sound alarm when a disk is bad?
Datacenters with lots of hosts and noise may want to disable this.
Default value: true

Default value: `$storcli::controller_alarm`

##### <a name="controller_smartpollinterval"></a>`controller_smartpollinterval`

Data type: `Any`

Time in seconds between polling drive SMART errors (0-65535)
Default value: 60

Default value: `$storcli::controller_smartpollinterval`

##### <a name="controller_patrolread_mode"></a>`controller_patrolread_mode`

Data type: `Any`

Run patrolread either, auto, manual, or off
Default value: auto

Default value: `$storcli::controller_patrolread_mode`

##### <a name="controller_patrolread_delay"></a>`controller_patrolread_delay`

Data type: `Any`

Set the patrolread delay to this many hours
Default value: 336

Default value: `$storcli::controller_patrolread_delay`

##### <a name="controller_patrolread_rate"></a>`controller_patrolread_rate`

Data type: `Any`

Set the patrolread IO percentage
Default value: 30

Default value: `$storcli::controller_patrolread_rate`

##### <a name="controller_patrolread_includessds"></a>`controller_patrolread_includessds`

Data type: `Any`

Should we patrol SSD devices
Default value: false

Default value: `$storcli::controller_patrolread_includessds`

##### <a name="controller_patrolread_uncfgareas"></a>`controller_patrolread_uncfgareas`

Data type: `Any`

Should we patrol unconfigured areas
Default value: false

Default value: `$storcli::controller_patrolread_uncfgareas`

##### <a name="controller_consistencycheck_mode"></a>`controller_consistencycheck_mode`

Data type: `Any`

One of off, seq, conc
Default value: conc

Default value: `$storcli::controller_consistencycheck_mode`

##### <a name="controller_consistencycheck_delay"></a>`controller_consistencycheck_delay`

Data type: `Any`

Set the consistencycheck delay to this many hours
Default value: 672

Default value: `$storcli::controller_consistencycheck_delay`

##### <a name="controller_consistencycheck_rate"></a>`controller_consistencycheck_rate`

Data type: `Any`

Set the consistencycheck IO percentage
Default value: 30

Default value: `$storcli::controller_consistencycheck_rate`


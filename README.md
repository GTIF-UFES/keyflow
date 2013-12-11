KeyFlow Core Switch
===================

A core switch for KeyFlow. Based on Stanford's OpenFlow Switch 1.0 implementation.

KeyFlow switch prototype is a OpenFlow switch instrumented for forwarding packets
based on the remainder of the division operations for processing flows, instead of
table matching. The switch becomes KeyFlow-enabled, when a local key is installed.
If it is not installed (default value zero), the flow processing happens as in the
standard OpenFlow 1.0. A minimally intrusive approach to OpenFlow reference
implementation was chosen. The identifier field vlan from Ethernet frame was used
for carrying the route path ID in our first KeyFlow prototype.


Usage
-----

To dump the switch key, use the key-mod option from the dpctl tool: 

    dpctl dump-key 

To modify the switch key and enable the KeyFlow feature, use the key-mod option
providing the key:

    dpctl key-mod <key>

Those options send the OpenFlow messages OFPT KEY MOD and OFPT KEY, respectively.


Reproducibility
---------------

Results obtained in the emulated environment are presented in their absolute for the sake of reproducibility. However, as far as timing is concerned, any eventual gain should be analyzed in a relative way due to the intrinsic limitations of emulated network environments.

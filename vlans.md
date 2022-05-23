# VLANs

The managed BTS switches use VLANs to logically segregate traffic into virtual networks. Each VLAN can be thought of as its own virtual network - for example, unless you deliberately bridge VLAN 50 and 60, devices on V50 can all see each other
but can't see anything on V60 even though they're both using the same switches and cable.

When data enters the network at a port on a switch, the port is configured to 'tag' it as belonging to a particular VLAN. This tagged traffic can be passed to any other switch that works with IEEE 802.1q ('dot1q'), even if the switch is from a different manufacturer. When the traffic leaves the switch by a port that isn't connected to another switch, the switch removes the VLAN tag and this has the benefit of ensuring more basic devices aren't confused by it.

The VLANs currently assigned within BTS are as follows. Note that BTS also have VLAN 400 on the BUCS network - this is provisioned on request and should be considered entirely separately to these numbers.

|No.|Usage|
|---|---|
|1|Default VLAN on some switches - often treated uniquely by switches (e.g. unique limitations), so avoid using|
|2|Switch management (ssh or web portal access)|
|34|Internet (mnemonic: rule 34 of the Internet)|
|50|Sound primary (mnemonic: 5 ~= S)|
|51|Sound secondary|
|52-59|Reserved for future sound use. Not configured on switches.|
|60|Lighting (mnemonic: LX == 60 in Roman numerals)|
|61-69|Reserved for future lighting use. Not configured on switches.|
|100|Video control (i.e. web interfaces for projectors, matrixers, etc)|
|101-108|Video isolated baluns|
|109-119|Reserved for future video use. Not configured on switches.|
|201-202|General usage (e.g. touring FOH engineer wants a connection to stage, or event control want to hop over our network)|
|203-219|Reserved for future general use. Not configured on switches.|

\* 'Not configured on switches' refers to switches which require VLANs to be explicitly configured on the switch in order to pass through traffic on it - some switches can be configured to allow all VLANs to pass through.

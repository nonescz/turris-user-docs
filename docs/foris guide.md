====== First setup | Foris Guide ======

Although a router is a device that does not need a permanent attention, it has to be configured before its first use. To make the configuration simpler, Turris router contains Foris web interface, which also contains an initial setup guide. Until you finish the basic router configuration, computers connected to the LAN ports won't be able to connect to the internet. \\
In order to access Foris configuration interface, you need to be connected to the same network as the router. It is possible to use only cable connection during the first run – WiFi network may be enabled later. \\
If you would like to go through the first step how to set up your router, you need to go to http://192.168.1.1 where you can find our administration interface Foris and its Guide, which is described here.

==== Setting password ====

{{ :en:howto:guide:pw.png?600 |Setting password without LuCI}}

You can set the password that will be used to access the Foris interface here. In the "Advanced" line you can choose if you want to set the same password with Foris or use another one. The same password will be used for the advanced configuration interface LuCI and for the user root when accessing the router via SSH.

{{ :en:howto:guide:password_ex1.png?600 |Setting password and different for LuCI}}

In the first column, you can set up the desired password for administration interface Foris. In the second you need to repeat this password.

If you do not need to adjust any advanced functions, we recommend you not to set the password for LuCI and SSH until the time when you need it. (This password can be changed at any time in the future on the Advanced administration page.)

If you are finished with choosing your password, click on the blue button Save in the right bottom corner. After this will show up in the right upper corner button "Next step".

==== Guide workflow ====

In this step, you can choose your workflow guide. You can choose from three options, everyone got something else. The first option, Router, is a more or less basic guide. You will choose this one if you want just connect your router to the worldwide net with basic configuration.

{{ :en:howto:guide:workflow.png?600 |Workflow options}}

If you plan to use Turris in other ways such as a server, AP, or something else, you can choose from other workflows.

For example, if you choose server workflow, you will get slightly different configuration guide with another default values.

{{ :en:howto:guide:workflow_chosen.png?600 |Chosen workflow - Router}}

If you want to configure just basics of the router and then configure rest by yourself, choose Minimal workflow. Guide will after this choice end. //
This workflow is recommended only to experienced users, because Turris will not be connected to internet and will not have any configuration after chosing minimal configuration.

This is, how you will see minimal configuration in next step.

{{ :en:howto:guide:workflow_minimal.png?600 |Finished workflow - Minimal}}

The selected workflow will be with red border, after saving you will see what's on the picture - in our example Router workflow.

==== Interface configuration ====

//Router and Server workflow//

In this step you can chose which interface you want to use for what.

If you will use your router in regular way, just click on Save and proceed to next step.

If you would like to use your router as AP (Access Point, which will increase the WiFi coverage), you need to move the port from WAN to LAN.

This can be done by clicking on the desired port, where you will see all the details and possibilities of moving port into another interface.

{{ :en:howto:guide:inter1.png?600 |Configuration of available interfaces}}


<WRAP center round tip 60%>
Look closer on selected LAN port. You can see check mark. That means you got cable connected to this port.

</WRAP>

{{ :en:howto:guide:inter2.png?600 |Check mark on chosen interface}}

==== WAN configuration ====

//Router workflow//

On this page you configure your connection to internet. In most cases is DHCP (default) configuration enough. In other cases, you should get all needed information from your ISP - static IP address, subnet mask, etc.

{{ :en:howto:guide:wan.png?600 |DHCP configuration - default}}

==== LAN configuration ====

//Server workflow//


In this step you can configure range of IP addresses, which should be in your local network. If you have no special requests, you can just click save and proceed to next step.

{{ :en:howto:guide:lan_ro.png?600 |LAN configuration - Router - with DHCP}}

{{ :en:howto:guide:lan_pc.png?600 |LAN configuration - Computer - Client}}

There is also difference with configuration router or computer. Router mode means that this devices manages the LAN (acts as a router, can assing IP addresses, ...). Computer mode means that this device acts as a client in this network. It acts in a similar way as WAN, but it has opened ports for configuration interface and other services.

If you need to chose more complicated options, we recommend to use interface LuCI.

==== Region and time ====

For proper work of your router Turris, you need to have setted up right time zone. If mid-european time zone is uncomplying for you, which is configured as default in Turris, you can change that in this step.

We recommend to use NTP. This is Network Time Protocol, which is used to synchronize time on devices with server. By using this protocol, you can avoid unwanted problems and malfunction of the router. //
For keeping the right time router Turris uses a RTC battery. This battery is still in use even when you shut down your Turris, and can't run out of voltage, which can bring unwanted troubles. If this happen, you will need to change that battery and configure the time again.

{{ :en:howto:guide:time.png?600 |NTP time}

==== DNS ====

The Turris router uses its own DNS resolver with DNSSEC support. It is able to work as a completely independent resolver or with the help of ISP's DNS resolver which is the target of the so-called forwarding. Where the ISP's resolver works correctly, it is preferred to use the forwarding mode which usually yields better response times. If this mode does not work in your network, you have to disable the forwarding mode. Forwarding can be broken in cases when your ISP does not support DNSSEC and has incorrectly configured servers.

Turris Omnia allows you to disable the DNSSEC validation. We highly recommend you not to do so, since you can easily become a target of a DNS spoofing attack then.

The connectivity test is used to test the individual components of your connection and includes, among other things, a test of the DNS itself and DNSSEC security. You can also use this test to verify forwarding settings.

{{ :en:howto:guide:dns.png?600 |DNS - provider option - default}}


==== Updater ====

Turris router can activate or deactivate the automatic updates. If the automatic updates are enabled, you can install lists of software packages using the Updater. These lists can simplify the installation of software required to turn your router into an NAS (network attached storage) for example, or allow you to connect a printer to the router. The packages will be installed shortly after selecting the desired package lists and pressing the Save changes button.

{{ :en:howto:guide:updater.png?600 |Updater tab - automatic updates}}

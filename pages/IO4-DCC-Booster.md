---
iseagle: true
sidebar: spcoast_sidebar
title: IO4-DCC-Booster
project: IO4-DCC-Booster
designer: John Plocher
author: John Plocher
fabricated: yes
fab_date: 2017.04
status: released
publish: yes
tags: [eagle, SPCoast]
layout: eagle
image_path: IO4-DCC-Booster.top.brd.png
tagline: IO4 DCC Booster
overview: >
    A DIY DCC booster for a BOM cost of about $20 when using bulk China/eBay parts.
    
    <p>I was working on designing a motor shield using the $10 IBT-2
    H-Bridge when I came across the work done by D. Bodnar at
    [train electronics.com](http://www.trainelectronics.com/DCC_Arduino/DCC_Booster/)
    
    <p>I wanted to use one of these for every control point on my layout
    instead of a DCC circuit breaker + booster power district mashup.
    As the DCC Breakers are at least double the DIY cost for these
    dedicated boosters, and I will end up with 10-20 control points on
    my SPCoast layout, the savings might actually cover the development
    costs :-)
    
    <p>These boosters DO NOT support auto-reverse, and the sketch software
    doesn't try to do soft start detection of sound decoder capacitor
    inrush currents.  Since there will be on average a single train
    powered by each of these boosters on my N-Scale layout, I don't
    expect this to be a real issue.  In practice, a simple 1 or 2 amp
    unit would probably be good enough; at 5 to 6 amps, this is overkill.
    
    
    From Bedner's original web writeup at trainelectronics.com:
    
    <blockquote>
    <H3>Introduction</H3>
    
    <p>In addition to experimenting with DCC++ over the last few months I
    have been trying out different H-Bridges to see if there is one
    that would work with DCC++ while delivering more than the 1 to 2
    amps that the standard Arduino Motor Shield provides.  Such a option
    would a good option for G scale layouts that typically draw much
    more power than smaller scales.
    
    <p>I came across a few higher power shields
    <A href="http://trainelectronics.com/DCC_Arduino/DCC++/">that are described here</A>
    including one that has an advertised power capability of 43 amps.
    While I am a bit skeptical about this claim my tests show that it
    has no problem delivering 5 or more amps, more than enough for my
    purposes.  I describe how this can be interfaced to the DCC++
    controller in the link above.
    
    <p>In order to make the use of this H-Bridge more convenient I decided
    to design a stand-alone DCC booster that would attach to a DCC
    signal and boost it before powering a track.  The booster is designed
    to work with DCC++, Digitrax and other systems.
    
    <H3>Hardware - H-Bridge</H3>
    
    <p>The H-Bridge is available from eBay, Amazon and other vendors -
    just search for "H-Bridge 43 amp BTS7960B".  Make sure you get the
    unit that has two BTS7960B devices on it - each is 1/2 of an H-Bridge.
    The control signals go to the 8 pins on the front and the power in
    and power out wires go to the 4 pin screw terminal connector at the
    rear.
    
    <p>This H-Bridge and similar units do not operate on the single PWM
    signal that most DCC systems provide.  It needs a right hand rotating
    PWM and a left hand PWM.  To change the single PWM signal to two a
    simple one transistor circuit is needed.  That circuit can be seen
    in the lower left corner of the schematic (below).
    
    <p>The H-Bridge can act as a DCC booster without much more than the
    Opto Coupler circuit and the one transistor converter.  The H-Bridge
    does hove an over current shutdown capability but it doesn't react
    until well over 30 amps are being drawn, way more than we are going
    to use.  To get around this problem so that the system shuts down
    immediately if the track is shorted an Arduino Pro Mini has been
    added.  The Arduino monitors the current sensing pin on the H-Bridge
    and can turn it off should it detect a high reading.
    
    </blockquote>
    
    Their prototype reused a board he had on hand; this project simply
    turns their schematic into a purpose-built board - and adds remote control
    (enable/disable and monitoring) via an IO-4 RJ12/6 interface.
    
    My differences:
      * powered by the DC booster power.
      * local control - a maintainer "disable track power" switch
      * remote control via IO4 connector
        * enable/disable track power
      * remote feedback via IO4 connector
        * enabled
        * occupied
        * overload
      * Loconet and NCE Booster Bus daisy chain command station cable jacks
    
    === Estimated BOM costs ===
    <pre>
    	$ 1.00  PCB
    	$10.00  IBT-2
    	$ 3.50  Pro Mini Clone
    	$ 0.45  6n137
    	$ 0.20  2200uF x2
    	$ 3.00  RJ and Phoenix connectors
    	$ 1.00  SPDT Switch
    	$ 1.00  R/C/LEDs
    	------
        ~$20.00
    </pre>
    
    The booster uses an external 12-18v 6A+ DC power supply; the logic and
    feedback electronics are isolated from the power supply (using opto
    isolator for the booster bus and a full wave bridge for the power
    supply), so there should be no problems driving a set of boosters
    from a single large amperage switching supply.
    
    As with ALL high power systems, use a SLOW BLOW or POLYFUSE in your
    power supply feed.  20v at 6A is 120W - similar to a very bright
    and hot incandescent bulb, if you remember them.  You don't want
    to arc weld or start a fire on your layout if something goes wrong!
    
    
images:
  - image_path: /versions/IO4-DCC-Booster/IO4-DCC-Booster.top.brd.png
    title: IO4-DCC-Booster.top.brd
---


This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)

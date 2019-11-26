---
iseagle: true
sidebar: spcoast_sidebar
title: Adapter-CMRI8-RJ45
project: Adapter-CMRI8-RJ45
name: Adapter-CMRI8-RJ45
designer: John Plocher
fabricated: yes
fab_date: 2018-12
status: released
publish: yes
layout: eagle
tags: [SPCoast, eagle]
tagline: CMRI Breakout8 Adapter RJ45 to 0.100, 3.5mm and 0.156 Molex
overview: >
    
    CMRI boards have traditionally used Molex KK 0.156 pitch I/O pins, which required crimping matching connectors onto layout wiring.
    This adapter board converts them into RJ-45 style used by common network cables.
    
    Crimping to RH45 connectors is (IMO at least) much simpler than the alternative.
    
    Another of these boards can be used at the other end of the 8-conductor
    cable, but this time it can be populated with a 0.1" or 3.5mm pitch
    screw terminal and mounted to the benchwork near where it's signals
    are used.
    
      * Added optional resistors inline for direct driving LED outputs with a default (cuttable) link for use as inputs...
    
artifacts:
  - path: /versions/Adapter-CMRI8-RJ45/Adapter-CMRI8-RJ45.gerbers.zip
    tag: Adapter-CMRI8-RJ45.gerbers
    type: download
    post: 
  - path: /versions/Adapter-CMRI8-RJ45/Adapter-CMRI8-RJ45.parts.csv
    tag: Adapter-CMRI8-RJ45.parts
    type: download
    post: 
  - path: /versions/Adapter-CMRI8-RJ45/Adapter-CMRI8-RJ45_array.gerbers.zip
    tag: Adapter-CMRI8-RJ45_array.gerbers
    type: download
    post: 
  - path: /versions/Adapter-CMRI8-RJ45/Adapter-CMRI8-RJ45_array.parts.csv
    tag: Adapter-CMRI8-RJ45_array.parts
    type: download
    post: 
  - path: /versions/Adapter-CMRI8-RJ45/Adapter-CMRI8-RJ45_array.scr
    tag: Adapter-CMRI8-RJ45_array
    type: download
    post: 
---
This technical documentation is licensed under the [CERN Open Hardware Licence v1.2](http://www.ohwr.org/attachments/2388/cern_ohl_v_1_2.txt)
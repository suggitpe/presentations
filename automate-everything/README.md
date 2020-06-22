# Automate everything
by Pete Suggitt 


## Introduction
* First joined UBS in 1998 (just after the SBC UBS merger)
* Started in OTC Operations and quickly moved into IT
* Worked across OTC Operations IT, Group Finance IT and now in Securities Operations IT
* Advice departments all over the bank on development techniques especially around automation of testing

## We are a sausage factory
* [background of a big sausage](http://static.guim.co.uk/sys-images/Guardian/About/General/2011/9/12/1315836441131/a-sausage-on-a-fork-005.jpg)
* we make the best god damn sausages in the world!
* These sausages give us competitive advantage
* But our customers want them
    * more cheaply
    * more quickly
    * and to a better standard
* They don't ask for much !!!!!
* We are going to have to automate the making of these sausages

## Automation
* [background of a steam train](http://www.luminous-landscape.com/articleImages/Harold_Ross_/The_Rocket_Train.jpg)
    * or babbage diff engine
* Why automate processes?
    * Efficiency
    * repeatability
    * quality control
* What things should not be automated
    * show some daft stuff (images) .. the cat washer is amusing funny
* What can be automated
* Which one to do first and why?
* Understand the value chain [use the force luke!]

## The value chain
* [background of a chain]()
* First we need to understand value: the true value
* What's the true value in the product we make
    * true value of a sausage is the sustenance it gives us
    * true value of a drill bit is the hole in the wall
    * What's the true value in the product you build
* How is that value released?
    * For the sausage you have to cook it and then eat it
    * For the holes in the wall you need to use a drill and 
* Now we understand the value we can work out how we create that value
    * What are all the stages we need to go through to create that value?
        * How long do they take
        * How reliable/repeatable is each of the phases?
        * Are the activities aligned to the outcome … are we doing silly things?
        * How much effort is required
        * Which ones MUST be repeatable
        * What's the $$ cost in each of the phases
        * Are they suitable for repeatability
    * Typically in IT the big thing that gets all the focus for automation is testing.
    * What about delivery of the application into the environments
    * What about the management of the environments
    * What about code creation … remember some things should not be automated
        * How many of you use code generation techniques?
        * We made some mistakes in the past with code generation
        * What is code?  Most of us use a 3GL with a compiler, this is automation
        * Anyone use GWT?
        * Anyone use SQL?  A 4GL

## This is what we found when we looked at our value chain
* [Background of 9 appold street]
* [Picture of our value chain]
* __Problematic area #1__: The physical act of releasing to production was      unreliable and hard to repeat
    * single script releases
        * **principle**: *releases to all environments must be the same.  Focus on simple and repeatable*
        * **Principle**: *PSG must be a boring job … its our objective*
    * about to adopt SWIFT from the NEO team
* __Problematic area #2__: The automated tests were consuming our time
    * The automated tests were the problem: data driven testing rather than         scenario driven
    * strategy failed to consider testing at scale
    * testing pyramid and quadrant working together
    * [picture of the pyramid]
    * [picture of the quadrant]
    * [picture of them working together]
        * **Principle**: *test at the appropriate level*
    * application hard to test:
        * **principle **: application must be testable
* __Problematic area #3__: Builds are always broken
    * When teams are all working on a common branch and following the continuous integration technique strictly you follow an unstable trunk branch strategy (branch to release)
    * [picture of unstable branch strategy]
    * When three commits happen and one breaks the build, how do you identify the change the broke the build
    * If you scale to 17 teams globally, the problem is amplified
    * [picture of single branch with millions of commits]
    * **Principle**: *only release to master when met 'done'*
    * Teams working on branches and integrating from master often
    * [picture of feature branch strategy]
    * When you have 1 or 2 teams this is usually fine
    * In a scaled model this is hard
    * If acceptance is a part of 'done'
        * does each team have its own, dedicated test environment?
    * How do we perform the right level of testing for each branches
    * **Principle**: *organise your continuous integration server into a build pipeline*
        * [picture of a pipeline theory]
        * [picture of our radiator]
        * Only use artefacts that have been through the pipeline
        * It will ensure quality is baked it
* __Problematic area #4__: static environments cannot scale
    * assuming the right level of automated acceptance testing, teams only need their branch code in an environment for a short period.
        * But it must only contain their discrete changes
        * They will likely need it when someone else is doing the same thing
        * static environments are a blocker
    * we need dynamic environments and the ability to release to them at will
    * they should be treated like cattle
        * pets and cattle
        * [picture from cern pets or cattle](http://regmedia.co.uk/2013/03/18/servers_pets_or_cattle.jpg)
    * Following the principle that you test as you release this leads to an obviously conclusion that we should treat production in the same way
    * __Principle__: _infrastructure as code_
    * [picture of puppet]
* __Problematic area #5__: The administration of releasing our application
    * Mysterious audit requirements and SOXES (the plural of SOX)
        * review of ICAP shows we do not actually need to do that much
    * Use the build pipeline to create all the artefacts you need for audit
    * __Principle__: _teams write code, automate all artefact creation_

# Things to take away
* Don't automate for the sake of it
* Use value chain analysis to understand value and how its created in your process
* Identify parts of your value chain to optimise based on:
    * cost
    * need for reliability and repeatability
* Iterate

# That's all folks
* [picture from Disney thats all folks](http://3.bp.blogspot.com/-ypYVcbNkatk/UuhoC-qtZ5I/AAAAAAAAANY/LxANurZ_rAA/s1600/the-end.jpg)


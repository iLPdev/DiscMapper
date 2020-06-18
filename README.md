# discMapper

<!-- PROJECT BANNER -->
<br />
<p align="center">
  <a href=".github/images/discMapper_logo.png">
    <img src=".github/images/discMapper_logo.png" alt="discMapper Logo" width="640" height="auto">
  </a>
</p>


  
<!-- PROJECT BADGES -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![GPL License][license-shield]][license-url]
[![standard-readme compliant][standard-readme-shield]][standard-readme-url]



<!-- SHORT DESCRIPTION -->
<p align="center">
   Discworld MUD mapping script for Mudlet
   <br />
</p>



<!-- LONG DESCRIPTION -->
The discMapper project gives [Discworld MUD](http://discworld.starturtle.net/lpc) players improved access to the advanced mapping features of the [Mudlet](https://www.mudlet.org) MUD client. By leveraging the specific "out of band" packets sent by Discworld MUD's server, discMapper correcly identifies rooms, stops creation of duplicate rooms, and accurately tracks your character's location on the map as you move about the disc. Additional convenience features include autosetting colors and symbols on the map based on the room type.

Project Link: <a href="https://github.com/iLPdev/discMapper" alt="Project Link">https://github.com/iLPdev/discMapper</a>


<!-- TABLE OF CONTENTS -->
## Table of Contents

* [Background](#background)
* [Install](#install)
* [Usage](#usage)
* [Roadmap](#roadmap)
* [Maintainer](#maintainer)
* [Acknowledgements](#acknowledgements)
* [Contributing](#contributing)
* [License](#license)



<!-- ABOUT THE PROJECT -->
## Background
<!-- [![Product Name Screen Shot][product-screenshot]](https://example.com)
-->

### History
The discMapper project was unofficially started sometime during the early weeks of April 2020. The Coronavirus Pandemic and Stay-at-Home orders prompted [@Stack](https://github.com/iLPdev) to make an unexpected return to MUDs after more than two decades. A robust and stable LPmud derivative under continuous development since 1991, [Discworld MUD](http://discworld.starturtle.net/lpc) seemed like a promising quarantine-life distraction from our collective global trauma. Various MUD clients were tested. Among them, [Mudlet](https://www.mudlet.org) appeared the most desirable. Unfortunately, of the regular 80-100 online Discworld players, almost none appeared to be using Mudlet due to a severe lack of game-specific scripts relative to an old, alternative MUD client. A college try was made with the amazing scripts available for the alternative client, but it was too late... Mudlet's clean, modern appeal and advanced features had already won out -- if only there were Mudlet scripts for Discworld MUD. 

Inspired and seeking assistance in learning, the [Mudlet Discord chat server](https://discord.gg/S9zVg7H) was found to be a friendly, engaging community of creative and dedicatedly caring coders. After several weeks of struggling to achieve reliable mapping with text-based detection routines, a basic GMCP room detection approach was developed as possible solution. Considerable progress was made in learning and incoporating game-specific GMCP support into an existing [generic mapping script](https://github.com/Mudlet/Mudlet/blob/development/src/mudlet-lua/lua/generic-mapper/generic_mapper.xml).

On May 24, 2020, [@vadi2](https://github.com/vadi2) was gracious enough to volunteer three hours helping @Stack live on a public audio chat. After initial assessment of the unique challenges of developing a custon mapping script for Discworld MUD, we spent a brief period exploring extension of the [IRE  mapping script](https://github.com/IRE-Mudlet-Mapping/ire-mapping-script), but affirmed the lack of GMCP exit data supplied by [FluffOS]((https://github.com/fluffos/fluffos)) was too great an obstacle. A return was made to the hybrid approach of adding GMCP room detection/indexing to the text-based exit detection of the generic mapping script included with Mudlet. At the end of three hours, we had achieved basic functionality with only a couple minor issues. 

Unfortunately, it was soon realized that cleanly installing this initial version of the discMapper to a new Mudlet profile with no prior mapping settings caused the script to break entirely. Many confused hours were spent chasing a quasi-solutions and residue problems until it became painfully clear that a more rigorously tracked and structured approach would be required: Enter this project's GitHub repository.

Having a wealth of various IT-related and HTML/CSS development experience but virtually no experience in modern software development, frustration has (mostly) been overcome by an eagerness to learn and true enjoyment of the process -- especially the Mudlet community (see [Acknowledgments](#acknowledgements)). discMapper was open-sourced upon conception. 

Obviously, this repo started with a [README-first approach](https://tom.preston-werner.com/2010/08/23/readme-driven-development.html) toward trying to conceptualize how best to go about this project. Also, in the course of producing a beta release, work is being conducted to climb the learning curve of Git, GitHub, software development prcesses, and the Lua language. 

### Vision
As complement to a planned Mudlet UI for Discworld MUD, the aim of this project is to provide existing and potential players with a newbie-friendly (accessible) and reliable means to map and navigate the Discworld MUD in an elegeant, modern MUD client. In line with that aim, the goal of this project is to release a Mudlet package with all the requisite aliases, triggers, and scripts. The primary initial objective is to develop and test a [Minimum Usable Mapper](https://github.com/iLPdev/discMapper/projects/1) (MUM) that returns the functionality we had previously achieved but maintained across Mudlet profiles and time. 

### Features
* Enables mapper access to [GMCP Core Supports](http://discworld.starturtle.net/lpc/playing/documentation.c?path=/concepts/gmcp) sent by Discworld MUD's FluffOS driver for: 
  * Precision Room Indexing using GMCP Identifier data - No more duplicate room creation!
  * Precision Character Tracking using GMCP Identifier data - No more misidentified player locations on map!
  * Precision Room Name detection using GMCP Room Name data
* Autoset Map Room Color based on Room Type - Defaults to [Kefka's Discworld MUD Maps](http://dw.daftjunk.com/) color scheme 
* Autoset Map Room Symbols based on Room Type - Choose and apply your preferred room symbols

### Built With
* [Lua](https://www.lua.org) is the programming language
* [Edbee Library](https://github.com/edbee/edbee-lib) provides the text editor component for Mudlet
* [Mudlet](https://github.com/Mudlet/Mudlet) is a cross-platform, open source, and super fast MUD client
* [Sublime Text](https://www.sublimetext.com) is the current maintainer's source code editor of choice
* [Sublime Merge](https://www.sublimemerge.com) is the current maintainer's cross-platform GUI git client
* [Git](https://git-scm.com) is the version-control system for tracking changes and project management
* [ImgBot](https://github.com/dabutvin/Imgbot) provides GitHub-integrated image optimization

### Versioning
Version numbering will approximate the [Semantic Versioning](http://semver.org) approach.

### Project Status
<!-- Show the build status if you have a CI server:
      Describe the current release and any notes about the current state of the project. Examples: currently compiles on your host machine, but is not cross-compiling for ARM, APIs are not set, feature not implemented, etc. -->
This fledgling project is under initial development. As such, the script is non-functional at this time and in need of continued development. 

**[^Top](#table-of-contents)**

<!-- GETTING STARTED -->
## Install
<!-- Code block illustrating how to install.
     Include any system-specific information needed for installation.
     An Updating section would be useful for most packages, if there are multiple versions which the user may interface with.
-->

The [Mudlet Makers](https://github.com/Mudlet/Mudlet/graphs/contributors) could not have made it easier to install preconfigured custom aliases, triggers, scripts, keybindings, and UIs. Just like any other package as of Mudlet v4.8+, you may install discMapper by simply dragging and droppping the package file into Mudlet. discMapper will then be merged into your active Mudlet profile, and you may delete the original file.

To install discMapper, just follow these simple steps:

1. Download the latest release of the discMapper package (available in this repo soon) to your PC.
1. Open Mudlet on your operating system of choice.
1. Open an existing Discworld MUD profile or create a new one.
1. Locate the saved `discMapper.zip` file on your PC.
1. Drag and drop the `discMapper.zip` file into your open Discworld MUD profile.
1. Optionally, delete the `discMapper.zip` from your computer.

### Dependencies
<a href="https://www.mudlet.org"><img src="https://www.mudlet.org/wp-content/uploads/2017/08/mudlet-wp-logo.png" alt="Mudlet" width="120" height="auto"></a>

To install discMapper, you need to install and run the [Mudlet][mudlet-url] application for your operating system (Windows, MacOS, and Linux):

1. Visit [Mudlet's Download page](https://www.mudlet.org/download)
1. Click the `Download Mudlet` button 
1. Double-click the downloaded file to install Mudlet

### Getting the Source
The discMapper project is [hosted on GitHub](https://github.com/iLPdev/discMapper). You can clone the project directly with this command:

```
git clone git@github.com:iLPdev/discMapper.git
```

**[^Top](#table-of-contents)**

<!-- USAGE EXAMPLES -->
## Usage
<!-- Code block illustrating common usage.
     If CLI compatible, code block indicating common usage.
     Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.
     Cover basic choices that may affect usage: for instance, if JavaScript, cover promises/callbacks, ES6 here.
     If relevant, point to a runnable file for the usage code.
-->
To get started, connect to Discworld MUD in Mudlet and then enter `map basics` at the prompt.

A simple help system covering basic usage, most commands, and configuration options is available by issuing the `map help` command at the prompt.
<!-- _For more examples, please refer to the [Documentation](https://example.com)_ -->

**[^Top](#table-of-contents)**

<!-- ROADMAP -->
## Roadmap
See the [open issues](https://github.com/iLPdev/discMapper/issues) for a list of proposed features (and known issues).

**[^Top](#table-of-contents)**

<!-- MAINTAINER(S) -->
## Maintainer
[@Stack](https://github.com/iLPdev) - Stop by and say hello on the [Mudlet Discord Server](https://discordapp.com/invite/kuYvMQ9)!

**[^Top](#table-of-contents)**

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
<!-- State anyone or anything that significantly helped with the development of your project.
     State public contact hyper-links if applicable. -->
* [@vadi2](https://github.com/vadi2) for inital logic development, `custom_locator` code, and tireless support and encouragement.
* [Generic Map Script](https://github.com/Mudlet/Mudlet/blob/development/src/mudlet-lua/lua/generic-mapper/generic_mapper.xml) (aka _generic_mapper_) by [@JorMox](https://github.com/JorMox) was forked from the 10/20/2019 v2.0.16 as included in Mudlet 4.8.2
* [Simple Discworld Mapping Script for Mudlet V3](https://forums.mudlet.org/viewtopic.php?p=17917#p17917) by Carudan - The Autoset Map Room Color and Character (Symbol) script routines were ported directly
* `README.md`:
  * [Best-README-Template](https://github.com/othneildrew/Best-README-Template) for initial inspiration
  * [Standard Readme](https://github.com/RichardLitt/standard-readme) spec
  * [Shields.io](https://shields.io/) for serving badges

**[^Top](#table-of-contents)**

<!-- CONTRIBUTING -->
## Contributing
Contributions are what make the open source community such an amazing space to be learn, inspire, and create. Any contributions you make are **greatly appreciated** -- that’s the main reason discMapper is open-sourced! There are so many ways to contribute, even if you’re not a technical person.

See the [open issues](https://github.com/iLPdev/discMapper/issues) for a list of ideas, questions, proposed features, and known issues.

There is not yet an clear workflow for this project. We'll likely begin with the [simplified Github workflow](http://scottchacon.com/2011/08/31/github-flow.html) to accept changes. Basically, you’ll need to:

1. Create an Issue (bug report / feature request)
1. Fork the Repository 
1. Create your Branch (optionally reference issue in branch name; `git checkout -b feature/AmazingFeature`)
1. Code Code Code
1. Commit your Changes (incrementally with detailed commit messages; `git commit -m 'Add some AmazingFeature'`)
1. Push to your Branch (`git push origin feature/AmazingFeature`)
1. Submit a Pull Request

### Ethics
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)

This project follows the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md) and operates under the W3C's [Code of Ethics and Professional Conduct](https://www.w3.org/Consortium/cepc):

> W3C is a growing and global community where participants choose to work
> together, and in that process experience differences in language, location,
> nationality, and experience. In such a diverse environment, misunderstandings
> and disagreements happen, which in most cases can be resolved informally. In
> rare cases, however, behavior can intimidate, harass, or otherwise disrupt one
> or more people in the community, which W3C will not tolerate.
>
> A Code of Ethics and Professional Conduct is useful to define accepted and
> acceptable behaviors and to promote high standards of professional
> practice. It also provides a benchmark for self evaluation and acts as a
> vehicle for better identity of the organization.

The expectation is that our community group acts according to these guidelines, and that participants hold each other to these high standards. If you have any questions or are worried that the code isn't being followed, please contact the [maintainer](#maintainer) of this repository.

### Contributors

**[^Top](#table-of-contents)**

<!-- LICENSE -- Must be last section. -->
## License
<a title="Zscout370, Sertion, e.a. / Public domain" href="https://commons.wikimedia.org/wiki/File:Copyleft.svg"><img width="12" alt="Copyleft" src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8b/Copyleft.svg/240px-Copyleft.svg.png"></a> _iLP development_. Distributed under GPL v3.0-and-later. For more information, see license in [`COPYING`](https://github.com/iLPdev/discMapper/blob/master/COPYING).

**[^Top](#table-of-contents)**

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/iLPdev/discMapper.svg?style=flat-square
[contributors-url]: https://github.com/iLPdev/discMapper/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/iLPdev/discMapper.svg?style=flat-square
[forks-url]: https://github.com/iLPdev/discMapper/network/members
[stars-shield]: https://img.shields.io/github/stars/iLPdev/discMapper.svg?style=flat-square
[stars-url]: https://github.com/iLPdev/discMapper/stargazers
[issues-shield]: https://img.shields.io/github/issues/iLPdev/discMapper.svg?style=flat-square
[issues-url]: https://github.com/iLPdev/discMapper/issues
[license-shield]: https://img.shields.io/github/license/iLPdev/discMapper.svg?style=flat-square
[license-url]: https://github.com/iLPdev/discMapper/blob/master/LICENSE.txt
[standard-readme-shield]: https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square
[standard-readme-url]: https://github.com/RichardLitt/standard-readme
[product-screenshot]: images/screenshot.png
[mudlet-url]: https://www.mudlet.org

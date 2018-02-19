---
title: Download
layout: main
---

### Installation ###

1. download and extract the zip file to an arbitrary folder
2. start Matlab (version 2012b or newer required - older versions have not been tested)
3. change the current folder in Matlab to the folder where MTEX is installed
4. type `startup_mtex` into the command window
5. click one of the menu items to import data or to consult the documentation

In case you experience any problems have a look at our [trouble shooting page]()

### Downloads ###

File Name  |||  Release Date||| Comments ||| Downloads
:-|-|-|:-|-|-|:-|-|-|-
[**mtex-5.0.0.zip**](https://github.com/mtex-toolbox/mtex/releases/download/mtex-5.0.0/mtex-5.0.0.zip) ||| February 2018 ||| Crystal Shapes and spherical functions, [changelog](files/doc/changelog.html) ||| 2
[**MTEXannotateGUI.zip**](https://groups.google.com/group/mtexmail/attach/e87c480486f4/MTEXannotateGUI.zip?part=0.1&authuser=0) ||| February 2018 ||| graphical user interface for analyzing EBSD data by J. Hiscocks |||
[**mtex-4.5.2.zip**](https://github.com/mtex-toolbox/mtex/releases/download/mtex-4.5.2/mtex-4.5.2.zip) ||| November 2017 ||| 3d orientation and ODF plots, [changelog](files/doc/changelog.html) ||| 4420
[**mtex-4.4.0.zip**](https://github.com/mtex-toolbox/mtex/releases/download/mtex-4.4.0/mtex-4.4.0.zip) ||| January 2017 ||| Slip Systems, Taylor calculation, [changelog](files/doc/changelog.html) ||| 678
[**mtex-4.3.2.zip**](https://github.com/mtex-toolbox/mtex/releases/download/mtex-4.3.2/mtex-4.3.2.zip) ||| July 2016 ||| GND calculation, [changelog](files/doc/changelog.html) ||| 1662
[**mtex-4.2.1.zip**](https://github.com/mtex-toolbox/mtex/releases/download/mtex-4.2.1/mtex-4.2.1.zip) ||| November 2015 ||| introduces triple points, [changelog](files/doc/changelog.html) ||| 1831
[**mtex-4.1.4.zip**](https://github.com/mtex-toolbox/mtex/releases/download/mtex-4.1.4/mtex-4.1.4.zip) ||| September 2015    ||| major release with many new features and syntax changes, [changelog](files/doc/changelog.html) ||| 1132
[__mtex-4.0.23.zip__](https://github.com/mtex-toolbox/mtex/releases/download/mtex-4.0.23/mtex-4.0.23.zip) ||| April 2015    ||| major release with many new features and syntax changes, [changelog](files/doc/changelog.html) ||| 1076
[**mtex-3.5.0.zip**](http://mtex.googlecode.com/files/mtex-3.5.0.zip) ||| December 2013   ||| minor release, [changelog]()||| 2398
[**mtex-3.4.2.zip**](http://mtex.googlecode.com/files/mtex-3.4.2.zip) ||| June 2013       ||| minor release, [changelog]()||| 1660

A full list of previous releases and downloads can be found [here](http://code.google.com/p/mtex/downloads/list).

<script src="js/jquery.min.js"></script>
<script src="js/bootstrap.min.js"></script>
<script src="js/jquery.timeago.js"></script>
<script src="js/jquery.fancybox.pack.js?v=2.1.5"></script>

<script type="text/javascript">
    $(document).ready(function () {
        GetLatestReleaseInfo();
    });

    function GetLatestReleaseInfo() {
        $.getJSON("https://api.github.com/repos/ShareX/ShareX/releases").done(function (json) {
            var release = json[0];
            var asset = release.assets[0];
            var downloadURL = "https://github.com/ShareX/ShareX/releases/download/" + release.tag_name + "/" + asset.name;
            var downloadCount = 0;
            for (var i = 0; i < release.assets.length; i++) {
                downloadCount += release.assets[i].download_count;
            }
            var releaseInfo = release.name + " was updated " + $.timeago(asset.updated_at) + " and downloaded " + downloadCount + " times.";
            $(".sharex-download").attr("href", downloadURL);
            $(".release-info").text(releaseInfo);
            $(".release-info").fadeIn("slow");
        });
    }
</script>

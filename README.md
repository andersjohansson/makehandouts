Forked from <http://doty.math.luc.edu/beamer-handouts>. Instructions below are adapted from there.


# Printing LaTeX Beamer Handouts (Linux or OS X only)

The LaTeX beamer class creates lovely slides for presentations including
overlays, pauses, and other nice effects. And since it is LaTeX, it
handles math, tables, and graphics spectacularly well. However, it is
not so easy in Linux or Mac OS X to format the slides for easy printing,
especially if there are overlays in the slides. (People trying to print
slides with overlays created using LaTeX beamer often find that each
physical slide is printed many times, and moreover there is just one  -
tiny - slide per page, thus wasting an incredible amount of paper.) A
solution to this problem is provided by the tools "pdfnup" which allows
you to put more than one physical slide per printed page, and
"pdfrotate" which allows you to print the slide rotated by 90 degrees
(i.e. in landscape mode). These tools are available in Linux and OS X as
part of the package "pdfjam". If you do not already have these commands
installed on your system, you can install by following Step 0 below;
otherwise, skip to Step 1.

## 0. Installing "pdfjam".
To install pdfjam (on debian or ubuntu) run the command:

    sudo apt-get install pdfjam

from a command line shell. You must have already installed a TeX
distribution.

## 1. Installing the script used to create handouts.
Assuming that you have a working TeX installation ('texlive' is a good choice) and have
installed pdfjam, the script
[here](https://raw.githubusercontent.com/andersjohansson/makehandouts/master/makehandouts)
is useful to create handouts of your beamer slides for easy printing. To
install the script, download it to your computer and make the  file "makehandouts" executable, by typing
the following command:


    chmod +x makehandouts

in a command shell. Move the script "makehandouts" somewhere convenient
in your search path, such as (for example) /usr/local/bin:\


    sudo mv makehandouts /usr/local/bin


(to check what folders are in your search path, do: "echo \$PATH" in a command shell). Installation is now finished.

## 2. Using the script to create handouts
Assuming that you have a LaTeX beamer source file named "xxx.tex" in some folder, in a terminal navigate to that folder and type:

    makehandouts xxx

(note that the file extension is NOT included). Of course, substitute
your *actual* file name in place of "xxx". The 'makehandouts' command
always creates 4 new PDF files, in the following formats:

-   xxx-handout.pdf is a viewable version of your slides, without pauses
    and overlays.\
-   xxx-handout1up.pdf is a printable version of the slides, one slide
    per page, rotated by 90 degrees (in landscape mode) for proper
    printing.\
-   xxx-handout2up.pdf is a printable version of the slides, showing two
    slides per page. \
-   xxx-handout4up.pdf is a printable version of the slides, rotated 90
    degrees to landscape mode, showing four slides per page.

**NOTE:** To print the handouts, choose your desired format and view the
corresponding PDF file using Abode's "acroread" (that tool fits
everything automatically to the page, and other tools are not so good at
doing such). Then print your slides using the print tool from within
acroread.

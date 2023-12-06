# Some notes and tips

## fontawesome

To use the fontawesome pics in the presentation I had to upgrade quarto and install the extension in the presentation directory:

```sh
cd ~/proyectos/codeRs/showcase-your-research/presentation/
quarto install extension quarto-ext/fontawesome
```
## transparent logo


I had to modify the logo image to make the background transparent. I used [ImageMagick](https://stackoverflow.com/questions/12424018/how-to-replace-white-background-color-with-transparent-of-an-image-in-imagemagic):

```sh
cd ~/proyectos/codeRs/showcase-your-research/presentation/
convert  ces-logo.png  -transparent white  ces-logo-transparent.png 
```

## create gifs

Go to the image folder and then use `convert` from image magick

```sh
cd ~/proyectos/codeRs/showcase-your-research/presentation/images 

  
convert -delay 110 -dispose background \
  https://www.r-project.org/Rlogo.png \
  https://s3.dualstack.us-east-2.amazonaws.com/pythondotorg-assets/media/community/logos/python-logo-only.png \
  https://www.rstudio.com/wp-content/uploads/2018/10/RStudio-Logo.png \
  https://jupyter-notebook.readthedocs.io/en/stable/_static/logo-rectangle.svg \
  https://code.visualstudio.com/assets/images/code-stable.png \
 -resize 200x200  -gravity Center -background white -extent 200x200 -loop 0  IDEs.gif
 
convert -delay 120 -dispose background \
 https://download.logo.wine/logo/Microsoft_Office/Microsoft_Office-Logo.wine.png \
 https://wiki.documentfoundation.org/images/6/65/LibreOffice_Initial-Artwork-Logo_ColorLogoBasic_500px.png \
 https://cdn-icons-png.flaticon.com/512/564/564406.png \
 https://www.openoffice.org/marketing/art/galleries/logos/main/aoo4-main-tm-logo-rgb.png \
 -resize 200x200  -gravity Center -background white -extent 200x200 -loop 0  offices.gif
 
```
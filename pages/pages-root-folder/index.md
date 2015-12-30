---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: utahscene1.jpg
widget1:
  title: "About JRJ"
  url: '/about/'
  image: jrj-headshot2015.jpg
  text: "Everything you never wanted to know about Joseph R. Jones but didn't care enough to ask."
widget2:
  title: "What I use"
  url: '/about/what-i-use/'
  image: jrjlaptop.jpg
  text: 'An overview of the tools and toys I love and use. Hardware, software, and more.'
widget3:
  title: "The jrjBlog"
  url: '/blog/'
  image: jrjblog-promo1.png
  text: "JRJ's personal blog, with a focus on security, privacy, technology, and the future."
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
# callforaction:
#   url: https://tinyletter.com/feeling-responsive
#   text: Inform me about new updates and features ›
#   style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---

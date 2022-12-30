---
title: "Introducing Poison"
date: 2022-11-23T13:43:53-06:00
draft: false
categories: ["test"]
tags: ["test"]
---

Poison is a clean, professional Hugo theme designed to captivate your readers.

<!--more-->

I use this theme on my personal site at https://lukeorth.com, so check it out to see Poison in action.

## Features

In addition to the normal features you get with Hugo (standard Built-in templates, shortcodes, etc.), Poison offers some unique features of its own.

- **Light & dark mode** -- Give readers the choice to read in either light or dark mode.  Light mode is the default when visitors first visit your site, but you can change this in your config file.
- **Table of contents** -- Provide readers on a desktop with a floating table of contents.
- **Series** -- Sensibly link and display content that can be grouped into "series" (i.e. *Tutorial One*, *Tutorial Two*, etc.).  
   
   This is accomplished using a custom taxonomy, so just add `series` to the frontmatter on each piece of content you'd like to group together.

    {{< highlight yaml >}}
    ---
    title: "Example to demonstrate how to use series"
    date: 2022-10-04
    draft: false
    series: "How to use poison"
    tags: ["Hugo"]
    ---
    {{</highlight >}}

- **KaTeX** -- Helpful if you intend to use mathematical notations.  

    For block math notations that appear on their own line, use `$$ ... $$`
    
    $$ 5 \times 5 = 25 $$

    For inline math notations that appear on the same line, use `$ ... $`
    
- **Tabs** -- For content that's better viewed using tabs (such as different snippets of computer code), you can create them with the custom shortcodes.
    {{< highlight text >}}
    {{</* tabs tabTotal="2" */>}}

    {{%/* tab tabName="First Tab" */%}}
    This is markdown content.
    {{%/* /tab */%}}

    {{</* tab tabName="Second Tab" */>}}
    {{</* highlight text */>}}
    This is a code block.
    {{</* highlight */>}}
    {{</* /tab */>}}

    {{</* /tabs */>}}
    {{</ highlight >}}
    
    {{< tabs tabTotal="2" >}}

    {{% tab tabName="First Tab" %}}
This is **markdown** content.
    {{% /tab %}}

    {{< tab tabName="Second Tab" >}}
    {{< highlight text >}}
    This is a code block.
    {{</ highlight >}}
    {{< /tab >}}

    {{< /tabs >}}


## Installation

To install Poison as your theme, first clone this repository into your `themes` directory:

{{< highlight text >}}
git clone https://github.com/LukeOrth/poison.git themes/poison --depth=1
{{</highlight >}}

Next, specify `poison` as the default theme in your config.toml file by adding the following line:

{{< highlight text >}}
theme = "poison"
{{</highlight >}}

Lastly, if there are any future updates to this repository that you wish to include in your local copy, you can retrieve these by running:

{{< highlight text >}}
cd themes/poison

git pull
{{</highlight >}}

For more information on how to get started with Hugo and themes, read the official [quick start guide](https://gohugo.io/getting-started/quick-start/).

## How to Configure

After successfully installing Poison, the last step is to configure it.

The best way to start is by copying/pasting the following code into your config.toml file.  Once you see how it looks, play with the settings as needed.

**NOTE**: To display an image in your sidebar, you'll need to uncomment the `brand_image` path below and have it point to your image file.  The path is relative to the `static` directory.  If you don't have an image, just leave this line commented out.

{{< highlight toml >}}
baseURL = "/"
languageCode = "en-us"
theme = "poison"
paginate = 5
pluralizelisttitles = false

[params]
    brand = "Poison"                    # name of your site - appears in the sidebar
    # brand_image = "/images/test.jpg"    # path to the image shown in the sidebar
    dark_mode = true                    # optional - defaults to false

    # Adjust as needed to display your site's menu in the sidebar.
    # Refer to my repo "hydes-poison-demo-site" for an example of how to configure.
    # Options:
        # Name:         The name to display on the menu.
        # URL:          The directory relative to the content directory.
        # HasChildren:  If the directory's files should be listed.  Default is true.
        # Limit:        If the files should be listed, how many should be shown.
    menu = [
        {Name = "About", URL = "/about/", HasChildren = false},
        {Name = "Projects", URL = "/projects/"},
        {Name = "Posts", URL = "/posts/", Pre = "Recent", HasChildren = true, Limit = 5},
    ]

    # Links to your socials.  Delete any you don't need/use. 
    github_url = "https://github.com"
    linkedin_url = "https://linkedin.com"
    twitter_url = "https://twitter.com"
    discord_url = "https://discord.com"
    youtube_url = "https://youtube.com"
    instagram_url = "https://instagram.com"
    facebook_url = "https://facebook.com"

    # Hex colors for your sidebar.
    sidebar_bg_color = "#202020"            # default is #202020
    sidebar_img_border_color = "#515151"    # default is #515151
    sidebar_p_color = "#909090"             # default is #909090
    sidebar_h1_color = "#FFF"               # default is #FFF
    sidebar_a_color = "#FFF"                # default is #FFF
    sidebar_socials_color = "#FFF"          # default is #FFF
    moon_sun_color = "#FFF"                 # default is #FFF
    moon_sun_background_color = "#515151"   # default is #515151

    # Hex colors for your content in light mode.
    text_color = "#222"             # default is #222
    content_bg_color = "#FAF9F6"    # default is #FAF9F6
    post_title_color = "#303030"    # default is #303030
    list_color = "#5a5a5a"          # default is #5a5a5a
    link_color = "#268bd2"          # default is #268bd2
    date_color = "#515151"          # default is #515151

    # Hex colors for your content in dark mode
    text_color_dark = "#eee"            # default is #eee
    content_bg_color_dark = "#121212"   # default is #121212
    post_title_color_dark = "#DBE2E9"   # default is #DBE2E9
    list_color_dark = "#9d9d9d"         # default is #9d9d9d
    link_color_dark = "#268bd2"         # default is #268bd2
    date_color_dark = "#9a9a9a"         # default is #9a9a9a

[taxonomies]
    category = 'categories'
    series = 'series'
    tags = 'tags'
{{</highlight >}}
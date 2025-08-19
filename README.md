# muBooru
The perfect booru
-# (full source code release is TBA)


## What is muBooru?
muBooru (μBooru, uBooru) is a smart image booru software created by KnockupAbyss (me!), with assistance from the lovely folks at Hugging Face, and some schoolmates. The goal of the software is to be sleek, easy to use, very customizable for sysadmins, and it's mostly oriented towards people who have vast libraries of multimedia, like images, animated GIFs, and videos, that they want to share with family, friends, or the public.

## What can it do?
A lot. Here's just some of the highlights:
* Automatic AI tagging and metadata. We're here to make art, not do laundry.
* Reddit-style comment threads, with image/GIF comment support. Discuss your posts with your peers, and have fun while you're at it.
* Easy moderation, with feature locking, reports, and the likes. Ban that annoying kid from school who comments that Lazer Dim 700 picture on every single post.
* Free, open source, and uncensored, with no logging and no ads. Your collection of ramen noodle pictures are private.

## Installation
Easiest installation is through Docker Compose on a Debian-based Linux distro using Supabase for custom function storage.

Before anything, obviously, git clone.
``` git clone https://github.com/knockupabyss/muBooru``` (this isn't gonna work until source release)

### Supabase Config
As muBooru allows users to configure custom functions for APIs like the auto-tagger, you will need a Supabase project to store the edge functions and tables for them.

1. Go to your Supabase dashboard, and create a new project.
2. Edit `src/integrations/supabase/client.ts` with your project URL and secret anon key.
3. Deploy edge functions and database tables. This info is available in `supabase/migrations`.

### Installation via Docker
After setting up databases using Supabase, you should be able to install via Docker Compose, then run using `docker-compose up -d`.

Obviously, before building, make sure you clone the repository and `cd` to it.
```
  docker-compose build --no-cache --pull
  docker-compose up -d
```

After running the app, it will be available at `http://localhost`. If you're on a remote server, it will be your server IP.


## Usage

This should be obvious, but I'll put it here anyway. 

* Upload files by clicking on the big Upload Files box, or dragging files in the box from your file explorer, finder, or any other program you use for browsing files. 
* It will take about 10-20 seconds, maximum about a minute, for each image to be processed fully. If you don't have any auto-tagging function set, it will either attempt to tag using Hugging Face's free Spaces API, or return the tags "uploaded, image". 
* Settings is where you will find everything an image booru website admin could ever need. It's 12:00AM and I'm getting tired so I'll leave this one blank for now. It'll be changed tomorrow.

## Tips
Here's some tips from the developer himself.

* Public instance administrators, please moderate your websites if you don't want a 4chan or soyjak.party reincarnation. Remember, this isn't really just a booru, it has comment threads and a bunch of other social features that make it difficult to moderate on a public instance.
* Have at least surface level knowledge of programming and computer science before you try to do this. Trust me, it's for your own good.
* I will never log any media, comments, or other data from instances not managed by me. Don't try to censor stuff because you think I'll see it and try to take it down.

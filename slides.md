---
theme: envek
title: "Keeping it Ruby: Why Your Product Needs a Ruby SDK"
titleTemplate: '%s - RubyWorld 2024'
layout: cover
background: https://images.unsplash.com/photo-1665686306574-1ace09918530
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
download: true
mdc: true
talkDurationMinutes: 14
progressBarStartSlide: 2
---

# Keeping it Ruby:<br /><small class="text-60%">Why Your Product Needs a Ruby SDK</small>

<div class="absolute bottom-0 left-0 w-full px-10 py-8 grid grid-cols-2 justify-items-stretch items-end gap-4">
  <div class="text-left">
    Sampo Kuokkanen, Andrey Novikov<br />
    <small>Evil Martians</small><br />
    <small><a href="https://2024.rubyworld-conf.org/">RubyWorld Conference 2024</a></small><br />
    <small><time datetime="2024-12-05">05 December 2024</time></small>
  </div>

  <div class="w-28 h-28 object-contain justify-self-end">
    <a href="https://evilmartians.com/"><img alt="Evil Martians" src="/images/01_Evil-Martians_Logo_v2.1_RGB.svg" class="block dark:hidden" /><img alt="Evil Martians" src="/images/02_Evil-Martians_Logo_v2.1_RGB_for-Dark-BG.svg" class="hidden dark:block" /></a>
  </div>
</div>

<style>
  a {
    border-bottom: none !important;
  }
</style>

<!--
Hello world! Or: Hello RubyWorld! Today, we’re diving into why your product needs a Ruby SDK and why Ruby remains a powerful choice for so many of us in 2024 and beyond.
-->

---
title: Speakers
layout: image
image: /images/speakers.jpg
class: two-columns grid grid-cols-[60%_40%] gap-4
---

<div class="col-left">

## Sampo Kuokkanen

- Head of Evil Martians Japan
- Ruby enthusiast
- A fan of imgproxy

</div>
<div class="col-right">

## Andrey Novikov

- Ruby developer at Evil Martians
- Open source enthusiast
- imgproxy early adopter

</div>

<style>
  .slidev-layout {
    text-shadow: 0.2em 0 0.25em black, -0.2em 0 0.25em black, 0 0.2em 0.25em black, 0 -0.2em 0.25em black;
  }

  h2 { font-size: 2em; }

  ul { margin-top: 19em; }
</style>

<!--
I’m Sampo Kuokkanen from Evil Martians, and I’m thrilled to be here today with colleague, and friend Andrey Novikov.

Thanks to Ruby we have been able to afford not Lambos, but a kei car and a 50cc scooter.
-->

---

<a href="https://evilmartians.com/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby">
<img alt="Evil Martians" src="/images/01_Evil-Martians_Logo_v2.1_RGB.svg" class="block dark:hidden object-contain text-center m-auto max-h-100" />
<img alt="Evil Martians" src="/images/02_Evil-Martians_Logo_v2.1_RGB_for-Dark-BG.svg" class="hidden dark:block object-contain text-center m-auto max-h-100" />
</a>

<p class="text-2xl text-center"><a href="https://evilmartians.com">evilmartians.com</a></p>

<!--
Evil Martians is a consultancy that transform growth-stage startups into unicorns, build developer tools, and create open source products.
Evil Martians headquarters are in New York, United States.
-->

---

<a href="https://evilmartians.com/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby">
<img alt="Evil Martians" src="/images/Evil-Martians_Logo_Katakana.svg" class="block dark:hidden object-contain text-center m-auto max-h-100" />
<img alt="Evil Martians" src="/images/Evil-Martians_Logo_Katakana.svg" class="hidden dark:block object-contain text-center m-auto max-h-100" />
</a>

<p class="text-2xl text-center"><a href="https://evilmartians.jp">evilmartians.jp</a>&nbsp;&emsp;</p>

<div class="absolute bottom-64px left-128px rotate-10 text-2xl">邪悪な火星人？</div>
<div class="absolute bottom-64px right-128px rotate-350 text-5xl">🏯</div>

<!--
Evil Martians is also in Japan! We have an office in Osaka! Be sure to contact us if you happen to visit Osaka and are interested in Mars! There are many of us, all year round! So reach out, we are always happy to connect and talk Ruby.
-->

---

# Martian Open Source

<div class="grid grid-cols-4 grid-rows-2 gap-4">
  <a href="https://ruby-next.github.io/">
    <figure>
      <img alt="Ruby Next" src="/images/martian-oss/ruby-next.png" class="object-contain h-32 mx-auto" />
      <figcaption>Ruby Next makes modern Ruby code run in older versions and alternative implementations</figcaption>
    </figure>
  </a>
  <a href="https://github.com/yabeda-rb/yabeda">
    <figure>
      <img alt="Yabeda" src="/images/martian-oss/yabeda.svg" class="object-contain h-32 mx-auto" />
      <figcaption>Yabeda: Ruby application instrumentation framework</figcaption>
    </figure>
  </a>
  <a href="https://github.com/evilmartians/lefthook">
    <figure>
      <img alt="LeftHook" src="/images/martian-oss/lefthook.svg" class="object-contain h-32 mx-auto" />
      <figcaption>Lefthook: git hooks manager</figcaption>
    </figure>
  </a>
  <a href="https://anycable.io/">
    <figure>
      <img alt="AnyCable" src="/images/martian-oss/anycable.svg" class="object-contain h-32 mx-auto" />
      <figcaption>AnyCable: Polyglot replacement for ActionCable server</figcaption>
    </figure>
  </a>
  <a href="https://postcss.org/">
    <figure>
      <img alt="PostCSS" src="/images/martian-oss/postcss.svg" class="object-contain h-32 mx-auto" />
      <figcaption>PostCSS: A tool for transforming CSS with JavaScript</figcaption>
    </figure>
  </a>
  <a href="https://imgproxy.net/">
    <figure>
      <img alt="Imgproxy" src="/images/martian-oss/imgproxy-light.svg" class="object-contain h-32 mx-auto block dark:hidden" />
      <img alt="Imgproxy" src="/images/martian-oss/imgproxy-dark.svg" class="object-contain h-32 mx-auto hidden dark:block" />
      <figcaption>Imgproxy: Fast and secure standalone server for resizing and converting remote images</figcaption>
    </figure>
  </a>
  <a href="https://github.com/DarthSim/overmind">
    <figure>
      <img alt="Overmind" src="/images/martian-oss/overmind.svg" class="object-contain h-32 mx-auto" />
      <figcaption>Overmind: Process manager for Procfile-based applications and tmux </figcaption>
    </figure>
  </a>
  <a href="https://evilmartians.com/oss">
    <figure>
      <div class="h-32 text-2xl flex items-center justify-center">
        <qr-code-vue value="https://evilmartians.com/oss" class="object-contain w-full h-full mx-auto p-4 dark:invert" render-as="svg" margin="1" />
      </div>
      <figcaption style="font-size: 1rem; margin-top: 0; line-height: 1.25rem;">Even more at evilmartians.com/oss</figcaption>
    </figure>
  </a>
</div>

<div v-click class="absolute bottom-32px left-256px rotate-10 text-2xl py-24 px-6 bg-rose-900/25 border border-rose-500">Today's topic</div>

<style>
  a { border-bottom: none !important; }
  figcaption {
    margin-top: 0.5rem;
    font-size: 0.6rem;
    line-height: 1rem;
    text-align: center;
  }
</style>

<!--
At Evil Martians, we’re passionate about open-source. We love to use it, and we also love to give back enhancements to the community. It is a win-win.

Some open source projects have even grown into commercial products, like anycable or imgproxy, still staying open source at their core. [click] And today we will be using imgproxy as an example of a non-Ruby open source product that has a robust Ruby SDK.
-->

---
layout: section
---

# Ruby in 2024: Still Going Strong

<!--
It's almost the end of 2024, but Ruby is still going strong! Let's look at some of the reasons for it.
-->

---
layout: default
---

# Ruby's Continuing Popularity

<div class="grid grid-cols-2 gap-4">
<div>

## RubyGems Downloads
- Over 100 billion total downloads
- Growing year over year
- Active ecosystem

## GitHub Statistics
- Top 10 most popular language!
- Strong in web development
- Active community

</div>
<div>

```mermaid {scale: 0.7}
graph TD
    A[Ruby Ecosystem] --> B[RubyGems]
    A --> C[Rails]
    B --> D[100B+ Downloads]
    D --> H[We Love Gems!]
    C --> E[Startup Favorite]
    A --> F[Active & Friendly Community]
    F --> G[Regular Updates]
    E --> K[Investments!]
```

</div>
</div>

<!--
This slide shows what makes Ruby special. There’s RubyGems, with its ever-growing library of gems, and GitHub stats proving Ruby’s strength in web development. For businesses, this means access to tried-and-tested solutions and a dependable language that gets things done. The startup popularity of Ruby proves that with Ruby, it's possible to move fast!
-->

---
layout: center
class: text-5xl
---

We 💓 Ruby

<!--
Ruby is a beautiful language that allows to write very concise code and develop fast. No surprise it is our language of choice for decades now. We love it.
-->

---
layout: center
class: text-3xl
---

But sometimes it is just not right tool for the job

<!--
But at the same time many of our open source products are written in Go. Performance, memory usage, and concurrency are things that weren't Ruby strengths for the long time. And while Ruby is getting more performant with every release, sometimes it might still worth it to make that trade-off.
-->

---
class: annotated-list
---

# The common problem for any web app

Handling images uploaded by users: profile pictures, product photos, reviews, …

We need to store them and show in various places, of course! And for this we need to:

<v-clicks>

 - Generate thumbnails to save bandwidth

 - Crop to fit design

 - Add watermarks to prevent theft

 - …

</v-clicks>

<!--
As an example of a problem that it is better to “offload” let's take a look at handling of images uploaded by users. Many webapps have to get pictures from users. And, of course, not only one need to receive images, but also then display them back in various forms back to users. And even now in year 2024 it is a bad idea to let browsers download original images just to show them in some list downsized to a size of a thumb.

So one need to [click] resize them, [click] crop if their aspect ratio differs from desired, [click] add watermarks, [click] strip sensitive metadata (like gps coordinates), [click] et cetera, et cetera.
-->

---
class: annotated-list
layout: two-cols-header
---

# “Classic” way

::left::

<v-clicks>

  - Upload image to the server

    Probably among other form fields

  - Store it somewhere

    Often on S3 or other cloud storage

  - Generate all required thumbnails

    As many as your design requires

  - Store them somewhere

    Again S3 or other cloud storage

  - Serve them to the user

    CDN will help here

</v-clicks>

::right::

```mermaid
sequenceDiagram
    User->>Server: Uploads Image
    Server->>Storage: Stores Image
    Server->>JobQueue: Queues Job
    Server->>User: Upload successful
    User->>Server: Requests thumbnail
    Server->>Storage: Retrieves Thumbnail
    Storage-->>Server: There are no thumbnails yet!
    Server->>User: “Image is processing”
    activate JobQueue
    Note over JobQueue: Job<br/>started
    Storage->>JobQueue: <br/>Retrieve image
    Note over JobQueue: Generates<br>thumbnail
    deactivate JobQueue
    User->>Server: Requests thumbnail
    Server->>ImageStorage: Retrieves Thumbnail
    ImageStorage->>Server: Oh yes, of course, here it is
    Server->>User: Returns thumbnail
```

<div v-click="3" class="absolute bottom-260px right-120px rotate-10 text-xs p-1 bg-rose-900/25 border border-rose-500 text-center">Unpredictable<br/>latency<br/>here</div>

<!--
And there is kind of traditional way of doing it:

 - [click] upload image to the server,
 - [click] store it,
 - [click] generate all required thumbnails,
 - [click] store them also,
 - [click] and finally serve them to the user.
-->

---
class: annotated-list
---

# Problems of “classic” approach

<v-clicks>

 - Hard to predict latency: **background jobs can queue**

   It can take a while to get your image processed, and “image is processing” fallbacks are ugly

 - Hard to add new variants: **need to reprocess all images**

   Possibly millions of jobs to run before enabling it on the front-end

 - And hard to clean up old ones

   Space is cheap, but not free

 - Deployment: **gets complicated**

   You need to install ImageMagick or libvips on all servers/containers

 - Security: **it is your headache**

   Processing images on your servers is a security and stability risk,
   e.g. [PNG decompression bomb](https://www.bamsoftware.com/hacks/deflate.html).

</v-clicks>

<!--
And this way is long and full of dangers:

 - [click] preparing all variants takes time, background jobs can queue, and that means latency.
 - [click] adding new images means having to process them **prior** to displaying
 - [click] does anyone ever clean up old unneeded variants?
 - [click] And oh yes, you need to install imagemagick or libvips to your servers and containers, too.
 - [click] And it is also security risk, as you need to process images on your servers, so any script kid can do a Denial of Service by uploading a PNG bomb to your application server.
-->

---
layout: cover
class: text-center
---

# Do we have to do things this way?

What if we could _just_ generate thumbnails on the fly?

<!--
But to be honest, even if we got used to this approach, it is not the only one. Do things have to be this way? NO!!! What if we could just generate thumbnails on the fly?
-->

---
layout: two-cols-header
---

# Meet image processing servers

::left::

They do just one thing, but do it well

There are many of them:

 - [imaginary](https://github.com/h2non/imaginary)
 - [thumbor](https://www.thumbor.org)
 - [cloudinary](https://cloudinary.com/)
 - [imgix](https://www.imgix.com/)
 - [imagor](https://github.com/cshum/imagor)
 - [**imgproxy**](https://imgproxy.net/) (our favorite ✨)

::right::


```mermaid
sequenceDiagram
    participant User
    participant Server
    participant Storage
    participant imgproxy

    User->>Storage: Uploads Image
    User->>Server: Notifies about upload
    Server->>User: Thumbnail URL
    User->>imgproxy: Requests thumbnail
    activate imgproxy
    Storage->>imgproxy: Retrieves image
    Note over imgproxy: generate thumbnail<br>on the fly
    imgproxy->>User: Respond with thumbnail
    deactivate imgproxy
```

<!--
And there are such services, they are called image processing servers. All they do is taking away burden of image processing from you and your application servers.

As you can see, application server doesn't have to even pass images through itself, all it needs to know is a source image URL.
-->

---
class: annotated-list
---

# Solving it with on-the-fly processing

<v-clicks>

 - Complexity: **replace your code with a microservice**

   Throw away all these background jobs, and replace them with a simple URL construction.

 - Latency: **dedicated service that do only images processing**

   Very performant per se, and you can scale it independently from your main application, also add CDN in front of it

 - Adding new variants: **just construct new URL**

   Construct new URL, request it, done!

 - Cleaning up old ones: **let CDN caches to expire**

   Do you really need to store thumbnails at all? Care only for originals.

 - Security and stability: **it is separate from your main application**

   It handles image bombs, and other nasty stuff, but even if some malicious code will be executed, it will find itself in empty Docker container without anything in it.

</v-clicks>

<!--
All pains are gone them:

[click] It is much simpler. Throw away all the code made for image processing, all background jobs, and server provision recipes. Deploy a microservice from a single docker image instead.

[click] Latency is gone. No more backed up queues/ Craft URL when you need it, browser makes a request and gets its thumbnail mostly instantly.

[click] You want new thumbnail variant? Just construct new URL, request it, let CDN to cache it, done!

[click] Removing old variants? You just don't! Let CDN caches to expire. Care only for originals.

[click] Security is also isn't your headache anymore. Even if some malicious code will be executed, it will find itself in an empty Docker container.
-->

---
class: text-2xl annotated-list
---

## Which one to choose?

<v-clicks>

 - Should it be one _written_ in Ruby?

   But if it is a dedicated service, does it matter?

   Maybe it is better to choose most performant one?

 - Should it be one that is **easy to use from Ruby**?

   What are you looking first for when choosing a new dependency?

</v-clicks>

<!--
But which one to choose for a Ruby app?
[click]
Should it be one written in the same language? But if it is a dedicated service, does it matter?
[click]Maybe it is better to choose the one that is the most easy to use from a Ruby app?
-->

---
layout: center
class: text-5xl
---

# Is there a gem?

of course there is!{.text-xl}

<!--
What is the first thing a Ruby developer looks into when choosing which service to integrate with? We all know the answer: A Ruby gem to add into Gemfile!
-->

---
layout: image-right
class: text-sm annotated-list relative
image: /images/imgproxy-website.png
---

# Introducing imgproxy

<div class="absolute right-0 top-10">
<img alt="Imgproxy" src="/images/martian-oss/imgproxy-light.svg" class="object-contain h-32 mx-auto block dark:hidden" />
<img alt="Imgproxy" src="/images/martian-oss/imgproxy-dark.svg" class="object-contain h-32 mx-auto hidden dark:block" />
</div>


- Open source image processing server
- Written in Go and C for performance
- Uses libvips for optimal image processing
- Dockerized and easy to deploy
- Most Ruby-friendly solution[^1]
- Started at Evil Martians
- Used by companies big and small:<br>Bluesky, dev.to, Photobucket, eBay, …<br><a href="https://bsky.app/profile/inazarova.bsky.social/post/3lc3745dvg22q"><logos-bluesky class="w-16 h-16" /></a>


[^1]: There is a gem! Two of them!

<style>
  a { border-bottom: none !important; }
  .footnotes-sep { margin-top: 3em; margin-bottom: 1em; }
  .footnotes { font-size: 0.8em; }
</style>

<!--
Let me introduce to you imgproxy. Imgproxy started its life at Evil Martians, but it is now an independent start-up. It allows you to process your images on-the-fly, without needing to do the dance of creating multiple versions of each uploaded image for different screen sizes, it uses modern libvips library with specifically crafted processing pipeline to optimize for maximum throughput and minimal memory consumption. It is pretty popular already, used by many companies, big and small, established and new, and we recently learned that Bluesky social app also uses imgproxy. Maybe in the future it could be integrated with Mastodon too? And, most important, as it was initially made in a Ruby-centric company for a Ruby on Rails project, it has exceptional Ruby client library from the day one. So there is a gem! Even two of them!
-->

---
layout: cover
---

# But why gem?

What value it brings to both product owners and users?

<!--
Now let's step back a bit and talk about what benefits making a Ruby gem will give to both you as a product creator and to your users. And of course we will use imgproxy ruby gem as an example.
-->

---
class: text-sm
---

## Technical example: URL signing

The only thing a client need to care about is constructing URLs to images processed through imgproxy.

Given original image URL:

```txt {all}{class:'!children:text-sm'}
https://mars.nasa.gov/system/downloadable_items/40368_PIA22228.jpg
```

Result URL to get 300×150 thumbnail for Retina displays, smart cropped, and saturated, with watermark in right bottom corner:

```txt {all|6|3-4|2|all}{class:'!children:text-sm'}
https://demo.imgproxy.net/
doqHNTjtFpozyphRzlQTHyBloSoYS13lLuMDozTnxqA/
rs:fill:300:150:1/dpr:2/g:ce/sa:1.4/
wm:0.5:soea:0:0:0.2/wmu:aHR0cHM6Ly9pbWdwcm94eS5uZXQvd2F0ZXJtYXJrLnN2Zw/
plain/
https:%2F%2Fmars.nasa.gov%2Fsystem%2Fdownloadable_items%2F40368_PIA22228.jpg
```

See https://docs.imgproxy.net/generating_the_url


<Arrow v-click="3" x1="780" y1="320" x2="500" y2="330" />
<div v-click="3" class="absolute top-310px right-60px">Digital signature</div>

<Arrow v-click="2" x1="755" y1="345" x2="475" y2="355" />
<div v-click="2" class="absolute top-335px right-60px">Processing options</div>

<Arrow v-click="1" x1="760" y1="370" x2="450" y2="400" />
<div v-click="1" class="absolute top-360px right-60px">Original image URL</div>

<!--
From the technical point of view, let's take a look at the main part of interaction with a image processing service: generating an URL to an image.

This is a simple process:
[click] First of all, we take address of the original image, URL-encode it, and place at the end of the result URL.
[click] Then we add processing options: what size it should be, how it should be cropped, what filters to apply, et cetera
[click] Finally, we calculate a digital signature of both the options and the original URL, so no one can use our image processing for their needs for free.
[click] And that's it!
-->

---
transition: slide-left
---

### Plain Ruby implementation

It is easy to implement yourself (for one specific use case)

```ruby {7-18|8-9|11|12-15|17|all}{class:'!children:text-xs'}
require 'base64'
require 'openssl'

key = ['943b421c9eb07c83...'].pack('H*')
salt = ['520f986b998545b4...'].pack('H*')

def generate_url(url, width, height)
  encoded_url = Base64.urlsafe_encode64(url).tr('=', '')
  encoded_url = encoded_url.scan(/.{1,16}/).join('/')

  path = "/resize:fill:#{width}:#{height}/#{encoded_url}"
  hmac = OpenSSL.hmac(
    OpenSSL::Digest.new('sha256'), key, "#{salt}#{path}"
  )
  signature = Base64.urlsafe_encode64(hmac).tr('=', '')

  "http://imgproxy.example.com/#{signature}#{path}"
end

url = generate_url("http://example.com/image.jpg", 300, 400)
```

<!--
Crafting this URL isn't hard. It is pretty simple. So simple, in fact, code that implementing it can fit one slide.

[click]Take and encode the original URL, [click] add processing options, [click] calculate a digital signature, [click] done!

[click]And for you, as author of the product, there will be a temptation to skip the whole packaging step and just provide this code as an example in your README: dear user, copy and paste this into your project and call it a day.
-->

---
transition: slide-left
---

### With imgproxy gem

But always better to use a battle-tested library that will hide all gory details

```ruby {all}{at:1,class:'!children:text-sm'}
require 'imgproxy'

Imgproxy.configure do |config|
  # Full URL to where your imgproxy lives.
  config.endpoint = "http://imgproxy.example.com"
  # Hex-encoded signature key and salt
  config.key = '943b421c9eb07c83...'
  config.salt = '520f986b998545b4...'
end
```
```erb {all}{at:1,class:'!children:text-sm'}
<%# show.erb.html %>
<%= image_tag Imgproxy.url_for(
  "http://images.example.com/images/image.jpg",
  width: 500,
  height: 400,
  resizing_type: :fill
) %>
```

<qr-code url="https://github.com/imgproxy/imgproxy.rb" caption="imgproxy.rb gem" class="w-36 absolute bottom-48px right-60px" />

<!--
But client library doesn't only provide an url helper. It also provides convenience. Hide implementation details from the user, provide an interface to configure itself. Client library can be updated, bringing bug fixes and new features. Even if it feels small, there is always a value into providing a conventional method of distribution to your users.
-->

---
layout: default
---

## ActiveStorage + imgproxy

What is even better: to use familiar API and don't change your codebase!

```ruby {all}{class:'!children:text-sm'}
# Gemfile
gem 'imgproxy-rails'
```

```ruby {all}{class:'!children:text-sm'}
# development.rb: use built-in Rails proxy
config.active_storage.resolve_model_to_route = :rails_storage_proxy

# production.rb: use imgproxy
config.active_storage.resolve_model_to_route = :imgproxy_active_storage
```

```erb {all}{class:'!children:text-sm'}
<%# show.erb.html %>
<%= image_tag Current.user.avatar.variant(resize: "100x100") %>
```

You don't even have to know that you are using imgproxy! ✨

And you can migrate the whole application to imgproxy in an hour!

<qr-code url="https://github.com/imgproxy/imgproxy-rails" caption="imgproxy-rails gem" class="absolute w-36 bottom-48px right-48px" />

<!--
And then you can go on a higher level: integrate with frameworks and then, if application is using framework built-in image handling, like ActiveStorage in Rails, you can hook into its URL generation, and this will allow to make migration to your product almost instant. Plug in, configure, and it just works. Feels like magic!
-->

---
layout: quote
---

## Let the community speak

<blockquote class="my-8">

I clicked the button, deployed the OSS version and hooked up **the imgproxy.rb ruby gem** in my app in under an hour.

Within a few weeks, we had switched over all of our upload, template, and graphic previews to Imgproxy…

Doing so resulted in the **removal of hundreds of lines of code** while also **enabling new functionality**.

</blockquote>

<div class="mr-36">

— **John Nunemaker**: Ruby programmer and founder, author of flipper and httparty gems{.text-sm.tracking-tighter}

  https://www.johnnunemaker.com/imgproxy/
</div>

<qr-code url="https://www.johnnunemaker.com/imgproxy/" caption="Imgproxy is Amazing" class="w-36 absolute bottom-48px right-48px" />

<style>
  blockquote p {
    font-size: 1.5rem;
    line-height: 1.5em;
  }
  blockquote p + p {
    margin-top: 1em;
  }
</style>

<!--
And users will appreciate all this: speed, simplicity, convenience of the client API. It won't go unnoticed. And if other services are ordinary ones, yours in comparison will be so good, people will want to scream of joy, like John Nunemaker did who wrote a whole blog post about his experience with imgproxy.
-->

---
layout: section
class: text-lg
---

# Why to “keep it Ruby?”

Why to spend time and effort to provide official Ruby SDK?

<v-click class="mt-10">
Answer is in this quote from the previous slide:

<blockquote class="my-8">

I clicked the button, deployed the OSS version and hooked up the imgproxy.rb ruby gem in my app <span v-mark.orange="{ at: 2 }" class="font-bold">in under an hour</span>.

</blockquote>

It wouldn't be possible without a ready to use Ruby gem!
</v-click>

<style>
  blockquote p {
    font-size: 1.5rem;
    line-height: 1.5em;
  }
  blockquote p + p {
    margin-top: 1em;
  }
</style>

<!--
So the answer to the question about why keeping your product Ruby-friendly is… [click] convenience and [click] speed. If it is so easy to integrate the product into existing apps, it means that you almost certainly will get new customers.
-->

---
layout: center
class: text-4xl text-center
---

Keeping your product Ruby-friendly

={class="text-8xl"}

more customers, happier customers

<!--
A new happy customers of your product! And that's great.

We'd like to reiterate that expressiveness of Ruby allows nice, natural integration of anything to a Ruby application!
-->

---

# Keep it Ruby! Thank you!

<div class="grid grid-cols-[8rem_3fr_4fr] mt-12 gap-2">

<div class="justify-self-start">
<img alt="Imgproxy" src="/images/martian-oss/imgproxy-light.svg" class="object-contain h-32 mx-auto block dark:hidden" />
<img alt="Imgproxy" src="/images/martian-oss/imgproxy-dark.svg" class="object-contain h-32 mx-auto hidden dark:block" />
</div>

- <logos-github-icon class="dark:invert" /> [@imgproxy](https://github.com/imgproxy/)
- <logos-twitter /> [@imgproxy_net](https://twitter.com/imgproxy_net)
- <logos-mastodon-icon /> <span v-mark.orange="{ at: 2 }">[@imgproxy<span class="text-sm tracking-tight">@mastodon.social</span>](https://mastodon.social/@imgproxy?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)</span>
- <logos-bluesky /> [@imgproxy.net](https://bsky.app/profile/imgproxy.net)

<div>
<qr-code url="https://imgproxy.net/" caption="imgproxy.net" class="w-32 my-2" />
</div>

<div class="justify-self-start">
<a href="https://evilmartians.com/"><img alt="Evil Martians" src="/images/01_Evil-Martians_Logo_v2.1_RGB.svg" class="w-32 h-32 object-contain block dark:hidden" /><img alt="Evil Martians" src="/images/02_Evil-Martians_Logo_v2.1_RGB_for-Dark-BG.svg" class="w-32 h-32 object-contain hidden dark:block" /></a>
</div>

<div>

- <logos-github-icon class="dark:invert" /> [@evilmartians](https://github.com/evilmartians?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)
- <logos-twitter /> [@evilmartians](https://twitter.com/evilmartians/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)
- <logos-mastodon-icon /> <span v-mark.orange="{ at: 2 }">[@evilmartians<span class="text-sm tracking-tight">@mastodon.social</span>](https://mastodon.social/@evilmartians?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)</span>
- <logos-bluesky /> [@evilmartians.com](https://bsky.app/profile/evilmartians.com?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)
</div>

<div>
<qr-code url="https://evilmartians.com/" caption="evilmartians.com" class="w-32 my-2" />
</div>

<div class="col-span-3">

Our awesome blog: <span v-mark.orange class="font-bold">[evilmartians.com/chronicles](https://evilmartians.com/chronicles/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)</span>!

<p class="text-sm">See these slides at <a href="https://envek.github.io/rubyworld-keep-it-ruby/">envek.github.io/rubyworld-keep-it-ruby</a></p>

</div>
</div>

<style>
  ul a { border-bottom: none !important; }
  ul { list-style-type: none !important; }
  ul li { margin-left: 0; padding-left: 0; }
</style>

<!--
Keep your non-Ruby products to be Ruby-friendly, and we will be happy to help you with that!

[click]
Please check out Evil Martians blog, we have a lot of interesting blog posts about Ruby, Rails, frontend, design, open-source and other things. Many of them have been translated into Japanese.

[click]
Also check out our social accounts (including Mastodon!), to know first about new blog posts.

And thank you very much for your attention! ご清聴ありがとうございました！
-->

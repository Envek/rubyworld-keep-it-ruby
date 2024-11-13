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

---
layout: two-cols-header
---

# Speakers

::left::

### Andrey Novikov
<img src="https://github.com/Envek.png" class="rounded-full w-32 mb-4">

- imgproxy early adopter
- Ruby & Go developer at Evil Martians
- Open source enthusiast

::right::

### Sampo Kuokkanen
<img src="https://github.com/sampokuokkanen.png" class="rounded-full w-32 mb-4">

- A fan of imgproxy
- Head of Evil Martians Japan
- Ruby enthusiast

<!--
Hello, world! Or: Hello, RubyWorld! I’m Sampo Kuokkanen from Evil Martians, and I’m thrilled to be here today with Andrey Novikov. Today, we’re diving into why your product needs a Ruby SDK and why Ruby remains a powerful choice for so many of us in 2024 and beyond. At Evil Martians, we’re passionate about open-source projects that genuinely make a difference, and we’ll show you how they can make your life much easier! And today's example could even save you money.
-->

---

<a href="https://evilmartians.com/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby">
<img alt="Evil Martians" src="/images/01_Evil-Martians_Logo_v2.1_RGB.svg" class="block dark:hidden object-contain text-center m-auto max-h-100" />
<img alt="Evil Martians" src="/images/02_Evil-Martians_Logo_v2.1_RGB_for-Dark-BG.svg" class="hidden dark:block object-contain text-center m-auto max-h-100" />
</a>

<p class="text-2xl text-center"><a href="https://evilmartians.com">evilmartians.com</a></p>

<!--
Evil Martians transform growth-stage startups into unicorns, build developer tools, and create open source products.
Evil Martians is located in New York, United States of America.
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
Evil Martians is also in Japan! We have an office in Edobori, Osaka! The Japanese office is also growing, we are soon going to have our sixth member join us. Be sure to contact us if you happen to visit Osaka and are interested in Mars! Unfortunately, we do not yet have an office in Shimane, but maybe some day.
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
One thing that we truly love is Open Source. We love to use it, and we also love to give back enhancements to the community. We eager to share results of our work as a ruby gem or npm package, it will help us in the first place to re-use our own solutions, and we can help others to solve their problems and often we will get feedback or patches back. It is a win-win.

And for many years we've created literally over a hundred of open source products, big and small, famous and not so. Very probably your application already depends on a few martian Ruby gems, so check out your Gemfile and count how many of them you have.

Some open source products have even grown into commercial products, like anycable or imgproxy, still staying open source at the time. [click] And today we will talk about imgproxy.
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
layout: image-right
image: https://images.unsplash.com/photo-1635776062127-d379bfcba9f8
---

# Introducing imgproxy

- Open source image processing server
- Written in Go and C for performance
- Dockerized and easy to deploy
- Perfect for Ruby applications
- On-the-fly image processing
- Cost-effective solution

<!--
Now, to understand the technical points Andrey is going to tell you about, let me introduce to you imgproxy. Imgproxy started its life at Evil Martians, but it is now its own company, Foxes With Matches Inc. It allows you to process your images on-the-fly, without needing to do the dance of creating multiple versions of each uploaded image for different screen sizes.
-->

---
class: annotated-list
---

# But I'm happy with my current setup!

<v-clicks>

 - Complexity: **where to store, how to process**

   You need to store all those versions, and process them in background jobs. This is a lot of code.

 - Latency: **background jobs can queue**

   It can take a while to get your image processed, need to display some placeholder meanwhile.

 - Create new variants: **a lot to do**!

   When you have millions of uploads, that means re-download all those original files and generate that new version in a million of millions backrounds jobs.

 - Clean up old unneeded ones: **do you even have a plan?**

   When you have millions of uploads, that means you have millions of files that are not used anymore.

 - Security and stability: **what if image processing go wrong?**

   Where your images are being processed? What if someone uploads a bomb image? Will it crash your main application?

</v-clicks>

---
class: annotated-list
---

# How imgproxy solves this

<v-clicks>

 - Complexity: **replace your code with a microservice**

   Throw away all these backround jobs, and replace them with a simple URL construction.

 - Latency: **Dedicated service that do only images processing**

   Very performant per se, and you can scale it independently from your main application, also add CDN in front of it

 - Adding new variants: **Just construct new URL**

   Construct new URL, request it, done!

 - Cleaning up old ones: **Let CDN caches to expire**

   Do you really need to store thumbnails at all? Care only for originals.

 - Security and stability: **it is separate from your main application** 

   It handles image bombs, and other nasty stuff, but even if some malicious code will be executed, it will find itself in empty Docker container without anything in it.

</v-clicks>

---
layout: default
---

# Traditional image processing vs imgproxy

<div class="grid grid-cols-2 gap-4">

<div>
<h3>Traditional approach</h3>

```ruby {all}{class:'!children:text-sm'}
# Heavy background jobs
class ProcessImageJob < ApplicationJob
  def perform(image)
    image
      .variant(resize: "800x600")
      .processed
  end
end
```

- Overall complexity
- Server storage needed
- Background processing (latency!)
- Higher infrastructure costs
</div>

<div>
<h3>imgproxy approach</h3>

```erb {all}{class:'!children:text-sm'}
<%# On-the-fly processing %>
<img src="<%=
  Imgproxy.url_for(
    'http://images.example.com/images/image.jpg',
    width: 500,
    height: 400,
    resizing_type: :fill
 )
%>">
```

- No storage needed
- Instant processing
- CDN-friendly
</div>

</div>

---
layout: quote
---

## Let the community speak

<blockquote class="my-8">

I clicked the button, deployed the OSS version and hooked up **the imgproxy.rb ruby gem** in my app in under an hour.

Within a few weeks, we had switched over all of our upload, template, and graphic previews to Imgproxy…

Doing so resulted in the **removal of hundreds of lines of code** while also **enabling new functionality**.

</blockquote>

— John Nunemaker: https://www.johnnunemaker.com/imgproxy/

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

```txt {1-6|2|3-4|6}{class:'!children:text-sm'}
https://demo.imgproxy.net/
doqHNTjtFpozyphRzlQTHyBloSoYS13lLuMDozTnxqA/
rs:fill:300:150:1/dpr:2/g:ce/sa:1.4/
wm:0.5:soea:0:0:0.2/wmu:aHR0cHM6Ly9pbWdwcm94eS5uZXQvd2F0ZXJtYXJrLnN2Zw/
plain/
https:%2F%2Fmars.nasa.gov%2Fsystem%2Fdownloadable_items%2F40368_PIA22228.jpg
```

See https://docs.imgproxy.net/generating_the_url


<Arrow v-click="1" x1="780" y1="320" x2="500" y2="330" />
<div v-click="1" class="absolute top-310px right-60px">Digital signature</div>

<Arrow v-click="2" x1="755" y1="345" x2="475" y2="355" />
<div v-click="2" class="absolute top-335px right-60px">Processing options</div>

<Arrow v-click="3" x1="760" y1="370" x2="450" y2="400" />
<div v-click="3" class="absolute top-360px right-60px">Original image URL</div>


---
transition: slide-left
---

### Plain Ruby implementation

It is easy to implement yourself (for one specific use case)

```ruby {all}{class:'!children:text-xs'}
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

---
transition: slide-left
---

### With imgproxy gem

But always better to use a battle-tested library that will hide all gory details

```ruby {all|none|all}{at:1,class:'!children:text-sm'}
require 'imgproxy'

Imgproxy.configure do |config|
  # Full URL to where your imgproxy lives.
  config.endpoint = "http://imgproxy.example.com"
  # Hex-encoded signature key and salt
  config.key = '943b421c9eb07c83...'
  config.salt = '520f986b998545b4...'
end
```
```erb {none|all|all}{at:1,class:'!children:text-sm'}
<%# show.erb.html %>
<%= image_tag Imgproxy.url_for(
  "http://images.example.com/images/image.jpg",
  width: 500,
  height: 400,
  resizing_type: :fill
) %>
```

<qr-code url="https://github.com/imgproxy/imgproxy.rb" caption="imgproxy.rb gem" class="w-36 absolute bottom-48px right-60px" />

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


---
layout: center
class: text-4xl text-center
---

Keeping your product Ruby-friendly

={class="text-8xl"}

more customers, happier customers

---

# Keep it Ruby! Thank you!

<div class="grid grid-cols-[8rem_3fr_4fr] mt-12 gap-2">

<div class="justify-self-start">
<img alt="Imgproxy" src="/images/martian-oss/imgproxy-light.svg" class="object-contain h-32 mx-auto block dark:hidden" />
<img alt="Imgproxy" src="/images/martian-oss/imgproxy-dark.svg" class="object-contain h-32 mx-auto hidden dark:block" />
</div>

- <logos-github-icon class="dark:invert" /> [@imgproxy](https://github.com/imgproxy/)
- <logos-twitter /> [@imgproxy_net](https://twitter.com/imgproxy_net)
- <logos-linkedin-icon /> [@imgproxy](https://www.linkedin.com/company/imgproxy)

<div>
<qr-code url="https://imgproxy.net/" caption="imgproxy.net" class="w-32 my-2" />
</div>

<div class="justify-self-start">
<a href="https://evilmartians.com/"><img alt="Evil Martians" src="/images/01_Evil-Martians_Logo_v2.1_RGB.svg" class="w-32 h-32 object-contain block dark:hidden" /><img alt="Evil Martians" src="/images/02_Evil-Martians_Logo_v2.1_RGB_for-Dark-BG.svg" class="w-32 h-32 object-contain hidden dark:block" /></a>
</div>

<div>

- <logos-github-icon class="dark:invert" /> [@evilmartians](https://github.com/evilmartians?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)
- <logos-twitter /> [@evilmartians](https://twitter.com/evilmartians/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)
- <logos-linkedin-icon /> [@evil-martians](https://www.linkedin.com/company/evil-martians/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)
- <logos-instagram-icon class="dark:invert" /> [@evil.martians](https://www.instagram.com/evil.martians/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)
</div>

<div>
<qr-code url="https://evilmartians.com/" caption="evilmartians.com" class="w-32 my-2" />
</div>

<div class="col-span-3">

Our awesome blog: [evilmartians.com/chronicles](https://evilmartians.com/chronicles/?utm_source=rubyworld&utm_medium=slides&utm_campaign=keep-it-ruby)!

<p class="text-sm">See these slides at <a href="https://envek.github.io/rubyworld-keep-it-ruby/">envek.github.io/rubyworld-keep-it-ruby</a></p>

</div>
</div>

<style>
  ul a { border-bottom: none !important; }
  ul { list-style-type: none !important; }
  ul li { margin-left: 0; padding-left: 0; }
</style>

<!--
That's it! Please check out Evil Martians blog, we have a lot of interesting blog posts about Ruby, Rails, frontend, design and other things.
-->

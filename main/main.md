!SLIDE big x009900

<script>
  $(".x009900").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#003300", border: "none", color: "#33cc66"});
    $("body").css({backgroundColor: "#003300"});
    $("#footer").css({backgroundColor: "#007700", color: "#003300"});
  });
  
  $(".x009900").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#33cc66", color: "white"});
    $("body").css({backgroundColor: "#33cc66"});
    $("#footer").css({backgroundColor: "#22cc55", color: "#009900"});
  });
</script>

# Where's the love? #


!SLIDE

# C extensions have become unpopular in recent years. Why? #


!SLIDE

# Ruby code is portable #

## (read: across platforms, and interpreters/VMs) ##


!SLIDE bullets incremental left transition=scrollLeft small wheres_the_love_03

<script>
    // bind to custom event
    wtl03_counter = 0;
    $(".wheres_the_love_03").bind("showoff:next", function (event) {
      wtl03_counter++;
      var wtl03_einr = $(event.target).find("#wtl03_einr");
      if (wtl03_counter==3) {
        event.preventDefault();
        wtl03_einr.css({display: "inline"});
      }
    });
</script>

* Patching, monkey-patching, debugging are difficult
* "Self-documenting code"... <span id="wtl03_einr" style="display: none; font-size: 1.1em; font-weight: bold;">except it's not Ruby!</span>


!SLIDE bullets incremental center transition=scrollLeft small

# Common Concerns:<br />/<span style="opacity: 0.5;">((monkey-)?</span>patch<span style="opacity: 0.5;">|debugg)</span>ing/ #

## if C extension, then presumably so for a reason ##


!SLIDE bullets incremental center small

# Common Concerns:<br />/<span style="opacity: 0.5;">((</span>monkey-<span style="opacity: 0.2;">)?</span>patch<span style="opacity: 0.5;">|debugg)</span>ing/ #

## <i>tweaking</i> a method's functionality <i>is</i> difficult <!-- (String#*) --> ##


!SLIDE bullets incremental center small

# Common Concerns:<br />/<span style="opacity: 0.5;">((monkey-)?patch|</span>debugg<span style="opacity: 0.5;">)</span>ing/ #

## A Rubyist now needs to debug C ##


!SLIDE bullets incremental left transition=scrollLeft small

# Common Concerns: Documentation #

* In a C extension, <b>code is not self-documenting</b>.
* Rubyists should not be expected to know C in order to discover what a method does, or how it does what it does. (`Range#to_s`)
* The common solution is documenting code in methods, and including RDoc-style comments (which YARD now respects) (`String#capitalize!`)


!SLIDE small xcccc33

<script>
  $(".xcccc33").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#cccc33", border: "none", color: "#333333"});
    $("body").css({backgroundColor: "#cccc33"});
    $("#footer").css({backgroundColor: "#ffff00", color: "#666666"});
  });
  
  $(".xcccc33").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#003300", color: "#33cc66"});
    $("body").css({backgroundColor: "#003300"});
    $("#footer").css({backgroundColor: "#007700", color: "#003300"});
  });
</script>

# Literature Example #

## Rubinius ##


!SLIDE transition=scrollLeft small rur

<script>
    rur_counter = 0;
    $(".rur").bind("showoff:next", function (event) {
      rur_counter++;
      var rur_01 = $(event.target).find("#rur_01");
      var rur_02 = $(event.target).find("#rur_02");
      var rur_03 = $(event.target).find("#rur_03");
      var rur_04 = $(event.target).find("#rur_04");
      var rur_05 = $(event.target).find("#rur_05");
      if (rur_counter==1) {
        event.preventDefault();
        rur_01.fadeTo( 200, 0.1);
        rur_02.fadeTo( 400, 0.1);
        rur_03.fadeTo( 600, 0.1);
        rur_04.fadeTo( 800, 0.1);
        rur_05.fadeTo(1000, 0.1);
      }

      if (rur_counter==2) {
        event.preventDefault();
        rur_02.fadeTo(500, 1.0);
      }

      if (rur_counter==3) {
        event.preventDefault();
        rur_03.fadeTo(500, 1.0);
      }

      if (rur_counter==4) {
        event.preventDefault();
        rur_04.fadeTo(500, 1.0);
      }
    });

    $(".rur").bind("showoff:prev", function (event) {
      rur_counter = 0;
    });
</script>

## <span id="rur_01">"A large aspect of popular languages such as C and Java is that the majority of the functionality available to the programmer is written in the language itself. Rubinius has the goal of adding Ruby to that list. Rubyists could more easily</span> <span id="rur_02" style="border-bottom: solid 3px black;">add features to the language,</span> <span id="rur_03" style="border-bottom: solid 3px black;">fix bugs,</span> <span id="rur_04" style="border-bottom: solid 3px black;">and learn how the language works.</span> <span id="rur_05">Wherever possible Rubinius is written in Ruby. Where not possible (yet), it's C++."</span> ##


!SLIDE center transition=scrollLeft small

# Literature Example #

## 10th Ed of Pickaxe ##

!SLIDE center transition=scrollLeft small

## "... The extension API is less relevant than it was, partly because the extensions you'll need have already been written..." ##


!SLIDE center transition=scrollLeft

# Valid Concerns #


!SLIDE center transition=scrollLeft

# Which is why most Ruby code is not written as a C extension, duh. #


!SLIDE center transition=scrollLeft

# However, sometimes the speed or existing-C-code benefits outweigh these concerns. #


!SLIDE center biggish xffffff_2

<script>
  $(".xffffff_2").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#ffffff", border: "none", color: "#000099"});
    $("body").css({backgroundColor: "#ffffff"});
    $("#footer").css({backgroundColor: "#eeeeee", color: "#000066"});
  });
  
  $(".xffffff_2").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#cccc33", color: "#333333"});
    $("body").css({backgroundColor: "#cccc33"});
    $("#footer").css({backgroundColor: "#ffff00", color: "#666666"});
  });
</script>

# Recent C Extensions #
# Ruby5 #


!SLIDE center transition=scrollLeft

<!-- Oct 19: -->
# TinyTDS #

## A modern, simple and fast FreeTDS library for Ruby using DB-Library ##


!SLIDE center transition=scrollLeft

<!-- Dec 10: -->
# Summarize #

## C Bindings for Open Text Summarizer ##


!SLIDE center transition=scrollLeft

<!-- Dec 14: -->
# RGeo #

## (you know, one of those... geographic libraries) ##


!SLIDE center transition=scrollLeft

<!-- Dec 17: -->
# <img src="../cool.io.png" /> #

## Node.Js-style Event-Driven Awesomeness ##
## (C bindings for libev) ##


!SLIDE center transition=scrollLeft

<!-- Jan 11: -->

# Streamly #

## a streaming REST client for Ruby,<br />using libcurl ##


!SLIDE center transition=scrollLeft

<!-- Jan 18: -->
# io_splice #

## exposes Linux's zero-copy function: splice() ##


!SLIDE center transition=scrollLeft small

<!-- Jan 21: -->
# HandlerSocket #

## "The NoSQL MySQL" ##
## Ruby extensions: <span style="white-space: nowrap;">ruby-handlersocket</span>, handlersocket ##


!SLIDE bullets incremental center transition=scrollLeft small

<!-- Jan 28: -->
# <img src="../gosu.png" /> #

* Gaming library
* C++ extension
* Chipmunk physics engine (Ruby bindings)
* ruby-gl (a C extension) to add 3D.


!SLIDE center transition=scrollLeft

# Mentions in Preston Lee's #

## "Ruby Supercomputing: Using The GPU For Massive Performance Speedup" ##


!SLIDE biggish xffffbb

<script>
  $(".xffffbb").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#ffffbb", border: "none", color: "#663333"});
    $("body").css({backgroundColor: "#ffffbb"});
    $("#footer").css({backgroundColor: "#ffff99", color: "#aa7777"});
    
    $(event.target).find("#tlc_don01").fadeTo(10, 0.0);
    $(event.target).find("#tlc_don02").fadeTo(10, 0.0);
    $(event.target).find("#tlc_don03").fadeTo(10, 0.0);

    var tlc_don01 = $(event.target).find("#tlc_don01");
    $(event.target).find("#tlc_don01").delay(600).fadeTo(50, 1.0);
    $(event.target).find("#tlc_don02").delay(900).fadeTo(50, 1.0);
    $(event.target).find("#tlc_don03").delay(1200).fadeTo(50, 1.0);
  });
  
  $(".xffffbb").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#ffffff", color: "#000099"});
    $("body").css({backgroundColor: "#ffffff"});
    $("#footer").css({backgroundColor: "#eeeeee", color: "#000066"});
  });
</script>

# The last big concern #

## <span id="tlc_don01" style="opacity: 0.0;">Don</span> <span id="tlc_don02" style="opacity: 0.0;">Don</span> <span id="tlc_don03" style="opacity: 0.0;">Don</span> ##


!SLIDE bullets incremental transition=scrollLeft ul-inline

# Are C extensions portable? #

<ul>
  <li><span class="littlebigcaps">Yes</span></li>
  <li><span class="littlebigcaps">*</span></li>
</ul>

* (but really, just think of that as a Yes)


!SLIDE bullets incremental left transition=scrollLeft small

# What's the <span style="color: red; font-size: 1.6em;">*</span> all about? #

* I'll ask one back: What does "portability" mean?
* 1\. Portability across "platforms"
* 2\. Portability across Ruby VMs / interpreters


!SLIDE bullets incremental left transition=scrollLeft small are_c_exts_portable_across_oss

<script>
    $(".are_c_exts_portable_across_oss").bind("showoff:show", function (event) {
      acepao_counter = 0;
      $(event.target).find("#acepao_wtf01").fadeTo(100, 0.0);
    });
    
    $(".are_c_exts_portable_across_oss").bind("showoff:next", function (event) {
      acepao_counter++;
      var acepao_wtf01 = $(event.target).find("#acepao_wtf01");
      if (acepao_counter==3) {
        event.preventDefault();
        acepao_wtf01.fadeTo(100, 1.0);
      }
    });
</script>

<h1 style="font-size: 4em;">Are C extensions portable <i>across OS's</i>?</h1>

<h2 style="text-decoration: underline;">Where is Ruby code portable?</h2>

* Ruby 1.9.2's NEWS file:
* **Supported:** Debian GNU/Linux <span style="font-size: 0.7em; font-weight: bold;">H</span>a IA32 <span id="acepao_wtf01" style="color: red; opacity: 0.0;">WTF?
* **Efforts made for:** `/(x64-)mswin(32|64)|mingw32/`; Mac OS X 10.5 (Intel), 10.6; FreeBSD 6+ (amd64, IA32); Solaris 10; Symbian OS.
* **Efforts made for:** Other Linux; Other OS X; cygwin; AIX 5; Other POSIX-compatible; BeOS (Haiku).


!SLIDE

# Are C extensions portable <i>across OS's</i>? #


!SLIDE bullets incremental left transition=scrollLeft small wiietcce

<script>
  wiietcce_counter = 0;

  $(".wiietcce").bind("showoff:show", function (event) {
    wiietcce_01 = $(event.target).find("#wiietcce_01");
    wiietcce_02 = $(event.target).find("#wiietcce_02");
    wiietcce_03 = $(event.target).find("#wiietcce_03");
    wiietcce_04 = $(event.target).find("#wiietcce_04");
    wiietcce_05 = $(event.target).find("#wiietcce_05");
    wiietcce_06 = $(event.target).find("#wiietcce_06");
    wiietcce_07 = $(event.target).find("#wiietcce_07");
    wiietcce_08 = $(event.target).find("#wiietcce_08");

    if (wiietcce_counter != 0) {
      wiietcce_counter = 0;
      wiietcce_02.css({top: wiietcce_02.offset().top-40}).fadeTo( 10, 0.0);
      wiietcce_04.fadeTo( 10, 0.0);
      wiietcce_05.css({top: wiietcce_05.offset().top-40}).fadeTo( 10, 0.0);
      wiietcce_06.css({top: wiietcce_06.offset().top-40, left: wiietcce_06.offset().left-135}).fadeTo( 10, 0.0);
      wiietcce_08.css({top: wiietcce_08.offset().top-40}).fadeTo( 10, 0.0);
    }
  });
  
  $(".wiietcce").bind("showoff:next", function (event) {
    wiietcce_counter++;
    if (wiietcce_counter == 2) {
      event.preventDefault();
      wiietcce_02.css({top: wiietcce_02.offset().top+40}).fadeTo(100, 1.0);
    }
    if (wiietcce_counter == 5) {
      event.preventDefault();
      wiietcce_04.fadeTo(100, 1.0);
    }
    if (wiietcce_counter == 6) {
      event.preventDefault();
      wiietcce_05.css({top: wiietcce_05.offset().top+40}).fadeTo(100, 1.0);
    }
    if (wiietcce_counter == 7) {
      event.preventDefault();
      wiietcce_06.css({top: wiietcce_06.offset().top+40, left: wiietcce_06.offset().left+135}).fadeTo(100, 1.0);
    }
    if (wiietcce_counter == 10) {
      event.preventDefault();
      wiietcce_08.css({top: wiietcce_08.offset().top+40}).fadeTo(400, 0.7);
    }
  });
</script>

# Where is it easy<br />to compile C extensions? #

* **Dead-fracking-simple:** <span id="wiietcce_01" style="position: absolute;">Linux (um, _any_, duh);</span> <span id="wiietcce_02" style="opacity: 0.0; position: absolute;">OS X (Xcode)</span>
* 
* **Um... I imagine dead-simple?** <span id="wiietcce_03" style="position: absolute;">FreeBSD; <span id="wiietcce_04" style="opacity: 0.0;">Solaris 10;</span></span> <span id="wiietcce_05" style="opacity: 0.0; position: absolute;">Symbian OS;</span> <span id="wiietcce_06" style="opacity: 0.0; position: absolute;">AIX 5+</span>
* 
* **Actually... also pretty simple:** <span id="wiietcce_07" style="position: absolute;">Windows*</span> <span id="wiietcce_08" style="font-size: 0.6em; opacity: 0.0; position: absolute;">(we'll get to that asterisk...)</span> 


!SLIDE acepao02

<script>
  $(".acepao02").bind("showoff:show", function (event) {
    $(event.target).find("#acepao02_01").css({opacity: 0.0});
    $(event.target).find("#acepao02_01").delay(800).fadeTo(500, 1.0);
  });
</script>

# Are C extensions portable <i>across OS's</i>? #

<h2 id="acepao02_01" style="opacity: 0.0;">Answer: Anywhere Ruby + a decent C compiler can be found</h2>


!SLIDE bullets incremental left transition=scrollLeft small

# Ok, now what is _that_ * for??? #

* Windows requires a few more steps (but is easier than using Xcode the first time, IMHO).
* 1\. Install Ruby via the RubyInstaller, or pik (think: RVM for Windows).
* 2\. Install DevKit, a "sane" enviroment for building C extensions (based on MinGW and MSYS).
* 3\. Install rake-compiler. 


!SLIDE bullets incremental left transition=scrollLeft

<h1 style="font-size: 4em;">Are C extensions portable <i>across interpreters/VMs</i>?</h1>

* Rubinius
* JRuby
* MacRuby
* <span style="opacity: 0.5;">IronRuby</span>
* MagLev


!SLIDE bullets incremental left transition=scrollLeft

# Rubinius #

* Requirements: gcc, g++ 4.x, bison, mri 1.8.7+, rubygems, git, ZLib, pthread, gmake, rake
* 1.0: Supports ... popular C extensions: ... sqlite3, mysql, nokogiri, yajl-ruby"
* 1.0.1: "The C-API support is extended to [support] gherkin, curb, rjb/buildr..."
* 1.2.0: 5 big bug fixes to C-API


!SLIDE bullets incremental left transition=scrollLeft

# JRuby #

* binaries for: OS X, Linux, BSD, Solaris, other UNIX, Windows(, maybe HP-UX)
* 1.6.0 RC1: "ships C extension support prebuilt for OS X"
* 1.6.0 RC2: "C extension support prebuilt for OS X, Linux (32/64), Windows (32)"
* 1.6.0 RC3: "More platforms with pre-built C extension support" (OpenBSD amd64?)


!SLIDE bullets incremental left transition=scrollLeft

# MacRuby #

* (Apr 30, '10) 0.6 release: "MacRuby 0.6 provides support for C extensions written for the original implementation of ruby. We were able to successfully use the Nokogiri, SQLite3 and PostgreSQL extensions from MacRuby."
* (Oct 1, '10) 0.7 release: "Better C extensions support."


!SLIDE bullets incremental left transition=scrollLeft smaller

# MagLev #

* @maglev (Mar 4, '11): "MagLev is still alpha. It will become beta after we finish C extensions. Beta target is end of March."
* @pbmclain (Mar 4, '11): "MagLev Nokogiri test results: 1040 tests, 2177 assertions, 4 failures, 4 errors, 1 skips"
* @maglev (Mar 4, '11): "MagLev-25375 released. Improvements in C-extensions"
* @jc00ke (Mar 5, '11): "C-ext support in @maglev! Hell yeah!!!"
* @maglev (Mar 13, '11): "MagLev 25439 is out... Improves C-Extension support."


!SLIDE biggish x000000_02

<script>
  $(".x000000_02").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#000000", border: "none", color: "white"});
    $("body").css({backgroundColor: "#000000"});
    $("#footer").css({backgroundColor: "#222222", color: "#999999"});
  });
  
  $(".x000000_02").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#ffffbb", color: "#663333"});
    $("body").css({backgroundColor: "#ffffbb"});
    $("#footer").css({backgroundColor: "#ffff99", color: "#aa7777"});
  });
</script>

# WTF does all of that<br />amount to? #


!SLIDE big

# The Punchline #


!SLIDE biggish

# C-extension-portable #
# = #
# Ruby-portable #


!SLIDE

# The State of C Extensions: #


!SLIDE 

# Not a dying breed among Ruby libraries #


!SLIDE

# Highly portable #


!SLIDE

# When used pragmatically, #
# Incredibly useful! #


!SLIDE bullets left

## Sam Rawlins ##

* Twitter: @srawlins
* Email: sam.rawlins@gmail.com
* Github: LMGTFY github srawlins
* No C extensions were used to make this presentation


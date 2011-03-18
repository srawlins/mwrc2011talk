!SLIDE title-slide

# MountainWest RubyConf 2011 #

## The State of C Extensions: ##

## Alive and Well, Deal with It ##


!SLIDE bullets left small whoami

<script>
$(".whoami").bind("showoff:show", function (event) {
  limit = 60*27;
  $('#footer').append('<span id="timer" style="float: right; font-size: 0.6em;"></span>');
  $('#timer').everyTime(1000, function(i) {
    remaining = limit - i;
    mins = Math.floor(remaining / 60);
    secs = remaining % 60;
    
    if (secs == 0) {
      $(this).css({fontWeight: "bold"});
    } else if (secs == 58) {
      $(this).css({fontWeight: "normal"});
    }
    
    if (mins == 2) if (secs == 0) {
      $(this).css({color: "red"})
    }
    
    if (Math.floor(secs/10) == 0) { secs = "0"+secs; }
    $(this).html(mins + ":" + secs);
  });
});
</script>

# Who am I? #

## Sam Rawlins ##

* Twitter: @srawlins
* Email: sam.rawlins@gmail.com
* Github: LMGTFY github srawlins
* Claims to Fame in the Ruby Community: none really
* Claims to Fame, Otherwise: um... none again


!SLIDE bullets incremental left smaller x4499ff

<script>
  $(".x4499ff").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#4499ff", border: "none"});
    $("body").css({backgroundColor: "#4499ff"});
    $("#footer").css({backgroundColor: "#55aaff", color: "#555555"});
  });
  
  $(".x4499ff").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "white"});
    $("body").css({backgroundColor: "white"});
    $("#footer").css({backgroundColor: "#eeeeee", color: "#000000"});
  });
</script>

# Quickly, Quickly: What's a "C Extension"? #


!SLIDE small

# MRI <span style="font-size: 0.5em;">(first implementation of Ruby)</span> is written in C #

!SLIDE transition=scrollLeft

# Many lower-level libs #
# are written in C #

!SLIDE bullets incremental left transition=scrollLeft big

* Fixnum
* Bignum
* String
* Hash

!SLIDE transition=scrollLeft

# Fixnum is older than my grandpa. #

!SLIDE bullets left transition=scrollLeft biggish

* 1.9.2 methods like `Array#keep_if`
* 1.9.2 methods like `Dir.home`
* 1.9.2 class: Fiber


!SLIDE transition=scrollLeft

# Ruby must be able to "talk to" the expansive world of C libraries. #


!SLIDE transition=scrollLeft

# Ruby C Extension API #


!SLIDE bullets incremental transition=scrollLeft favorite_gems

<script>
    // bind to custom event
    fg_counter = 0;
    

    
    jQuery.fn.center = function () {
      return this.each(function() {
        var rent = $(this).parents('.slide');
        var top = (rent.height() - $(this).outerHeight()) / 2;
        var left = (rent.width() - $(this).outerWidth()) / 2;
        $(this).css({position:'absolute', margin:0, top: top+'px', left: left+'px'});
      });
    }


    
    $(".favorite_gems").bind("showoff:next", function (event) {
      fg_counter++;
      var fg_mysql = $(event.target).find("#fg_mysql");
      var fg_pg = $(event.target).find("#fg_pg");
      var fg_sqlite3_ruby = $(event.target).find("#fg_sqlite3_ruby");
      var fg_ruby_oci8 = $(event.target).find("#fg_ruby_oci8");
      var fg_ibm_db = $(event.target).find("#fg_ibm_db");
      var fg_dbi = $(event.target).find("#fg_dbi");
      if (fg_counter == 2) {
        fg_mysql.fadeTo(300, 1.0).center().animate({left: "+=280", top: "-=65"}, 600);
        fg_pg.delay(           400).fadeTo(300, 1.0).center().animate({left: "+=180", top: "+=0"}, 600);
        fg_sqlite3_ruby.delay( 800).fadeTo(300, 1.0).center().animate({left: "-=200", top: "+=0"}, 600);
        fg_ruby_oci8.delay(   1200).fadeTo(300, 1.0).center().animate({left: "-=300", top: "-=65"}, 600);
        fg_ibm_db.delay(      1600).fadeTo(300, 1.0).center().animate({left: "-=200", top: "-=130"}, 600);
        fg_dbi.delay(         2000).fadeTo(300, 1.0).center().animate({left: "+=180", top: "-=130"}, 600);
      }
    });
</script>

# Some favorite gems are C extensions #

* <span style="position: aabsolute;">`/.*sql.*/`</span><span id="fg_mysql" style="opacity: 0.0; position: absolute;">mysql</span><span id="fg_pg" style="opacity: 0.0; position: absolute;">pg</span><span id="fg_sqlite3_ruby" style="opacity: 0.0; position: absolute;">sqlite3-ruby</span><span id="fg_ruby_oci8" style="opacity: 0.0; position: absolute;">ruby-oci8</span><span id="fg_ibm_db" style="opacity: 0.0; position: absolute;">ibm-db</span><span id="fg_dbi" style="opacity: 0.0; position: absolute;">DBI</span>
* 
* Nokogiri
* JSON
* FastThread


!SLIDE bullets incremental left transition=scrollLeft

# RubyGems.org #

* 21911 gems | ~415 extensions
* Of top 100 most downloaded, 18 are C extensions


!SLIDE left transition=scrollLeft

# Top 10 Most Downloaded #

<p style="font-size: 2.6em;">
1. sqlite3-ruby<br />
2. nokogiri<br />
3. json<br />
4. mysql<br />
5. fastthread<br />
6. eventmachine<br />
7. hpricot<br />
8. ffi<br />
9. gherkin<br />
10. mongrel
</p>


!SLIDE biggish x663300

<script>
  $(".x663300").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#663300", border: "none", color: "white"});
    $("body").css({backgroundColor: "#663300"});
    $("#footer").css({backgroundColor: "#552200", color: "#996600"});
  });
  
  $(".x663300").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#4499ff", color: "black"});
    $("body").css({backgroundColor: "#4499ff"});
    $("#footer").css({backgroundColor: "#55aaff", color: "#555555"});
  });
</script>

# Motivations for Writing a C Extension #


!SLIDE transition=scrollLeft

# &gt; 95% of C Extensions #
# are motivated by: #


!SLIDE transition=scrollLeft big

# 1. Speed #


!SLIDE transition=scrollLeft biggish

# 2. Bridge to an existing C library #


!SLIDE transition=scrollLeft

# Many C extensions are a mix of both #

# zlib #
# nokogiri #


!SLIDE center transition=scrollUp small x000000

<script>
  $(".x000000").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#000000", border: "none", color: "white"});
    $("body").css({backgroundColor: "#000000"});
    $("#footer").css({backgroundColor: "#222222", color: "#999999"});
  });
  
  $(".x000000").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#663300", color: "white"});
    $("body").css({backgroundColor: "#663300"});
    $("#footer").css({backgroundColor: "#552200", color: "#996600"});
  });
</script>

# I am Not a C Extension Nazi. #


!SLIDE center transition=scrollLeft small

# I am a Rubyist. #


!SLIDE bullets incremental left transition=scrollLeft

# Sidenote #

* For any anti-monolingual nazis
<li style="font-size: 0.4em;">(Zed)</li>
<li style="font-size: 0.4em;">A lot of people, actually</li>


!SLIDE center transition=scrollLeft

# How do I define 'Rubyist'? #


!SLIDE transition=scrollLeft

# As a Rubyist, #
# I try program in Ruby #
# > 50% of the time #


!SLIDE center transition=scrollLeft small

# I am a Rubyist. #


!SLIDE transition=scrollLeft small this_is_why

<script>
  $(".this_is_why").bind("showoff:show", function (event) {
    var tiw_if = $(event.target).find("#tiw_if");
    var tiw_tiw = $(event.target).find("#tiw_tiw");
    var tiw_isce = $(event.target).find("#tiw_isce");
    var tiw_tertmce = $(event.target).find("#tiw_tertmce");
    tiw_if.delay(800).fadeTo('fast', 1.0);
    tiw_tiw.delay(1400).fadeTo('fast', 1.0);
    tiw_isce.delay(2000).fadeTo('fast', 1.0);
    tiw_tertmce.delay(3000).fadeTo(400, 1.0);
  });
</script>

<div id="tiw_if"   style="opacity: 0.0; font-size: 3.8em; text-align: left;">In fact</div>
<div id="tiw_tiw"  style="opacity: 0.0; text-align: center; width: 65%;"><span style="border-bottom: solid 4px #FF0000; font-size: 5.0em; font-weight: bold;">this is why</span></div>
<div id="tiw_isce" style="opacity: 0.0; font-size: 3.8em; text-align: right;">I support C extensions</div><br /><br />

<div id="tiw_tertmce" style="opacity: 0.0;">
  <h1>They expose Ruby</h1>
  <h1>to more computing ecosystems.</h1>
</div>

!SLIDE x33cc66

<script>
  $(".x33cc66").bind("showoff:show", function (event) {
    $(".slide").css({backgroundColor: "#33cc66", border: "none", color: "white"});
    $("body").css({backgroundColor: "#33cc66"});
    $("#footer").css({backgroundColor: "#22cc55", color: "#009900"});
  });
  
  $(".x33cc66").bind("showoff:prev", function (event) {
    $(".slide").css({backgroundColor: "#000000", color: "white"});
    $("body").css({backgroundColor: "#000000"});
    $("#footer").css({backgroundColor: "#222222", color: "#999999"});
  });
</script>

# I try to be pragmatic. #


!SLIDE transition=scrollLeft

# Pragmatic C Extensions #


!SLIDE bullets incremental transition=scrollLeft

# Chunky PNG #

* --->
* <span style="font-size: 1.6em;">OilyPNG</span>


!SLIDE smaller transition=scrollLeft cpvsop

<script>
  cpvsop_counter = 0;
  $(".cpvsop").bind("showoff:next", function (event) {
    cpvsop_counter++;
    var pre = $(event.target).find("pre");
    var h2 = $(event.target).find("h2");
    var cpvsop_01 = $(event.target).find("#cpvsop_01");
    var cpvsop_02 = $(event.target).find("#cpvsop_02");
    var cpvsop_03 = $(event.target).find("#cpvsop_03");
    var cpvsop_04 = $(event.target).find("#cpvsop_04");
    var cpvsop_05 = $(event.target).find("#cpvsop_05");
    
    if (cpvsop_counter == 1) {
      event.preventDefault();
      cpvsop_01.fadeOut(600);
      cpvsop_03.delay(400).fadeOut(600);
      cpvsop_05.delay(800).fadeOut(600);
    }
    
    if (cpvsop_counter == 2) {
      event.preventDefault();
      pre.animate({fontSize: "3.6em"}, 800);
    }
    
    if (cpvsop_counter == 3) {
      event.preventDefault();
      h2.fadeTo(200, 1.0);
    }
  });
</script>

<h1 style="font-size: 7em;">Chunky PNG vs OilyPNG</h1>

<pre><code><span id="cpvsop_01">---------------------------------------------
ChunkyPNG (0.10.2) decoding benchmark (n=20)
---------------------------------------------</span><span id="cpvsop_02">
                         ChunkyPNG      OilyPNG</span><span id="cpvsop_03">
PNG - no filtering      ( 1.056832)  ( 0.078345)  (13.6 x)
PNG - UP filtering      ( 3.327986)  ( 0.078387)  (42.7 x)</span><span id="cpvsop_04">
PNG - PAETH filtering   ( 7.499367)  ( 0.089143)  (84.3 x)</span><span id="cpvsop_05">
From RGBA pixelstream   ( 0.032571)  ( 0.035790)  ( 0.92x)
From RGB pixelstream    ( 0.221163)  ( 0.226358)  ( 0.98x)</span></code></pre><br /><br />

<h2 style="font-size: 7em; opacity: 0.0;">More than 80x as fast!</h2>


!SLIDE

# Pragmatic C Extensions #


!SLIDE bullets incremental big transition=scrollLeft

# JSON #

* Two variants


!SLIDE bullets incremental transition=scrollLeft code big

* **gem install json**

* **gem install json_pure**


!SLIDE bullets incremental transition=scrollLeft code biggish

# **require 'json'** #

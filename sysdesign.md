##v1:

Search in video
0:00
Hey everyone and welcome back to the
0:02
channel. Uh for those of you who are new
0:03
here, my name is Jordan. I'm a Google
0:05
software engineer and uh in today's
0:07
video I will be beginning my refactored
0:10
systems design interview series. So uh I
0:13
am absolutely a hypocrite for this in
0:15
the sense that I said I didn't want to
0:17
make redundant content on my channel. Uh
0:19
but at the same time um one of the
0:22
biggest pieces of feedback that I
0:23
received in my last series was that even
0:25
though the content was very rich uh I
0:27
often didn't give a lot of visual aid
0:30
and uh trust me you know I understand
0:32
that visual aid is very important you
0:34
know for example try you know doing your
0:36
thing without hub or something it would
0:37
be real tough so with all these things
0:40
in mind um you know I've acquired an
0:42
iPad I don't really know how to use it
0:44
very well my drawing skills are very bad
0:46
and my hands are shaky but uh you know
0:48
worse Worst comes to worse, the iPad is
0:50
going to make certain parts of my life a
0:52
lot easier. And uh yeah, my ultimate
0:54
goal is to make content on this channel
0:57
that is pretty much as good as all those
0:58
paid courses from these grifting tech
1:00
YouTubers. Uh with the exception that it
1:03
is completely free. In fact, I hope to
1:06
make it better because uh yeah, you
1:08
know, I'm just going to try and do a
1:09
really really thorough deep dive on
1:10
everything. And unlike my last series
1:12
that I kind of made, I'm hoping to even
1:14
do smaller chunks per video for a couple
1:16
of reasons. One is that it's more
1:18
digestible and the other reason is that
1:20
I'm a lazy [ __ ] and I don't like editing
1:22
that much. And so I figure that, you
1:24
know, it's a win-win for the both of us
1:26
if this series takes a little bit longer
1:27
by doing less per video. So with that
1:30
all being said, if you're new here or if
1:32
you're new to systems design in general,
1:34
I think this series will be super useful
1:36
for you. It really does cover a lot. So,
1:38
you know, expect to learn a lot and uh
1:40
you know, this is a great time to start
1:41
learning because the economy is in a
1:43
downturn at the moment, but in 6 months
1:45
to a year when this series is finished,
1:47
you know, jobs are probably going to be
1:49
pretty hot again and uh you're going to
1:52
want to get a refresh on that RSU price.
1:54
So, all those things being considered,
1:56
uh let's jump into it. we can go ahead
1:58
and do a little example of what systems
2:01
design kind of means or is or the
2:02
considerations that you might have on
2:04
the iPad and I will do my best to make
2:07
it understandable for all of you. Uh
2:09
have a happy new year and let's get into
2:10
it. All right, let's go ahead and get
2:13
into this. So to kind of frame the
2:15
systems design interview as a problem,
2:18
it's basically something like this.
2:20
You're a website. You are perhaps even
2:22
just an internal infrastructural service
2:24
with a lot of usage, right? So much so
2:26
to the point that just storing
2:28
everything on one machine is not
2:31
sufficient anymore. And so let's give an
2:33
example of that. So here I am drawing
2:36
myself on screen. As you can see, I've
2:39
drawn myself to figure absolutely jacked
2:41
and muscular. So this is me and in the
2:44
context of a website like a social media
2:46
website, let's say Facebook for example,
2:48
I am what is known as the client. I make
2:51
requests to the servers of the social
2:53
media website and in exchange I expect
2:56
data. So let's go ahead and show that
2:59
tradeoff. Here I am drawing a nice
3:01
little arrow and then if we're talking
3:03
about Facebook for example, here is the
3:06
Facebook application server which will
3:08
probably be located in one of their data
3:11
centers. So now what I'm asking for from
3:13
Facebook is some data. At some point I
3:15
probably stored something like a profile
3:17
picture there. I stored some information
3:19
about myself or my past posts and I want
3:22
to get it back from them. If Facebook
3:23
didn't store this data in the first
3:25
place, how could they possibly leak it?
3:27
So, here we go. And we have these
3:29
Facebook servers. And so, the question
3:31
is now uh kind of one of the ways that I
3:34
want to start thinking about these
3:35
problems is where do we actually store
3:37
the data? So, before we even think of,
3:39
you know, what servers we store the data
3:41
on, let's think about what hardware we
3:43
store the data on. So when it comes to
3:45
uh data in general and computers, there
3:48
are two basic places that you can put
3:49
it. And one is RAM. You know, it looks
3:52
like a little long rectangular
3:55
skinny dick chip. And that is good for
3:58
random access or basically it's short
4:00
for random access memory, but it's good
4:01
for temporary storage of data.
4:05
You know, that's where we do our
4:06
computations when we're coding. If
4:07
you're writing like a for loop, you're
4:08
adding a couple numbers. Uh technically,
4:11
you know, a lot of that's going on in
4:12
CPU registers, but eventually it's going
4:14
to get stored uh with the variables and
4:16
RAM. And in addition to that, we have
4:18
our HDD or our hard drive. And so this
4:22
is you, I'm sure you've seen this
4:23
before, looks almost like an iPad, but
4:25
with a nice little skinny metal disc in
4:28
the middle and then this kind of pointer
4:30
which points to a specific part of the
4:32
disc. Again, pardon my bad drawing
4:34
skills. And the good thing about hard
4:36
drives is that can actually permanently
4:39
store data at least in the sense that
4:42
the hard drive itself is not broken or
4:44
you know other extenduating
4:45
circumstances. So when we are actually
4:47
going to store data for a company like
4:49
Facebook, we want to obviously put that
4:51
on the hard drive. Why? Because servers
4:52
can shut down at any given time. You
4:54
know, maybe someone unplugs the power
4:55
and if that were to happen, we don't
4:57
want to lose the data. Of course, you
4:58
know, hard drives can be broken too and
5:00
we have to think about more than that.
5:01
But uh at least for now, let's just
5:03
think we're storing our data on this
5:05
hard drive. And that's going to be a
5:07
little bit slower than RAM, but we'll
5:09
touch upon this in future episodes. This
5:10
is mainly just for an introduction. So
5:12
the next question is what computer do we
5:14
actually put uh this data on? Every
5:16
computer has a hard drive, but which
5:18
computer is the one actually holding the
5:19
data? Should it be the Facebook
5:21
application server? Well, actually the
5:23
answer is probably not. And why is this?
5:26
Well, for starters, the Facebook
5:28
application server is not just talking
5:30
to me. it's talking to a bunch of other
5:32
people right here are all these other
5:34
betas throughout the world. Even though
5:36
I'm the alpha, unfortunately, I have to
5:38
contact the same servers as them. And so
5:40
eventually there going to be so many
5:42
people that just one application server
5:44
to talk to all these people isn't going
5:45
to be enough. I'm actually going to need
5:47
more. And so, you know, we've got all
5:49
these other servers. And if we were to
5:52
actually store, you know, my specific
5:54
profile data on the original server, now
5:57
that's going to be a problem because
5:58
when these guys go ahead and contact
6:00
other servers, they're not actually
6:02
going to be able to see their data.
6:04
They're not going to have access to it.
6:06
And so, in this sense, we want our data
6:08
itself to be scalable in a way that is
6:10
separate from our application servers.
6:13
the application servers or at least the
6:14
user requests to application servers
6:17
typically becomes a bottleneck to the
6:18
performance of our website before the
6:21
actual accessing of the data does. Uh
6:24
typically that's because there's things
6:25
like caching where we can temporarily
6:27
store some of the data on these servers
6:29
and you know that that makes things
6:30
easier. But again this is all stuff
6:32
we're going to get into later. So what
6:33
we really want to be doing instead is
6:35
basically having one other computer in
6:38
the background. You'll see I'll draw it
6:39
as this cylinder here. And this is what
6:41
I'll call a database.
6:44
The database is only responsible for
6:46
being basically the sole source of truth
6:48
of all of that profile data, post
6:50
history, all of these things. And now
6:52
application servers can go ahead and
6:54
just ask the database for specific data
6:57
about profiles, my users, all my
6:59
Facebook history, etc., etc., etc.
7:02
This is completely oversimplified,
7:04
right? The truth of the matter is when
7:05
you have so many users, even one
7:07
database isn't going to be enough,
7:08
right? We could make the computer that
7:10
the database is located on more
7:12
powerful, but eventually even that's not
7:14
good enough. There's simply just too
7:15
many humans in the world. And so the
7:17
main kind of point of systems design is
7:20
how can we make the fetching and storing
7:21
of this data faster both in reads and
7:25
writes and more reliable. What do I mean
7:27
by more reliable? I mean fault tolerant.
7:31
What if I were to unplug the computer
7:32
that the database was on? Now I could
7:35
never fetch my post history because all
7:36
these application servers would fail to
7:38
contact the database. So what that means
7:41
is we have to come up with ways to
7:43
basically have backups. If there's too
7:45
much data for one database, we may have
7:46
to actually split the data into multiple
7:48
databases and be smart about that. And
7:51
again, pretty much all of this just
7:53
arises from complications of having tons
7:55
and tons of users on these massive
7:57
websites.
7:59
And so in order to kind of first tackle
8:01
the problem of covering all of these
8:03
systems design interview tips, I prefer
8:05
to kind of start with the inside out in
8:08
the sense that I'm going to start from
8:09
the database and slowly slowly move
8:11
towards kind of the client layer, right?
8:13
Going to the application servers,
8:15
thinking about caching, things like
8:16
that. And if you know what those terms
8:18
mean, that's great. If you don't, no
8:20
worries. We're going to learn all of
8:21
them and it's going to take a while, but
8:23
ultimately it will be well worth it. So
8:25
guys, thank you for watching the first
8:27
episode. I hope that this format of
8:28
teaching works well for you in the sense
8:30
that I will now mostly be doing a lot of
8:32
writing on the iPad. Uh but at the end
8:34
of the day, we're all going to learn a
8:35
lot. I'm still learning a lot by
8:36
teaching this. And uh yeah, let's do our
8:39
best. to have a happy new year again.

##v2:


Search in video
Introduction
0:00
hey everyone and welcome back this is my
0:03
second shot at recording for this series
0:05
uh apologies for the technical
0:07
difficulties last time my iPad recording
0:09
was getting turned off more frequently
0:11
than my ex-girlfriend whenever I tried
0:13
to make sexual advances uh but the great
0:15
thing about this series is that I can
0:17
really crank these out
0:18
um I'm not going to finish that joke off
0:20
uh because I have pretty much already
0:23
made them all before so as you can see
0:24
I'm making my second one of the day
0:26
which is great so um you know if you
0:29
recall from last time we started to get
0:31
into the contextualization of the
0:33
database problem how we want to actually
0:35
organize our data that we can read fast
0:38
write fast keep it persistent and so
0:41
today what we're going to do is take a
0:43
look at the actual internals of a
0:44
database and how we want to put our data
0:47
on the disk in order to maximize
0:48
performance all right welcome back
0:50
everybody I have now gotten the iPad and
0:52
I'm ready to do some work you may see
0:54
this is a different day I'm just coming
0:56
home from the office right now and I
0:58
have to take a very badly so let's
0:59
get this is done with relatively quickly
1:01
so we established basically three facts
1:04
about the data last video that we're
1:06
first going to talk about number one is
1:08
the following that we want the data to
1:10
be stored persistently
1:13
number two
1:15
even more importantly is that we want to
1:17
be doing this on a hard drive that kind
1:19
of follows from persistence we know that
1:22
RAM does not store data between
1:24
computers shutting off and on so it's
1:26
more durable on a hard drive the third
1:28
thing is of course that the hard drive
1:30
is in a database
1:33
or at least we're running database
1:35
software on some computer and the actual
1:38
data itself is being stored at that hard
1:40
drive
1:40
so before we go ahead and move further
1:43
let's go ahead and look at our hard
1:45
drive in more depth so I'm going to draw
1:46
another picture of it this time a little
1:48
bit bigger so hopefully that helps we've
1:50
got basically some rectangle with a
1:53
metallic disc and then some moving arm
1:55
that goes to the proper place on disk in
1:59
order to read or write data so generally
2:02
the point of this is that because this
2:03
little arm has to actually move around
2:05
the metallic disc the closer that you
2:07
put data together on disk the faster it
2:09
is to access so for example you know if
2:11
I have one piece of data here and the
2:13
other here that's kind of bad instead it
2:15
would be better if you know we had our
2:17
first piece of data here again and the
2:19
second one right next to it
2:21
we're more likely to get better read
2:22
speeds okay so now let's actually go
2:26
ahead and start thinking about you know
2:28
the data is going to just look like an
2:31
array on disk right we have all of our
2:33
little bytes that we can write down and
2:35
slots and so again you know the closer
2:38
the data is to one another when we want
2:40
to access it together the better so
2:42
that's how I'm going to preface this
2:43
entire lesson but we'll see this coming
2:45
to play more and more so let me go ahead
2:47
and scroll down a little bit so now
Database Example
2:50
let's imagine a website right where
2:52
basically all it does is it stores a
2:55
bunch of names of people and their shoe
2:57
sizes and every time you load up the
2:58
website it'll show you all those people
3:00
and their shoe sizes so I'm now going to
3:02
draw up an example database table for
3:04
this website so you can see we're going
3:06
to have a few rows of people and their
3:09
respective shoe size so the first person
3:11
is going to be me Jordan
3:14
uh and you know my shoe size is 18
3:17
because you know big shoes means quite a
3:20
little bit about what else is going on
3:22
in your body and we know that uh
3:23
unpacking number two is going to be
3:26
Donald
3:27
for Trump he has small hands so he
3:29
probably has small shoes as well we're
3:30
gonna go ahead and throw him a seven and
3:33
then we've got Shaq for Shaquille O'Neal
3:36
that dude is massive probably has like a
3:38
size 24. I can concede to Shaq so what
3:41
is my point about this table well the
3:43
first thing is let's say I want to find
3:45
rows
3:47
where name is Jordan
3:50
this is something you can do in most
3:52
databases
3:54
right in order for me to go ahead and do
3:56
that I have to check each row
3:58
individually I have to go here then row
4:01
number two then row number three and
4:03
what that means when you have to do
4:04
proportional work to the number of rows
4:07
in the actual table itself is that this
4:10
is going to be an O of n time complexity
4:14
right if there are n rows we have to do
4:17
n amounts of work basically or work
4:20
proportional to the N rows in order to
4:23
actually find the row that we care about
4:25
so in addition to that let's say I
4:28
wanted to actually edit a size turns out
4:30
Shaq is bigger than we thought his shoe
4:32
size is actually going to be 26. so
4:35
again if we're going to write first what
4:38
that means is that we have to actually
4:39
find the proper row right we're going
4:41
all the way through these rows again and
4:43
then we're going and changing our
4:45
existing Row from a 24 to a 26. so that
4:48
means o of n time complexity for both
4:51
reads
4:52
and writes
4:56
okay so let me quickly erase this 26
5:00
and throw back our 24 because what I'm
5:04
now going to show is a slightly better
5:06
design of a database table that would
5:09
basically allow us to improve at least
5:11
our right complexity
5:13
so let's say this time instead of
5:15
editing Shack I want to edit Donald so
5:18
we knew normally that in order to make
5:19
that edit we would actually have to find
5:21
the road Donald in the table and edit it
5:22
but now what I'm proposing is instead of
5:25
actually doing any physical edits what
5:27
we do instead sorry I don't know how to
5:30
use this iPad yet is we would go ahead
5:32
and add a new row to the table
5:35
where I would now just say Donald
5:38
with the new shoe size let's say his
5:40
foot is actually even smaller than we
5:42
realized now it's a six and then every
5:44
time we search for a row now we actually
5:47
just go ahead and search from the bottom
5:48
of the table up so in the case of Donald
5:50
I would say oh it's got to be this row
5:52
here not this one because this Donald is
5:56
actually lower to the bottom and so now
5:58
because we know that we're always going
6:00
to be writing in the same place every
6:02
time which is the bottom of the table we
6:04
can basically keep a pointer to that
6:06
address and disk and that makes right
6:08
times o of one
6:09
uh however this does come on the
6:11
trade-off of a worse read time the
6:14
reason for that is that even though
6:15
reads are still o of n
6:18
it means that uh they're going to
6:20
actually be more rows in the table
6:22
overall so that n is going to be bigger
6:24
obviously this isn't going to be
6:26
acceptable as o of n reads are basically
6:29
slower than Joe Biden trying to read
6:31
from a teleprompter and he is a boomer
6:33
so it's not ideal but the truth of the
Why Indexes
6:35
matter is actually in a lot of these
6:38
problems or a lot of these big websites
6:40
We Care a lot more about read speeds
6:42
than write speeds and at least as far as
6:45
I've just showed you those read speeds
6:46
were pretty unacceptable o within is not
6:49
good enough right we're going to cross
6:51
that out just go ahead and say it right
6:53
there the reason o of n isn't good
6:55
enough is because when we have hundreds
6:58
of thousands or even millions or
6:59
possibly more rows in our database we
7:02
don't want to have to literally Loop
7:03
through every single one in order to
7:05
find the proper row that we want we need
7:07
to make things faster than that think
7:09
about Facebook for example
7:11
all right this is the example I keep
7:13
using if I have to go through every
7:15
single Post in the database in order to
7:18
go ahead and load our news feed that is
7:20
going to be impractical and it simply
7:22
doesn't make sense we need a better way
7:24
of actually organizing our data
7:29
and this is where the need for indexes
7:32
come in
7:33
so before I actually explain what an
7:36
index is let's think about some things
7:38
that an index or just a better way of
7:40
reading from databases in general could
7:42
help us do well for one we care about
7:44
finding rows
7:46
with specific key values right so in the
7:50
last example
7:51
uh basically that was finding a row by a
7:56
name
7:58
sorry I can't write terrible handwriting
8:00
in the last example it was finding a
8:02
specific row with a name that matched
8:05
the parameter that I provided but in
8:07
another example you know maybe it could
8:09
be names maybe we care about finding a
8:11
row with a specific shoe size that could
8:13
help as well and we want to be able to
8:14
do this faster than just by linearly
8:16
scanning through that whole table
8:18
another possibility
8:20
is performing something known as a range
8:22
query
8:23
so we gave some names before an example
8:27
of a range query would be show
8:29
rows
8:31
with
8:33
names
8:35
between
8:38
A and B
8:39
right
8:41
so
8:42
if they're you know Abraham Lincoln in
8:44
there you know Alex Adams anyone like
8:47
that you want to go ahead and return all
8:49
those rows
8:54
and this is a very common query if you
8:55
think about it in something like a
8:57
social media site maybe we want all
8:59
posts from you know one hour ago until
9:01
now right so it's basically any sort of
9:03
range query where we have these kind of
9:06
two delimiting parameters and we
9:07
ultimately want to get every single
9:09
thing in between so these are very
9:11
common cases where we care about
9:12
optimizing them even if it means
9:14
potentially taking a penalty in our
9:17
write speeds right because at the end of
9:18
the day if we're doing a lot more
9:19
reading than writing something in the
9:21
database that can help us improve our
9:23
read speeds even if it makes writing
9:25
more expensive is still going to be a
9:28
big win in the average case for the user
9:30
experience
9:31
and so ultimately what we want is going
9:33
to be called a database index a database
9:36
index like I've started to hint at
9:38
basically does the following basically
9:41
does The Following
9:43
the read speeds
9:46
go up
9:47
and the write speeds
9:50
go down and this is for a specific key
9:55
right so we can have a database index on
9:58
one field for example like names in that
10:01
table but you know when you mention an
10:04
index typically it is on one field at a
10:06
time you can create multiple indexes
10:08
where there is an index on both the name
10:11
and the shoe size you could even
10:13
potentially have an index on both the
10:15
name and the shoe size but we'll kind of
10:17
explain what all of that is in the next
10:19
video where I am going to show you one
10:21
example of how to implement an index and
10:24
kind of the pitfalls and the benefits of
10:27
that specific implementation which is
10:29
going to be a hash index
Outro
10:31
all right everybody thanks again for all
10:33
the support on the first video of this
10:35
series again I'm sorry about the
10:36
flickering but uh hopefully we can get
10:38
that fixed up this time around I am now
10:40
going to go ahead and take a fat crap
10:42
and I will see you in the next one


##v3:


Search in video
0:00
Hello everybody and welcome back. I am
0:02
your host of the series Google software
0:04
engineer Jordan. Uh I am actually known
0:07
as the best back-end developer in the
0:09
world due to the sheer size and
0:11
gravitational force of my ass. And of
0:14
course I'm wellversed in git all
0:16
commands with the exception of git
0:18
pulling. If you were here for the last
0:19
video, you know that we started to go
0:21
into what database indexes are. And in
0:23
today's video I'll be covering one
0:25
specific type known as hash indexes. So
0:28
without wasting any more of your time,
0:30
let me go ahead and grab the iPad and we
0:32
can start scribbling. All right, welcome
0:34
back everybody. Let's go ahead and get
0:36
started. So to review from last video,
0:39
we talked about indexes in general and
0:41
why we might need them. So in that case,
0:43
there's going to be two reasons. Here's
0:46
number one. The first one is O of N
0:48
reads.
0:50
So O of N reads basically means that uh
0:54
effectively it ties into reason number
0:56
two. we have to go through all database
0:59
rows through all rows to find the rows
1:03
that we want. Which means if we have
1:05
some sort of table and here are all my
1:08
rows in it every single time if I want
1:11
to find all rows for example where the
1:13
name is Jordan or the ID is 10 or
1:15
anything like that I have to go through
1:18
every single one and that is O of end
1:20
time complexity and so that is kind of
1:23
the backdrop of this entire lesson made
1:25
pretty simple. So, let's go over a
1:27
different type of index effectively that
1:30
is going to act as a precursor for the
1:33
other indexes that we're going to go
1:34
over and we're going to see the pros and
1:35
cons of this one. So, today's video is
1:37
about hash indexes. Makes me think of
1:40
hash browns cuz I'm fat. But let's go
1:43
into this further. Okay, so let's review
1:46
a hashmap because of course hash indexes
1:49
are actually going and based off a
1:50
hashmap. So, the first thing to talk
1:52
about when we talk about a hashmap is a
1:54
hash function. So a hash function is
1:56
effectively this. It is a black box,
2:00
right? We have no clue what's going on
2:02
in there. But all we know is that out of
2:04
all uh the elements that we could pass
2:06
into it, you know, let's say I'm passing
2:08
in Jordan,
2:10
what it's going to spit out is a number.
2:13
Obviously, hash functions can spit out
2:14
anything, but we know that whenever we
2:16
pass in Jordan, it's always going to
2:18
spit out some number. Let's say that
2:19
number is four. And so this hash
2:21
function, it's always going to spit out
2:23
the same number from this domain to the
2:25
range where let's say the range that it
2:27
could possibly spit out is 0 to 10. And
2:30
so Jordan is always going to return a
2:31
four. Uh, you know, let's say we put in
2:34
apple, that's going to return uh, who
2:36
knows, a six or something like that. And
2:38
of course, it is possible that sometimes
2:40
I'll do another word and it's also going
2:42
to return a four, right? Let's uh, we'll
2:44
do shack just to keep things consistent
2:46
with last video. you know we get unlucky
2:48
that also happens to return a four. So
2:51
basically the premise of a hashmap is
2:53
that we have our hash function h and
2:55
when we take in the the key and the
2:57
value that we want we basically take h
2:59
of key and that's going to return some
3:02
value v. We put it at basically the
3:06
index v of the array. So in the previous
3:08
example let's imagine we have this array
3:11
with uh indexes 0 through 9, right? It's
3:14
size 10. And our hash function can
3:15
return anywhere from 0 to 10. In the
3:18
event of the hashmap, basically what I'd
3:21
be doing is I'd be putting Jordan
3:25
at index 4, right? And so this allows us
3:28
to have O of one uh or constant time
3:32
reads and writes. The reason for this
3:34
being that our hash function is going to
3:35
take constant time and basically then we
3:38
can jump over to this place in memory,
3:40
which is really really great. So we jump
3:42
right over here and that is O of one to
3:45
be able to access our element Jordan
3:47
check if it's in the hashmap etc etc
3:49
etc. This is more of a hash set just
3:51
since I haven't um you know added like a
3:53
corresponding value to Jordan but don't
3:54
worry about that for now who cares. Um
3:57
and then you know the the other thing to
3:58
consider is that sometimes like I said
4:00
you know Shaq for example would also uh
4:03
be hashed to the same place. So what do
4:04
we do if two things are hashed to the
4:06
same box right you know now we have
4:07
Jordan and Shaq. Well, there's a couple
4:10
ways of actually uh dealing with this.
4:12
One is where instead of just putting the
4:14
key here, you would actually have a
4:15
linked list, right? So, I would have a
4:17
node that contains Jordan and then a
4:20
node containing Shack. That's called
4:22
chaining.
4:24
And then the other alternative is
4:26
probing, right? Where I would just look
4:27
for the next available spot in the
4:29
hashmap. So, for example, that would be
4:31
this one here. And then Shaq would be
4:33
placed in this box of the array. Uh yes,
4:36
obviously that does ruin the kind of
4:38
constant time complexity of it, but uh
4:40
if you do some math using advertised
4:42
time complexity and uh something called
4:44
a load factor, you can basically uh
4:46
prove that it is still on average
4:48
constant time. And uh you know, I'm not
4:50
going to get into that for this video. I
4:52
have a dedicated video to this. But you
4:53
know, that's generally how something
4:55
like a hashmap would work. So let's
4:57
continue to scroll down. So we have our
4:59
hashmap, right?
5:02
And the general kind of gist of a hash
5:04
index is just literally use a hashmap,
5:07
right? So we know that the point of an
5:08
index is we want to easily be able to
5:10
scan for a certain key.
5:15
So in the case of you know uh Jordan for
5:18
instance, I would basically put in the
5:21
hashmap Jordan as the key and then the
5:24
value corresponding to it would be the
5:26
place on disk. who knows what address it
5:28
would be or possibly even the actual row
5:31
itself. Um, but then that's what's in
5:33
the hashmap. You know, you could do the
5:35
same thing with Shaq. And, you know, to
5:37
keep the example uh from last time, you
5:39
could do the same thing with Donald,
5:41
right?
5:47
Should all make sense for uh the most
5:49
part? Whatever. Let's assume those are
5:51
addresses on disc. Who knows? They're
5:52
probably not. Uh, but yes, that's the
5:54
point. We have our hashmap that maps
5:56
keys and values of basically the index
5:58
key that we care about and then the
6:00
actual location on disk of the row. And
6:02
so this is going to be zero of one to
6:05
actually find a row when we're searching
6:06
by uh the name. And that's in both reads
6:09
and writes,
6:12
right? Because we can just go right to
6:13
the row and update it too, which is
6:14
perfect. However, there are some pretty
6:17
big issues with the hashmap. So the
6:20
first one is that hashmaps
6:23
are bad on disk.
6:30
So the reason that they're bad on disk
6:32
is this is now going to be the third
6:35
episode out of three that I've drawn
6:36
this. We have our wheel and we have our
6:39
pointer in a hashmap. The values that
6:43
you care about are stored all over that
6:46
array, right? I might have one here.
6:48
might have one here, might have one in
6:49
the middle because the entire point of
6:51
the hashing function is to distribute
6:53
elements evenly.
6:56
And so what that means is that on disk
6:59
we also have elements distributed
7:01
equally because disk is effectively just
7:03
that big array, right? You know, 1 2 3
7:07
etc etc. So the performance is actually
7:09
pretty poor on hashmaps because we're
7:11
jumping around all over this metallic uh
7:13
disc and as a result it just doesn't
7:15
work very well. So what that means is
7:17
that hash indexes
7:19
are always kept in memory.
7:24
But this has a couple of other issues.
7:27
One is that memory is expensive. I'm
7:31
going to say RAM instead of memory. RAM
7:33
is expensive.
7:36
So there's less of it.
7:41
And because there's less, it means that
7:43
we actually have less leeway in terms of
7:45
putting data in our database because all
7:47
of our keys at the end of the day have
7:49
to fit in RAM.
7:57
So that's basically one issue, right?
7:59
That's kind of the fundamental trade-off
8:01
that we're making here. Obviously, hash
8:03
indexes are going to be super fast,
8:04
right? All the operations are O of one.
8:07
Uh, and it's also in memory, which is
8:08
even faster than disk. Random access
8:10
memory means you can just jump around
8:12
super quickly. That's the entire point.
8:13
You're doing random accesses all over
8:15
this array. So that's great. But there
8:17
are still more downsides to having
8:20
everything in memory because if we
8:21
recall, RAM is not durable.
8:26
And for our database, it would be pretty
8:28
terrible if we could just lose data all
8:30
the time. That wouldn't work very well
8:31
for us at all, would it? So basically
8:33
now what we need to do is figure out a
8:35
way of actually keeping our data.
8:37
Because if our computer were to shut
8:38
down, our entire contents of our
8:40
database would be lost. And the way that
8:42
we're going to do this is with this a
8:44
write ahead log.
8:48
So I haven't really gone into this topic
8:50
yet, but it is pretty similar to
8:52
something that I showed last episode
8:53
where imagine a write ahead log as
8:55
literally just a list every single time
8:57
of all the writes and updates that
8:59
you're making to the database. So for
9:01
example, one thing could be, you know,
9:02
change size of row, you know, with
9:08
Jordan
9:11
to 10,
9:13
something like that. And so we write
9:14
down all the changes that we're making
9:16
in the database. And the write ahead log
9:18
is actually stored on disk. It's
9:20
completely writing sequentially on disk,
9:23
right? So this is literally right next
9:24
to this line, which is next to this
9:26
line. And so since those lines are next
9:28
to each other, these writes are
9:29
relatively fast. We're still doing
9:30
sequential writes which are not bad on a
9:32
hard drive. So because we're using this
9:34
write ahead log now we have durability.
9:36
And so if the computer ever dies and we
9:39
needed to actually recreate our hash
9:41
index, we could do so by replaying all
9:44
those changes in the write ahead log.
9:45
First we would replay this one, then we
9:47
would replay this one, then we would
9:49
replay this one. And so that way we
9:51
could repopulate the hash index.
9:55
And so that is how our write ahead log
9:57
provides durability. This is not
9:59
something that's only used in the hash
10:01
index. It's actually used in multiple
10:02
different types of indexes, but we will
10:04
cover that in future videos. So that's
10:06
how we would repopulate the hash index.
10:09
So even though uh the hash index is
10:11
itself kept in memory, having the write
10:14
ahead log is going to slow things down
10:15
because disk writes are definitely going
10:17
to be slower than memory writes even
10:19
though it is an O of one time
10:20
complexity, right? Because we're writing
10:22
sequentially. Okay, so what's our last
10:24
problem?
10:26
We have this hash index. We know we have
10:28
to write to disk first if we want
10:30
durability. If we don't care, sure, it's
10:31
effectively just a hashmap in memory.
10:34
Our last problem is that we can't do
10:36
range queries.
10:42
Why can't we do range queries? Well,
10:43
think about how hashmaps work. Last time
10:45
I introduced the problem of a range
10:47
query as let's say we want all rows with
10:50
names between
10:52
A and B.
10:55
Uh with names
10:57
between A and B. So what the hashmap is
11:03
really good for is we can easily check
11:06
basically
11:08
you know Alex
11:10
uh Abe
11:13
and Allen we can easily check if the key
11:18
Alex is in the hashmap right that's O of
11:21
one but for us to actually check all the
11:24
rows with names between A and B we would
11:27
have to literally loop through every
11:28
single possible name between A and B and
11:31
check if that's in the hashmap, which is
11:32
not feasible. There are infinite names
11:33
between A and B, you know, if we're not
11:35
just like, you know, sticking to actual
11:38
names that exist on the Earth. So, we
11:40
would have to check literally every
11:41
possible string, and again, there are
11:42
infinite of those. So, that doesn't work
11:43
very well. That's why this isn't really
11:45
feasible for range queries because the
11:47
only way to do a range query with a
11:48
hashmap is to either iterate through all
11:50
the indexes which again is O of N or to
11:54
literally check all of the possibilities
11:57
uh between A and B which in some cases
11:59
is endless. Right? So O of N is probably
12:02
what we would stick with. We would just
12:04
go through all the indexes in the array
12:05
and check if it fits our predicate. Um
12:08
but again this is useless to us because
12:10
we've already said ON reads are not good
12:12
enough for us. So we're going to need a
12:13
better solution in the future. Um some
12:16
of you may be thinking use something
12:18
like uh a tree set, right? Uh you
12:20
remember binary search trees. Binary
12:22
search trees are very nice because uh
12:25
you know you're able to actually perform
12:26
range queries really easily because the
12:29
kind of invariance of the binary search
12:31
tree means that let's say you know we
12:33
want everything between uh whatever this
12:37
node and this node is. You know, I'm not
12:39
explaining this well, but whatever.
12:41
Point is, binary search trees work much
12:43
better in terms of doing range queries.
12:45
You can actually do them. However,
12:48
unlike with a hash index, uh, reads and
12:51
writes are going to be O of login, which
12:53
is worse than our hash index, right?
12:55
Where everything was O of one. So,
12:56
basically, in conclusion, hash indexes
12:59
are really, really great if you want to
13:01
do O of one reads and O of one writes,
13:04
but you don't need range queries. And
13:07
additionally, it comes with the even
13:08
further constraint that you basically
13:11
have to keep all of your keys in memory.
13:13
So if you do have a sufficiently small
13:15
data set and it's something that you're
13:17
willing to tolerate where you're not
13:19
looking for range queries, but you're
13:20
mostly just looking to get one row at a
13:21
time, then the hash index could be for
13:23
you. So keep this in mind, guys. Um, you
13:26
know, as we move on through the indexes,
13:28
um, there are obviously going to be
13:30
trade-offs between all three, but these
13:31
are kind of the main pros and cons of
13:33
the hash index.

##v4:


Search in video
Intro
0:00
hey everyone and welcome back sorry for
0:02
the nasally voice on my end kissing lots
0:04
of dudes over the weekend and it looks
0:06
like it finally caught up to me uh just
0:08
a quick announcement before we actually
0:09
get into the content of today is that I
0:12
just want to shout out one of my viewers
0:14
Ty who reached out to me over LinkedIn
0:15
to tell me that he got four senior
0:17
offers recently primarily studying the
0:19
content from this very channel so to
0:21
those of you who are haters believe in
0:23
this channel take your own notes be like
0:25
Ty and go get to the bag anyways let's
0:28
get into the content of today's video
0:30
sorry again about my voice but we'll get
0:32
through it we're going to be talking
0:33
about bee trees how they work and what
0:35
they're good for
What is a BTree
0:37
all right so I decided to do a bunch of
0:39
pre-drawing so that we wouldn't have to
0:41
wait for me to draw everything and my
0:42
handwriting would be worse but let's go
0:44
ahead and actually start talking about
0:45
what a b tree is so a b tree is another
0:48
type of database index so I started last
0:50
episode by talking about hash indexes
0:52
and how that's basically just a hash map
0:54
kept in memory on the other hand the
0:56
cool thing about a b tree is that it's
0:58
kept entirely on disk so it doesn't have
1:00
some of the downsides that hash maps
1:01
have right we don't have to keep all of
1:03
our keys in memory and you know we don't
1:05
have to worry about the durability of
1:07
our index well for the most part we'll
1:09
talk about the cases where we might so
1:11
basically the B tree as we can see from
1:13
the iPad is this tree-like structure
1:15
where it basically gives the ranges of
1:18
all the keys and gives references to
1:20
other locations on disk that we have to
1:22
Traverse to in order to go ahead and
1:24
find the row that we want so you can see
1:26
written out here let's imagine we have a
1:27
bunch of names and the scores that they
1:29
got on a math test so basically all the
1:32
rows from a to L we can see there's a
1:34
reference pointer that leads us and
1:36
basically says okay now follow and
1:38
Traverse the reference from a to e if
1:41
you want those names or if you care
1:42
about the names between E and O we can
1:44
go and Traverse to this Leaf node which
1:47
is basically going to have something
1:48
like Edward with a score of 80 and
1:50
Gordon with a score of 95. so the point
1:53
is we can Traverse through this tree
1:54
basically going to the reference that
1:56
matches up with the range of key that we
1:58
want and this is really really great for
2:00
a couple of reasons so one is that this
2:02
is relatively Speedy for reads why
2:04
because to actually go and find the key
2:06
that we want all we have to actually do
2:08
is follow these references right or in
2:10
this case it's not this reference that
2:12
we want but it's this one here typically
2:14
I didn't draw it out completely but the
2:16
speed tree is going to stay balanced
2:18
we'll talk about how that works in a
2:20
little bit and so that's really really
2:21
useful for making sure that the height
2:23
of the tree is relatively constant and
2:26
additionally these page sizes right here
2:28
are typically pretty big I can't
2:29
remember the exact amount but I think
2:30
it's typically something like 250
2:32
megabytes and if it's 256 megabytes or
2:36
250 or whatever it means that we can
2:38
have a tree that encompasses a ton uh we
2:42
can have a tree that encompasses tons of
2:43
keys and values uh while also staying
2:46
relatively short and that means we're
2:47
jumping around on fewer places on disk
2:49
because keep in mind on the actual ring
2:52
that is the disc all of these references
2:53
are in different locations so jumping
2:55
around is actually pretty tough but if
2:57
we only have to do it a couple of times
2:58
that's relatively fast so for both
3:01
reading and updating the general process
3:03
is actually just traversing through the
3:05
tree finding where it is that the key
3:08
that we want to look at already exists
3:10
if it's an update then we just go ahead
3:12
and update it in place and if it's a
3:13
read we can go ahead and read it well
3:15
what about her rights this is where
3:17
things get a little bit more complicated
3:18
so I'm going to draw out another diagram
3:21
all right so let's talk about actually
3:23
writing so let's imagine that I wanted
3:25
to basically this is like a you know one
3:28
root two Leaf path in our B tree and
3:30
let's imagine that I wanted to add the
3:31
key Betty with a score of let's say 90.
3:36
right so basically the fundamental thing
3:38
here to remember is that every single
3:40
kind of node of the B tree has a set
3:42
size let's imagine it's 256 Megs
3:45
and so let's imagine now that we have
3:47
this kind of bottom node right here
3:50
if it has extra space we're in pretty
3:52
good shape right it means we can
3:53
actually just add Betty right over here
3:55
and we'll be fine because we don't
3:57
actually have to change the structure of
3:58
the B tree at all the one thing to note
4:00
is that Adam Bob and Betty still needs
4:03
to remain in alphabetical sorted order
4:04
so we do actually have to kind of write
4:07
this one particular node right we would
4:09
go and make one over here with Adam
4:12
Betty you know or rather Adam Betty and
4:15
Bob
4:17
and then we would change the reference
4:19
to this page so that's how you would
4:21
write if there is actually space in this
4:23
child node however what if there isn't
4:25
space in the leaf node then things
4:27
actually become complicated so now what
4:30
actually has to happen is I would have
4:31
to split the child node into two so I
4:34
might have one node with Adam and Betty
4:38
sorry I'm trying to write here and then
4:40
the other with just Bob and then how can
4:43
I actually go ahead and rectify this
4:44
well now I have to go ahead and split
4:46
the parent node right but you might
4:49
actually see here that this parent node
4:51
doesn't have enough space in it right so
4:54
ideally what we would want to do is
4:56
basically delineate the parent node to
4:58
have some boundary
4:59
where what we're effectively doing is
5:02
saying here's everything from A to B E
5:04
and then here's everything from
5:07
Bo to C right because Bob De C is over
5:10
in this other page and that would refer
5:12
to here and then this one would be
5:14
referred to by this reference sorry it's
5:16
getting a little bit messy however if
5:17
there's no space in this node we
5:20
basically have to keep traversing up
5:21
through the B tree splitting every
5:23
single node into two pieces until we
5:25
actually find free space in one of the
5:27
notes as you can see there is some free
5:30
space in this route So eventually we'll
5:31
be in good shape if the root itself
5:34
doesn't have free space we actually have
5:36
to split the root itself into two
5:38
different pieces and then create a new
5:40
root node all the way on top of it which
5:42
points down to the old root node so I
5:45
know that's a little bit of a convoluted
5:46
explanation but you can think it out the
5:48
point is by making sure to split these
5:50
pages when they get too big we can
5:52
guarantee that our B tree is going to
5:54
remain balanced so there's actually an
5:56
issue here and one of those things is
5:58
what if for example you know we're
6:00
updating a node and then basically B
6:04
tree dies and what I mean by that is
6:07
computer turns off you know mid B tree
6:10
update
6:11
and for example now the references are
6:14
all out of whack we've created these two
6:16
pages right here
6:18
but we haven't actually updated the
6:19
reference in time so now our B tree is
6:21
in a consistent in inconsistent State
6:23
computer dies
6:26
well if you recall from last episode the
6:29
best thing to do to ensure that you can
6:31
always get your state back is to have
6:33
something like a write ahead log right
6:35
our sequential only right log that tells
6:38
us everything that we're about to do in
6:40
our database before we actually do it so
6:43
every single time before we actually
6:44
write to the B tree or update the B tree
6:47
that's first going in the right ahead
6:48
log then if the computer were to die we
6:51
can actually go and replay all of these
6:53
messages to recover the state of our B
Summary
6:56
tree
6:56
okay so let's summarize our B tree again
6:59
in terms of how it compares to the
7:00
actual hash index itself obviously it is
7:03
going to be slower right that's because
7:05
the primary amount of data in the index
7:07
is kept on disk which is always going to
7:09
be slower than memory that being said
7:11
the B tree relatively speaking is still
7:13
not bad it's relatively good in terms of
7:16
reads because you only have to do a
7:17
couple of traversals on disk in addition
7:19
the main advantage to the B tree over
7:21
something like the hash index is twofold
7:23
first of all not all of the keys have to
7:26
fit in memory we can now have a much
7:27
bigger size in our data set and even
7:29
more importantly we can do range queries
7:32
so if you recall range queries are when
7:34
we want keys that are similar to one
7:36
another adjacent to one another in
7:37
memory or on disk so that we can find
7:39
them if you look at the actual child
7:41
structure of a b tree we can see that
7:44
the keys that are similar to one another
7:45
are actually going to be next to each
7:47
other in these child pages so this way
7:49
if I want say all the keys between e and
7:53
l i can just go down the tree reference
7:55
back to this child mode fetch all of
7:57
them at once I don't have to do a bunch
7:59
of different reads the data is
8:01
conveniently effectively sorted through
8:03
this B tree so just to summarize it and
8:05
write this out
8:07
a b tree is the following it is a
8:10
self-balancing tree on disk
8:16
and that means one
8:19
no limits
8:21
to data set size within reason of course
8:24
obviously hard drives do have bigger
8:26
capacities but they're not infinite
8:28
and then the second and more important
8:30
point is that now we actually have
8:32
support for range queries
8:37
the one thing to note is that even
8:38
though B trees are relatively quick with
8:40
reading the rights themselves are not
8:42
super fast for the reasons we discussed
8:44
you may actually have to do a bunch of
8:46
Rights not only to the right ahead log
8:47
but to the bottom of the tree and then
8:49
you may have to Traverse all the way
8:50
back up the tree basically switching all
8:53
of these references on disks so that can
8:55
take a while we'll talk about in the
8:57
next video a different type of index
8:59
that tries to optimize on this and kind
9:01
of improve the write speed while at
9:03
least maintaining similar read speeds to
9:05
the B tree and a similar ability to
9:07
perform range queries alright guys have
9:09
a good one and I will see you in the
9:10
next video

##v5:


Search in video
Intro
0:00
Hello everybody welcome back to the
0:03
channel uh the numbers are going good so
0:05
far for this whole systems design series
0:06
which is great because it keeps my
0:08
depression at Bay uh today I'm trying
0:10
something a little bit new with the iPad
0:12
where I kind of pre-draw most of the
0:13
stuff as to save everybody time not
0:15
having to wait for me drawing and also
0:17
it means my drawings are going to be a
0:18
little bit better I can put some more
0:19
thought into them so let's go ahead and
0:21
talk about some LSM trees and SS tables
0:24
and we can start learning all right
LSM Tree
0:26
let's get started so today we're going
0:28
to be talking about an LSM tree which is
0:30
another type of database index that was
0:32
developed a little bit later in time
0:33
relative to the B tree which we talked
0:35
about in our last video so the kind of
0:38
main component of this LSM tree index
0:40
that we're going to start by looking at
0:41
is a red black or perhaps a b tree or an
0:45
AVL tree basically any balanced binary
0:47
search tree that is going to be put in
0:50
memory so I've drawn that out for us
0:52
below let's imagine we have a bunch of
0:53
students and their scores on the last
0:55
math test or computer science test or
0:56
whatever so we've got you know a bunch
0:58
of these guys as you can see because
1:00
it's about binary balance search tree we
1:02
know that for every single node all the
1:04
nodes to the left of it are going to
1:05
have a lower key and all of the notes to
1:06
the right of it are going to have a
1:08
higher key so we can see our invariant
1:10
has been satisfied so for now let's
1:12
imagine that all of the reads and rights
1:14
to and from the database are going to
1:16
this tree right so if I were to add this
1:18
key down here in red or maybe that's
1:20
orange I am colorblind we're going to go
1:23
ahead and add it under Chuck and to the
1:25
right of Chuck which is good it means
1:27
it's in the right place and what that
1:28
means is that all of these reads and
1:30
writes are going to be o of log n really
1:33
really good goes to memory which is very
1:35
fast okay but as we've discussed plenty
1:38
of times already just doing everything
1:40
in memory is not so simple so right now
1:43
we've got a couple of issues we have our
1:45
in-memory balance binary search tree
1:47
which like I said red black AVL B tree
1:49
any of those algorithms might work I'm
1:51
not going to cover them because they're
1:52
all pretty complicated and frankly I
1:54
don't even know them that well you can
1:55
do that on your own time
1:57
okay so a couple of things come up when
2:00
we have a tree that is in memory and
2:02
we've spoken about this in the past
2:03
especially as it pertains to Hash
2:04
indexes so there are two main issues the
2:07
first one is going to be that there is
2:09
no durability right that means if the
2:11
computer shuts down your index is
2:13
effectively lost and that is not going
2:15
to work for us so what are we going to
2:17
do well similarly to the hash index we
2:19
are going to use a write ahead log now
2:21
that is a sequentially written log that
2:23
we store on disk meaning that rights are
2:25
going to be relatively fast because we
2:27
don't have to jump all over the place on
2:28
disk and basically if it's going to be
2:30
the case that you know something like uh
2:33
you know the machine were to crash or
2:35
anything like that all we would do is go
2:37
ahead through the changes on the right
2:39
ahead log and replay them gradually
2:41
reformulating our LSM tree which is
2:43
really good so now we've covered
2:45
durability but it does come at the cost
2:47
of slower rates because now we have to
2:49
deal with disk i o okay the other big
2:51
issue is that we have less space for
2:53
hash indexes I basically just told you
2:55
to go yourself I said all the keys
2:58
have to fit in memory but for the LSM
3:00
tree itself there's actually a very
3:02
clever solution to this and this is
3:03
where this video actually starts to get
3:05
complicated so we've got this big thing
3:07
right here less space and the only way
3:09
we're going to get more space is by
3:11
starting to incorporate all of that
3:12
extra space that we have on disk so
3:15
let's go ahead and do something our LSM
3:17
tree has gotten too big let's say it
3:19
surpassed some threshold in bytes right
3:21
we know that that might be you know some
3:24
amount of kilobytes let's leave it at
3:26
that I'm not going to name an exact
3:27
amount that's for the researchers so
3:29
when that LSM tree gets too big we're
3:31
going to do two things first of all
3:33
we're going to reset it right we're
3:34
going to purge it of all the nodes in it
3:36
and then second of all we're going to
3:37
convert it to something called an SS
3:39
table and that is going to be on disk so
3:42
the SS table itself is basically the
3:44
following it is a conversion of our LSM
3:47
tree over here to the left to be sorted
3:49
in order with all of the scores kept the
3:52
same and that SS table is immutable once
3:55
we've converted this to an SS table
3:56
we're not touching the results of that
3:58
SS table we're just keeping it in disk
4:00
and I'll explain to you kind of how that
4:02
works in a second you may also say to
4:04
yourself damn isn't that a pretty
4:05
expensive operation to convert this tree
4:08
to a sorted list on disk sorting is
4:10
obviously very expensive if you have to
4:12
sort an array that is going to be o of n
4:14
log n at best well actually kind of the
4:17
really great part about us using a
4:19
binary search tree is the fact that we
4:21
can do an in-order traversal on it and
4:23
that's an algorithm that happens in
4:24
linear time I've literally written out
4:26
the pseudo code right here and what that
4:28
means is that by running our inorder
4:30
traversal we can get all of those nodes
4:31
in order so that we get this sorted
4:34
table relatively quickly we can write it
4:36
on disk and then we're done with it okay
4:38
so now we have our sorted table so to
SSTables
4:41
just kind of give a bigger picture of
4:43
what's really going on here we have
4:44
basically the following right we've got
4:46
our LSM tree
4:48
which is in memory and then once that
4:50
becomes sufficiently big it's going to
4:52
get converted to SS tables so you see
4:54
now that we have multiple SS table files
4:56
because these are basically the
4:58
conversions of past LSM trees once
5:00
they've gotten too big and these again
5:01
are on disk okay so what is the point of
5:05
having all of these SS table files well
5:07
basically the main thing is that you
5:10
know all of our rights are going right
5:12
here into the LSM tree but when we're
5:14
reading we have to also incorporate
5:16
those SS table files so how are we
5:19
incorporating the SS tables basically
5:21
when we read the first thing that's
5:22
going to happen is we look for our key
5:24
in the LSM tree that's literally just a
5:27
tree traversal this is a binary search
5:28
tree we all know how to find a key in a
5:31
binary search tree so that's going to be
5:32
step one if our key isn't in there it
5:35
was perhaps written in the past right
5:36
maybe it's on one of our SS tables so
5:39
then we have to actually check the most
5:40
recent SS table and we have to check the
5:44
second most recent SS table if the key
5:46
happens to be in both of these tables
5:49
well it means that the one that was
5:51
written most recently is the most
5:52
up-to-date value of that key because
5:54
like I said SS tables are immutable if
5:57
we want to update a value we basically
5:59
just have to write it again and the same
6:00
thing actually goes for deleting a key
6:02
so what if we want to do a delete well
6:05
this is where we do something called a
6:07
tombstone
6:08
so I have it written down on the bottom
6:10
left of the screen right here for this
6:12
Tombstone let's imagine that I want to
6:13
delete the key Jordan so if you know the
6:16
key Jordan is in SS table 2 over here
6:19
with value 10 and then it's also in SS
6:22
table 1 over here with the tombstone
6:25
value you can see that's just the Red X
6:26
with the circle it means that because
6:28
the tombstone value is in the more
6:30
recent SS table I know that comparing
6:32
the two of them I can be certain that
6:35
basically the key Jordan has been
6:36
deleted assuming it's not in our LSM
6:38
tree of course so the other big thing to
6:40
note here is that every single one of
6:42
these reads that we're going to be
6:43
performing for an individual key is O of
6:46
log n right because in an LSM tree this
6:49
is a balanced binary search stream so we
6:51
know that we're reaching logarithmic
6:53
time complexity when finding a key
6:55
additionally for all of these SS tables
6:57
on disk the really nice thing is that
6:59
they're already sorted and so because of
7:01
the fact that they're sorted it means
7:03
that you can go ahead and binary search
7:05
them for the proper value of your key so
7:08
binary search of course means that you
7:10
know we're starting here let's say uh we
7:12
have an A and A Z over here and we're
7:14
looking for key e right so the letter in
7:16
the middle of the alphabet is going to
7:18
be k or something like that and then we
7:19
say oh shoot you know we're looking for
7:21
K so now we're going between a and K uh
7:24
oh wait uh you know now we've got uh D
7:26
oh wait we want e which is between D and
7:29
K so now let's look over here and
7:30
eventually we find our row right so
7:32
that's binary search that's logarithmic
7:34
complexity
7:35
okay so I've basically said to you now
7:38
recall that every single time we do a
7:40
read we first check the LSM tree then we
7:42
check all of our SS tables on disk in
7:45
the order that they were submitted or
7:47
basically rather reverse chronological
7:49
order so what we're going to actually go
LSM Tree Optimization
7:51
ahead and get into now are some LSM tree
7:54
optimizations right because that read
7:57
process that I've described the loan can
7:59
actually take a pretty long time and so
8:01
there are a few things that we can do to
8:03
speed this up especially as it pertains
8:05
to the tables on disk so the first thing
8:07
that we can do is actually add something
8:09
called a sparse index so let's imagine I
8:11
have an SS table here and basically all
8:14
it has is all names right let's imagine
8:16
every single person that has ever been
8:18
received a name from A to Z is in This
8:20
Ss table well what we can do is actually
8:23
create something known as a sparse index
8:25
where we take certain keys out of that
8:27
SS table and write their uh basically
8:30
their location on disk so by putting all
8:32
of these right here see we have Adam
8:34
Jordan Sam and Quincy we can actually
8:36
get started on our binary search a
8:38
little bit faster so if I know that um
8:41
you know the name that I want is between
8:42
a and j right I'm looking for Dan I know
8:45
that I only have to binary search
8:46
between the locations for Adam and
8:49
Jordan and that is going to speed up our
8:50
query because it skips out on a couple
8:52
iterations of binary search which is
8:54
really great so that's going to help us
8:56
a lot for reads and again it doesn't
8:57
take up a lot of space on disk because
8:59
this index is sparse it's not containing
9:01
all of the keys just some of them so we
9:03
actually have an index for our SS table
9:06
in addition to that we can do something
9:08
else called a bloom filter now the bloom
9:10
filter itself is something that I'm
9:12
going to cover in a separate video
9:13
because it kind of deserves its own
9:15
video it's a really cool kind of
9:16
probabilistic data structure but
9:18
basically the gist of it here is the
9:20
bloom filter allows us to say whether a
9:23
key is not in a table right so basically
9:26
you know if I'm looking through the name
9:28
Tech lead in This Ss table I can't
9:30
imagine anyone has actually been legally
9:31
named Tech lead unless he is that would
9:33
be wild and so of course our bloom
9:35
filter would just go ahead and say no
9:37
it's not in there now this isn't going
9:39
to be 100 accurate right if it happens
9:41
to say that the key may be in there it
9:43
could be wrong but all of these no's
9:45
basically means that we can skip out on
9:47
searching this particular SS table and
9:49
that again is going to speed up our
9:51
query
Compaction
9:52
okay so finally we've gotten through all
9:55
of our LSM table specific details but
9:58
there's just one last issue I've
10:00
mentioned so far that there's no
10:01
explicit deletions of keys right we just
10:03
have this concept of a tombstone and
10:06
whenever we update a key we're
10:07
effectively just adding another copy of
10:09
it right into our index so we're going
10:12
to potentially be wasting tons of
10:13
storage so the last thing to think about
10:15
that kind of some of these indexes will
10:18
do is perform a step known as compaction
10:20
so you can see that I've drawn up on the
10:22
iPad screen right here these two SS
10:25
tables SS table 1 which I'm going to
10:27
assume is the more recently written one
10:29
and SS table two and you can see that
10:31
they each have three students in their
10:33
respective scores and the issue is that
10:35
the key Alex is duplicated in both let's
10:37
imagine the teacher made an error and
10:39
then she went ahead and corrected Alex's
10:41
score and so now Alex has an updated
10:43
score of 93 instead of 91. in reality
10:47
there would probably be even more wasted
10:48
space than this as opposed to just one
10:50
example so let's go ahead and perform
10:52
compaction
10:53
what we're going to first do is start
10:55
with basically two pointers right and
10:57
they're going to start at the zeroth
10:58
index of both of these SS table arrays
11:00
I'm now going to compare the two of them
11:02
I see Alex from SS table 1 and SS table
11:05
2. as you can see Alex from SS table 1
11:09
is the same as Alex from SS table 2
11:11
because they have the same key but since
11:13
s is table 1 is more recent the value
11:15
Alex with 93 is going to win and that is
11:18
why we have 93 in our new combined SS
11:21
table
11:21
next we're going to move the pointer
11:23
ahead on s's table 1 since we selected
11:26
that value
11:27
and we're going to actually do the same
11:28
on SS table 2 since it was actually a
11:30
duplicate so now we have Bob compared to
11:33
Dan Bob is going to be the lower key
11:34
hence we have Bob here we're going to do
11:37
the same thing now with Dan not moving
11:38
forward and we're going to compare
11:40
Charlie to Dan as you can see Charlie
11:41
again is lower so that's why Charlie
11:43
comes in and then finally We'll add Dan
11:45
and Edward from the other table that is
11:47
how we can go ahead and actually keep
11:49
the resulting list from our two SS
11:51
tables sorted and of course that is
11:54
going to be in O of n complexity you can
11:57
go ahead and check this problem out on
11:58
lead code you're literally just merging
12:00
to sorted lists okay so let's go into
Conclusions
12:06
some conclusions to talk about because
12:07
we've gone over three types of indexes
12:09
now which are the main ones that I
12:11
wanted to address for this series and I
12:13
want to kind of make an overarching
12:15
statement about what's good for which
12:17
use case so let's start out with the
12:19
hash index since that's what we did
12:20
first and hopefully you guys have a good
12:22
sense of that now so the great thing
12:23
about the hash index is that because
12:25
it's in memory and because it's a hash
12:26
map it is super super fast we have o of
12:29
one reads and writes in memory now the
12:31
rights are obviously going to get a
12:32
little bit slower due to that right
12:33
ahead log but at the end of the day this
12:35
is going to be the fastest in terms of
12:37
performance for just individual key
12:39
reads and writes that being said there
12:41
are two main downsides the keys need to
12:43
fit in memory because our index is just
12:45
in memory and also there are no range
12:48
queries allowed we've said that hash
12:49
maps are really really not good for
12:51
dealing with range queries and if you
12:53
want to deal with range queries you
12:55
probably have to figure out a way to
12:56
sort your data
12:58
so that is kind of where our B tree
13:00
comes in now this is kind of the
13:01
standard index and a lot of relational
13:03
databases we'll cover what a relational
13:05
database is in a future video but
13:07
basically the advantages of a b tree is
13:10
that you can get really fast range
13:11
queries right everything is co-located
13:13
to the basically similar keys on disk if
13:17
I have a key atom and I have a key Alex
13:19
they're going to be very close together
13:21
on disk and they're going to be far from
13:23
the key Zachary at the same time the
13:26
rights are actually going to be pretty
13:27
slow because they're going straight to
13:29
disk unlike the hash index where writes
13:31
are in memory having to go through a few
13:33
iterations of a tree on disk and
13:35
ultimately make it right is probably
13:37
pretty slow so the B tree definitely
13:39
really sacrifices on rights there but
13:41
again the main advantage is this is
13:43
actually feasible for big data sets you
13:45
can actually keep all of your keys on
13:46
disk as opposed to having to keep them
13:48
all in memory and then kind of the last
13:50
big thing here is of course the LSM tree
13:53
which we've just spoken about so you can
13:55
see I actually have a couple of white
13:56
points here the reason for that being
13:57
that they're kind of the middle ground
13:59
between the B tree and the hash index so
14:02
basically the main kind of pro point for
14:04
the LSM tree is of course that you're
14:05
not limited by the size of ram in your
14:07
computer in terms of how many keys you
14:09
can store at the same time we have a
14:10
couple of kind of mediocre points on one
14:13
hand compared to B trees the rights are
14:15
going to be fast that's because they're
14:17
going to memory of course there is a
14:19
right ahead log involved which is going
14:20
to make rights a little bit slower but
14:22
at the end of the day just know that
14:24
rights to LSM tree indexes are faster
14:26
than b trees of course though they are
14:28
going to be slower than the hash index
14:29
that's because even though you're
14:31
writing to memory for both writing to a
14:33
hash map is going to be faster than
14:35
writing to a binary search tree just
14:37
based on time complexity alone
14:39
additionally another great thing about
14:41
the LSM tree that we didn't cover in too
14:43
much depth is that it supports range
14:45
queries this is because all of our SS
14:47
tables have sorted keys right so it
14:49
means that all of the keys that are
14:50
similar to one another are going to be
14:52
close to one another in our SS tables
14:54
however of course as with just a normal
14:56
read query four range queries we're
14:58
going to also have to read all of those
15:00
SS table files and by doing so it means
15:02
that those range queries are going to be
15:04
slower than just a simple B tree range
15:06
query where we only have to do one read
15:08
and of course kind of the last big deal
15:11
in all of this is compaction we've
15:14
mentioned compaction so far as a way to
15:16
kind of reduce the amount of disk space
15:17
that we've used and effectively because
15:20
of compaction we are going to be doing
15:22
some background CPU usage in order to
15:24
merge those SS table files together
Outro
15:27
all right guys I hope you enjoyed this
15:28
video I'm doing my best to kind of make
15:30
these as comprehensive as possible and
15:32
as always I hope you have a great day

##v6:


Search in video
Intro
0:00
must be on call because it looks like
0:01
your backend needs some attention.
0:03
Welcome back everybody. Today we'll be
0:05
doing some wrapups of database indexes.
0:07
Now, I would like to implore all of you
0:09
viewers because I consider myself a role
0:11
model to all of you that this is the
0:13
only time you should ever be dealing
0:14
with anything pertaining to wrap-ups. I
0:16
recommend in all aspects of life. And in
0:18
addition to that, as with systems
0:20
design, you can always fall back on plan
0:22
B. So, without further ado and without
0:24
any more corny jokes, let's get into the
0:26
subject for today. All right, so let's
What are indexes
0:28
go ahead and get into things. I've got
0:30
the iPad up and we can get started. I've
0:32
done a lot of prewriting again, so we
0:33
can hopefully make this an even faster
0:35
lesson. So to basically wrap up the
0:37
entire point of indexes. I mentioned
0:39
this in the introduction to indexes
0:41
video, but now that you know how they're
0:42
actually implemented, you should
0:44
understand this point a little bit
0:45
better. The main point of indexes is the
0:47
following. Obviously, we want to use
0:49
them to get faster reads on a specific
0:51
key value. That means, for example, if I
0:53
have a bunch of different columns in a
0:54
database table, I get to pick one of
0:56
those columns, put an index on it, and I
0:59
know now that if I'm searching for all
1:00
columns with a value on that specific
1:03
column, then it is going to be made
1:04
quite significantly faster. On the
1:07
contrary, the problem here now is that
1:09
every single write that I do to this
1:10
database table is going to be
1:12
significantly slower as opposed to just
1:14
appending to the end of some, you know,
1:16
disk file. Now I have to do that plus
1:19
also deal with the logarithmic time
1:21
complexity that's incurred dealing with
1:23
either a B tree or an LSM tree and SS
1:26
tables. So for now I'm going to scroll
Index abstraction
1:28
down a little bit and basically the way
1:29
I want to kind of think throughout this
1:31
video is think about the index from an
1:33
abstraction point of view. So for right
1:36
now let's throw out the kind of idea of
1:37
the hash index and think about just the
1:40
abstraction. Right? So basically if we
1:42
have an index on a key imagine that that
1:44
basically means that we are sorting our
1:46
database table by that key. The entire
1:48
point is that our database is sorted so
1:50
that we can do O of login binary
1:52
searches on it both for individual row
1:54
reads and also range queries. So imagine
1:57
that we have some like almost like
1:59
Twitter post database right here where
2:01
we have an index on the username of the
2:03
poster and then we also have like a date
2:05
column and the actual text of what I
2:07
posted. As you can see, the keys are
2:09
themselves sorted in alphabetical order.
2:11
So I know that if I were to ever go and
2:13
look for the specific key that I want,
2:15
it's not like finding a needle in a hay
2:17
stack anymore. There's actually an
2:18
organized way of finding this key. And
2:20
so again, that takes that read time
2:22
complexity from a linear time scan to a
2:25
logarithmic time scan, which is really
2:27
huge, especially when you have a super
2:28
large database table. So this is kind of
2:31
the main idea of indexes, right? We've
2:33
taken this read, which would have been
2:34
otherwise super complicated. we've made
2:36
it a lot faster and of course it is
2:38
going to give us a right penalty. But
2:40
when you are for example an app that
2:42
heavily relies on making read speeds
2:44
super fast for you know kind of good
2:47
performance for your customers that is
2:49
sometimes a worthwhile trade-off.
2:50
Everything in systems design has
2:52
trade-offs and the index is a perfect
2:54
example of one of them that comes along
2:56
with databases. Okay so basically what
2:59
we have written right over here as you
3:01
can see this is what's called a
3:02
clustered index. So I kind of acted as
3:04
if all indexes were clustered indexes in
3:07
my past videos, right? Where I
3:08
insinuated that the data of the row
3:10
itself was stored within the index. So
3:12
in this case, the data of the row would
3:14
be the date and the text of the post.
3:16
However, the truth of the matter is a
3:18
lot of times you're not necessarily
3:20
using a clustered index. So the benefit
3:22
of a clustered index is that you get
3:24
faster reads, right? Because you
3:25
literally go and search through your
3:27
index and then right once you're there,
3:29
you can actually access the data
3:30
directly. But instead, a lot of the time
3:33
what indexes will do is they will
3:35
actually just go ahead and put the
3:37
address of the corresponding row on disk
3:39
within the index. So basically the main
3:42
advantage of this second type of index
3:44
where we've only got disk addresses
3:45
instead of the actual data in the row is
3:48
less data duplication. So this is really
3:50
really huge for us in the sense mainly
3:53
that uh you know now we don't have to
3:55
duplicate every single row in all of the
3:57
indexes that we have. So, one thing that
3:59
you'll see in a lot of databases that
4:01
it's common to have more than one index.
4:03
Perhaps there are two fields that we
4:04
want to optimize our reads on. And so,
4:06
if we have two fields with indexes, that
4:09
means that every single row that we
4:10
write would have to entirely fit in both
4:13
of those index. So, imagine we took this
4:15
entire gigantic uh clustered index right
4:18
here and had to double it. Now, we're
4:20
basically storing two times as much
4:22
data. And obviously, that's going to be
4:23
unacceptable if we're trying to optimize
4:25
the amount of data that we're storing.
4:27
it is not worth it to do that. And so
4:29
again, that's why this kind of address
4:31
index is the one that you see used more
4:32
often in practice. There is also a
4:35
middle ground known as kind of like a
4:37
covered uh index where as opposed to
4:40
storing all of the fields like you see
4:41
right here, maybe we would only store
4:43
one important field and then the other
4:45
one is elsewhere on disk or we would
4:47
have, you know, an address on disk,
4:48
whatever. Um, but the general point is,
4:50
you know, we would only have a subset of
4:52
fields in the index. And that kind of
4:53
provides that trade-off where you're
4:54
storing less data, but you know, you
4:57
still have faster reads for the fields
4:58
that we want in the index.
Multidimensional index
5:01
Okay. So, the last thing that I plan on
5:04
covering in this video is the concept of
5:06
a multi-dimensional index. So, we've
5:08
covered, you know, what an index on a
5:10
single field is, but a lot of the times
5:11
what you'll want is kind of a combo
5:13
index where not only do we have um an
5:16
index on one field, but within that
5:18
sorted order, we also want uh basically
5:21
an internal sorted order. We don't just
5:23
want it to be random. So, imagine I was
5:25
a social media site and I want to
5:27
organize all of my posts first by the
5:29
username of the poster and then also by
5:32
the date that they posted, right? So for
5:34
example, as you can see here, what's
5:36
actually going to go ahead and happen is
5:38
we have the name sorted and then the
5:40
date sorted. So the the later the date
5:42
of posting, uh, basically the later down
5:44
it's going to be in that database table.
5:47
Keep in mind this is in contrast to
5:49
having two separate indexes on the name
5:51
and date field, right? So for example,
5:53
if we were to have an index on the date
5:55
field, then the rows would actually be
5:57
in chronological order. And it would be
5:59
something like, you know, January 1st,
6:02
then February 5th, then March 10th,
6:05
then over here, June 1st, then September
6:08
10th, and then December 1st. So the
6:10
order would completely switch if we
6:12
wanted an index just on the date field.
6:15
But because we have this kind of
6:16
multi-dimensional composite index, it's
6:18
one sort order. first on the name and
6:20
then afterwards we sort every single key
6:23
internally on the name in the date. And
6:25
so that is also a really useful feature
6:27
that is as if you just had one index,
6:29
right? Two separate indexes will sort
6:31
each field individually. So I just
6:33
wanted to go ahead and clear that up.
Outro
6:36
All right, everyone. Well, I hope this
6:37
video was useful. Um, looking forward to
6:39
seeing you guys in the next one. I'm
6:40
going to switch up the order a little
6:42
bit from my original series because I'm
6:44
thinking that it will benefit us to kind
6:46
of do all the database internal stuff
6:48
first and then we can start talking
6:51
about things like replication and
6:52
partitioning where we're going not just
6:54
from one computer or one database but to
6:56
many database nodes in a cluster. Okay,
6:59
looking forward to it and I will see you
7:00
guys in the next

##v7:


Search in video
0:00
Hey guys, welcome to another systems
0:01
design video. Today we'll be talking
0:03
about acid transactions. Now, uh if
0:05
you're not familiar with acid
0:07
transactions, I should let you guys know
0:08
to be careful with this episode. The
0:10
last time I personally dealt with an
0:12
acid transaction, I thought I was a
0:13
pineapple for about 12 hours. I ended up
0:15
in prison and uh I'm not exactly sure
0:17
what was in my But with all of those
0:20
things being said, let's get into the
0:21
video and figure out what these
0:22
transactions are all about. Okay, so
0:25
acid transactions, like I mentioned,
0:26
that's going to be the subject of
0:28
today's video. So what are acid
0:30
transactions? Well, effectively acid
0:32
transactions are a way of writing to
0:34
certain databases. Um, and basically the
0:37
database provides certain abstractions
0:39
about those rights that allow us to
0:41
guarantee that certain properties are
0:42
going to hold. So those certain
0:44
properties are going to basically follow
0:45
the acronym ACID, hence the word ACID.
0:48
So let's go through what all of those
0:50
properties mean and then I'll
0:51
demonstrate some examples and uh we can
0:53
touch upon how databases might actually
0:55
go ahead and uh implement these
0:57
transactions or at least partially for
0:59
the scope of this video and in the
1:00
future we'll kind of finish that off. So
1:02
the first thing is a and that's going to
1:04
be atomicity. So basically what
1:06
atomicity says about rights is that
1:08
either all the rights are going to
1:10
succeed in a transaction or none of them
1:12
do. So the classic example here is some
1:14
sort of exchange of money, right? Let's
1:16
imagine I am going to write to a
1:18
database because I just went ahead and
1:20
purchased Karinov's bathwater. So I just
1:23
lost $10 and I've given her my $10. And
1:26
it's important that either both of those
1:28
succeed or they both fail. Let's imagine
1:30
that only one of them succeeded. So
1:32
let's say I lost $10 and she didn't gain
1:34
$10. Now all of a sudden $10 have been
1:36
taken out of our banking system and cash
1:38
is disappearing. That can't happen. Same
1:40
thing goes if only the right giving her
1:42
money were to fail. If that were the
1:43
case and I'm the banker, I've
1:45
effectively just lost $10 of my own
1:47
money in the sense that I've just given
1:48
one of our clients $10. So, they either
1:50
need to both succeed or they need to
1:52
both fail. So, moving on to C, we've got
1:55
ourselves some consistency. So,
1:58
consistency basically means that the
2:00
database when it does fail is going to
2:02
fail gracefully, right? It's never going
2:04
to fail part of the way through the
2:05
right. And if it does, it means that
2:07
objects aren't getting corrupted all of
2:08
a sudden. And that's kind of a very
2:10
important distinction is that yeah,
2:12
obviously the database can fail and it
2:13
can fail whenever, but when it does
2:14
eventually boot back up, things aren't
2:16
going to be in an absurd state. So for
2:18
example, let's imagine we have a
2:20
database and uh you know, we need an
2:22
invariant to hold that there's always
2:23
one officer uh on shift at a current
2:25
moment. So basically, you know, we've
2:28
got Larry currently on shift and we're
2:30
going to go ahead and delete that row
2:32
and instead add the row Oscar. Right? So
2:34
the point is you know uh if there's a
2:36
failure in the middle of this now the
2:38
issue is that we have no security guard
2:40
there. So we need to make sure that
2:41
during that right uh you know if there's
2:43
a failure to happen that we can kind of
2:45
roll back properly or you know finish
2:47
the right as intended. This kind of ties
2:49
into atomicity but just the general
2:51
point is that atomicity and consistent
2:53
uh kind of successfully enforcing
2:55
atomicity uh guarantees consistency or
2:58
at least it should. So we've gone
3:00
through A and C. Let's go ahead and move
3:02
on to I. So I is kind of the most
3:04
important part of acid transactions and
3:06
I stands for isolation. Isolation
3:09
basically means that there are no race
3:10
conditions. If I perform a transaction
3:12
and you perform a transaction on the
3:14
database at the same time, remember that
3:16
the database is of course a
3:17
multi-threaded server. It means that uh
3:20
you know it seems as if they were
3:21
interacting or actually writing
3:23
independently of one another. We don't
3:25
have to worry about you know them
3:26
running at the same time and causing all
3:28
sorts of wonky bugs. So what exactly is
3:30
a race condition? Well, a race condition
3:32
like I said just arises when two threads
3:34
are executing concurrently on the same
3:36
pieces of data or I guess related pieces
3:39
of data. We'll discuss some more race
3:40
conditions in the near future. But the
3:42
classic example is let's imagine we have
3:44
this value right here zero and uh
3:47
imagine that's just a counter of how
3:49
much money I have and then here's me
3:51
over here and here's my friend. You
3:54
know, we both want to increment that
3:55
counter by $1. Let's say we both got a
3:57
dollar to put into the counter. Um, so
4:00
I'm going to go ahead and read that zero
4:02
value as zero. I'm going to increment it
4:04
by one. And now I'm going to write one
4:06
to that zero, turning it into a one.
4:08
Right? That's all on the left side over
4:10
here. However, if my friend is doing
4:12
this at the same time, we might be
4:14
reading at the very same time. There's
4:15
no way to know exactly what order these
4:17
steps are occurring in. And so if he
4:19
reads at the same time as me, we're both
4:21
going to read this value zero. We're
4:23
both going to increment zero by one, and
4:25
then we're both going to write back one.
4:27
And so the eventual value of zero is
4:29
going to be one when it should be two.
4:32
And that right there is an example of a
4:34
race condition. So uh a database that
4:37
supports acid transactions is going to
4:39
make sure that these types of race
4:40
conditions are not possible. Um and kind
4:43
of the issue with isolation is in
4:45
practice it's not actually so easy to do
4:48
that. Um obviously it's very doable but
4:50
more so when we do that the performance
4:52
of the database can really deteriorate.
4:53
So we'll talk about that in future
4:55
videos. Then of course we've got D. So
4:57
we've already mentioned AC and I and the
5:00
last piece is just durability right when
5:02
we write something when we commit that
5:03
right that's what it's called when we
5:05
complete a transaction effectively the
5:07
data is just going to be permanent now
5:09
of course nothing can be truly permanent
5:11
right I can always take that hard drive
5:12
and hit it with a hammer and now your
5:14
data is gone too bad but you know the
5:16
assumption is so long as the hard drive
5:18
is functioning properly the data will be
5:20
there of course you know for databases
5:21
that are running in memory then there
5:23
are probably extra things that you have
5:25
to do in order to ensure that this
5:26
durability prints principle is being
5:28
met. Okay, so the last piece of this
5:30
video is actually going to be the
5:32
following where you know I'm going to
5:34
touch mostly upon isolation in a future
5:37
video cuz like I said it is hard to do
5:39
right and it's hard to do right in a way
5:41
that uh gets all the performance under
5:44
wraps and actually working well. But in
5:46
terms of achieving atomicity, remember
5:48
that's just basically saying all rights
5:50
succeed or fail. Consistency, basically
5:52
saying the database is in a good state,
5:54
right? It's not like you don't have a
5:56
bunch of corrupted objects. And
5:57
durability data is, you know, on the
6:00
hard drive. This can all be achieved
6:02
very very easily with a write- ahead
6:03
log. So if you recall, a write ahead log
6:06
is literally just something that goes on
6:07
disk and you write all of the things
6:09
that you're doing sequentially. So the
6:11
same thing applies with every single
6:12
transaction. So, here's what one entry
6:14
of the write ahead lock might look like.
6:16
We've got basically something saying,
6:18
okay, transaction number 12 is Riley
6:20
Reed gets $10 for foot pictures. Jordan
6:23
gives her $10 for foot pictures, and
6:25
then we write commit. The reason we have
6:27
commit here is because, you know, let's
6:29
say uh we were to crash right before we
6:31
write commit, then we know that this
6:33
transaction is invalid. Once we write
6:35
commit, it's effectively a valid
6:36
transaction. And it means that you know
6:39
all the rights that we were going to put
6:41
in this write ahead log block were
6:43
completed or not necessarily completed
6:45
but they're written in the write ahead
6:46
log and you know we're not going to have
6:48
anything done partially. So basically if
6:50
the system were to shut down and you
6:53
know we needed to go ahead and make sure
6:54
that everything were in a consistent
6:56
state we could go through all the
6:58
entries of the write ahead log replaying
7:00
every single transaction and rebuilding
7:02
the state that we need to ensure that
7:04
we're not only in a consistent state but
7:06
that all of those transactions were
7:07
atomically executed. Either we fully
7:10
execute one of these transaction blocks
7:12
or we don't execute it at all. Okay
7:14
guys, well I hope this was a useful
7:16
introduction to acid transactions. Like
7:18
I mentioned, ACID is effectively just a
7:20
massive abstraction for the way that
7:22
certain databases choose to implement
7:24
the right functionality. Uh not all
7:27
databases uh implement ACID transactions
7:29
because doing so can incur a large
7:31
penalty. And so in future videos, we're
7:33
not only going to see how you would
7:34
implement ACID transactions, but also
7:36
what certain other types of databases
7:38
decide to do instead and basically what
7:41
they support instead of complete full
7:43
isolation or serializability as some
7:45
people might call it. Have a good one
7:47
guys and I will see you

##v8:

0:00
hey everyone and welcome back to the
0:02
channel this is your host YouTube's
0:04
favorite power bottom Jordan uh with
0:07
that being said let's go ahead and get
0:09
back into some systems design with all
0:11
the layoffs going on as I've covered
0:12
plenty in this channel uh and view horde
0:15
of course uh you know it is a great time
0:17
to get studying and go ahead and get
0:20
really good at this content so that you
0:21
can you know pass your interviews in the
0:23
future so today we'll be talking about
0:25
read committed isolation a topic that I
0:27
personally have been putting off as uh
0:29
to quote my ex-girlfriend I am scared of
0:31
commitment so let's go ahead and get
0:33
into it alrighty so let's go ahead and
0:35
get into the iPad portion of this video
0:37
so the subject of today's content is
0:40
read committed isolation so before we
0:43
can actually go ahead and get into what
0:45
that means let's talk about databases a
0:47
little bit so in the past we've
0:48
mentioned the databases are
0:50
multi-threaded and so effectively what
0:52
multi-threaded means is that we have a
0:54
bunch of reader threads a bunch of
0:55
writer threads basically a bunch of
0:58
concurrent executions have happening on
1:00
the same computer and so we don't
1:02
actually know the order of those
1:04
executions and as a result of that we
1:06
can have a lot of issues that basically
1:08
threaten the correctness of our results
1:10
so as you can see in My Graph here you
1:12
know in time one we would have a writer
1:13
thread time two we would have a reader
1:15
thread going time three we have a
1:17
different reader thread but the point is
1:19
because all of these are being sent at
1:21
around the same time there's not really
1:23
any good way for us to know exactly
1:25
what's being written first and then
1:27
what's being read I mean this could
1:28
happen in a completely different order
1:30
and so we don't know about the
1:32
legitimacy of our results it's really
1:34
hard to tell and so we need to go ahead
1:35
and put in some precautions so basically
1:38
what this does is it introduces a lot of
1:40
race conditions so before we uh you know
1:43
talk about some examples of race
1:44
conditions that we might see in a
1:46
database I just want to introduce some
1:48
terminology which I've kind of mentioned
1:49
in the past but let's go ahead and make
1:51
it official so this concept is actually
1:53
going to be the word commit committing a
1:55
right basically just means that you know
1:58
the right is confirmed in the database
2:00
for example if we have a sequence of
2:02
Rights you know I'm writing in one row
2:04
and then I'm writing in a second row
2:05
those two rights are only committed when
2:08
both of them are successful right so if
2:10
I've written in the first row but I
2:11
haven't yet written in the second we
2:12
know that that first right is not yet
2:14
committed so they have to all be
2:16
finished
2:16
okay so let's talk about some examples
2:19
of race conditions and so the first one
2:21
is going to be called the dirty right
2:24
so the dirty right while it sounds like
2:26
a sex position is not in fact it's
2:28
something that happens in databases so
2:30
let's imagine we have two threads right
2:31
we've got T1 and T2 that stands for
2:33
Threads not time and then the time axis
2:36
is actually going to be going down this
2:37
way so as you can see as we go down
2:39
that's kind of the order of what
2:41
operations are happening so imagine we
2:44
have basically two different rows on our
2:46
database maybe two tables in the
2:47
database and one row from each one is
2:49
going to be our you know bath water
2:51
table and then the other is going to be
2:53
our delivery addresses table for example
2:55
you know great and great example right
2:57
so our bathwater.purchaser uh T1 is
3:01
basically me right
3:03
I am going to go ahead and try and
3:05
purchase some bath water so I'm setting
3:06
the purchaser to Jordan at the same time
3:09
our former president Donald Trump is
3:11
also trying to purchase the same
3:12
bathwater we have similar taste in women
3:13
and so he is going to go ahead and set
3:16
bathwater.purchases to Donald makes
3:18
sense similarly though his right is
3:21
reaching the database faster than mine
3:23
so now he has address dot delivery water
3:25
is the white house because that's where
3:27
he wants it sent to and I of course want
3:29
it sent to your mom's house at T4 so
3:31
basically our rights go ahead and get
3:33
interleaved even though my right of I
3:35
guess technically got there first he was
3:37
able to get both rights done before I
3:39
could and then we're both committing at
3:41
time five so now what ends up happening
3:43
basically is as a result of this dirty
3:46
right we see that um you know the the
3:48
purchases bro has Donald set as the
3:51
value so this one wins and then as far
3:53
as the delivery water goes because you
3:55
know Donald was after Jordan as far as
3:57
the delivery water goes your mom's house
3:59
wins over the White House so now we have
4:01
inconsistent results out of our database
4:03
and effectively what a dirty right is is
4:06
when writing
4:08
over
4:10
uncommitted values
4:14
so in this case as you can see none of
4:16
our rights had actually committed and we
4:18
just wrote over them and so the problem
4:20
with that is that we can then get in
4:21
this inconsistent State and that is
4:24
going to break some invariance of our
4:25
database so how can we actually go ahead
4:28
and think about fixing a dirty right
4:30
well what would work really nicely is
4:33
something like locking so if you're not
4:34
familiar locking basically just means
4:36
that you know if I have the lock on a
4:38
certain row no one else can do anything
4:40
with that row right they have to be able
4:42
to grab the lock but they can't until I
4:44
release it so let's imagine this one is
4:46
me this one is Donald
4:49
and then you know we're both trying to
4:50
grab two rows to write to them so let's
4:52
imagine first I grab the lock now I have
4:54
it Donald says okay well I'm gonna go
4:57
ahead and try to do the same thing
4:59
because I want to write
5:00
guess what buddy you can't I already
5:02
have it so that's not gonna work now you
5:05
might say oh well Jordan what if he
5:06
grabs row number two and then you try
5:09
and grab row number two and then you
5:11
know now you're in a deadlock because
5:12
neither one is going to release either
5:14
of the locks and effectively we both
5:16
want each other's resources and we're
5:18
never gonna give them up well I would
5:19
argue that one solution is you could
5:21
just grab the rows in the same order the
5:23
database could somehow decide The
5:24
Ordering of the rows or if worse comes
5:26
to worst you could do some sort of
5:27
Deadlock detection which is a thing in
5:29
you know some kind of pieces of Hardware
5:32
like databases where they'll actually
5:34
look for resources in deadlock and if
5:35
that's the case they'll have to make one
5:37
of those transactions give up its locks
5:39
okay so row level locks are basically
5:42
how we go ahead and fix dirty rights
5:44
which is writing over uncommitted data
5:45
however dirty rights are not the only
5:48
issue that we're talking about today
5:49
another one is dirty reads so again
5:52
we've got two transactions where the
5:54
vertical axis is going to be time sorry
5:56
for my crappy arrows
5:58
so in this case basically we've got
5:59
transaction one which is me removing ten
6:03
dollars from my balance because I have
6:05
bought more foot pictures from Karina
6:06
cop in transaction two you know maybe
6:09
it's me checking my bank account balance
6:11
and seeing that I am ten dollars down
6:14
right similarly now Karina cough is
6:17
going to be receiving 10 more dollars
6:19
but what if the right to karinikov
6:21
receiving 10 more dollars fails for
6:22
example who knows maybe her bank account
6:25
is now invalid or you know she was
6:27
laundering a ton of money and now her
6:29
account has just been deactivated the
6:31
issue now is that I have gone ahead and
6:33
read an uncommitted right right because
6:36
Jordan balance minus ten dollars was not
6:38
actually yet committed the commit
6:40
happens down here because the commit
6:43
only happens once both of these rights
6:44
go through and since the Karina cop one
6:46
failed I've now read an incommitted uh
6:49
or not in committed but uncommitted
6:51
right and so basically a dirty read is
6:53
reading
6:54
God I can't spell today
6:58
reading
7:00
uncommitted
7:03
data and obviously that's a problem
7:05
because now if I'm reading my bank
7:07
account balance I think that I lost ten
7:10
dollars but I still don't have my foot
7:12
pictures and so that is obviously going
7:14
to be an issue so how can we go ahead
7:16
and fix dirty reads well there are a
7:18
couple of options
7:19
the first one is we could do row level
7:21
locking like what we did before right
7:23
let's scroll back up here I could do row
7:26
level locks because I would have to grab
7:28
the relevant Row in order to basically
7:31
read it but I couldn't read it yet
7:33
because someone else had it locked
7:34
because they were writing that row
7:36
however that's kind of a pain in the ass
7:38
the reason being that locking is slow
7:40
and if we can avoid having locks that is
7:43
very good because it means that anytime
7:44
we're writing something all of the other
7:47
threads trying to read it are going to
7:48
be unable to do so and they are going to
7:50
get bottlenecks significantly reads are
7:53
much faster than rights and as a result
7:55
you know one slow right can slow down a
7:57
ton of reads and so it would be much
7:59
better if we could just avoid using
8:01
locks in general
8:02
so basically the fix here is that we
8:04
want to store the old value until the
8:06
commit right so let's imagine my bank
8:08
account old value was 100 then I buy
8:11
those foot pictures so we've got new at
8:13
90 and then the second Karina cop
8:15
gets hers uh to a plus 10 then we switch
8:19
that pointer over to new and now guess
8:22
what we're reading from this value so
8:24
this is how we're able to do this we
8:25
just have to store an extra value and
8:26
this way even though we're incurring a
8:28
little bit more storage overhead we are
8:31
greatly decreasing the amount of locks
8:33
that we have to wait on and speeding up
8:34
our database significantly so again
8:36
that's why I have this right over here
8:38
could use locking but much more
8:39
expensive we shouldn't be doing that so
8:42
ultimately I've now covered two types of
8:43
race conditions right we've got our
8:45
dirty Reeds right here and then
8:47
scrolling all the way up we've got our
8:49
dirty rights so basically ultimately any
8:52
database that is going to protect
8:54
against both dirty reads and dirty
8:56
rights is one that is implementing read
8:59
committed isolation and so now you know
9:01
what that term means basically the point
9:03
is if we're protecting against those two
9:05
this database is considered to be read
9:07
committed however we should note that
9:10
there are many more rage conditions than
9:12
just the ones that I've outlined in this
9:14
video and in subsequent videos we're
9:15
going to go ahead and talk about those
9:17
there are basically you know others that
9:20
are even more pesky and harder to catch
9:22
and so the databases that do protect
9:23
against those obviously have to use more
9:25
complex Solutions we'll talk about those
9:27
in the future videos and I will see you
9:29
guys next time

##v9:


Intro
0:00
hey fellas welcome back uh I know I'm
0:02
sitting kind of alarmingly close to the
0:04
camera today but I'm gonna kind of try
0:06
this one out uh yes I have bad skin
0:08
welcome to the party I'm a coder what
0:10
else is new so uh first of all quick
0:12
announcement thanks everyone for 7 000
0:14
subscribers I really appreciate that and
0:17
uh yeah I'm eternally grateful to all of
0:19
you especially those of you who have
0:20
been here since even like before I
0:22
collaborated with gorab or whatever and
0:24
got a few thousand people
0:26
um yeah again I'm making these videos to
0:28
help people mostly and the subscriber
0:30
count is not really what I'm optimizing
0:32
for at the end of the day but you know
0:33
to me it indicates that uh people are
0:35
gaining some you know usefulness out of
0:37
this Channel and that makes me a happy
0:39
guy you know I always want to try and
0:40
help and I think I'm doing that so far
0:42
so that makes me very happy Additionally
0:45
the more subscribers I get uh you know I
0:47
can stick it to this one Tick Tock girl
0:49
that I went out on a date with and she
0:50
was not into it so let's uh move on from
0:54
that and get into some content for today
Read Skew
0:56
all right we're back in Action I've got
0:58
the iPad in front of me so let's get
0:59
started so today I am going to be
1:01
talking about another race condition and
1:04
I do not mean Israel Palestine I mean
1:06
repeatable read which is also known as
1:08
read skew so basically the way I'm going
1:11
to go ahead and talk about this is by
1:13
doing the following with an example so
1:15
let's imagine I have a table that shows
1:17
all the bank accounts of the Kardashians
1:20
I know there are eight names on here
1:21
there might be more than that I'm sorry
1:23
I even know eight but you know don't
1:25
judge me whatever so the predicate of
1:27
this table let's imagine that we know
1:29
the balances must add up to a million
1:31
dollars they at one point did add up to
1:32
a million dollars and I'm going to make
1:34
the arbitrary constraint that basically
1:36
they can only exchange balances with
1:38
each other so there's always going to be
1:40
a million dollars of value in this table
1:42
okay so we have basically all the
1:44
Kardashians listed below and their
1:46
respective balances I got pretty lazy
1:49
finding two more names hence why Scott
1:50
has 300K so let's imagine that I'm doing
1:53
some kind of housekeeping work for the
1:55
family I'm going through the database
1:56
and telling everyone how much money they
1:58
have in their bank account so that's
1:59
going to require me to read every single
2:01
row of the database and then return all
2:02
of those values so it's going to start
2:04
something like this I'm going to read
2:05
Caitlyn I'm going to read Kylie I'm
2:08
going to read Kendall I'm going to read
2:09
Chloe I'm going to read Courtney and
2:11
then right before I read Chris Caitlyn
2:14
decides that she needs some more plastic
2:15
surgery so all of a sudden Chris the
2:18
mother of the family is going to send
2:19
Caitlin her hundred thousand dollars so
2:22
now Caitlyn actually has 200k
2:25
and Chris has zero dollars so basically
2:29
the invariant of the table still holds
2:30
right all these values do still add up
2:32
to a million but we had already read
2:34
that Caitlyn's value was 100K and now
2:37
when we finally get to Chris we are
2:39
going to read that her value was Zero
2:41
because this right has just executed in
2:43
the middle of our massive read right our
2:45
rights don't actually block reads and
2:47
we're still reading committed data this
2:49
entire time so there's no issues here
2:50
but now when we add up all of these
2:53
balances we're actually going to be
2:54
minus a hundred thousand because we
2:56
didn't account for the fact that Caitlyn
2:58
is going to be getting another hundred
3:00
thousand Midway through the read so that
3:02
is basically the idea of read skew we
3:05
have this table it has some sort of
3:07
invariant and ultimately due to a right
3:09
in the middle of some massive read
3:11
possibly due to an analytical query the
3:13
invariant no longer holds we want to be
3:15
able to see the database in a consistent
3:18
State and basically because we're doing
3:20
this long read and there were rights
3:22
interjecting it we weren't able to do so
3:24
so let's think about ways that we can
3:26
fix this and the way that I'm going to
3:27
propose starts with our friend the right
3:29
ahead log so let's go ahead and scroll
Right Ahead Log
3:31
down so as we know every right that goes
3:34
into a database is going into our right
3:36
ahead log that's really useful for both
3:37
durability and atomicity and so for the
3:41
right ahead log it's just one list on
3:43
disk and all the rights are sequential
3:44
so what this allows us to do is actually
3:46
go ahead and order transactions so as
3:49
you can see you know if we're making
3:51
sure that writes and reads block each
3:52
other they don't necessarily have to so
3:54
I can take this one out but you know we
3:56
have a write at T1 we've got to write at
3:58
T2 we've got a right at T4 and basically
4:01
whatever hits the write ahead log first
4:03
we can assign a monotonically increasing
4:05
sequence number monotonically increasing
4:07
just means that it's going up by one
4:09
every single time but it's not a big
4:10
deal and you know same goes for all of
4:12
these other lines right here that we're
4:14
adding in the future they're going to
4:15
get sequence numbers as well so we've
4:18
now basically given all of our
4:19
transactions a number and for a given
4:21
transaction let's say we want to be able
4:24
to see a consistent snapshot of the
4:26
database at the time that that
4:28
transaction was written so let's see an
Exercise
4:30
exercise of how we can actually do this
4:32
so let's imagine we have a bunch of
4:33
rights to our database which again has
4:35
the account balances of a bunch of
4:37
Kardashians and we want to basically see
4:39
the database snapshot at T15 well the
4:43
way that I'm basically going to propose
4:45
that we do this is every single time
4:47
that a value gets overwritten instead of
4:50
just deleting that value what you do is
4:52
store all of the values with the
4:54
transaction number that wrote them and
4:56
then keep all of those values so as you
4:58
can see a transaction one basically said
5:00
that Caitlyn's bank account account
5:02
balance was 100K on transaction 6 it was
5:05
overridden to be 300K and on transaction
5:08
12 it was overwritten to be 200k the
5:10
point is here you don't have to actually
5:12
write a value for every single one of
5:14
the transactions but only the
5:16
transactions that modify the rows
5:17
themselves so these are going to be
5:19
relatively sparse it's not going to take
5:20
up a ton of extra storage in theory okay
5:23
so let's imagine we want to basically
5:25
see what the database was looking like
5:27
at T15 right so whatever transaction 15
5:30
was written so right off the bat we know
5:32
that something like this right here
5:34
which was written in transaction 17 is
5:36
invalid and the same goes for this right
5:38
that was done by transaction 22.
5:41
so to really find what we care about
5:43
from transaction 15 I'm going to draw
5:45
this line that basically cuts out all
5:47
the rights after transaction 15 and then
5:50
for all of the rows we're going to take
5:52
basically the most recent value that was
5:55
before 15. so in the case of Caitlyn
5:57
that's the right that was done at
5:58
transaction 12 so she has two hundred
6:00
thousand dollars in the case of Kendall
6:02
it was the right of transaction 15. so
6:05
she has a million dollars in the case of
6:07
Chris that key was only written at
6:09
transaction 22 in the first place so at
6:11
transaction 15 Chris doesn't even exist
6:14
there's no Row for Chris in the database
6:16
and then finally for Lamar it was only
6:18
written once at transaction three and
6:20
there's going to be 100K so basically
6:22
again the point is you don't delete
6:24
these old values but rather you store
6:26
them and so for these big reads that we
6:28
might have that take a long time to
6:30
execute we don't have to risk seeing the
6:32
database at some inconsistent state but
6:34
rather we can use a database snapshot
6:36
and that right there is the premise
6:38
behind snapshot isolation so guys I hope
Outro
6:41
you enjoyed this video relatively short
6:43
but hopefully simple my point of this
6:45
new series is to make sure to really
6:46
hone down on topics and not brush over
6:49
them like I at times did in my previous
6:50
series snapshot isolation I probably
6:53
covered in all of 30 seconds in my
6:55
previous series and while that's good
6:56
for some people for others it is you
6:59
know good to make sure to really cover
7:01
every single edge case and make sure
7:02
that you really understand it so anyways
7:04
guys have a great night wishing you all
7:06
the best and thanks again for all the
7:07
love

##v10:

0:00
hello everybody and welcome back to the
0:02
channel I am racing to get this video
0:04
recorded before my roommates come home
0:06
and I also have to poop pretty badly so
0:08
I'm in quite a rush let's go ahead and
0:10
get started today we'll be covering
0:12
right skew and Phantoms
0:14
alrighty so I've got the iPad out so
0:17
let's go ahead and get into today's
0:18
lesson basically the subject of today is
0:21
Right skew which is another type of
0:23
database race condition so one database
0:26
race condition and this is kind of a
0:27
disclaimer that I didn't explicitly
0:28
cover in its own video is lost updates
0:31
uh the reason for that being that I
0:32
effectively covered lost updates in the
0:34
acid transactions introductory video
0:36
where you know one example is my friend
0:38
and I are both trying to modify a
0:40
counter and we both want to add one to
0:42
it but because I basically read the old
0:44
value and so did he one of our
0:46
increments gets lost and basically the
0:49
solution to that is just logging so
0:50
let's not worry about that we're going
0:52
to talk about right SKU so let's go
0:54
ahead and get into it basically here's
0:56
an example of red SKU so imagine that we
0:59
have basically an emergency room and
1:00
right now I have a table with the names
1:02
of the doctors and whether they're
1:04
active or inactive now one invariant of
1:06
this emergency room is that greater than
1:08
one doctor has to be active right we
1:11
need at least one doctor active at all
1:12
times so if a patient comes in with an
1:14
emergency see they can be tended to so
1:16
we've got Dr Oz and Dr toboggan
1:18
currently active but let's say that they
1:20
both want to take breaks Dr Oz you know
1:22
has to take a break to go grab some
1:24
tissues and lotion and toboggan just
1:26
went ahead and smoked some weed so now
1:28
they both want to set themselves to
1:29
inactive and they can basically just
1:31
both go ahead and do separate rights and
1:33
do that right inactive and then the same
1:36
thing goes for Dr toboggan we've changed
1:39
our status and now the invariant of the
1:41
database is broken and this is bad so
1:44
how can we actually go ahead and avoid
1:46
something like right skew from happening
1:48
well basically the solution is to use
1:50
locking but a little bit differently
1:52
than before so as you can see over here
1:54
on the left side of the screen we've got
1:57
three different locks and these are
1:58
going to be our row level locks all
2:00
databases have them you're able to
2:02
basically grab a lock on a row when you
2:04
want to be able to modify it but the
2:05
fundamental issue with right SKU is that
2:08
the two rows that are basically
2:09
affecting the invariant are not impacted
2:12
by each other's locks right if I want to
2:14
write to Dr toboggan I only have to grab
2:17
Dr toboggan's lock and I don't need to
2:19
grab Dr Oz's lock hence these two rights
2:21
can actually both go ahead and happen
2:23
and they can just grab their own lock
2:25
and there's never actually an issue with
2:27
the invariant however with right skew in
2:30
order to prevent it what we need to do
2:32
is actually go ahead and grab all the
2:34
locks of the relevant rows so in the
2:36
case of red SKU what we need to do is
2:38
grab locks
2:40
and we want to do it
2:42
where doctor is active
2:46
right so this way if any doctor wants to
2:49
go from active to inactive we have to
2:52
basically go ahead and grab all the
2:53
locks of the other active doctors this
2:56
way when Dr toboggan and Dr Oz tried to
2:59
go offline basically at the same time
3:01
they both try and grab the same locks
3:03
and only one of those rights is going to
3:05
be permitted to win the other is going
3:07
to fail so as you can see with right SKU
3:09
the solution is basically to grab more
3:11
locks of rows that you may not have
3:13
thought you needed but the truth is that
3:14
you do because even though these rows
3:16
aren't inherently related they both
3:18
impact the same database invariant so I
3:21
hope that makes sense let's move on to
3:23
another variation of right skill so this
3:25
one is actually going to be called
3:27
Phantoms so let's imagine that I'm in a
3:30
bakery right and it's me and Trump
3:32
because we're both fat and we love
3:34
cookies so as you can see here are two
3:36
existing rows in the database let's say
3:39
that Jordan went ahead and bought the
3:41
cookies right so that's an example of
3:42
the room and then you have my email
3:43
right there sexycodermanage gmail.com
3:46
similarly Trump went ahead and bought
3:48
the pie he's got carpets match drapes
3:51
yahoo.com but what if we were to both go
3:54
in there and try and get a cupcake
3:56
so we've got this row and I would go
3:59
ahead and write myself because I just
4:01
claim the cupcakes and then you know we
4:03
got our email blah blah and then
4:06
similarly Trump who's trying to get the
4:08
cupcakes at the same time also puts his
4:10
Row in the database
4:11
so a cupcake
4:13
Donald and then his email right
4:16
the issue now is that we've both claimed
4:19
cupcakes if there were locks on these
4:20
rows
4:21
it wouldn't even help us because the row
4:23
that we want to lock which is you know
4:26
this cupcake row right here it didn't
4:28
even exist yet we actually wrote a new
4:30
row to the database table so we couldn't
4:32
even lock it it literally was not
4:34
physically possible and that's kind of
4:36
the issue with Phantoms Phantoms occur
4:41
when two people
4:45
right
4:47
new rows
4:49
that conflict
4:52
and the issue with new rows is there are
4:56
no locks
4:57
to grab
5:00
if we can't both grab a lock it means
5:02
that you know our rights aren't actually
5:04
going to realize that they're
5:05
conflicting with one another they're
5:06
both going to go through and then we
5:08
have a broken database invariant so how
5:10
can we actually go ahead and fix a
5:12
phantom
5:12
this is by doing something known as
5:15
materializing conflicts so a
5:17
materializing conflicts basically means
5:19
is that for every row or basically for
5:21
every item in the bakery stock that we
5:23
could possibly have some sort of
5:24
conflict over we needed to pre-populate
5:27
that Row in the database so that we can
5:29
actually grab a lock for it we said the
5:31
bakery has cookies pie and a cupcake but
5:34
instead of just you know writing that
5:36
row into the database when someone
5:38
claims them we need to pre-populate all
5:40
of those rows in the database already so
5:42
that they can actually have a lock
5:43
object corresponding to them so in the
5:46
case of the actual cupcake you know we
5:48
have Jordan
5:49
we have Donald and we both want it to be
5:52
the case that we get our fields in the
5:54
name and email however what we're both
5:57
going to have to first do because
5:58
there's now a row that exists is grab
6:00
the lock for it so only one of us is
6:02
going to win let's say Jordan manages to
6:04
grab the lock first and then goes ahead
6:07
and writes his name here and then puts
6:09
his email over here it means that now
6:12
Donald cannot overwrite this you know we
6:14
just go ahead and say if there's already
6:15
a name in there that it can't be
6:16
overwritten and now Jordan wins and
6:18
actually gets the cupcake before before
6:21
we were able to materialize conflicts
6:22
there was no actual lock to prevent race
6:25
conditions happening and now the
6:27
invariance of our system were broken
6:28
okay guys well I hope that makes sense
6:30
uh as always hope the video is useful
6:33
and if you have any questions reach out
6:34
to me in the comments have a great day
6:36
and I will speak to you soon


##v11:

0:00
hello everybody and welcome back to the
0:02
channel as you can see I look slightly
0:04
less like a discount version of Sam
0:06
bankman freed today the reasoning for
0:08
that being that I am about to go out uh
0:10
this is actually my last time going out
0:12
in New York city so I'm actually in a
0:13
bit of a rush to get the night started
0:15
so let's make this video quick today
0:17
we'll be talking about actual serial
0:18
execution so let's get it started okay I
0:21
have whipped out the iPad and I've
0:22
whipped out my dick let's get started so
0:25
actual serial execution what is it well
0:27
basically in the past few videos what
0:29
we've done is we've talked a lot about
0:31
weak forms of isolation the reason being
0:33
that actually achieving transactions
0:35
that don't step on each other's toes and
0:37
cause race conditions is not only hard
0:39
to do it's also expensive to do it makes
0:42
the performance of the database much
0:43
slower and so when actually trying to
0:45
achieve full serializability or
0:47
isolation we need to make sure to take
0:49
care to actually keep performance as
0:51
good as possible or else our databases
0:53
are going to be pretty useless at scale
0:55
so one attempt at doing this is actually
0:57
come around a little bit more recently
0:58
and it's known as actual serial X
1:00
execution the reason I've put volt DB in
1:03
parentheses is if you're curious to see
1:04
an actual example of this in the wild
1:06
you should look up volt DB it's
1:08
basically doing exactly what I'm going
1:09
to describe in this video so what is it
1:11
that actual serial execution actually
1:13
means well for starters basically CPUs
1:16
are faster than they used to be and so
1:19
now as opposed to having to necessarily
1:21
rely on multi-threading one thing that
1:23
you can actually do in order to make
1:24
sure the transactions are just running
1:26
in order and not running at the same
1:27
time is literally running them in order
1:30
and not running them at the same time so
1:32
all we're doing is running every single
1:34
thing possible on just one core and so
1:37
there are some limits to this right
1:38
because obviously if we were doing
1:40
everything in a multi-threaded way that
1:41
allows us to get a lot of performance
1:43
gains on multi-core processors however
1:45
you know putting everything on one core
1:47
is going to require some extra work on
1:49
our end to make sure that things are
1:50
fast enough so there are a couple things
1:52
that are going to limit the performance
1:53
of your system if you're running
1:55
everything on One Core so the first
1:57
thing is going to be using a disk right
1:59
I've drawn this picture of a hard drive
2:00
many times over and the fundamental
2:02
issue with disks is that they are slow
2:04
we've got this metallic seeking disc and
2:07
as a result it's just going to be a lot
2:09
slower than using something like an SSD
2:11
or perhaps even better literally keeping
2:13
all of your data in memory so we've got
2:16
a couple of things here the first thing
2:18
is that we should be running pretty much
2:20
our actual serial execution on a
2:22
database that keeps everything in memory
2:23
and it's got some pros and some cons
2:25
that come with that the first thing is
2:27
that it's going to be faster right we
2:28
can use our hash index or if we want
2:30
support for range queries we can use a
2:32
self-balancing binary search tree based
2:34
index like a red black tree and AV L
2:37
tree something like that but it comes
2:39
with the cons of a having far less space
2:41
right memory is more expensive so most
2:43
computers don't have as much of it and B
2:45
and more importantly the data is not as
2:48
durable I didn't even write that there
2:49
but you know it's something that I
2:50
realized you can use a right ahead log
2:52
but then now you're writing to disk
2:53
again and that slows things down the
2:55
other important thing we're going to
2:57
touch upon a little bit more is that the
2:59
network is slow right so what is it that
3:01
you're actually conveying to a database
3:02
well of course there's some data that
3:04
has to be written but if you're just
3:05
running you know a certain complicated
3:07
query actually sending that query to the
3:10
database itself can be slow so let's
3:12
imagine that you know we're YouTube and
3:14
we have this basically SQL script right
3:16
subscribe to channel.sql and we're
3:18
sending that over the network from our
3:20
server
3:21
to the database
3:23
and what if that you know script is
3:25
effectively long enough that maybe it's
3:27
two kilobytes in size compared to the
3:29
actual data which might just be like
3:31
literally putting uh one name in the
3:33
subscriber column of a channel the
3:35
actual script itself can be a lot of
3:37
data and network bandwidth is obviously
3:39
going to be a lot slower than just
3:41
running instructions off of a CPU so
3:44
it's very important to minimize the
3:45
amount of data that we're sending over
3:47
the network so how can we do that well
3:49
basically in order to do this we would
3:52
use something known as stored procedures
3:54
so if you've heard of stored procedures
3:56
it's probably actually in a negative
3:58
light the reason being that generally
4:00
speaking you don't need to use these
4:01
stored procedures are basically when you
4:04
know before you even start running your
4:05
database running your application you
4:07
send a bunch of SQL functions or the
4:09
functions could really be in any
4:10
language to your database saying here
4:13
are the types of commands that I'm going
4:14
to tell you to do and when I want to
4:16
invoke these commands all I'm going to
4:17
do is you know send over a parameter
4:19
right so you know we're going to
4:21
basically call the function we're going
4:23
to give it it's our arguments so for
4:24
example if we want to add inventory to a
4:26
certain product maybe we have the SQL
4:28
script for that already pre-loaded onto
4:30
the database and what we would do is
4:31
send over something like the product ID
4:33
and the quantity right and so that way
4:36
that's a lot less data that we're
4:37
sending over the network than the entire
4:39
SQL script to add the inventory with the
4:41
product ID and quantity hard coded in
4:43
right the product ID is probably just
4:45
literally a number so 32 bits and the
4:47
quantity is another number so 32 bits
4:49
compared to you know however many
4:51
characters that script might actually be
4:53
okay so what are the advantages of the
4:55
stored procedure well of course like I
4:57
mentioned it's less data to send over
4:59
the network and that's hugely important
5:01
when every single thing that we're
5:03
sending over the network every single
5:04
write that we have to do is
5:05
bottlenecking all of our other rights
5:07
because they're only occurring on one
5:08
single thread
5:10
on the other hand stored procedures
5:11
themselves are not great to use the
5:13
reason being that just for a developer
5:15
they're kind of a pain in the ass it's
5:17
annoying to kind of keep these in line
5:18
with your other code because you know
5:20
it's held on the database it's not as
5:21
easy to check into your version control
5:23
system it's not as easy to deploy these
5:25
in a good way you know especially if you
5:27
have multiple instances of a database if
5:28
you have replicas or anything like that
5:30
it's not so easy to you know kind of
5:32
send all of these stored procedures to
5:34
all of them but in conclusion guys
5:36
basically the general gist of this is we
5:38
know the underlying Assumption of how
5:40
we're achieving isolation is we have to
5:42
do it on one chord so what's every
5:44
single possible optimization that we can
5:46
do in order to make those reads and
5:48
writes on that single core as fast as
5:49
possible the slower the reads and the
5:51
rights the more delay that every other
5:53
operation becomes because they're
5:55
effectively all just enqueued on this
5:57
single core anyways guys I know it's a
5:59
short video but I got to get out of here
6:00
and get drunk so have a great night and
6:02
I will hopefully see you soon

##v12:

0:00
Hey everybody and welcome back to the
0:02
channel. Um, so if you've been following
0:04
up with uh current events in my life, I
0:07
have recently left Google and I'm
0:08
actually doing some traveling. I'm in
0:10
Amsterdam, hence the change of scenery
0:11
here. Um,
0:14
for those of you who are wondering why
0:15
I'm not able to post more often than one
0:17
time a week, I'm probably spending about
0:19
22 hours a day and hence I'm a little
0:21
bit distracted. You know, I've been
0:22
considering front-end development more
0:24
so than distributed systems in the past,
0:26
you know, couple weeks. But for what
0:29
it's worth, I'm still trying to get
0:30
things out every once in a while, like I
0:31
mentioned, and this will probably be the
0:33
case for the next two-ish months. But
0:35
obviously, I'm still going to post
0:36
videos whenever I can. So, today we are
0:38
going to be covering two-phase locking.
0:40
So, let's go ahead and get into it.
0:42
Okay, I've got the iPad out, so let's go
0:44
ahead and get started. So, the subject
0:46
of today's video is two-phase locking.
0:49
So two-phase locking is just another
0:51
method of achieving isolation or
0:52
serializability, which effectively just
0:55
means that when we have a bunch of
0:56
transactions going on concurrently
0:57
within our database, it seems as if they
0:59
were just running one at a time. So in
1:02
our last video, we kind of discussed how
1:03
we would do this by literally running
1:05
them one at a time in terms of actual
1:07
serial execution. However, for today,
1:09
we're going to figure out a better way
1:10
of doing that by using a bunch of
1:12
locking. So let's go ahead and get
1:14
started. Typically, two-phase locking is
1:16
something that has been used in the past
1:17
because actual serial execution wasn't
1:19
feasible. CPUs weren't fast enough. And
1:22
so, you'll see this in a lot of
1:23
traditional SQL databases. Okay. So, the
1:26
thing that we're going to start out with
1:27
as follows. As you can see, I have
1:29
myself a row right here. You know, we
1:31
can go ahead and draw it out. And
1:32
imagine that the columns of this row are
1:34
basically my name and a shopping cart of
1:37
items that I want to purchase. And it's
1:39
got a corresponding lock. So basically
1:41
in the past, at least in my race
1:43
condition videos, what I've kind of
1:44
spoken about is locks basically means
1:47
exclusive access to this piece of data,
1:49
right? I couldn't read a row unless I
1:50
grabbed the lock. I couldn't write a row
1:52
unless I also grab the lock. So now what
1:55
we've got is this concept of basically
1:58
two-phase locking where instead of just
2:00
being a lock is enabling you exclusive
2:03
access to the row itself, you may
2:05
actually have a concept of shared
2:07
access. So in two-phase locking,
2:09
basically what we've got is the
2:10
following. We have a reader lock and
2:13
also a writer lock. So consider them the
2:15
same lock, but basically it's got two
2:17
modes. So if we want to go ahead and
2:19
read this row, what I can do is go ahead
2:21
and grab the lock right here in reader
2:24
mode. And basically, if I want to then
2:26
write to it, I would have to upgrade
2:28
that to a writer mode. But the kind of
2:30
trick here is that multiple threads or
2:32
multiple transactions can be reading a
2:35
row, but effectively in order to write
2:37
to that row, you have to be the only one
2:39
grabbing a lock. So you need to wait for
2:40
all of those readers to leave and then
2:42
upgrade your access to exclusive. So
2:45
basically the reason this works is that
2:47
for something like a read modify update
2:50
cycle which is basically the cause of
2:52
many different race conditions within
2:53
databases we know that our predicate aka
2:56
the read is always going to remain valid
2:59
because of the fact that whatever rows
3:01
we're reading in our predicate can't be
3:03
modified because no one is going to be
3:06
able to upgrade to get the writer lock
3:07
because we're concurrently reading them.
3:09
So again it means the predicate is
3:11
valid. Hence, this two-phase locking
3:13
approach actually works. So, what is a
3:16
big issue that we have to work with
3:18
here, and I'm going to circle this over
3:19
and over and over again because it's the
3:21
most important thing when it comes to
3:22
two-phase locking is deadlocks. So,
3:25
let's go ahead and show a diagram of how
3:28
this might happen. Because you might say
3:29
to yourself, "Oh, well Jordan, well, if
3:31
everyone grabs the resources in the same
3:33
order, it's impossible to have
3:34
deadlocks, right?" Well, no, that's not
3:37
necessarily the case. So, let's imagine
3:39
that if I put a square on a lock, that
3:41
means I'm grabbing it in reader mode.
3:42
And if I put a circle on the lock, I'm
3:44
grabbing it in writer mode. So,
3:46
basically, again, I'm doing the name
3:48
shopping cart example. Again, we've got
3:49
Jordan and Snoop Dogg. Two very re
3:52
realistic shopping carts for the both of
3:53
us. So, let's go ahead and get started.
3:55
Let's imagine that myself and Snoop Dogg
3:58
look at each other's shopping carts and
3:59
we say, "Oh, shoot. You know what? I
4:01
like those items that they have. Let's
4:03
go ahead and add those to ourselves."
4:04
So, what we're both going to do is read
4:06
each other's shopping cart and then
4:08
basically take all those items and add
4:10
them to our own. So, what that first
4:12
entails is let's imagine now that this
4:14
is the Jordan transaction, right? So,
4:16
first Jordan aka myself is going to grab
4:18
the reader lock for the Jordan lock.
4:21
It's going to grab the reader lock for
4:23
the Snoop Dog because I need to be able
4:25
to read a list in order to modify it.
4:27
And similarly, I need to be able to read
4:28
the Snoop Dogg row in order to
4:31
eventually get the items from it so I
4:33
can add them to my cart. And then
4:35
similarly, Snoop Dogg, which is
4:36
executing at the same exact time, he's
4:38
going to grab the reader lock for
4:40
himself, and he's also going to grab the
4:42
reader lock for Jordan, right? Because
4:44
we're both reading both our own and the
4:46
other person's shopping cart in order to
4:49
eventually make this update. So now,
4:51
what we would want to do is try and grab
4:52
the writer lock, right? But I've told
4:54
you earlier that you can't grab a writer
4:56
lock unless you are the only person
4:58
that's trying to write that row. Right?
5:00
If I were to put a circle here, that
5:02
would be bad. It would break the
5:03
invariant that, you know, a writer lock
5:05
needs to be exclusive. So, what we have
5:07
here is a deadlock. I can't complete my
5:10
right until Snoop Dogg completes his
5:11
right. And he can't complete his right
5:13
until I've completed my right. So, we
5:15
have a deadlock. And what that means is
5:18
that basically we need to go ahead and
5:20
avoid those somehow. So, the issue with
5:23
deadlocks is that it makes two-phase
5:24
locking slow. The reason for this being
5:27
that there are a bunch of deadlocks like
5:28
I've just described, and the system
5:31
effectively has to detect them and abort
5:33
them, right? It's going to have to go
5:35
back. It's going to have to cancel one
5:37
of the transactions that's part of the
5:39
deadlock and then run them again. So,
5:41
basically, in order for this to work,
5:43
you know, Snoop Dogg, I would have to go
5:44
ahead and pause this. I would have to
5:46
run Jordan to completion. And, you know,
5:48
once that's done, then I can run the
5:49
Snoop Dogg transaction.
5:52
So obviously that is going to take quite
5:54
a bit longer. We're no longer running
5:55
them concurrently and that's a problem.
5:58
Okay. And then in addition to basically
6:00
deadlocks which are a big problem with
6:03
two-phase locking. It takes a lot of
6:04
resources to grab the locks. So that's
6:06
slow too. And everything is defensive as
6:09
well. You know, we're grabbing locks
6:10
when we don't even necessarily need
6:11
them. We didn't even necessarily cover
6:13
all of our race conditions. Still, our
6:15
system here is not perfect. So let's
6:17
remind ourselves about phantoms. I
6:19
covered these I think two videos ago,
6:21
but basically uh phantoms are when you
6:23
do a read modify update cycle and the
6:26
update part is actually adding new rows
6:28
to your table. So in this case basically
6:31
let's imagine that uh you know a phantom
6:33
example would be this. My friend and I
6:34
both want to join a class with an
6:36
enrollment capacity of three. So let's
6:38
imagine that class is the flexibility
6:39
class at 6 p.m. So it's going to be
6:41
these two rows right here which I put
6:42
X's in front of. And right now there are
6:45
already two people in it. So we would
6:47
run the following SQL query on the right
6:49
over here put an arrow over there and
6:52
we'd basically say you know select all
6:54
the count uh from the classes basically
6:57
let's imagine the table name is classes
6:59
where the class name is flexibility and
7:00
the class time is 6:00. I personally
7:02
would like to get more flexible for
7:03
reasons I don't want to talk about. And
7:06
so basically the issue now is that
7:07
what's going to end up happening is that
7:09
we're both going to write rows to this
7:11
table, you know, with myself and then
7:15
him over here with my friend, Jordan's
7:19
friend. And so now there are four people
7:21
in the class. Why are there four people
7:23
in the class? Because these rows didn't
7:25
even exist yet. So we couldn't put locks
7:27
on them to prohibit each other from
7:28
writing. All we did was both grab the
7:31
reader locks
7:33
like so, like we saw just before. And
7:35
then we were both able to make a right.
7:37
There was nothing prohibiting us because
7:39
again, there's no locks to be had on
7:41
these two rows that don't yet exist. So,
7:44
like I say over here, we need to be able
7:45
to lock rows that don't even exist yet.
7:48
So, how can we fix this? Well, there's
7:50
something known as predicate locks. So
7:52
predicate locks are basically allowing
7:54
us in certain databases to grab all rows
7:58
that fit certain conditions. So in this
8:00
case, you know, I wanted to get my
8:02
predicate by figuring out all the rows
8:04
where the class name was flexibility and
8:06
the class time was 6:00. So in the case
8:09
of a predicate lock query, I would say
8:11
to myself, well, okay, I know that this
8:13
is kind of the predicate I want to put a
8:15
lock on. So before I actually make my
8:17
write, please put a lock on all of the
8:20
rows where the class name is flexibility
8:21
and the class time is 6:00. And that way
8:24
if the row doesn't even exist yet, it
8:26
would still have a lock on it because it
8:27
fits those parameters. That being said,
8:30
the issue with predicate locks is that
8:31
they're slow to run. We have to evaluate
8:33
this entire query where class name is
8:35
flexibility, class time is 6:00, and if
8:38
there's not necessarily an index that
8:40
perfectly corresponds with this query,
8:42
this could be very slow to run and
8:44
evaluate. So, what we move on to then is
8:48
the last part of this lesson called
8:50
index range locking. I basically already
8:52
described this predicate lock where I
8:54
would go ahead and search out these two
8:56
rows in the table and lock them. But the
8:58
issue with that is it takes a while.
9:01
Why? Well, let's imagine we have this
9:03
table right here where we have an index
9:05
on the class name field, but we don't
9:07
have an index on the class time field.
9:09
The index is indicated by this asterisk
9:11
here. So, because class time is not
9:14
necessarily organized in a linear
9:16
manner, it's not going to be easy to
9:17
find these two rows. But what is really
9:20
easy is if we just search by class name
9:22
because there's an index on class name
9:24
and that means that everything is sorted
9:25
that way. So what we could actually do
9:27
instead is simply grab the lock for all
9:31
the rows in flexibility because it's
9:33
really easy to find all the flexibility
9:35
classes in O of login time simply by
9:39
virtue of the fact that uh there is an
9:41
index on that field. And so now we can
9:44
go ahead and lock more rows than we
9:46
actually need to because it's a little
9:48
bit faster to run that query. This does
9:51
come with the one disadvantage of the
9:53
fact that well now if we're locking more
9:55
rows than we necessarily need to it's
9:57
possible that other queries that didn't
9:59
have to be blocked are now going to be
10:00
blocked. So you want to be careful about
10:02
doing this right you wouldn't want to
10:04
lock the whole table for example just to
10:06
run a very small query because then
10:07
we're going to be blocking all
10:08
transactions. So, it's a delicate
10:10
balance, but the point is, you know, if
10:12
you have to run a super in-depth query,
10:14
sometimes it's better to actually just
10:16
lock a supererset of the rows, right?
10:18
Where you're actually locking more than
10:19
necessary because running the query to
10:22
figure out which rows to lock is a
10:23
little bit faster. Okay guys, I hope
10:26
that makes sense and as always, hope you
10:28
have a great day. I will see you in the
10:29
next

##v13:

0:00
hey guys welcome back for another video
0:02
uh still traveling here in Amsterdam so
0:04
trying to make it so I can crank out
0:06
about a video a week and stay consistent
0:08
a couple quick announcements first of
0:10
all uh By the time this one's posted uh
0:13
hopefully I'll be around 7 500
0:14
subscribers uh which if that is the case
0:16
then thank you guys a lot um I
0:19
appreciate all the nice feedback you've
0:20
been giving me all the work that you
0:21
guys are putting in if I don't have 7
0:23
500 I'll look like kind of an ass by
0:25
saying this but whatever we're close
0:26
enough another quick thing to say is I
0:29
want to give a shout out to two of my
0:30
viewers both of whom have reached out to
0:32
me in light of their recent new
0:34
positions uh both to Carl for his
0:36
position his senior engineering manager
0:37
at Google and for Roy on his offering
0:40
Microsoft these are guys who have been
0:41
commenting and interacting with the
0:42
channel for a while so to see that
0:44
payoff really does make my day sometimes
0:47
this channel doesn't get as many views
0:48
as I would like but at the end of the
0:50
day if that's really all that you care
0:51
about um I would just post Day in the
0:53
Life videos on Tick Tock and you know
0:55
[ __ ] systems aside so anyways let's get
0:58
into the content for today I'm gonna
0:59
whip out the iPad and get started all
1:02
right so today's video is going to be
1:03
about serializable snapshot isolation
1:05
which is a type of optimistic
1:07
concurrency control and so we're going
1:09
to talk about what that means so if you
1:11
guys watched last video which I'm hoping
1:12
you did it'll help you understand this
1:14
one a lot better what we did was we
1:16
talked about acid databases how they
1:18
tend to achieve full isolation or
1:20
serializability and in the past this has
1:22
been done with something known as
1:23
two-phase locking which is a pessimistic
1:26
concurrency control meaning that
1:28
basically every single transaction that
1:30
runs regardless of whether it impacts
1:32
other transactions has to grab locks for
1:34
all of the rows that it reads and writes
1:36
and this can be problematic because most
1:39
of the transactions like myself are
1:41
Sigma males they don't deal with other
1:43
transactions they do their own thing and
1:45
so if I'm just going to run one isolated
1:46
transaction and you know no one else is
1:49
even coming near it I don't have to
1:51
actually grab those locks I can just do
1:53
my own thing it would speed up the
1:54
database quite a bit so basically
1:56
optimistic and currency control is
1:58
asking the question well do we really
2:00
need locks effect if what's going to
2:03
happen is we can just run as normal and
2:05
if we do catch that we're about to make
2:06
a mistake we can just abort one of those
2:08
offending transactions and run it so
2:11
let's go ahead and start looking at a
2:13
couple of cases because the general gist
2:15
of this is we're reading from a snapshot
2:17
right and then once we see some read
2:20
modify update transactions that we don't
2:22
like then we're going to have to take a
2:25
little bit of extra action so let's look
2:27
at case one there are two cases here and
2:29
this is where SSI is going to come in so
2:31
in the first case let's imagine we have
2:34
a database snapshot at t18 so the first
2:36
thing I should say is a snapshot is just
2:38
a consistent state of a database at some
2:41
point in time in this case it would be
2:43
after transaction 18 was committed if
2:46
you want to know more about snapshot
2:47
isolation I already made a video on it
2:49
probably three or four ago so I'd
2:50
recommend watching that if you're a
2:52
little unsure what I mean here
2:54
so let's imagine we have some database
2:56
table where you know we've got a couple
2:57
of uh women and whether they like Jordan
3:00
or not obviously most of the rows are
3:02
going to be true but we'll talk about
3:04
how that changes throughout the example
3:05
so first we've got Kate Upton
3:08
and she obviously likes Jordan as one
3:10
does however t19 is coming in and t19 is
3:14
going to change that field from True to
3:15
false but as we know with transactions
3:18
first at least for All rights they're
3:20
going to be uncommitted and then
3:22
eventually they're going to commit so
3:23
there's this little bit of time where we
3:25
can see that a write exists but it
3:26
hasn't necessarily gone through yet
3:28
meaning we can't read it because if we
3:30
could read uncommitted rights I believe
3:32
if I'm remembering correctly that's a
3:34
dirty read so
3:36
let's go ahead and look at kind of the
3:38
the time by time things that's going to
3:40
happen so the first thing is transaction
3:42
19 is going to say Kate Upton no longer
3:44
likes Jordan maybe she saw me busting
3:46
out some moves on the Dance Floor I gave
3:48
her the ick who knows doesn't really
3:49
matter at time 20 I'm coming along and I
3:53
see that Kate Upton likes me obviously I
3:55
want to send her a DM at the same time
3:57
though I also see an uncommitted right
3:59
and I say to myself hmm well it looks
4:01
like there's a chance that she might not
4:03
like me but it hasn't committed yet so
4:04
I'm not sure I'm still going to go ahead
4:06
and try and add her to my DMs table
4:09
so at right after that at the third time
4:11
stamp t19 is now going to commit and so
4:14
when I eventually go ahead and try to
4:16
send that DM I'm going to say to myself
4:17
hmm I remember there was an uncommitted
4:19
piece of write data I should probably
4:21
check whether that's committed or not
4:22
just so that I don't look like a fool by
4:24
sending a girl who doesn't like me a DM
4:26
and so what I'll see now when I actually
4:28
go and check that out is that the
4:30
committed right has actually gone
4:32
through or rather the uncommitted right
4:33
has actually gone through and what this
4:35
means for me is that I need to aboard my
4:37
transaction it's no longer valid this
4:39
uncommitted piece of data that I knew
4:41
existed but didn't want to act on just
4:43
yet actually went through unfortunately
4:45
I've got to restart my transaction and
4:47
this time around I'll be sending
4:49
karenicopt a DM instead
4:51
okay so let's look at case number two
4:53
case number two is very similar to case
4:54
number one and obviously to to be
4:57
consistent I've kept the same example
4:58
with Kate Upton and karinikov who both
5:00
like me so let's imagine now that at t18
5:03
the database looks the same again both
5:05
Kate Upton likes Jordan and Karina Kopp
5:07
likes Jordan
5:08
and so I'm really feeling spicy today
5:10
I'm gonna send her three DMS and all of
5:12
those DMS are predicated on the fact
5:14
that Kate Upton still likes me and those
5:16
DMS are going to be t19 T20 and t21
5:20
right uh you know if she still likes me
5:22
I'm gonna say hey what's up how you
5:24
doing
5:25
who knows let's not get into the
5:27
specifics of Riz here leave that to
5:29
other content creators anyways so now we
5:31
have three transactions that have read
5:33
this value right here and they haven't
5:35
yet committed because the the
5:37
corresponding right has not yet been set
5:39
so we have to check if the predicate is
5:41
still valid so right now every single
5:43
time uh we're gonna first say okay well
5:45
we've all read this row there aren't
5:48
actually any uncommitted rights on this
5:49
so in theory we're looking good but we
5:52
know that the value can still change
5:54
between my read and my right so what we
5:56
have to do here is this piece
5:58
the row itself once it's being read in a
6:01
transaction is going to keep track of
6:03
all those in progress transactions that
6:05
have yet to complete so t19 T20 and t21
6:10
are not yet done until they send a
6:12
corresponding right by virtue of putting
6:14
a row in the DMS table so now what's
6:17
going to happen at t22 is a new
6:19
transaction entirely comes along Kate
6:21
Upton decides you know what I don't like
6:23
Jordan anymore sucks to suck this is
6:26
very similar to what happens to me in
6:27
real life so as you can see now Kate
6:30
Upton has been written and that right
6:32
has both been you know uncommitted and
6:35
also committed so when I say write I
6:37
mean that the right actually went
6:38
through and it's been committed so
6:41
what's useful now is the the row itself
6:43
is actually keeping track of all of the
6:45
transactions that were depending on it
6:47
so when this value goes to false we now
6:49
need to go right over here and abort all
6:52
three of these transactions so as you
6:53
can see we're aborting t19 T20 and t21
6:57
and we can retry those eventually and
6:58
just make sure are the same conditions
7:00
apply
7:01
and see what actually happens so by
7:03
virtue of not actually grabbing locks
7:05
we're able to achieve isolation but you
7:09
know it's not always necessarily the
7:10
best thing to do so let's quickly look
7:12
at a conclusion SSI is a really great up
7:15
and coming technology but it's only
7:17
really good when most the transactions
7:19
aren't getting in the way of each other
7:20
let's say we were to have like I don't
7:23
know a distributed counter or something
7:25
where every single transaction needs to
7:27
read the counter and then increment it
7:28
by one SSI isn't going to work well
7:31
because then every single one of the
7:32
transactions is going to eventually have
7:34
to be aborted and restarted because
7:36
there are so many conflicts in that case
7:38
we would want to be using two-phase
7:40
locking so if we're thinking okay well
7:42
you know most of the transactions are
7:44
probably going to be creating race
7:46
conditions or concurrency bugs with each
7:47
other we should stick to a pessimistic
7:50
concurrency control method such as
7:51
two-phase locking but in the majority of
7:54
cases actually a lot of rights are
7:55
disjoint and don't really affect one
7:57
another if I'm going on Facebook and I'm
7:59
posting to my profile in your post
8:01
listening to your profile our rights
8:02
probably aren't impacting each other you
8:04
know that being said if two computers at
8:06
the same time are logged into my profile
8:08
and writing that could be a problem but
8:10
that's exactly what optimistic
8:11
concurrency control is able to handle in
8:13
that Minority case it's actually able to
8:15
go ahead and fix those race conditions
8:17
so I hope you guys enjoyed this video
8:19
and I will be seeing you in the next one
8:21
definitely had to avoid making a lot of
8:23
abortion jokes throughout this but I did
8:25
my best and have a good one guys

##v14:

0:00
What's up, gigachads, and welcome back
0:01
to the channel. Um, sorry I haven't
0:03
posted in a while for a couple of
0:04
reasons. For starters, uh, as you know,
0:07
uh, I was in Amsterdam, and I had a
0:09
roommate during that, and frankly, I'd
0:10
rather be caught than caught with a
0:12
YouTube channel. So, uh, again, uh, kind
0:15
of was taking my time with filming
0:17
there. Uh, but now I am actually alone
0:19
in a room in Sydney, Australia. For
0:22
those of you who are Australian watching
0:23
this channel, what the hell are you
0:24
doing down here? It literally takes a
0:26
full day to get down here. I don't
0:28
understand why you're doing it. Get out
0:29
of here. It's It's too far away. You're
0:31
on the other end of the world. Okay, so
0:33
anyways, you know, with that rant about
0:35
Australia done, as nice as the weather
0:36
is, let's start making some videos
0:38
because I am a little bit behind and I
0:40
owe you guys a couple. So, today we're
0:42
going to be talking about column
0:43
oriented storage. Might as well get into
0:45
it. All right, everybody. This one's
0:46
going to be on the longer side, so bear
0:48
with me here, but we're going to go
0:49
through these things and uh hopefully it
0:51
comes out to be an interesting video. So
0:53
today basically what we're going to do
0:54
is go ahead and talk about column
0:57
oriented storage. So before we can even
1:00
talk about column oriented storage I
1:01
should probably preface the video by
1:03
talking about what row oriented storage
1:04
is. So row oriented storage is pretty
1:07
obvious. It's how you would think a
1:08
database would store its data and this
1:10
is in fact how it's typically done. So
1:12
let's imagine we have five rows in a
1:14
database. What row oriented storage will
1:16
typically do is divide those rows up
1:18
into a bunch of different chunks. And
1:20
those chunks will basically be stored
1:22
into files. So you see we've got one txt
1:24
file, another txt file. They wouldn't
1:26
really be txt files in real life, but
1:28
whatever. I just put that there as a
1:29
random suffix. And then if we're zooming
1:31
in on one row, we'll see that every
1:33
single entry of each row is adjacent to
1:35
each other on disk. Imagine this as one
1:37
big array on disk. That's how this is
1:40
going to work. So that's row oriented
1:43
storage. But let's now go ahead and talk
1:45
about column oriented storage. So
1:47
imagine we have a table with the three
1:49
fields name, email, and company.
1:51
Basically what we would do is we would
1:52
take every single value from the names
1:54
column in order and place them into one
1:57
names.txt file. Similarly, we would do
1:59
the same exact thing with email. And
2:01
then finally, we would do the same exact
2:03
thing with company. So zooming in on
2:05
company for example, adjacent to each
2:07
other on disk, we would have everyone's
2:08
company. So obviously in increasing
2:11
order of prestige, we've got Google at
2:12
the lowest, then Amazon, then Jane
2:14
Street, and then finally Albertson's the
2:17
top company. So hopefully that makes
2:19
sense. Basically the gist of it is in
2:21
row oriented storage you store the data
2:23
from one row together on disk and in
2:24
column oriented storage you store the
2:26
data from one column together on disk.
2:28
So why would we ever actually want to do
2:30
this? Well let's go ahead and talk about
2:32
it. So row oriented storage is good for
2:35
things like a web app. Imagine that
2:36
you're Facebook and typically a common
2:39
usage pattern of the data is I want to
2:41
load my entire profile. Now my entire
2:43
profile is probably or at least the
2:45
metadata of it is going to be stored in
2:47
one row of a database. And so typically
2:49
it would be really useful if we have all
2:51
of those rows stored continuously to one
2:53
another on disk. On the other hand,
2:55
let's say I'm a data science person at
2:58
Facebook and it would be really useful
3:00
to me to be able to basically perform
3:02
some analytics on some of our data. So
3:04
in in that basically in that scenario,
3:07
it's really really useful to be able to
3:08
basically grab all of the values of one
3:10
single column so that we can perform
3:12
some math on them. Maybe get something
3:13
like the minimum, the maximum, the
3:15
average, the sum, anything along those
3:17
lines. And so the reason again that this
3:19
is all useful all comes down to this
3:21
right here, the hard drive. The closer
3:24
that the data is together on a hard
3:26
drive, the less that arm has to move
3:27
around and the faster these operations
3:29
become. But wait, there's more. Column
3:33
oriented storage isn't just useful
3:34
because data is closer together on disk.
3:37
It's also useful because we can perform
3:38
something known as column compression.
3:40
So let's take a look at how we might do
3:42
column compression and then I'll explain
3:44
some of the advantages of it. So, let's
3:46
imagine that we have a table as follows
3:47
on the left here. And so, this is very,
3:50
you know, I'd say this is a realistic
3:51
depiction of how my time goes whenever I
3:53
go out to clubs, but I've got seven days
3:56
of me going to a club, the club name,
3:57
and then also the number of times I get
3:59
rejected by a girl. As you can see,
4:01
these are typically spanning anywhere
4:03
from 1 to five times. So, on day 1, 2,
4:05
and three, I start off with three
4:06
rejections. On four, and five, I lose my
4:08
confidence and only get rejected once
4:10
cuz I'm not even willing to go for
4:12
anything. Day six, I say, "Screw it. Get
4:14
rejected five times." In day seven,
4:15
we're back to a happy medium of two. So,
4:18
as you can see in the num rejections
4:20
column, which I want to do some
4:21
analytics on, there are only going to be
4:23
values from 1 to 5. Now, of course, you
4:25
know, if the values can be literally
4:27
anything and there's no pattern to them,
4:28
that is a different story and it's
4:30
harder to perform column compression.
4:31
Column compression is easiest to perform
4:33
when the data within the column is very
4:35
similar to one another. So, let's do an
4:37
example of column compression. So, we
4:39
can do two things. First, we would
4:40
perform a bit map encoding and then we
4:42
could perform a run length encoding. So
4:44
if you go over here and look at what we
4:45
have on the right, for example, for the
4:47
number one aka times where I get
4:49
rejected once per night, you can see
4:52
that the first three lines here, here,
4:54
and here are uh not ones. So I would put
4:57
three zeros representing those in the
4:58
bit map encoding. The next two lines are
5:00
ones. So that's why we have 1 one. And
5:04
then finally, we can end that with 0 0
5:06
because five and two are not equal to
5:08
one. Okay, so we have our bit map
5:10
encoding. And then now we can actually
5:12
go ahead and convert that even further
5:14
into a run length encoding. So a run
5:16
length encoding is basically taking the
5:18
number of zeros and putting a number for
5:21
it. Then the number of ones and then the
5:23
number of zeros again in your bitmap
5:24
encoding. So as you can see it starts
5:26
out with three zeros. Then we have two
5:28
ones and then again two zeros. Hence the
5:31
number 322. So as you can see I've
5:34
basically encoded everything in terms of
5:35
its bit map and its run length encoding.
5:38
And I've left the number five to do for
5:40
ourselves. So let's go ahead and do
5:41
that. So basically the first three
5:43
things are going to be threes. So that's
5:44
0 0 0. The next two are ones. So that's
5:47
0 0. The next one is a five. So that's
5:49
our one. And then finally the last one
5:52
is a two. So that's going to be a zero
5:54
again. And so looking at this that means
5:56
our run length encoding starts with five
5:58
zeros then has a single one and then
6:01
goes back to another zero. So 5 1. So,
6:05
as you can see, this has allowed us to
6:06
seriously compress down our data in a
6:08
column where many of the metrics in
6:11
there are actually going to be very
6:12
similar. If there's a lot of repeat
6:13
values if the values next to each other
6:15
are similar, that is really, really
6:17
useful in terms of reducing the size.
6:19
So, what are the benefits of column
6:21
compression? Well, for starters, uh
6:23
there's a lot less data that actually
6:25
has to be sent over the network. If I am
6:27
say trying to do some analytics on a
6:29
column and I want to load all of those
6:31
values onto my personal computer, it
6:33
means that that query is going to run a
6:35
lot faster, which is super useful if
6:37
you're a data scientist and you want to
6:38
speed up your workflows. Secondly, and
6:41
even more importantly, now we can
6:43
actually keep more of that data stored
6:45
in memory or in our CPU cache, which
6:47
allows us to perform faster queries.
6:49
Obviously, disk is going to be quite a
6:51
bit slower than these other forms of
6:53
data storage. And so, as a result, the
6:55
more that we can fit in there, the
6:56
better. That's what she said. Anyways,
6:58
um moving onwards, we can actually do
7:01
some more compression on this data. So,
7:03
let's go back to my previous example, uh
7:05
in which um I was talking about
7:07
basically all the clubs that I go to.
7:09
And so, what we're going to perform on
7:10
these is called dictionary compression
7:12
where we take arbitrary strings of
7:14
basically a finite set and we're able to
7:16
compress them to only a few bits. So in
7:19
this case, dictionary compression works
7:21
because I've only got uh five different
7:23
clubs here. And so as you can see, I've
7:25
got five distinct clubs in this list. So
7:28
let me go ahead and write that five
7:30
distinct. And when you have five
7:32
distinct clubs, that means you can
7:33
represent those with just three bits.
7:35
Why three bits? Because 2 to the^ of 3
7:38
is 8, which means you can represent up
7:40
to eight things with three bits. If I
7:42
had only four distinct clubs, I could
7:44
use two bits. Hopefully that makes
7:46
sense. So I create this dictionary right
7:48
here where I take all of these bit
7:49
values and map them to a club. So go
7:52
ahead and look over here on our right. I
7:54
say that the club 000 is live, 001 is
7:57
marquee, 010 is leane, uh 011 is 11, and
8:01
then 10 is the DL. So now I can actually
8:04
take this column that was previously
8:06
taking up quite a bit more space because
8:08
every single character is two bytes and
8:10
actually go ahead and convert those to
8:12
just a few different values of three
8:14
bits. If you think about that, that is
8:16
saving us a ton of storage. And again,
8:17
the more storage that we save, the less
8:19
data there is to send over the network,
8:21
the more data that we can fit in our
8:23
caches.
8:24
So that's obviously going to be a really
8:26
big deal. And then finally, the last
8:28
thing that I kind of want to talk about
8:30
in terms of a feature of column oriented
8:32
storage is known as predicate pushdown.
8:35
So basically, predicate pushdown is a
8:37
feature of something called parket or
8:39
maybe it's not specifically a feature of
8:40
parket, but that's how I've heard of it.
8:42
So, Parket is effectively an open-
8:44
source Apache file format that allows
8:46
you to perform column oriented storage.
8:48
And so, it makes things easy for you.
8:50
And the really nice thing about this is
8:52
that what it actually do is it'll take a
8:54
column like so. As you can see, we've
8:56
got column one right here. And it'll
8:58
divide the values into a bunch of
8:59
different chunks. And so, as you can
9:01
see, you know, the first few values of
9:03
the column go into file 1.txt. The next
9:05
few go into file 2.txt. And then so on,
9:08
basically until you reach the end of
9:10
those values. And within these files, we
9:12
actually store some metadata about the
9:14
data points in them. So, for example, if
9:16
they're numeric, we might have the
9:17
minimum value, say 60, the maximum value
9:20
is 80, the sum of the values 10,000, and
9:22
the average is 70. And so, we have these
9:24
useful little pieces of metadata. The
9:26
reason being that uh they can actually
9:28
speed up our queries if used properly.
9:30
So, let's say I wanted to run a SQL
9:32
query where I want to find all the rows
9:35
where the value stored in column 1 is
9:38
greater than 60. Well, if you look at
9:40
file 2.txt and the metadata surrounding
9:43
it, you can see that the max value
9:45
within that column chunk is actually
9:47
going to be 55. So, what we can do here
9:49
is perform something known as a
9:50
predicate push down where we basically
9:52
just go ahead and skip querying this
9:54
part of the data. This is going to speed
9:56
up our query considerably because this
9:58
metadata basically gives us hints about
10:00
where we actually have to look in the
10:01
data for the results that we want. Okay,
10:04
so I hope that makes sense. Those are
10:06
three pretty interesting things that you
10:07
can do with column oriented storage to
10:10
save both time and space with your data.
10:12
But are there any downsides of column
10:14
oriented storage? Well, yeah, I would
10:16
say so. For starters, every single
10:18
column has to have the same sort order.
10:20
So, that's annoying, but it's just the
10:23
only thing that makes sense. Otherwise,
10:24
your data would not be sensical, right?
10:26
If I had different sort orders within
10:28
all of the files that store my columns,
10:30
well, how would I be able to tell, you
10:32
know, which piece of data corresponded
10:34
to which? I wouldn't. So they have to be
10:35
sorted in the same way. It is possible
10:38
that you could basically duplicate all
10:40
of your files and have a separate copy
10:42
of the data with a different sort order.
10:44
That's feasible. And you know that's
10:46
kind of something you would have to
10:47
weigh the trade-offs. Is it worth it for
10:49
me to store all of this extra data? Does
10:51
it speed up my queries enough to justify
10:53
that? But again, that's specific to your
10:55
application. Additionally, uh we have
10:57
another question of basically each write
11:00
needs to go to many different places.
11:01
Why is that? Well, because we're writing
11:03
one row at a time, but every single
11:05
element from the row needs to go to a
11:07
different file. Or does it? Well,
11:09
actually, we've discussed kind of a data
11:12
indexing structure that allows us to get
11:14
around this and make things a lot
11:15
easier. So, what we can actually do, if
11:17
we all recall our LSM tree and SS table
11:20
based index, which I hope you do, I
11:22
recommend watching that video if you
11:23
haven't yet, is we can basically write
11:26
our rows to an LSM tree. So an LSM tree
11:28
to just give a quick refresher is an
11:30
in-memory balanced binary search tree.
11:34
And basically all we can do is go ahead
11:36
and write our entire row to that. So
11:38
again it is column oriented storage but
11:40
for now we're just going to write the
11:41
entire row to our LSM tree. Why? Because
11:44
when this thing gets too big
11:47
we can go ahead and flush it all to disk
11:50
and do bulk writes of all of these
11:52
basically column oriented files. And of
11:55
course, you know, if down the line we
11:57
want to rearrange the sort order of
11:58
these files, we know that uh basically
12:01
there's going to be SS table compression
12:03
down the line and those can get merged
12:05
in in all the same ways, thus preserving
12:07
the sort order. So yeah, uh hopefully
12:10
this was clear. Basically the gist of it
12:12
is you write your row data to the LSM
12:14
tree and then uh this way we can just
12:17
write our column oriented files in bulk
12:19
as opposed to you know having to
12:21
basically write to a bunch of different
12:22
places at once and especially having to
12:24
write into the middle of a sorted list
12:26
which takes forever because then you
12:28
have to move all the other uh indexes
12:30
out of the way. So again the LSM tree is
12:32
definitely the way to go here. All right
12:34
guys, well I hope this video helped. Um
12:37
going to try and get one more out. uh
12:40
hopefully this weekend and that is going
12:42
to be about you know serialization
12:44
frameworks. I think that that should be
12:46
the last video that I need to cover
12:47
where it's like what's going on in a
12:49
single database node and then after that
12:51
we can start talking about replication,
12:53
partitioning, SQL, NoSQL, all that good
12:55
stuff and uh really get into distributed
12:58
systems. So have a great day and I will
13:00
see you in the next one.

##v15:

0:00
hey everyone and welcome back to the
0:01
channel unfortunately I'm kind of
0:03
starting to get my life together here
0:04
which is great because it means that
0:06
I'll be able to post videos a little bit
0:07
more often they'll be coming more
0:09
regularly in about two weeks though once
0:11
I have a little bit more time and I'm
0:13
back in the US
0:14
um just quick announcement congrats to
0:16
pranav who hit me up on LinkedIn uh was
0:18
laid off was able to get another job
0:20
um accredits this channel for some
0:22
amount of help though I doubt it because
0:24
all I do is act like an idiot and
0:25
blabber about systems design so congrats
0:28
to you pronov congrats on staying in
0:29
America and uh yeah let's get into
0:31
today's video which is about
0:33
serialization Frameworks all right so
0:35
let's quickly go ahead and do this video
0:37
so I can go and get some food so
0:40
basically the premise of the problem is
0:41
this I have this field called a person
0:44
object as you can see it has myself my
0:47
attractiveness level and my girlfriend
0:48
and her attractiveness level and I want
0:51
to be able to hold this data on a
0:53
database and additionally you know it's
0:55
probably going to be sent from some
0:56
server to the database so it'd be nice
0:58
if you know we found a good way to go
1:00
ahead and encode this data somehow and
1:02
send it from our server to a database so
1:05
basically the traditional way of
1:07
actually holding this piece of data on a
1:09
database would be with a SQL or a
1:11
relational database so let's imagine we
1:13
had some table called person and I'll go
1:15
ahead and write that down and then in
1:18
person we would have IDs for every
1:20
single row we would have the names the
1:22
attractiveness and then foreign ID or in
1:25
this case it wouldn't be foreign because
1:26
it's the same table but another ID that
1:28
actually points to the person so in this
1:30
case the ID of my girlfriend would be
1:31
two and that would be pointing to Karina
1:34
Kopp who I'm obviously dating
1:35
so another way of doing this is to
1:38
actually store the data in a more
1:40
denormalized fashion right because the
1:42
issue with the relational model is that
1:44
if I want to have all of the data in my
1:46
record accessible in one place this is
1:49
not necessarily possible so in the
1:51
relational model you know you might have
1:52
multiple tables that are combined in
1:54
order to fetch one single record you
1:56
know if uh for example I had like um
1:59
a YouTube videos table and I had ideas
2:03
showing that I was the one creating them
2:04
I would have to go to the YouTube videos
2:06
table in order to fetch all of the
2:07
YouTube videos that I've created so for
2:10
example now what we have is some other
2:12
basically ways of storing this data in
2:15
more of a key value format and the ways
2:17
that databases might actually do them so
2:19
the common ones are going to be things
2:20
like Json and XML right so these are
2:23
just plain text formats in ways in which
2:25
we can effectively store data and look
2:27
at them and read them and it makes
2:29
things pretty simple right so the what I
2:31
have on the left here is basically Json
2:33
where I have some Field named person and
2:35
then I go ahead using brackets to list
2:38
out all of the other data that's there
2:40
and that's great because they're human
2:41
readable but at the same time these have
2:44
a lot of issues as well so even though a
2:46
lot of us use Json for example in just
2:48
like making our own web app in a massive
2:51
company these are not too feasible the
2:53
reasoning being they're less typesafe so
2:55
Json for example is hard to distinguish
2:57
between types of numbers and there's
2:59
some issue use there with XML as well
3:00
but more importantly there's a ton of
3:03
overhead with Json and XML so if you
3:05
look here I'm writing out the field
3:07
person a bunch of times and writing out
3:08
the word name attractiveness girlfriend
3:10
and the truth is if I know that every
3:12
single Row in my database has all of
3:14
these fields consistently I don't
3:17
actually have to write those out I can
3:18
store this data in a much more efficient
3:20
format thus saving me a ton of space so
3:23
why is it good to save us a ton of space
3:25
well for starters it means that there's
3:28
less disk usage that we're going to be
3:29
having in our company and also it means
3:32
if we're sending data from a server over
3:34
to the database there's less that
3:36
actually has to travel over the network
3:37
so basically you know we want this data
3:40
locality and by doing so we would prefer
3:43
to use something like a serialization
3:45
library so I'm going to go ahead and
3:47
show you how those works so the example
3:49
of serialization libraries that I'm
3:51
first going to talk about are things
3:52
like Google's protocol buffers and
3:55
Apache Thrift and the way these work are
3:58
as follows so we've got basically some
4:00
sort of message so a message would just
4:02
kind of be think of it as like the row
4:04
of your database and in this case it
4:07
would be named person
4:08
so what we're going to do here is give
4:11
every single field in our person message
4:13
a number and this is how these things
4:15
work so we would say there's some name
4:17
field that's going to be required and
4:19
the kind of index of it is number one or
4:22
not even an index but just basically the
4:24
field tag is what it's called then we
4:26
have our attractiveness field with an
4:29
INT type again this is typesafe which is
4:31
great and that's going to be field
4:33
number two and then finally an optional
4:35
girlfriend field because well Karina
4:37
Koff doesn't have a girlfriend but I do
4:39
so as you can see what we can now do is
4:42
when we store these things on disk it
4:44
allows us to not have to list out the
4:46
word person name attractiveness
4:48
girlfriend every single time we can
4:50
literally just keep a mapping from the
4:52
tag number to the field value so in this
4:54
case you know tag number one means that
4:57
I am sending uh the word name is equal
4:59
to Jordan so that's very important it
5:01
saves us a ton of space especially
5:03
because one can be represented in binary
5:05
as just either a literal one or you know
5:08
say we have four fields in total or
5:10
three Fields here I can just use
5:12
effectively o1 so again by effectively
5:15
just using uh these kind of small
5:18
mappings from field tags to field names
5:20
we can save a ton of space on disk in
5:23
addition to that these actual files of
5:25
messages are useful for other
5:27
programmers they just act as good
5:28
documentation they show the fields off
5:30
that are in your data so it's easier to
5:31
reason about what exactly is in your
5:33
database or what exactly is being sent
5:35
over the network
5:36
this does come at the cost of course of
5:39
being not human readable right so as you
5:42
can see down here uh basically we have
5:43
to serialize or encode our data using
5:47
the actual message format itself and
5:49
what that means is that in the actual
5:51
database the data is not stored as like
5:54
physical text but it's stored as a bunch
5:56
of zeros and ones and so you know we
5:58
would have to go ahead and deserialize
6:00
it so there is some CPU penalty that
6:01
comes with that but again it is
6:03
oftentimes worth it for the amount of
6:05
storage that it gets saved
6:07
okay so one thing that we've covered now
6:10
is that we do have to have basically
6:11
some files that list out what the format
6:14
of our data is however that itself kind
6:17
of leads to some problems because why
6:19
data basically just evolves over time
6:21
we're eventually going to want to add
6:22
some fields to this and it wouldn't be
6:25
acceptable if we weren't able to do that
6:27
right so keep in mind we have this
6:29
person message before and we had that
6:31
name attractiveness and girlfriend field
6:33
and now I want to go ahead and add some
6:35
other field called net worth right well
6:38
what I actually have to do is just go
6:40
ahead and add it as an optional field
6:42
because we know that any existing rows
6:44
in the database don't have that net
6:45
worth field yet so if we made it
6:47
required or we made it required without
6:49
some sort of default value it would mean
6:51
that all of our existing rows in the
6:53
database would be invalid and if we were
6:54
to ever read them from the database in
6:56
our code we could potentially break our
6:58
application and cause an error so by
7:00
making this thing optional or making it
7:01
nullable it means that our code is
7:03
actually going to be forwards compatible
7:05
which is great and by definition all of
7:08
this stuff is also backwards compatible
7:10
because say I have a piece of code that
7:12
reads from the database and you know it
7:15
doesn't expect the net worth field to be
7:16
there but there is a net worth field in
7:19
the data it will just ignore that field
7:20
and operate as per usual so again this
7:24
is really great but even still protocol
7:27
buffers and Thrift do have some
7:29
disadvantages
7:30
I keep mentioning that they basically
7:32
require a file on the part of the coder
7:34
to go ahead and write out the data
7:36
schema so what that means is that you as
7:38
the programmer has to know about the
7:40
schema of the data at compile time but
7:42
there are some points in life where this
7:43
isn't always possible imagine that you
7:46
have some sort of database and you've
7:48
got a server a and a server B and they
7:50
keep publishing rows to the database and
7:52
those just change over time they could
7:54
even be rows from like an external
7:55
company or someone else and you're
7:58
basically just ingesting them into your
7:59
data warehouse or data lake or whatever
8:01
it may be your Hadoop or anything like
8:03
that and you don't even know what the
8:05
format is going to be but you want to
8:06
make sure that once you do have all of
8:08
those rows of data that you are
8:09
compressing them as necessary so let's
8:12
imagine now again that server a is
8:14
publishing a thousand rows and server B
8:16
is publishing two thousand rows well we
8:18
actually just want to be able to create
8:20
data schemas for those on the Fly and
8:22
that is kind of what this framework
8:24
Apache Avro does so Avro is very similar
8:27
to Thrift and protocol buffers with the
8:29
exception that in instead of giving all
8:31
those fields unique tags or numbers what
8:33
it does is it basically just creates a
8:35
schema based off of the names of all the
8:37
columns and it does this in a way that
8:40
is very smart and we'll cover that in a
8:42
second so basically from server a we can
8:44
create an average schema called version
8:46
8.00 and then from server B we can do
8:49
the same thing with version B .00 which
8:51
is great
8:52
so let's go ahead and continue this
8:54
example because it's not so simple right
8:56
even if we give all of these a thousand
8:58
rows and extra fields that basically
9:00
says here's the Abra version right 8.00
9:02
and then we know how to read it in the
9:04
database there are often going to be
9:06
times where say I want to be able to
9:08
read the data on server B that I
9:11
published from server a and server B
9:13
doesn't actually have access to the
9:16
format of the data in advance so in this
9:18
case abro is actually able to perform
9:20
some cool things for us so let's imagine
9:22
we have some adverse schema database
9:24
right and we'll hold this on our
9:27
database it's useful for the database to
9:28
actually decode the data because we need
9:31
to be able to have all the schemas in
9:32
order to read the data and we've got our
9:35
8.00 and our B point zero zero formats
9:38
so you can see that the difference
9:39
between them is that they both have the
9:40
field name
9:42
but net worth is an A and net worth is
9:45
not in B sorry for my ridiculous check
9:47
mark there so what we can actually do is
9:50
we can call a basically the writer
9:52
schema and we can call B the reader
9:54
schema because we want to read data on
9:56
server B that was written from server a
9:58
we'll read from the database
10:00
so what can Avro actually do for us well
10:02
it'll do the following it'll basically
10:04
rectify the writer and the reader schema
10:06
in a smart way so it'll see that both of
10:08
these things have the field name and
10:10
it'll match those right so it'll
10:12
basically say okay I know that about
10:13
this field I'm going to go ahead and
10:15
read it it'll look at uh some field
10:18
called net worth and it'll say I've
10:19
never seen net worth before I'm just
10:21
going to ignore it well that's fair
10:22
enough because that's only in the writer
10:24
schema but not in the reader schema and
10:26
then finally we have this field
10:28
attractiveness so server B expects some
10:30
field attractiveness but it doesn't see
10:32
it in server a it's not present so we
10:34
have to do then is make sure to provide
10:37
all of these columns with a default
10:38
value in the case of attractiveness it's
10:40
an INT so I imagine it would be zero and
10:42
then basically server B would fill that
10:45
value 0 in for attractiveness when
10:46
reading all of these rows so that's how
10:48
Abra would go ahead and rectify kind of
10:51
the writer versus the reader schema if
10:53
the reader doesn't have access to the
10:55
writer schema often it should because
10:56
again there should be a centralized
10:58
repository of average schemas right if
11:01
we are all writing to Hadoop then Hadoop
11:03
should go ahead and store all of those
11:05
schemas in some separate database that
11:06
everyone else has access to them but
11:09
that's not necessarily always a
11:10
possibility so again Abra is a really
11:12
smart thing it's super useful when
11:14
you're doing a ton of data ingestion to
11:16
be able to kind of update your schema on
11:17
the fly if you don't know how things are
11:19
going to be in advance
11:20
all right guys well I hope this video
11:22
helped as per usual um I'll be back in
11:24
about a week and then hopefully once I'm
11:26
back to Chicago I can start uh actually
11:28
posting videos on a more consistent
11:30
basis so looking forward to it and I
11:32
will see you guys soon

##v16:

0:00
hey guys and welcome back
0:02
um so it seems like I'm still here in
0:04
Sydney Australia hence the infrequent
0:05
posting but let's go ahead and get into
0:07
another video so I've been kind of
0:09
debating you all for a while now saying
0:12
that I was going to cover all of the
0:13
distributed systems topics in this new
0:15
series and I haven't really been doing
0:16
so
0:17
um and that's for good reason in my
0:19
opinion I think that it's really
0:20
important that we kind of slow down and
0:22
take the time to understand everything
0:23
that has been happening on a single
0:26
database node before we make it even
0:27
more complicated by talking about a
0:29
bunch of database nodes so hopefully you
0:32
know by actually slowing down really
0:33
diving into the weeds a little bit we
0:35
can get these Concepts down a little bit
0:36
better and then I won't have to answer
0:38
so many goddamn questions in the
0:40
comments and waste my own time so
0:42
without further Ado let's talk about an
0:44
introduction to database for application
0:46
this is pretty much the most important
0:48
possible Topic in distributed systems
0:50
so yeah let's get into it okay so I'm
0:52
back again with the trusty iPad so let's
0:55
start talking about replication and kind
0:58
of what that means so for you beginners
1:00
let's go ahead and start this out with a
1:02
very simple scenario I am the owner of a
1:05
website and this is kind of what my data
1:07
setup looks like right I've got it all
1:09
drawn out so we've got one server over
1:12
here we've got one database and then
1:14
we've got let's say five different users
1:16
so these three are going to be from the
1:18
US and then we've got Australians over
1:20
here as you can see other side of the
1:22
planet the Earth is in fact flat so keep
1:24
that in mind so like I said we've got
1:27
one database right one server very
1:29
simple five users what if one day I'm
1:32
going ahead and walking in my apartment
1:34
with my one database and I trip and
1:36
spill my coffee on this database well a
1:39
few things are going to be problematic
1:40
for starters one what happens to all of
1:42
the data that I had on this machine well
1:45
if I'm able to restart it and it just
1:46
powered down for some reason okay fine I
1:48
don't lose my data but I do still have
1:50
some some down time right now all of my
1:52
users aren't going to be able to use my
1:53
server and as a result my application is
1:55
going to stop making money but what if
1:57
the data does get corrupted hard drives
1:59
break pretty frequently you know besides
2:01
spilling coffee I might just come around
2:03
and eat one and as a result you know
2:05
it's pretty easy to lose your data so
2:07
literally just having one single disk
2:09
where that's all stored is a pretty poor
2:10
idea and then even besides all of that
2:13
there's some performance concerns as
2:14
well like I mentioned I have these two
2:16
idiots over here for whatever reason
2:18
they're living in Australia I don't know
2:20
why anyone would do that and as a result
2:22
they're super far away from my database
2:24
which will be conveniently located in
2:26
the United States so all of the requests
2:28
are taking forever even more so another
2:30
problem is there might just be a ton of
2:32
users and if there's so many users just
2:34
having one database to handle all of
2:36
those user requests user reads and user
2:38
rights probably isn't sufficient so
2:40
let's go ahead and move on and we'll
2:42
talk about now what life is when we do
2:45
replication so before we can even talk
2:47
about what life with replication
2:49
actually is we have to talk about what
2:51
replication means basically for now
2:53
let's assume it's just going to mean
2:55
many databases
2:58
and what many databases means is many
3:00
copies of that data that we care about
3:02
on our database so yeah you can
3:05
replicate other things and we certainly
3:06
will later in the series but for now
3:08
we're only going to talk about
3:09
replication as it pertains to databases
3:11
so again we've got our server over here
3:14
we've got our database as like our
3:17
cylinder looking things and then over
3:19
here you know we've got our Americans
3:21
we've got our Asians so we'll call this
3:24
uh basically
3:25
um you know what no this will be Europe
3:27
and this will be Australia or APAC
3:31
and so as you can see now all of us have
3:33
different servers and different
3:34
databases and so the nice part about
3:36
that is a few things one we have
3:38
redundant data which means no lost data
3:41
if every single one of these databases
3:43
has its own copy of all of the data from
3:45
our website it means that if one of them
3:47
were to go get taken out we could all
3:50
route our request to the other databases
3:52
which is really nice
3:53
another thing now is that we have
3:55
increased database throughput the reason
3:58
for this is that all of my American
3:59
users get to use one database all of my
4:01
Australian users get to use another and
4:03
then all of our European users get to
4:05
use another so effectively we've
4:06
increased our database throughput by
4:08
three times just by allowing everyone to
4:10
use their own copy of the data obviously
4:12
this is going to come with some caveats
4:14
but we'll discuss those later and then
4:16
of course now we can allow Australians
4:18
to have basically a database that's
4:20
closer to them so not only is there
4:22
increased database throughput by virtue
4:24
of having more databases but also we can
4:26
geolocate our data centers closer to
4:29
certain users so that they can get
4:30
better performance so again screw
4:32
Australians but fair enough we'll give
4:34
them a database so that's really nice so
4:37
before we even you know go into
4:39
basically certain types of replication
4:41
that you can do with your database I
4:43
just want to you know quickly put an
4:45
informative warning on this video I'm
4:47
not going to get too deep into the weeds
4:49
here this is an introduction the next
4:51
three videos are going to get quite a
4:53
bit deeper but we are going to go
4:54
through some of the basics of how you
4:56
actually replicate data from one
4:58
database node to the other
5:00
so first we're going to talk about
5:01
synchronous replication versus
5:03
asynchronous replication so thinking
5:05
it's a replication is basically the
5:07
following we've got our one guy over
5:09
here this is our client and we've got a
5:11
couple of databases so let's say the
5:13
client writes the first database saying
5:14
X is equal to four just some key value
5:17
start and then the first database says
5:19
okay I agree X is equal to four you're
5:22
good to go
5:23
then what's going to happen now is the
5:25
first database has to go ahead and
5:27
forward this request to the second
5:28
database because the second database
5:30
needs a full copy of the data so it's
5:32
going to go ahead and do that and then
5:34
the second database says okay X is in
5:36
fact equal to four now what's going to
5:38
happen is basically once the the client
5:41
receives word from both databases that X
5:43
is equal to four we know that this right
5:46
is considered valid and basically other
5:48
clients who did not in fact do the x
5:50
equals four right can start reading the
5:52
new value of x this is known as strong
5:55
consistency basically meaning that you
5:58
know the second I do a write I'm not
6:00
going to consider it valid until every
6:02
single replica has a copy of that data
6:04
in contrast we also have asynchronous
6:07
replication where the first thing I
6:09
would do when I'm making a right is go
6:11
ahead and perform the right hear back
6:12
from my database but then from there on
6:15
the database can actually consider that
6:17
write valid in the background the first
6:19
database is going to asynchronously
6:21
replicate x equals 4 to the second
6:23
database but in the meantime it's still
6:25
possible for another client to go ahead
6:27
and read x equals three if three was the
6:30
old value so what this is known as is
6:33
eventual consistency the main point
6:35
being here that in strong consistency
6:36
it's not possible to read stale data
6:39
where stale data is I guess data that
6:41
would be considered old right we know
6:43
that x equals 4 is the proper value but
6:45
in an eventually consistent model the
6:48
thing that's going to happen is it's
6:49
still possible for other clients to read
6:50
older pieces of data because we didn't
6:53
require the second replica to have to be
6:55
completely updated the second the right
6:57
came in so this comes at a cost
7:00
obviously with strong consistency which
7:02
is that well rights are going to take
7:03
forever right because now we have to
7:05
write to two databases instead of one
7:07
and in my example from before that means
7:09
every single American is going to have
7:11
to write to the database that's in
7:12
Europe that's going to have to write to
7:14
the database that's an APAC and these
7:16
rights are going to take a while to
7:17
propagate so in reality we don't really
7:19
see strong consistency use too much
7:21
there are cases where we do have to use
7:23
it because stale reads are unacceptable
7:25
but in a lot of common modern web
7:27
applications
7:28
basically eventual consistency is the
7:30
norm and we'll talk about ways to kind
7:32
of Be Clever with it to try and avoid
7:34
getting a lot of stale reads okay so
7:36
that is basically one kind of concern
7:39
which is you know kind of when do we
7:41
actually do our replication do we do it
7:43
immediately do we do it in the
7:44
background but more importantly another
7:46
important part of replication is
7:49
actually how we replicate right so we
7:51
know that we're going to have one
7:53
database which is going to receive a
7:54
write and it's going to pass all of that
7:56
information to other databases which
7:57
need to make a full copy of it so there
7:59
are basically three ways that you can do
8:01
this and we're going to talk about the
8:02
trade-offs of Performing every single
8:03
one of them so the first thing is a
8:06
pretty easy option we just take all of
8:08
the SQL statements or if it's a nosql
8:10
database whatever other statements are
8:12
kind of going into the database and
8:13
copying them directly to our replica
8:15
database so for example if we have the
8:18
command insert row Jordan you know we
8:20
could just copy that over however there
8:22
are some pretty obvious issues with just
8:24
copying SQL statements which is that
8:25
some of them are non-deterministic so
8:27
for example if we were to use the
8:28
command time.now it means that you know
8:31
the original right result of time dot
8:33
now is going to be different than the
8:35
result of the replica time dot now and
8:37
we don't want write conflicts that is
8:39
very unacceptable they're hard to
8:41
resolve and it's going to cause a lot of
8:42
pesky issues down the road when you're
8:44
trying to read data that's unacceptable
8:45
so for this reason just exporting SQL
8:49
statements tends to be unacceptable
8:51
another possible option is using the
8:53
right ahead log so we've spoke about the
8:55
right ahead log plenty in the past and
8:58
basically all it is is saying at exact
9:00
byte values what you're going to be
9:02
writing at a certain point of time it's
9:03
just a sequential logon disk so for
9:05
example you know in memory address or
9:07
rather a disk address 0x0 AFF write the
9:10
word Jordan
9:11
so this could work and in fact it's a
9:14
pretty good implementation however it
9:15
does have some fundamental issues which
9:17
is that not all of our replicas are
9:19
going to be running the same database
9:21
software for example I might be running
9:23
one instance of MySQL and I want to be
9:25
replicating that to a postgres SQL
9:27
instance maybe because in postgres there
9:29
are certain reads that are a little bit
9:31
more optimized and we want a copy of the
9:33
data formatted that way so that we can
9:34
read from it postgres is going to look
9:36
at 0x0 AFF and say what the hell am I
9:39
doing with this I don't use this memory
9:41
address so why do I need that so for
9:43
this reason right ahead logs can be
9:45
pretty useless when it comes to
9:47
replication which ultimately leads us to
9:49
our last and final solution which is
9:51
what's often done in practice called a
9:53
replication log so a replication log or
9:56
a logical log basically just says at
9:58
what id to perform the right because
10:00
every single one of these SQL databases
10:02
is going to have the concept of
10:04
basically an ID in a row so as long as
10:06
you say you know at id1 put Jordan with
10:08
an attractiveness of 10 and an id6 put
10:11
them name of tech lead with an
10:12
attractiveness of six every single SQL
10:15
database is going to understand that and
10:17
so it's obviously going to be very easy
10:19
to then go ahead and send those changes
10:21
over the network from a mySQL database
10:23
to a postgres database obviously it does
10:26
come at the cost of having to create
10:28
this logical log because we already have
10:30
a right ahead log but we don't have a
10:32
replication log we are going to have to
10:33
make one and in theory that should add a
10:35
little bit of extra overhead on each
10:37
right but hopefully for the most part
10:39
this introduction to replication does
10:41
make sense the general gist of it is
10:43
literally creating extra copies of your
10:45
database data it allows for more
10:47
throughput for all of your users it
10:49
allows for durability in the event of a
10:52
crash or an idiot like myself spilling
10:54
coffee on the database and of course it
10:56
allows for the possibility of placing
10:57
certain databases in regions such that
11:00
they can serve certain users even better
11:01
so overall for any big application any
11:04
Google or Facebook or anything like that
11:06
replication is a complete must-have
11:08
there's no way in hell that you would
11:10
possibly have a huge company that relies
11:12
on data without completely replicating
11:14
that data many many times over so with
11:17
that being said guys I hope you enjoyed
11:18
the introduction I will speak to you
11:20
guys in the next one and we'll dive into
11:21
this quite a bit deeper because there's
11:23
a lot to unpack here

##v17:

Intro
0:00
hello everybody and welcome back to the
0:02
channel I'm here with another video
0:03
before I leave Australia for good and
0:05
get the [ __ ] out of this desert country
0:07
so today we are going to be talking
0:09
about eventual consistency and why it is
0:12
hard to deal with and some ways that we
0:14
can make life a little bit easier for
0:15
our clients when we have an application
0:17
that uses eventual consistency now
0:20
obviously the problem with eventual
0:21
consistency is of course that it is
0:23
eventual I can go ahead and tell you
0:25
guys that I'm eventually going to get a
0:27
girlfriend but in all likelihood and
0:29
frankly in reality that's probably going
0:31
to be between somewhere from 10 to 90
0:33
years from now so anyways let's go ahead
0:35
and jump into this we can talk about it
0:36
and see what we can do to make life a
0:38
little bit better for the people using
0:40
our application alright so I've got the
Making eventual consistency less shit
0:42
iPad up so let's go ahead and get into
0:44
things as you can see I've got this
0:46
handy dandy title making eventual
0:48
consistency less [ __ ] so if you recall
0:51
from last episode we often are going to
0:53
be doing things that are eventually
0:55
consistent the reason for this being
0:57
that strong consistency while nice is
0:59
too big the price to pay if I make a
1:01
right I don't want to have to wait for
1:03
that right to go to every single
1:04
database in my system I may have a
1:06
database in the US I may have a database
1:08
in Europe I may have one in Australia
1:10
and the penalty of having to wait for
1:12
that right to go to every single one of
1:13
those databases is just too big and
1:15
frankly not worth it so instead what we
1:18
end up doing is dealing with eventual
1:20
consistency where we write to one or two
1:22
or even a couple of places but we know
1:24
that some of those database replicas are
1:26
eventually going to get that right later
1:28
so with this in mind let's think of some
1:31
cool simple hacks that are going to make
1:33
life a lot easier for our user or the
1:36
client of our application so they're not
1:37
reading heinously and blatantly stale
1:40
data so example number one is just kind
1:44
of the base case of eventual consistency
1:45
recall that basically we've got one
1:48
client he's going to go ahead and make a
1:50
right to a database
1:52
he's going to receive an acknowledgment
1:54
from that database that the right has
1:56
gone through
1:57
and then he can go ahead and read from a
2:00
replica which effectively has no time
2:03
limits on when it's going to receive the
2:04
right it could come in in a day it could
2:06
come in a year who knows so he reads
2:08
that right he doesn't see his right from
2:10
before and now he's saying what the hell
2:12
I thought I just did something but it
2:14
turns out it didn't go through so let's
Examples
2:16
look at a few examples of things that
2:18
could happen when we're dealing with
2:19
eventual consistency and we're going to
2:21
go ahead and talk about these and uh
2:24
basically look at these cases and make
2:25
sure they don't happen and there are a
2:27
few easy ways of doing this so number
2:29
one is reading your own rights wouldn't
2:31
it be terrible if I and my girlfriend
2:34
who doesn't exist but it would be nice
2:35
if she did updated my relationship
2:38
status on Facebook you know this is uh
2:40
FB right here for Facebook and then of
2:43
course happen to read from a replica
2:44
right after which still went ahead and
2:46
told me that my status was single now my
2:49
girlfriend thinks that I'm snaking her
2:50
looking around for other girls to hook
2:53
up with in my spare time which frankly I
2:55
would and she thinks that I'm cheating
2:57
on her so obviously if we had strong
2:59
consistency this wouldn't be an issue I
3:01
would read from the replica and you know
3:02
it would say that I was in a
3:03
relationship
3:04
but one clever way of dealing with this
3:07
where we can still have eventual
3:08
consistency is we can say well for
3:10
starters if I'm going to make a right
3:12
for let's say you know 10 seconds after
3:14
I make this right I'm only going to read
3:16
from the database that I wrote to so
3:19
we're going to make sure that we get the
3:20
proper results back now our girlfriend
3:22
is happy and we can continue to cheat on
3:24
the DL no I'm just kidding but also what
3:27
we could do is even put a timestamp on
3:29
this right let's say I'm making this
3:30
right at time 100 I can look at another
3:33
replica let's say this one over here
3:36
before I make a read and say oh have you
3:38
seen rights from time 100 oh you have
3:41
well that means we can read from you
3:43
it's going to contain the fact that I am
3:45
in a relationship now if you've watched
3:47
my last series uh you know and you've
3:49
been on this channel for a while you
3:51
know that time stamps aren't really too
3:52
reliable when it comes to distributed
3:54
systems so there are a bunch of edge
3:56
cases where this won't work properly but
3:59
in the majority of cases it is good
4:01
enough to be right let's say 99 of the
4:03
time and you know save the time stamp
4:06
discussion for a future video
Monotonic Read
4:08
okay let's now go on to something called
4:10
monotonic rights or in this case the
4:13
lack thereof so let's say we've got one
4:15
group chat over here on the left where I
4:17
send three messages hey guys let's hang
4:18
out I'm free today and that has messages
4:20
ID one two and three respectively so
4:23
then my friend is going to come along
4:25
over here and read from these three
4:26
databases so basically let's imagine
4:29
that uh you know when you're reading
4:31
there's this button that says get last
4:34
message and you can just keep clicking
4:36
that and if there's a new message it'll
4:38
give it to you so effectively what guest
4:41
get last message does is let's say our
4:43
guy over here is going to first read
4:45
from a replica that has C in message
4:47
three and that's the last one it's seen
4:49
so first he's going to read I'm free
4:51
today which is great that's kind of what
4:53
we want we want to read from the most
4:55
up-to-date replica but then what's going
4:57
to happen is his next read where he
4:58
clicks get last message again because he
5:00
wants to see if there's anything new is
5:02
going to return message number two let's
5:04
hang out because that's the one with id2
5:06
and then finally he's going to do it one
5:07
more time for a replica that's only seen
5:10
message one as the last one and now he's
5:12
gonna see hey guys so effectively even
5:14
though it started out as if he had seen
5:16
all three of those messages what's
5:18
happening is our reads are effectively
5:19
going back in time and things are coming
5:21
in backwards because we're reading from
5:23
replicas that are progressively less
5:24
updated and that is obviously going to
5:27
be a pretty big problem so as you can
5:29
see I've written down the messages are
5:31
coming in in reverse order so what
5:33
actually is our fix here here well in
5:35
this case one easy thing that we could
5:37
do is actually have our user read off of
5:40
the same exact replica every single time
5:42
so even though the data that you might
5:44
be getting could be stale it's certainly
5:46
not going to be going back in time
5:47
because you're reading off the same
5:49
thing it's definitely going to be going
5:51
forward in time or as we might call this
5:53
a monotonic read so that's very
5:55
important to do how could we do this
5:57
well if you remember our modulo function
5:59
let's say our user ID is 20 we could do
6:02
20 mod 3 because there are three
6:03
replicas and that's going to be equal to
6:06
two so let's say this one is replica 2
6:08
over here we're always going to read
6:09
from that replica in particular so that
6:12
is going to simplify things for us a lot
6:13
obviously this has issues if one of
6:15
these replicas were to go down and of
6:17
course like all the things I'm saying in
6:19
this video because it's still pretty
6:21
overly simplistic there are a lot of
6:22
edge cases here however at least
6:25
thinking naively about this problem and
6:27
trying to get monotonic reads and writes
6:29
it's very important that basically you
6:31
know we're reading from the same replica
6:33
it can avoid this type of crappy
6:35
Behavior
Consistent Prefixes
6:36
okay then the last kind of edge case
6:38
that we want to talk about is actually
6:40
going over something known as consistent
6:42
prefix reads so for me to talk about
6:45
this I suppose the first thing we should
6:47
do is talk about something called
6:49
partitioning so partitioning is a topic
6:52
that I will be covering in depth on this
6:54
channel in probably five or six videos
6:56
but for now I'm going to make things
6:58
very simple let's say we've got one
7:01
database which is super big rather than
7:03
storing all the data in that one table
7:05
let's split it into two mini tables that
7:07
are on different computers so that's
7:08
going to be this guy and this guy and
7:10
let's assume now that we have two
7:12
messages basically one is me asking my
7:15
friend if he wants to grab lunch and the
7:17
other is the friend responding sure so
7:19
as you can see those are basically going
7:21
to two different partitions right the
7:22
arrows are pointing to two different
7:24
computers and the issue with that is
7:26
that each partition is going to have its
7:28
own separate replica so let's imagine
7:31
that we have a replica for partition two
7:33
which is this guy here and a replica
7:36
from partition one and because there's
7:38
no guarantees on when messages are going
7:41
to be transmitted over the network it's
7:42
possible that that message sure is going
7:44
to get to P2 replica before want to grab
7:47
lunch is going over to P1 replica and so
7:50
if that happens when person 3 the last
7:52
guy in our group chat goes and reads our
7:55
chat he's only going to see short and
7:57
he's going to say oh I wonder what that
7:59
was about I don't know and he's never
8:00
going to know that he actually could
8:01
have grabbed lunch with his other two
8:03
friends so how can we go ahead and fix a
8:05
problem like this well
8:07
basically what this is known as is a
8:09
causal dependency the only reason that
8:12
Shore was sent in the first place is
8:14
because it implicitly relies on the
8:15
sending of want to grab lunch now
8:17
obviously it's kind of tricky in terms
8:19
of how we can actually keep track of
8:21
these causal dependencies and for each
8:23
application that would be specific but
8:25
let's say that you know there was some
8:27
like reply feature in our application
8:29
you know a button that literally says
8:30
Reply and then the person wrote sure in
8:33
response to want to grab lunch what we
8:35
could do is say okay every time someone
8:37
uses the reply functionality to respond
8:40
to a message let's make sure that
8:41
they're actually go both going to the
8:43
same partition that way the messages
8:46
from that partition are going to be sent
8:48
in order to their replica and we won't
8:50
have to deal with any lack of consistent
8:52
prefix reads right this will allow us to
8:54
make sure that all causally dependent
8:56
rights are going to be on the same
8:58
replica which will solve our issue so
Summary
9:01
what's kind of the gist of this video
9:02
guys well it's not too complicated but
9:04
the point is this we are often going to
9:07
be dealing with eventual consistency now
9:09
that we've brought replication into the
9:10
picture and yes it is pretty much
9:13
impossible to completely get rid of any
9:15
sort of stale Reeds however there are
9:17
some sort of stale reads that are going
9:19
to make your user experience very bad
9:21
and very janky those examples are pretty
9:24
much the three that I covered in this
9:26
video and so as you can see there are
9:28
some clever solutions to basically
9:30
getting rid of the most blatant
9:31
violations of consistency right it's
9:34
always possible for example that if I'm
9:36
going to go to my Facebook news feed and
9:38
I'm going to say hey let me get a news
9:39
feed I'm not going to see all the most
9:41
up-to-date posts however that's not a
9:43
big deal because I don't know what the
9:45
most up-to-date posts are on the other
9:47
hand if I'm going to make a right to the
9:48
database and then five seconds later I
9:50
don't see it I'm going to be pissed off
9:52
so these three ways are kind of
9:54
loopholes and you know being clever to
9:56
make sure that your client of your
9:58
application is not getting too pissed
10:00
off due to the eventual consistency of
10:02
your application so in the next videos
10:04
I'm going to cover the specifics of in
10:06
replication topologies how you actually
10:08
want to basically send those rights from
10:10
one node to another in your databases
10:12
and once we do that we'll have a much
10:14
better sense of the entire picture of
10:16
replication and which type is right for
10:18
you anyways guys have a good one and I
10:20
will see you in the next video

##v18:

0:00
well guys I'm freaking pissed off today
0:02
why well uh so I basically recorded this
0:06
video earlier and uh just because I've
0:08
just moved again I'm actually back in
0:09
the US now of course I didn't have my
0:11
microphone set up properly and I go to
0:13
edit the video and uh there's no
0:16
audio and so I'm now looking at this
0:18
video uh thinking to myself well I
0:20
just popped two Edibles and now I have
0:22
to re-record a 10 minute YouTube video
0:24
on systems design so uh this should go
0:26
really well and uh I'm hoping it does
0:29
and let's get into it but before we do I
0:31
should probably quickly announce that uh
0:33
I guess we've just reached the one year
0:35
anniversary in the channel so I'd like
0:37
to thank everyone for their subscription
0:39
and watching and just in general being
0:41
very supportive you guys are great in
0:42
the comments and it's clear that
0:43
everyone's taking this very seriously
0:45
and following along and interviewing
0:46
themselves so thanks again for all the
0:48
support let's get into this video so I
0:50
can finish this before I get high
Single Leader Replication
0:52
alrighty welcome back everybody I've got
0:54
the iPad on my lap I just deleted all
0:56
the annotations and markings that I did
0:58
with it before which is great and uh
1:01
let's go ahead and start talking about
1:03
this video so that uh I can get it out
1:05
before I forget what replication is so
1:07
basically to start we have this concept
1:09
of a single leader replication so in the
1:12
past couple videos we talked about what
1:13
replication is why we might need it and
1:15
also synchronous versus asynchronous
1:17
replication so for the purpose of this
1:19
video I'm going to assume we're
1:20
generally using asynchronous replication
1:22
because synchronous replication
1:23
generally speaking is not very practical
1:26
there are some scenarios where you do
1:27
need to do it if you have to ensure that
1:29
you can never have a stale read but I'd
1:31
say 99 of the time you're probably not
1:34
replicating synchronously so let's go
1:36
ahead and assume that every time I write
1:38
a dotted line with an arrow such as this
1:41
one here that means asynchronous
1:42
replication so what is single leader
1:45
replication well it's known as a
1:46
replication schema which basically means
1:49
that it's a way of sending rights to the
1:51
database and then basically reading from
1:53
it later so we've got our client over
1:55
here and it's going to perform a right
1:57
to our leader database so the point of
1:59
the leader is that all rights no matter
2:01
who is sending them have to go to our
2:03
leader database however we also have
2:06
many follower databases as you can see
2:08
we've got one here we've got one here
2:10
and basically as they asynchronously
2:12
receive rights from the leader any other
2:14
client including the original writer
2:16
such as this guy over here can perform a
2:18
read from them and the same client can
2:20
perform a read from this database down
2:22
here it can perform a read from the
2:24
leader itself so again it gives us a lot
2:26
more opportunities to increase our read
2:28
throughput so let's actually go into a
2:30
breakdown of what single leader
2:31
replication achieves for us so basically
2:34
there is a couple of benefits and then
2:37
we'll break those down a little bit more
2:39
even so basically number one most
2:41
importantly is increased durability we
2:44
have many copies of our data now and it
2:45
means that if I were to take a nuke and
2:47
go nuke one of our data centers we still
2:49
have a few other copies of that data
2:51
which is great
2:52
additionally we also have increased read
2:54
throughput this is a result of what I
2:56
showed over here so in this case as
2:58
opposed to having just you know normal
3:00
read throughput from the leader itself
3:01
we're also adding two followers which
3:04
gives us three times as much read
3:05
throughput which is great and it's
3:07
basically for free right all we have to
3:09
do is just add a couple of extra
3:10
databases which are asynchronously
3:12
reading rights in the background so it's
3:14
pretty easy to go and extend our system
3:16
to support single leader replication
3:19
so let's look at a couple of failure
3:21
scenarios because the entire point of
3:22
replication aside from increasing read
3:25
throughput and sometimes but not in this
3:27
case increasing right throughput is to
3:29
basically make sure that in the event of
3:31
failures we still have a working system
3:33
so let's look at a couple of these so
Failure Scenarios
3:35
one type of failure scenario is our
3:37
follower goes down right let me zoom in
3:39
here so we don't get distracted and so
3:42
let's say we have one follower right
3:44
here and I go ahead and trip over some
3:46
wire and now I've pulled the plug on it
3:48
so pulled
3:50
plug
3:51
here we go so now we're down one less
3:54
follower let's imagine that right before
3:56
the follower went down we know that it's
3:59
seen all rights up to position 50 in our
4:02
replication log right so we have this
4:04
concept of a log that can just be stored
4:07
on disk and that log is being sent
4:10
basically from the leader to all the
4:14
followers right and so we can actually
4:16
keep track on every single follower what
4:18
the last position that they've seen on
4:20
the replication log is and so let's say
4:22
this guy goes down and we know that it's
4:24
at position 50 right over here let's now
4:26
say though that eventually I realized
4:28
that I pulled the plug out on this thing
4:30
I get up you know I put a Band-Aid on my
4:32
knee because I tripped and then we go
4:35
ahead and see that hey the leader is at
4:36
position 70. well now what the leader
4:40
can actually do is just go ahead and
4:41
send rights from 51
4:43
to 70 all the way to our basically newly
4:48
revived follower and then he can be
4:50
caught back up and so what's great now
4:52
is that this guy is back up to date
4:54
after only a little bit of time so when
4:57
a follower does go down in a single
4:58
leader replication situation this is
5:00
super easy to deal with happens all the
5:02
time to be expected on the other hand
5:04
when a leader goes down we've got many
5:07
many challenges to deal with so let's
5:09
discuss basically three different
5:11
scenarios of things that can go wrong
5:12
when a leader goes down and we'll kind
5:15
of explain why this is such a big deal
5:17
in a single leader replication setup
5:19
so let's look at scenario one over here
5:21
in the top left so I'll even zoom in on
5:23
it for us so basically let's imagine
5:26
that we've got one follower over here
5:28
and he thinks that the leader is dead
5:31
right because maybe just the network
5:33
connection between the leader and
5:34
follower is down hence this x right here
5:37
well it's possible actually that the
5:39
follower just has bad internet as you
5:41
can see our other follower is
5:42
criticizing him because the truth of the
5:45
matter is the leader could still be up
5:46
and running and there might just be an
5:48
issue communicating between the leader
5:49
and the follower
5:51
and so if a follower were to think the
5:53
leader is down it might want to replace
5:54
it somehow with a new leader but the
5:56
reality of the situation is it's really
5:58
hard to actually be sure that that's the
6:00
right thing to do because of the fact
6:02
that you know the network is
6:03
asynchronous we're not actually sure
6:05
when the leader is going to communicate
6:06
with the follower next so it's hard to
6:08
be sure that the leader is down so
6:10
that's one problem already and we're
6:12
going to touch upon you know probably
6:13
many videos later how we can actually
6:15
fix something like that but it's
6:17
definitely not easy and it's going to
6:18
require a lot more thinking so problem
6:21
number two is this you know you think oh
6:23
just because I have single leader
6:24
replication that you're never going to
6:26
have any lost rights right every right
6:28
goes to the leader and then eventually
6:30
it's going to be propagated right back
6:32
to the followers so every single right
6:34
is eventually going to every one of the
6:36
followers we're never going to lose any
6:37
rights right well not necessarily
6:39
because let's say we've got a leader who
6:42
on you know our replication log
6:47
the last right that it wrote when that
6:49
log was 80. and remember that those
6:51
rights are being propagated
6:52
asynchronously to the followers so if
6:55
this guy gets right number 80 and it
6:57
basically goes down because someone
6:59
pulls the plug on it and then our
7:01
follower has only seen up to right 70 in
7:03
the replication log well now we've
7:06
basically taken right 71 to 80 and just
7:08
said they don't exist
7:10
and so you know these could actually be
7:13
valuable rights you know this could be
7:14
someone's financial data this could be
7:16
my message to a baddie over Tinder
7:18
anything like that now all of a sudden
7:19
you know it's just gone it's completely
7:21
in the void and that right that you
7:23
thought was valid no longer exists
7:25
anymore so even though this leader is
7:27
you know basically you know we've taken
7:30
our follower and we've promoted him to
7:32
leader one
7:33
the issue is that doesn't actually have
7:36
all of the rights that we thought it
7:37
would and so now we have a data
7:39
Integrity issue so that's the second
7:40
issue and I'm still not even offering
Split Brain
7:43
any solutions at this point because
7:44
frankly it's really really hard to offer
7:46
solutions to this and so we'll discuss
7:48
that in a second
7:49
so now our third scenario is this let's
7:51
imagine we have this original leader
7:53
over here
7:54
it goes down we elect a follower as our
7:57
new leader Prime
7:59
now it loves being the leader for sure
8:01
and then all of a sudden
8:03
as if coming back from the dead our
8:06
original leader is back and now we have
8:08
two leaders
8:09
what is this known as it is called split
8:13
brand so let me go ahead and write that
8:15
down
8:16
and so split brain is when our system is
8:19
only supposed to have one liter but do
8:21
do basically just you know issues with
8:24
certain nodes coming back on certain
8:26
nodes going down we end up having two
8:28
liters and so now if we have a second
8:30
guy not only does this guy here not know
8:32
who to write to but our second guy might
8:34
write to this right leader and then the
8:37
first guy might write to the left leader
8:39
and then they're both sending rights to
8:41
all of the followers and the followers
8:43
are like what the hell where are these
8:45
rights coming from split brain clearly
8:47
if it were to happen is a major data
8:49
Integrity issue and you can be certain
8:51
that one of those two leaders is going
8:53
to have to get shut down or else chaos
8:54
can ensue so as you can see clearly
8:57
having a leader that does go down is a
9:00
massively problematic situation and
9:02
truthfully due to the fact that there's
9:04
no guarantees on when you know a network
9:06
message is going to get from a leader to
9:08
a follower or a follower back to a
9:10
leader or from a follower to a follower
9:12
it's really really hard to say oh I know
9:15
for sure that this leader is down and I
9:17
know for sure that this node is the
9:19
leader right you basically need
9:21
something called this distributed
9:23
consensus and so a distributed consensus
9:25
is saying is that you know if we got a
9:28
few databases oh my God I'm terrible at
9:29
drawing if we have a few databases
9:34
let's say we've got three of them
9:38
it means that all three even though
9:40
they're not physically the same computer
9:42
are a hundred percent sure not only of
9:45
who the leader is but whether it's up or
9:48
it's down so in this case it would be
9:50
leader and everyone agrees and this
9:52
concept distributed consensus is
9:54
something that we're going to have to
9:55
cover in detail you know a few videos
9:57
down the line but it is super important
9:59
because basically without this concept
10:01
of being able uh to agree on some sort
10:04
of consensus amongst multiple computers
10:06
we would basically have no setup for
10:08
replication that allows us to ensure the
10:10
correctness of our data and that would
10:12
obviously be super problematic so I just
10:14
wanted to show this off as a problem to
10:16
kind of set the stage for that a few
10:18
videos from now but anyways let's do a
Conclusion
10:21
quick conclusion of single leader
10:23
replication before we go on to our next
10:25
videos and I can doze off
10:28
so number one is like I mentioned it's
10:30
simple right if you already have a
10:32
single database turning that into a
10:34
single leader replication setup is super
10:35
easy you just add followers and it's
10:38
also simple in the sense that if a
10:39
follower goes down you can either add a
10:41
new follower and just restore it using
10:42
the replication log or you can bring
10:44
back the old follower and again restore
10:46
it using the replication log at the same
10:49
time there is quite a bit more read
10:51
throughput right if I'm in Chicago and
10:53
then you've got a bunch of idiots who
10:54
live in Australia for God knows what
10:56
reason they can easily access that data
10:58
via a replica that is located closer to
11:01
them which is very important at the same
11:03
time there are some downsides to single
11:05
leader replication we've touched already
11:07
upon like the leader going down and for
11:09
now let's assume that we do actually
11:11
have a solution for the leader going
11:13
down and that we can perform something
11:14
known as a failover where we elect a new
11:17
leader and things go well again but even
11:19
besides that assuming we can figure out
11:22
a way to elect a new leader we do have
11:24
this other problem which is this what if
11:27
we want more right throughput a lot of
11:29
applications just have a ton of Rights
11:31
and what I've only given you the option
11:32
to do right now is get more read
11:34
throughput because at the end of the day
11:36
you can have this type of setup
11:38
but what's going to happen is that your
11:41
right throughput is limited to that one
11:45
liter and so ultimately what we need to
11:47
end up doing is coming up with different
11:49
types of replication schemas that are
11:51
going to allow you to write to multiple
11:53
different places and by doing so then we
11:56
could increase our right throughput so
11:57
we're going to talk about that in the
11:58
next few videos and of course the
12:00
problems that arise when we try and do
12:02
things like that and I'm looking forward
12:04
to it guys so have a great night I will
12:06
be doing the same and I'll see you in
12:08
the next one

##v19:

0:00
hello everyone and welcome back to the
0:02
channel it is a warm sunny day here in
0:05
Chicago which is unusual considering it
0:07
is normally a desolate Tundra
0:09
additionally it seems like a fine day
0:11
for all of us to talk about multi-leader
0:13
replication now personally I'm not a big
0:16
fan of multi-leader replication because
0:18
as an Alpha Sigma male myself I actually
0:21
don't believe in having multiple leaders
0:23
clearly such a setup is destined to fail
0:25
as you can see in this video there are
0:28
many problems with multi-leader
0:30
replication regardless of the advantages
0:32
that it does bring so let's go ahead
0:34
bring the iPad out and talk about all of
0:36
them alrighty so as I mentioned today
Overview
0:39
we're going to be talking about
0:39
multi-leader replication
0:42
and let's go ahead and get into it so
0:45
let's start out with a basic diagram of
0:47
what multi-leader replication actually
0:48
looks like as you can see we've got a
0:51
few leader nodes
0:52
where the leaders can be marked with L's
0:55
and of course we have some follower
0:58
nodes as well where the followers can be
1:01
marked with f
1:02
so what does multi-leader replication
1:04
actually get us well basically the point
1:06
here is that anyone can write to any of
1:09
the leaders and they can write anything
1:10
and of course we can still only read
1:13
from the followers and the followers are
1:15
going to be getting those rights
1:17
propagated to them probably
1:18
asynchronously so again what does this
1:21
afford US it affords us more right
1:22
throughput why because now we can write
1:24
to a bunch of different places and
1:26
additionally another thing that's really
1:27
nice about this is say we've got a user
1:29
in Europe we've got a user in North
1:31
America and one in Africa the guy who's
1:33
in Europe doesn't have to go ahead and
1:35
write all the way to North America
1:36
because obviously those are further
1:38
apart it's going to take a longer amount
1:40
of time for his message to cross all of
1:42
those internet cables and having leaders
1:44
in all of these different places may
1:46
make life a lot more convenient so as
1:48
you can see in this case though the
1:49
leaders themselves
1:51
are not exactly isolated either right
1:53
they're still passing their rights from
1:55
one to another and there are many
1:56
different configurations in which they
1:58
can actually pass these rights from one
1:59
to another so let's go ahead and start
2:01
talking about them so the first and most
Circle Topology
2:04
basic that we'll talk about is the
2:07
circle topology so this is pretty simple
2:09
basically imagine all of these nodes
2:11
that I have in this graph are liters and
2:14
they're going to go ahead and pass
2:15
rights to one another so you know we've
2:17
got rights coming from here we've got
2:19
rights coming from here but of course
2:21
this does beg the question what if I
2:24
killed one node let's say I went ahead
2:26
tripped on a power cable and now this
2:29
guy is gone well shoot it just occurred
2:31
to me that this guy right here is
2:34
relying on the existence of this node in
2:37
order to get his rights over to this guy
2:39
so now all of a sudden our system cannot
2:42
move forward right rights are no longer
2:43
going to be propagated around our
2:45
multi-leader setup and we've basically
2:47
just screwed ourselves so that's the
2:49
issue Circle topology is basically have
2:51
no no kind of durability or protection
2:53
against one single node failure so what
2:56
can we actually do to make this better
2:57
well of course another possible solution
3:00
is the star topology
Star Topology
3:02
so why is this another solution well
3:06
let's go ahead and kill some nodes let's
3:08
say that the point of the star topology
3:11
keep in mind is we've got one Center
3:12
node right which you can see right here
3:14
and then a bunch of outer nodes that are
3:16
passing all of their rights to the
3:17
center node and then the center node in
3:18
turn is going to distribute them to the
3:21
rest of the nodes in the star topology
3:22
if I were to go ahead and kill this guy
3:25
right here well it's no big deal because
3:27
these two can actually still go ahead
3:29
and communicate with each other right
3:31
it's fine right all of the star is still
3:34
maintained on the other hand of course
3:37
we are still susceptible to one major
3:39
failure which is the center of the star
3:42
because if this guy goes down right I go
3:45
ahead and nuke that now all of a sudden
3:46
these two databases can no longer
3:49
communicate with each other because
3:50
they're both sending messages to that
3:52
Center node the center node isn't
3:54
responding and they're saying
3:56
we're out of luck okay so what can we do
All To All Topology
3:59
that's possibly even better than that
4:01
well
4:02
the all to all topology
4:04
now this thing is where pandemonium
4:06
really starts to go crazy you know
4:07
they're sending messages around like I
4:09
send DMS to girls on Instagram
4:11
as you can see if a single node goes
4:13
down it's actually not an issue why
4:15
because they're all communicating with
4:16
each other anyway that being said there
4:18
is still a problem of kind of causality
4:21
right where so for example let's say uh
4:24
this guy has a message a written to it
4:26
and then this guy is going to receive a
4:30
and then now all of a sudden someone
4:32
writes uh B on top of a okay and then
4:36
this guy then passes B over to this note
4:38
over here and yet this guy still hasn't
4:42
even received a yet right so a is going
4:44
very slow but it's still only over here
4:47
so now we have an issue where this
4:49
database has received a message B that
4:52
is causally dependent on the message a
4:54
so it is possible for our rights to get
4:56
out of order and this is something
4:59
that's fixable but it's going to take
5:00
quite a bit of thinking to get done and
5:02
it's something that I'll talk more about
5:04
in the next video so you know this whole
5:06
causality thing it's not a huge point
5:08
but the main issue here is keep in mind
5:10
that when you're passing messages all
5:11
around indiscriminately things can get
5:13
out of order and out of whack so with
Replication Log
5:16
that in mind well how actually can they
5:18
get out of order and out of whack and
5:19
how can we make sure that when messages
5:21
are bouncing around the databases all
5:24
over the place right because we've got
5:25
things going up and down and side to
5:29
side and they're coming back we want to
5:31
make sure that all of these rights are
5:33
not being applied multiple times on
5:35
every single database node so we
5:37
actually have to go ahead and make a
5:39
change to the replication log to ensure
5:41
that rights aren't being bounced around
5:43
forever so every single database can
5:45
obviously keep track of which rights its
5:47
apply it but you know it's probably
5:49
going to take that right that it gets in
5:51
and send it to all the other database
5:53
nodes if it thinks that they haven't
5:55
seen it yet so what can we actually do
5:57
well we can modify our replication log
5:59
to actually keep track of which rights
6:02
in the replication log have been seen by
6:04
which database nodes so let's say we've
6:06
got five nodes one example of what we
6:09
can do right here let's say in the
6:10
replication log we're writing you know
6:12
Jordan is equal to sexy obviously and
6:15
then what we would do is in a
6:17
multi-leader setup we can actually add
6:19
the fact that as this right kind of goes
6:22
to a specific database node that it's
6:24
been seen by that database node so this
6:26
way you know once one two one three and
6:29
five goes to one two three four five any
6:33
database that receives that right is now
6:35
not going to send it out any further so
6:36
that's the only way we can ensure that
6:38
there's not going to be effectively just
6:40
like an infinite Loop of a ton of Rights
6:42
being sent around and clogging our
6:44
system and screwing things up so that is
6:46
very useful basically it answers which
6:49
replicas have seen the right as best as
6:51
we are aware and that makes sure that we
6:54
aren't just passing the message around
6:55
indefinitely and possibly even applying
6:58
it more than once because that could be
6:59
really problematic
7:01
okay so kind of the elephant in the room
Conflict Avoidance
7:03
that I haven't spoken about so far is
7:06
the issue with their basically being two
7:08
leaders right and what two leaders leads
7:11
to is Right conflicts because we can now
7:14
write to multiple places so let's look
7:17
at a quick example of this as I try and
7:19
scroll and whatnot so we've got leader
7:22
one right here we've got leader two over
7:25
here what is a right conflict well let's
7:27
say I've got one guy probably myself
7:30
writing that Jordan is Alpha to leader
7:33
one and then we've got a second guy
7:35
probably a major coward writing to L2
7:38
that Jordan is beta so when L1 and L2
7:41
eventually pass rights to each other as
7:43
we know they will regardless of the
7:44
topology
7:45
how do we actually know whether Jordan
7:47
is Alpha or Jordan is beta because they
7:50
were written basically at the same time
7:52
we're assuming actually that the person
7:53
who wrote Jordan is Alpha does not know
7:56
about the Jordan is beta right when they
7:58
wrote it and Sam goes for the Jordan is
8:00
beta writer what this effectively means
8:02
is that these two rights are concurrent
8:04
and now we have to resolve a right
8:06
conflict between them
8:08
so which one is actually going to be the
8:10
winner well one easy solution is
8:13
actually known as conflict avoidance
8:18
and What conflict avoidance does is
8:20
basically says that all rights to the
8:22
same key are going to the same replica
8:24
right so the way we could actually avoid
8:26
this situation is by instead of letting
8:28
this guy write Jordan equals beta to L2
8:30
he has to write it to L1 because then we
8:33
know that alpha or beta is going to get
8:35
there first and then one of them is
8:37
going to win
8:38
on the other hand this is actually going
8:41
to limit the type of write throughput
8:42
that we have right because if all of our
8:45
guys have to write to the same replica
8:47
for the same key you know let's say this
8:49
guy over here is in Africa now he has to
8:52
write to North America and it's going to
8:54
take a little bit longer what we've
8:56
effectively done here is partition the
8:58
database and partitioning is something
8:59
we're going to talk about a lot in the
9:01
future but for now let's not really
9:03
think about this strategy too much
9:05
because more so what we care about is
9:06
actually resolving right conflicts so
9:09
let's think about a way that we can do
Last Right Wins
9:10
it well one strategy that I often see
9:13
mentioned is last right wins so every
9:15
single right to a database is going to
9:17
have a time stamp right you know I'm
9:19
writing Jordan equals Alpha at four
9:22
o'clock P.M and so what we can use is
9:25
that time stamp to decide right if I
9:27
write Jordan's Alpha at four o'clock and
9:29
someone writes Jordan as beta at 401
9:31
well it turns out Jordan is beta is the
9:33
more up-to-date value So in theory this
9:35
does work right however in reality
9:37
there's actually a lot of problems the
9:39
first problem is what time stamp do we
9:41
actually use do we use the timestamp of
9:43
the sender well probably not this isn't
9:46
a great idea because if we use the
9:47
timestamp of the sender someone can
9:49
actually just like purposely manipulate
9:51
their device timestamp you know for
9:53
example if I always wanted to make sure
9:55
that the value for Jordan was Alpha I
9:57
could just go ahead and change my device
9:59
timestamp to 2100 because now all of a
10:02
sudden I'm 77 years in the future and my
10:05
right is pretty much always going to win
10:07
for the next 77 years on the other hand
10:09
we could use the timestamp of the
10:11
receiver right we could actually use the
10:13
timestamp on the two individual leader
10:15
nodes in order to determine which right
10:17
was more recent now yes technically this
10:20
does work if of course we could rely on
10:23
those timestamps so it turns out we
10:25
actually can and why is this we're
10:27
actually going to do a little bit of a
10:28
deep dive into computer hardware
10:30
so basically clocks in computers are run
10:33
on something called a quartz crystal and
10:35
the quartz crystal is set to vibrate at
10:38
a certain frequency that allows the
10:39
computer to tell how much time has
10:41
elapsed between two periods so that's
10:43
really useful that being said this
10:45
quartz crystal is not perfect in
10:47
response to certain changes in the
10:49
weather and just randomly over time the
10:51
frequency that it vibrates can actually
10:53
change a little bit that's known as
10:55
clock skew so actually the computer time
10:57
stamp can you know be a few nanoseconds
11:00
or milliseconds a little bit away from
11:02
the actual time that it should be and
11:04
this itself turns out to be a problem
11:06
why is that well obviously if we can't
11:09
rely on our time stamps on our computers
11:11
it means that say I may have written the
11:13
right later than someone else calling me
11:16
beta however it turns out that that
11:19
computer or that leader that the beta
11:20
right went to just happened to have a
11:22
later time step so what do we actually
11:24
do because clock skew is a serious
11:26
problem in modern Computing well
11:28
frequently what we would do let's take
11:30
my cell phone over here and you know
11:31
we've got a time that says four o'clock
11:34
however we know it's really supposed to
11:36
be 359 right or 358 rather so what we
11:40
would typically do is we would perform a
11:42
network request over ntp which is
11:44
Network time protocol so ntp allows us
11:47
to ask some sort of global time server
11:49
which has a GPS clock which is going to
11:52
be a lot more accurate than quartz drift
11:54
and then we can actually go ahead and
11:56
adjust our computer clock in response to
11:59
that so this allows us to at least stay
12:01
pretty close to the actual time however
12:03
even this isn't perfect because ntp
12:05
implies that we are making that request
12:07
over a network and by making a request
12:10
over a network we are subject to network
12:12
delay so you can see right here that
12:15
even if ntp tells us it's 358 if we have
12:18
a one second delay now all of a sudden
12:20
on my phone I think it's 359 which is
12:23
still wrong and what this means is that
12:25
all of a sudden the time on your device
12:27
can literally jump backwards in time and
12:30
so if you're doing this it's not very
12:31
reliable for trying to build a robust
12:33
application we can't order rights this
12:35
way because just basically randomly in
12:38
response to the time on your computer
12:39
which isn't accurate you can just lose
12:42
rights right like the Jordan is beta
12:44
right if it were to lose there would
12:45
just be lost forever and we wouldn't
12:46
even know it existed so it's very
12:48
important that our time stamps be
12:50
accurate except the truth of the matter
12:52
is it's not very easy to do so
12:54
so again this leads to Lost rights at
12:57
the end of the day now I am going to
12:59
stop the video here because the truth of
13:00
the matter is there's not a great
13:02
solution to solving right conflicts
13:04
we're going to talk about in the next
13:05
video some more in-depth ways of doing
13:08
so and there are some pretty clever
13:09
tricks to be able to identify two rights
13:12
that have occurred concurrently but
13:13
there's no hard and fast rule to look at
13:15
two rights and say hey one definitely
13:17
came before the other and here's how we
13:20
know there are some databases that have
13:22
kind of tried doing this and they are
13:24
making some progress but they're pretty
13:26
Niche Hardware decisions for the most
13:28
part and we will talk about those
13:30
eventually too anyways guys I hope you
13:32
have a great rest of the day I will see
13:34
you in the next one and uh yeah keep
13:36
grinding

##v20:

0:00
hey everyone and welcome back I needed
0:02
an excuse to put on some underwear and a
0:04
t-shirt so I figured I would go get
0:06
myself on camera and uh if you're
0:09
noticing right now that my skin seems a
0:11
bit
0:12
I don't know perhaps shiny maybe moist
0:14
it's not what you think it is I've begun
0:16
a skincare routine to hopefully fix my
0:18
gross pepperoni face so uh now that I've
0:20
gone through this little opening ramp
0:22
let's go ahead get started we'll talk
0:23
about detecting concurrent rights how we
0:26
can do that how this is better than last
0:28
right wins and uh yeah let's just go
0:30
ahead and get into it so I can get
0:32
myself to sleep
0:33
so if we recall where we left off from
0:35
last time basically I introduced the
0:37
concept of multi-leader replication so
0:40
it means now that instead of just having
0:42
to write to one place we can actually
0:43
write to a bunch of different places
0:45
which is really nice for increasing
0:46
right throughput at the same time we run
0:49
into the potential of Riot conflicts so
0:51
how can we actually address those
0:53
conflicts well one way is by giving
0:55
every single right a timestamp but time
0:57
stamps aren't very reliable so let's
0:59
look at a potentially better way of
1:01
doing so so to introduce today's video
1:03
we're going to start with the concept of
1:05
trying to build a distributed counter
1:07
using a multi-leader replication setup
1:10
so like I mentioned we've got our
1:11
distributed counter we've got two liters
1:14
right over here and over here and the
1:17
gist is that you know we've got one guy
1:19
writing to our left leader doing
1:21
increments we've got another guy writing
1:23
to our Right leader also doing
1:24
increments so let's imagine we've got
1:27
our version one over here so in version
1:30
one the left guy has a count of three
1:32
the right guy has a count of five and
1:35
let's say now that uh it gets to the
1:37
point where they're sending their rights
1:39
to one another so they can actually you
1:41
know go ahead and confirm uh the values
1:44
that they have so the left guy is going
1:46
to send three to the right the right guy
1:48
is going to send five to the left well
1:50
how are they actually going to rectify
1:51
these how do we merge this right
1:53
conflict because they both disagree on
1:55
the value well I guess one way that
1:57
would be pretty simple would just be hey
1:59
you know five is a higher number than
2:00
three probably there's just been two
2:03
more rights that we didn't account for
2:04
on the left side just yet and now we
2:06
should set the left to five you know so
2:08
we would do something like this
Concurrent Rights
2:10
and uh you know five basically just
2:13
stays as five on the right because you
2:15
know five is bigger than three so in
2:17
theory
2:18
that could work however in practice it
2:21
obviously doesn't why not because the
2:23
guy on the left who was writing those
2:25
three times to the left is different
2:27
than the guy on the right who is writing
2:30
five times so the ideal result that we
2:32
actually want to be getting is eight
2:33
that's the correct answer so this should
2:36
introduce ideally the concept of
2:38
concurrent rights basically we know that
2:40
we have two people on the left and the
2:42
right writing at the same time they
2:44
don't know about each other's rights
2:46
right they haven't seen those rights
2:48
before they're doing their own and as a
2:50
result that's what makes them concurrent
2:52
you may have heard the term concurrent
2:53
before meaning two things happening at
2:55
the same time but truthfully uh you know
2:58
they can happen at slightly different
2:59
times but as long as they didn't know
3:01
about each other that is what makes them
3:03
concurrent so let's talk about version
3:05
two which I'm sure you were already
3:07
starting to think about because example
3:09
one was clearly pretty stupid
Version Vector
3:11
which is this concept of a version
3:14
Vector so let's go ahead and talk about
3:18
that as I zoom in this window
3:21
pardon me okay we're properly zoomed so
3:25
this time instead of just storing a
3:28
counter on each database we're actually
3:30
going to store the number of increments
3:32
that we've seen from each leader node so
3:34
in the starting State remember that we
3:37
had a guy on the left writing three
3:39
times hence the version Vector three
3:41
comma zero in the first index of this
3:44
Vector we know that we've seen three
3:46
increments the left side and zero
3:48
increments to the right side
3:50
similarly on the right side we've had
3:52
five increments so now we've seen zero
3:55
increments from the left side and five
3:57
increments from the right side do recall
4:00
that eventually these databases are
4:01
going to send their rights to one
4:02
another so when that happens they can
4:04
both send the actual counter value but
4:07
they can also send the version Vector so
4:10
instead of literally just going and
4:12
setting a naive counter now we have this
4:14
version vector and what we can do is
4:16
merge them so as you can see on both
4:18
sides it's going to result in a version
4:21
Vector of 3 and 5 and a counter of eight
4:24
why because the left side has been
4:26
incremented three times the right side
4:28
has been incremented five times and so
4:30
now we can just go ahead and combine
4:32
those values and the total counter is
4:34
going to be the sum of the entries in
4:36
that version Vector you know 8 is
4:38
obviously equal to three plus five
4:40
so now what if uh something were to
4:43
happen where basically the left side
4:44
gets incremented again see over here
4:46
we've got one increment and now the left
4:48
side turns into nine because we're
4:51
incrementing our counter by one and the
4:53
left side has been updated four times
4:54
the right side at least according to the
4:56
left has still only been updated five
4:58
times So eventually what's going to
5:00
happen is that version Vector of four
5:02
five with a counter of nine is going to
5:05
be passed to the right side and what
5:07
we'll say is okay on the right we now
5:10
see that a counter of nine is coming in
5:12
are we just going to add 9 to our count
5:14
of eight no we're not going to because
5:16
that would give us 17 and that would be
5:18
wrong the truth is that this 9 and 8
5:21
have a significant amount of overlap how
5:23
much overlap do they have well the three
5:26
and the five themselves overlap so the
5:28
only difference is actually this four
5:30
right here so we're only just adding one
5:33
to our version Vector saying okay now
5:35
we've seen one more increment from the
5:37
left leader and now our counter is nine
5:40
okay so hopefully you guys are starting
5:42
to get the concept of this but the point
5:43
is version vectors basically just keep
5:45
track of how many increments they've
5:47
seen from each leader database
Thought Exercise
5:51
okay so let's do a little bit of thought
5:53
exercise now how can we actually see
5:56
which rights are concurrent by using
5:59
version vectors so let's imagine we've
6:01
got these three liters right here right
6:03
oh oh and they're in an all to all
6:07
replication setup which keep in mind
6:09
that means that any right can be sent to
6:11
any node and it puts no guarantees on
6:14
The Ordering of when certain rights are
6:16
getting two nodes within that
6:17
replication
6:19
so notice now that we've got two one two
6:22
over here on the top what does that mean
6:24
it means that it's basically go ahead
6:26
and scene two rights from our left
6:29
leader it's seeing one right from the
6:32
bottom guy and it's seen two rights from
6:35
itself
6:36
okay now what if you were basically
6:39
getting past 111 from the bottom node
6:43
right so it goes one one all the way up
6:45
here we've got some right with some
6:47
value in the version Vector Associated
6:48
is one comma one comma one well
6:51
basically what this guy would say is I'm
6:53
going to disregard
6:55
we're not making any changes to this
6:58
leader because we've already accounted
7:00
for all of those rights why is that
7:02
because 2 comma 1 comma 2 is strictly
7:05
greater than or equal to one comma one
7:08
comma one which means that we've already
7:10
accounted for two rights in the first
7:13
leader one right and the second leader
7:15
and two rights in the third leader so
7:17
any right that comes to us by saying
7:19
we've only accounted for one right and
7:21
the first leader one right and the
7:22
second and one right and the third we've
7:24
already accounted for all of those in
7:26
our leader and so we don't have to make
7:27
any changes so we know that a version
7:30
Vector where all of the entries are
7:32
strictly greater than or equal to all of
7:34
the entries of another version Vector we
7:37
can say that the first right has come
7:39
after
7:42
the second right they are not concurrent
7:44
on the other hand if the opposite
7:47
applies we can say with certainty that
7:49
those two rights are concurrent for
7:52
example look at B's over here
7:54
five is greater than four but two is
7:58
less than three and so what that means
8:00
is that one of the servers
8:03
has seen one more right than the other
8:06
that went to leader number one but that
8:10
Sam server has seen one less right from
8:12
leader two which means that these two
8:15
rights could not have possibly known
8:16
about each other
8:18
if you need to take a second pause think
8:20
about this concept but the gist is that
8:22
if we have two basically interleav
8:25
inversion vectors we know that those two
8:27
rights could not have possibly known
8:28
about each other they must have been
8:30
concurrent and so what can we actually
8:33
do when we realize that rights are
8:35
concurrent
Option 1 Store siblings
8:36
well let's think about it option one is
8:39
to store siblings so let's say I've got
8:41
one guy over here who writes Jordan is
8:44
scary and then we've got a second guy on
8:47
the left who writes Jordan as cute so
8:49
according to our version vectors we know
8:51
that the version Vector for Jordan
8:53
equals Q is one comma zero why because
8:55
there's been one right on the left side
8:57
and zero writes on the right side
9:00
at least accounted for in this leader
9:02
and then similarly the guy who writes
9:05
Jordan equal scary has an Associated
9:06
version Vector of zero comma one why
9:09
because this database node hasn't seen
9:11
any rights from leader one but it now
9:13
has one right for itself
9:15
and so we look at these two things and
9:18
we'll say okay well one comma zero and
9:21
zero comma one how do they compare
9:24
well in this case one is greater than
9:27
zero but zero is less than one so they
9:30
must be concurrent
9:32
and if they are concurrent that means
9:35
that this is a right conflict and so if
9:37
it's a right conflict what can we do
9:39
well we can actually store both rights
9:42
in our database that's known as storing
9:44
the siblings so an example of a database
9:47
right here now would be the key is
9:48
Jordan but the value is either cute and
9:51
or scary I know on both things and so
9:54
one way of actually kind of resolving
9:56
this conflict is the next time that
9:58
anyone makes a read from our databases
10:01
once they kind of combine and have both
10:03
values
10:04
is you can actually offer the user a
10:07
choice say hey wait a second we see in
10:09
the database that you know there are two
10:11
different values so do you choose cute
10:13
or scary and then once that value is
10:15
chosen we can now delete one of them and
10:18
now we've resolved our merge conflict so
10:20
that's one way of doing things to
10:21
actually use the application layer and
10:24
the user in order to manually resolve
10:25
merge conflicts another one is actually
Option 2 Merge automatically
10:28
to have the database do it automatically
10:31
so this is kind of the premise behind
10:33
something known as crdts or
10:35
conflict-free replicated data types so
10:38
the premise here is that by effectively
10:40
detecting concurrent rights we can
10:42
figure out a smart way to merge them and
10:44
so there are a few different types of
10:45
data structures that we can build where
10:48
we can actually basically make them
10:50
write conflict resistant one example
10:52
would be a counter which is effectively
10:54
the same thing as a version Vector right
10:56
we saw the counter earlier in this video
10:58
you can build a counter that is
11:00
conflict-free because all you have to do
11:02
is go ahead and merge those version
11:04
vectors and now we have a counter
11:06
similarly you can do something like that
11:08
with a set and possibly even more
11:11
complicated data types I'm going to
11:13
leave this concept until next video but
11:15
so far at least I hope all of this has
11:17
made sense we've got one more tough one
11:19
with the crdts and then we're going to
11:21
go into leaderless replication

##v21:

0:00
gentlemen and ladies about three percent
0:02
of you welcome back to the channel
0:04
today's video is going to be pretty long
0:06
because it's on crdts which is a
0:08
complicated topic and frankly according
0:10
to my video analytics most of you tend
0:12
to only last about three minutes that
0:15
being said that's pretty good because I
0:16
typically tend to only last about one
0:18
minute so without further Ado let's get
0:20
into this video and get it done alright
0:22
so let's get started the iPad is out so
0:24
to remind everyone what was happening
0:26
last video basically we know that in
0:29
multi-leader replication we are prone to
0:31
write conflicts so I want to write
0:33
conflict inevitably happens what can we
0:34
do well we have three options the first
0:37
one is last right wins AKA lww which I'm
0:42
going to write right here
0:44
last rate wins is not really very
0:46
reliable because we can't really trust
0:47
time stamps in distributed systems
0:49
because they can get out of sync with
0:51
one another and jump around due to ntp
0:53
additionally a second option is we can
0:56
detect concurrent rights via something
0:58
like a version Vector which allows us to
1:00
see when two rights knew about one
1:01
another or did not and then we can go
1:03
ahead and store both rights in the
1:05
database known as storing siblings we
1:07
can eventually then have the user merge
1:09
them down the line
1:10
a third option is to actually have the
1:13
database merge them automatically so my
1:15
pen keeps not working here and that is
1:17
known as a crdt or of course a
1:20
conflict-free replicated data type so
1:23
what is actually the meaning of these
1:25
things well what is a crdt let's imagine
1:28
that we've got two liters over here on
1:30
our left and we're trying to build a
1:31
shopping list and we've got basically
1:33
two sets of items so on the left we've
1:36
got one guy who's written now uh ham and
1:38
eggs and on the right we've got a second
1:41
guy who's making conflicting rights
1:43
saying milk and cookies and what we want
1:46
is for these two sets to eventually
1:48
converge right we want both leaders to
1:50
agree on the value of the shopping cart
1:52
so ideally what we would want is
1:54
eventually both of those leaders are
1:56
going to agree that ham eggs milk and
1:58
cookies are what's actually in the set
2:00
that is the ideal scenario here so how
2:03
can we actually go about doing this well
2:05
that's going to come up in a bit but
2:06
let's first quickly in response to a
2:09
comment left by one of my viewers talk
2:10
about where crdts can actually be used
2:12
well some databases that we might see
2:15
them are ryak which is a multi-leader
2:18
leaderless distributed key value store
2:20
I'll talk about that more in a future
2:21
video and the second one is redis which
2:24
is a completely in-memory database often
2:26
used for caching in their Enterprise
2:28
version they use crdts for sets redis
2:31
again is something I will talk about in
2:33
a future video
2:35
so let's talk about two possible
2:37
implementations of crdts before I talk
2:39
about specific data structures that we
2:41
can Implement with them so let's recall
2:43
from last video the concept of a
2:46
distributed counter we're going to use
2:48
the distributed counter here to
2:49
demonstrate what an operational crdt is
2:52
so remember that we can demonstrate kind
2:55
of a distributed eventually consistent
2:57
counter by this list right here which is
3:00
basically a version Vector but the point
3:02
is every single element of the list
3:04
indicates how many increments we've seen
3:06
from each leader so there's two
3:08
delegates that we've seen two increments
3:10
from the first leader the one delegates
3:12
that we've seen one increment from the
3:13
second leader and then the zero says
3:16
that we've seen no increments from the
3:17
third leader now obviously each of these
3:19
leaders is going to keep their own
3:21
version Vector so that they can keep
3:22
track of their local state of how many
3:24
increments that they've seen and have
3:26
been set that way the counter is
3:28
actually just the sum of the elements in
3:30
the list so in the case of an
3:32
operational crdt what we're actually
3:34
doing is instead of sending this whole
3:36
list from one node to another in our
3:38
replication setup we're actually going
3:40
to send just an operation so in the case
3:42
of encounter there's only one operation
3:44
and that would be increment so for
3:46
example if this guy gets incremented and
3:48
this is said zeroth leader we might go
3:51
ahead and send Inc zero to the next
3:54
database and that's now going to change
3:56
its Vector to 3 comma 1 comma zero so
3:59
basically in this case again increment
4:01
just tells the database which index to
4:03
increment and the advantage of something
4:05
like an operational crdt is that you
4:08
don't actually have to send this full
4:09
Vector which grows linearly with respect
4:12
to the number of nodes but rather you
4:13
can just send one operation and this is
4:16
O of one in terms of space sent over the
4:19
network
4:24
it's a sent over Network because my
4:26
handwriting is terrible whenever I'm
4:28
rushed so what are the downsides of an
4:30
operational crdt because we said that as
4:32
opposed to sending the full Vector now
4:34
we get to send a lot less over the
4:36
network it's going to be a lot faster
4:37
well there is actually a pretty
4:40
significant downside which is that
4:42
whenever we have causal relationships
4:45
amongst our operations and operational
4:47
crdt could possibly let us down so let's
4:50
imagine that we have a set and we're
4:51
trying to implement that with a crdt
4:54
so in this case let's say on leader one
4:57
or database one I'll just write an L
4:58
here to indicate it's a leader and then
5:00
database two is also a leader on
5:02
database one we're going to first add
5:04
ham to our set then we're going to
5:06
remove hand from our set and then on
5:08
database 2 we're obviously going to be
5:10
propagating those operations so first it
5:12
receives the fact that we're adding ham
5:13
and then it's receiving the fact that
5:15
we're removing ham from our set
5:17
but what if I were to X this out right
5:20
here and in turn we never add him so
5:23
database 2 only gets that we're removing
5:25
him now it tries to remove ham from a
5:27
set that doesn't have ham in it and
5:29
we've got a problem it's going to throw
5:30
some sort of error and obviously that's
5:32
not acceptable the point is that these
5:34
two rights are causally related right
5:37
because you can only remove him if you
5:40
first added it so it's important
5:42
actually that if we have an operational
5:43
crdt we need a causally consistent
5:46
broadcasting system where messages do
5:49
not get dropped and they also don't get
5:51
duplicated because these operations are
5:53
not known as item potent item potent
5:56
meaning that here I'll write it here but
5:59
we'll see it later you can do the same
6:01
thing
6:03
many times over
6:07
and no difference
6:11
and I'm saying that these operations are
6:13
not item potent right if I send the
6:16
message add ham five times we're now
6:18
going to add five quantities worth of
6:20
ham so again this is not going to work
6:23
for us we need to make sure that in our
6:25
message delivery again we have no drops
6:28
and we have no duplicates so it's very
6:30
important for operational crdts
6:33
on the other hand we have our
6:34
state-based crdt and I was already
6:36
alluding to this before with sending the
6:39
whole kind of version vector or sending
6:41
the whole counter in a distributed
6:42
counter but that's what I'm
6:43
demonstrating here in this diagram so
6:45
let's say that this leader on the left
6:47
has a state of 5 comma four right it's
6:50
seen five increments to itself it's
6:52
seeing four increments from the Right
6:53
leader and it sends five four to the
6:56
second leader right because we're
6:57
sending the whole state of the crdt
6:59
instead of the operations
7:01
then in a state-based crdt as opposed to
7:04
just applying one operation to our local
7:06
crdt we call this merge function right
7:09
here and so on the Right leader we're
7:12
going to be merging our local crdt with
7:15
the incoming State base crdt and Via
7:19
this merge function we now have a new
7:21
result so after receiving 5 comma four
7:24
the right database merges and changes
7:27
itself to five comma six
7:30
so what do we actually have to know
7:31
about the merge function for something
7:33
like this to work well basically we know
7:36
that it needs to be commutative right
7:38
because if the basically we want the
7:41
same result whether the Right leader is
7:43
sending its results to the left leader
7:45
or the left descending its results to
7:47
the Right leader we also want it to be
7:49
associative again this just ensures that
7:52
no matter what order those State
7:53
messages are coming in we don't care and
7:56
we also again want it to be item potent
7:58
I just explained item potency before but
8:00
the point is if we receive the same
8:01
state multiple times over we're not
8:04
going to mess up our results right it
8:06
has no effect we just need to receive
8:08
that state once and we're good to go so
8:10
I have the the concrete mathematical
8:12
definitions down here you don't have to
8:13
focus too hard on those but if it helps
8:15
you understand what I mean when I say
8:17
these things that's good so the point of
8:19
this is if the merge function satisfies
8:21
all three of these things it means that
8:23
we don't actually have to care about
8:25
what order we receive these state-based
8:28
updates in unlike the Opera additional
8:30
updates which means we can just go ahead
8:32
and basically just fire out State base
8:34
updates all over the place and as long
8:36
as every single node gets them will be
8:38
eventually consistent so what does this
8:40
work really well with it works really
8:42
well with something called a gossip
8:44
protocol
8:45
so I haven't explained this yet in this
8:47
series but I did definitely explain it
8:48
in the past one basically the gist of
8:50
this is that it allows you to really
8:52
easily communicate with a bunch of nodes
8:54
in the cluster without any messaging
8:56
middleware how do we do this well
8:58
basically we pick one starting point so
9:00
let's imagine that this node had you
9:02
know its own counter base codt of one
9:05
comma two or something and it's now
9:07
going to pick say any two random nodes
9:09
in the cluster so it's got this guy here
9:11
and this guy here and now these two
9:12
nodes are considered infected so what
9:15
these two nodes are now going to do in
9:16
the next round of Gossip protocol is
9:18
also send its message to two more nodes
9:20
so as you can see now these guys are
9:22
infected and similarly
9:25
you know maybe it'll send it here it
9:27
doesn't matter if this guy receives the
9:29
message twice because remember it is
9:31
idem potent so receiving that message
9:34
twice is no big deal similarly you know
9:37
if we had another guy sending messages
9:39
because it has its own counter update to
9:41
send out it doesn't matter whether let's
9:44
call this message a and message B it
9:46
doesn't matter whether a gets there
9:48
before b or B gets there before a
9:50
because the merge function is
9:52
commutative so we're in great shape
9:54
either way we just need to make sure
9:56
that all those messages eventually get
9:58
passed around and then everything will
9:59
be eventually consistent so just to keep
10:01
demonstrating how this gossip protocol
10:03
is going to look this guy is infected
10:05
right here it's going to pick two random
10:06
nodes to pass messages to in the next
10:09
round all the newly infected nodes are
10:11
going to keep passing messages they're
10:12
going to keep passing messages they're
10:14
going to keep passing messages
10:16
and eventually what's going to happen is
10:19
all of these crdt State updates are
10:21
going to get propagated around the
10:23
system such that we are eventually
10:25
consistent and everyone agrees on the
10:27
state of our crdt
10:29
that's great so again even though state
10:32
crdts are good they are
10:35
effectively pretty hard to implement
10:37
sometimes if the amount of data in them
10:39
is pretty big right because at the end
10:41
of the day gossip protocols have no
10:44
guarantees on necessarily when uh that
10:47
update is going to get there obviously
10:49
it probably will because just randomly
10:51
speaking probabilistically speaking the
10:53
message is going to get to a node but it
10:55
could take a while with all those random
10:56
iterations to actually get the message
10:59
to the right note additionally State
11:01
crdts can just be big and so they can
11:03
take a lot longer to pass over the
11:05
network
11:06
so now that we've gone over operational
11:09
versus state-based crdts let's take a
11:11
look at a few different types of data
11:13
structures that we can Implement via a
11:15
crdt and use well in a multi-leader
11:18
replication setup okay so the first one
11:20
that we're going to talk about is
11:22
actually going to be a distributed
11:25
counter so I'm trying to zoom here so I
11:27
get this one right but you know not too
11:29
bad just don't don't focus on the bottom
11:31
part of the screen I'm sorry all right
11:33
so the first one is going to be a
11:34
counter we already covered this it's got
11:36
one operation where you can basically
11:38
just call increase so if we wanted to
11:39
implement this via an operation based
11:41
crdt the operation would be increase
11:43
where the parameter would just be which
11:45
leader it's coming from
11:47
similarly uh it would hold all of those
11:49
increases in a single vector and then to
11:52
basically get the count on a node just
11:54
do some of the increase Vector right
11:57
because this would be basically six
11:59
we've seen oh my God I can't do math
12:03
holy it's five three plus two wow
12:06
who would have thought
12:08
um next we've also got a decreasable
12:10
counter this one has two operations you
12:13
can obviously increase that counter or
12:15
decrease that counter and the way we
12:17
would implement this on every single
12:18
node is similarly the last time we would
12:20
have a list of increments but we would
12:22
also have a list of decrements basically
12:24
where each decrement is saying how many
12:26
decrements have we seen coming from
12:28
every single leader node so in this case
12:30
the sum is very simple it's literally
12:32
just going to be summing up the
12:34
increments list 0 plus 3 plus 2 and
12:37
subtracting the sum of the decrements
12:38
list zero plus one plus zero so in that
12:41
case it would be four
12:42
so that's simple enough but we can also
12:45
do a little bit more complicated things
12:47
so let's go ahead and build out some
12:50
sets I've kind of been implying we could
12:51
do this anyway so let's do it so the
12:54
operations on a set would be adding and
12:56
removing and the way we can easily
12:57
represent us at on every single node is
12:59
we basically have all of the elements
13:01
that we've inserted that's called the
13:03
ads and all of the elements that we've
13:05
deleted which we will in turn call the
13:08
the remote
13:09
and so to actually get the
13:12
representation of the set on an
13:13
individual node you take all of the
13:15
elements in the Hat in the ads so in
13:17
that case that would be ham eggs and
13:18
cheese and then you would get rid of
13:20
cheese because it's in the remove set so
13:22
this works really nicely because now for
13:24
our merge function all we actually have
13:26
to do is take the union of two ad sets
13:29
and the union of two remove sets and by
13:33
doing so we can easily basically have a
13:36
right conflict-free representation of a
13:38
set now if you think about this there
13:40
actually is one issue with this
13:42
representation which is that once an
13:44
element goes in the removes list so Chi
13:47
is right here it can never be re-added
13:49
back to the set because I've said that
13:51
the set is you're basically if cheese is
13:53
ever present in the ads you're always
13:54
getting rid of it because it's in the
13:56
remove set
13:57
so how can we do this where we're
13:59
basically able to add an element back
14:01
well one way that would be pretty cool
14:03
is you basically just pick a random tag
14:06
with every single addition to the set
14:08
that you do so now in your ad set we've
14:11
got a ham with an ad identifier of one
14:13
two three eggs with an ad identifier of
14:16
762 and let's say some other leader
14:19
wanted to add ham again now the add
14:21
identifier might be two four one on the
14:24
other hand let's now say that at the
14:26
time the set only had these elements
14:29
right here that someone went ahead and
14:32
said I want to remove
14:35
ham one two three
14:37
and so now ham123 goes in the removes
14:40
list but at the same time if another
14:42
leader basically went ahead and said
14:44
okay well I'm adding ham 241.
14:47
we know that ham 241 hasn't actually
14:50
been canceled out yet so our resulting
14:52
set is going to be these two guys right
14:54
here so now we have eggs
14:57
and ham so by virtue of having these
15:00
unique tags we have to basically uh you
15:03
know know about the right already in
15:05
order to cancel it out and additionally
15:07
it means that we can rewrite things back
15:09
into a set which is great because it
15:11
limits us quite a bit less so moving on
15:14
to the last topic of the video which
15:15
isn't really a topic but it's more so a
15:17
teaser for a future video the last thing
15:20
we're going to talk about is sequence
15:21
crdts so this is basically making a list
15:24
in a right conflict freeway and that's
15:27
going to be really really tough because
15:29
the issue with the list is that it
15:31
depends on an ordering of some elements
15:33
and if you don't know about the elements
15:35
beforehand when you're making that right
15:38
it's kind of hard to just go ahead and
15:39
make an arbitrary ordering over them so
15:42
sequence crdts are very tough in
15:44
practice to actually implement but some
15:46
people have made them really well
15:47
there's some really cool open source
15:49
versions of these and they actually
15:50
power a lot of the technology behind
15:52
real-time collaborative text editors
15:54
like Google Docs or I don't know I think
15:57
um vs code has some text editor I'm sure
15:59
there are plenty of others you can think
16:00
of but the point is I am eventually
16:03
going to dedicate a video to these alone
16:05
because not only do they come up in
16:07
interviews but they're just a pretty
16:08
cool Topic in general that one may come
16:10
up in a while since it's a little bit
16:12
less relevant to what we're talking
16:13
about right now but either way hope you
16:15
guys are looking forward to it well guys
16:18
hope you enjoyed the video I will see
16:19
you in the next one and uh hope everyone
16:22
got through this if you only lasted
16:24
three minutes you're like all the rest
16:26
of the men in the world so don't worry
16:27
about it

##v22:

0:00
hello guys and welcome back to the
0:02
channel as you can see I've got yet
0:04
another change of scenery in my
0:06
background here that's because I finally
0:08
moved into a place in Chicago which is
0:10
pretty sweet so no complaints there the
0:13
one thing is I am living alone for the
0:15
first time which means that I have a lot
0:17
more responsibility I'm also a lot more
0:19
likely to go completely insane and if I
0:21
do that would make these YouTube videos
0:23
a little bit more interesting so uh you
0:25
know in the best interest of all of us
0:27
let's see if that happens hopefully it
0:29
does but without further Ado let's start
0:31
talking about some replication I put you
0:33
guys in about a three week wild goose
0:34
chase to talk about crdts so let's get
0:37
back into it
0:39
all right so today we're going to get
0:40
started by talking about leaderless
0:42
replication so the gist of leaderless
0:44
replication is pretty simple and you can
0:46
see it right down here but basically now
0:48
instead of just writing to one node
0:50
which we've always done in the past
0:52
we're actually going to write to a bunch
0:54
of different nodes so that's chaos we're
0:56
going to be doing it even at the same
0:57
time and to make matters even worse
0:59
we're also going to be reading from a
1:00
ton of notes so everything that we know
1:02
so far throw it right out the window
1:04
because things are about to get real
1:06
so let's move on where do we actually
1:09
use leaderless replication again I'm
1:11
going to try and make an emphasis on
1:12
actually pointing out some systems that
1:14
do these things so you know you can
1:16
contextualize these videos a little bit
1:17
uh this is definitely used in Cassandra
1:20
that's probably the most popular One
1:21
open source database ryak is another
1:24
open source database very similar to
1:26
Cassandra and then you may happen to
1:28
think that this is used in dynamodb
1:30
which many people seem to say online
1:32
however they would be incorrect because
1:35
actually this type of leaderless
1:37
replication was originally invented in
1:39
the open source Amazon Dynamo paper but
1:42
dynamodb as far as I can tell seems to
1:45
use single leader replication it's kind
1:46
of unclear I would not say that dynamodb
1:49
uses leaderless for application if it
1:51
were to come up in an interview
1:53
okay so let's move on how does this
1:55
thing actually work so here's a very
1:57
realistic scenario we've got Kate Upton
2:00
as per usual on the left over here and
2:03
she is going to write that Jordan is
2:05
cute to a few different databases so
2:07
let's say that she writes it to two of
2:09
them so as you can see we have three
2:11
different databases each of them with
2:13
basically some sort of snapshot
2:15
versioning we've spoken about this in
2:16
the past but let's imagine that the
2:18
Jordan key has a version so originally
2:20
it starts out as version 20 on all three
2:22
of these databases and then the two that
2:24
get the right which are this guy and
2:26
this guy are now updating version 21 to
2:29
Jordan equal to Q then of course Jordan
2:32
is going to read those values from these
2:34
two databases and he's going to see the
2:36
following version 21 of Jordan equals Q
2:39
version 20 of Jordan equals ugly so
2:42
technically we have two conflicting
2:44
values here of the Jordan key but keep
2:47
in mind that that's what these versions
2:48
are for right because we know that 21 is
2:51
greater than 20.
2:52
we know that the actual most up-to-date
2:55
value is that Jordan is equal to Q
2:58
and another actually cool thing that you
3:00
can do in this leaderless replication is
3:03
me being Jordan can see that you know
3:06
this guy this database over here
3:07
database number three has an outdated
3:09
value for Jordan and so he's actually
3:12
going to write back saying hey for
3:15
version number 21 we know that Jordan is
3:18
actually equal to Q so then this guy
3:20
over here is going to basically update
3:23
its value and say oh you know what I
3:25
just got a new update it turns out
3:27
Jordan is actually cute
3:29
and the process of actually taking a
3:31
database with a stale value and updating
3:33
it after performing a read is known as
3:36
read repair so this is important to know
3:39
and the reason that's useful is because
3:41
it is one of the basically two main ways
3:43
that we can make sure that our data
3:46
values are up to date so let's take a
3:48
look at the other way of ensuring that
3:49
our values are up to date so this one is
3:52
called anti-entropy
3:54
so the gist here is we've got these two
3:57
leader databases or just in general
3:59
databases because there isn't really a
4:01
leader in this setup and the list of
4:04
letters below are the rights that
4:05
they've processed so this guy on the
4:07
left is processed a c e f g and on the
4:10
right he's processed b c d f and g so
4:14
let's imagine then that basically the
4:16
left database wants to replicate all of
4:19
those changes to the database on the
4:20
right so that they have at least similar
4:23
data right so typically in a single
4:26
leader or a multi-leader setup we would
4:28
use the replication log right and that's
4:30
just going to be one long list of all
4:32
the rights that have happened on that
4:33
node and you're passing each right one
4:35
at a time over the network from one
4:37
database to the other however in this
4:40
case it doesn't really make sense to do
4:41
that the reasoning being that this
4:43
database over here on the right is
4:45
probably already going to have a lot of
4:48
the information that is contained on the
4:49
left because of the fact that rights go
4:51
to multiple places so we don't actually
4:54
want to send every write that might be
4:55
in a replication log but we actually
4:57
only want to send select rights that are
5:00
present on the Node on the left but not
5:02
present on the Node on the right so
5:04
that's the whole point over here we only
5:05
want to send rights A and E
5:08
so how can we actually quickly tell
5:10
which rights to send well the easiest
5:12
way would be to literally scan through
5:14
all of the values and rights present on
5:16
the left node that are not present in
5:18
the right node however there are a
5:20
couple of issues with that the first one
5:22
being that these are large tables and
5:25
when you have large tables in order to
5:27
perform a scan over them that is linear
5:29
time complexity it takes a while to
5:31
perform and additionally it might have
5:33
to be a ton of data that we're sending
5:35
over the network to basically have those
5:37
two databases confirm with one another
5:38
that you know one has certain rows and
5:41
the other doesn't so what can we do
5:43
instead that's better well it's time to
5:45
introduce a concept known as the Markle
5:47
tree so I've spoken about this in the
5:49
past on my channel but for the new
5:51
series obviously we're going to
5:52
reintroduce it so here's how a Merkle
5:55
tree would work so let's imagine we have
5:57
a database that looks like this right
5:59
here so we've got four rows and
6:01
basically it's a key value pair of a
6:03
equals 10 B is 45 C is 63 and D is seven
6:08
so I'll explain how these Miracle trees
6:10
work in a little bit but the general
6:11
gist is that you want to use them to
6:14
tell how to database tables differ
6:16
really quickly and efficiently so let's
6:19
create the Merkle tree for our database
6:21
table right here so the first thing that
6:23
we're going to do this is Step One is we
6:25
take the hash of each row so let's
6:26
imagine that our hash function generates
6:28
output from zero to a thousand and these
6:32
numbers right here the four outputs that
6:34
we get from hashing
6:35
then from there we're going to take all
6:37
pairs of hashes we're going to sum them
6:40
up and then we're also going to take
6:42
hashes of those so in this case 762 plus
6:45
127 is 889 hence why we're taking the
6:49
hash of 889 and we do the sum again and
6:51
we take the hash of 1339. so now finally
6:55
we have 574 and 626 and then we're going
6:58
to do that same step one more time until
7:00
we get to one root node right so we take
7:02
these two we sum them up conveniently
7:04
they sum up to 1200 we take the hash of
7:07
them and let's imagine that spits out
7:08
213 which leads us to our final result
7:11
over here on the right so 213 is going
7:14
to be our root note of the Merkle tree
7:16
with two children as 574 626 and then of
7:20
course we're going to have our Leaf
7:21
nodes which are 762 127 901 and 438
7:28
so let's scroll down a little bit more
7:29
because we've seen how to create a
7:31
Merkel tree but how can they actually be
7:33
useful for us so let's imagine now that
7:35
we have two database tables right we've
7:37
got uh all four rows again we've got a b
7:40
c and d and the only difference between
7:42
the two of them is that as you can see
7:44
here B is equal to six and on the right
7:47
B is equal to nine so what can we use
7:50
these Miracle trees to do well let's say
7:52
we took a look at these two trees and we
7:54
said all right where are these databases
7:56
different just using the Merkle trees so
7:58
we'll start by looking at the root nodes
7:59
between them we've got 305 and 642.
8:03
those two are not equal so clearly
8:05
there's got to be a difference somewhere
8:07
in this Merkle tree right the next thing
8:09
we would do is start with the children
8:11
let's do a breadth first search for now
8:13
so we'll take a look at 119 and we'll
8:16
say 119 is different than 505 so we know
8:20
eventually we'll have to keep going down
8:21
this path similarly or actually in this
8:24
case differently
8:25
463 is equal to 463 on the right so we
8:30
actually don't have to care about any of
8:32
these entries over here because we know
8:34
that everything under 463 is highly
8:37
likely to be the same we don't have to
8:39
take a look at those or worry about it
8:41
all we have to do is inspect the left
8:43
half of this tree right now
8:45
so now moving on down our tree we can
8:48
see that 746 is equal to 746 so we've
8:52
got no issues there like I said a is 10
8:55
in both trees but then finally because
8:57
821 is different than 314 we found our
9:02
difference between the two trees it's
9:03
just the fact that b is equal to 9 first
9:06
B is equal to 6 and now if these were
9:08
two databases for example we could send
9:10
the facts that b is equal to 6 to this
9:12
guy over the network we're only sending
9:14
one row instead of the whole table so
9:16
it's much more efficient and then it can
9:18
change its value and say oh shoot B is
9:20
equal to 6. the really nice thing about
9:22
this again is instead of having to do a
9:23
linear scan over the whole table and
9:26
figure out where they're different this
9:27
is an O of log n why because we're
9:30
creating a binary tree and binary trees
9:33
are basically continuing to split the
9:35
table into two over and over and over
9:36
again and that gives us logarithmic time
9:38
complexity so for now basically that is
9:41
going to be the introductory video for
9:44
leaderless replication but next next
9:46
time around we are going to get into a
9:48
very very important concept which we
9:50
didn't touch upon too much just yet and
9:52
so the point there is that so far we've
9:55
seen how rights will go from one
9:57
database to another in the cluster but
9:59
what we haven't seen is how we can
10:01
actually guarantee that if I'm a guy on
10:04
the left here and I'm writing to a few
10:06
nodes how do I know that my guy on the
10:08
right is going to see that right away
10:10
because right now the guy on the right
10:12
has to wait for something like
10:14
anti-entropy he could in theory do some
10:17
read repair but if he were doing read
10:19
repair that would be reliant on the fact
10:21
that one of these two nodes that he's
10:22
reading from is going to be one of the
10:24
three that gets written to so read
10:26
repair isn't actually going to work for
10:28
us here you have to wait for some
10:30
unclear amount of time for anti-entropy
10:32
to happen and sometimes that's not good
10:34
enough so in theory there is a way that
10:37
we can actually guarantee that this guy
10:38
on the right is going to make sure that
10:40
he sees all of the rights made by the
10:43
guy on the left and that is going to be
10:44
the topic for next video anyways guys
10:47
have a good one I'll see you in the next
10:48
one and I'm looking forward to it

##v23:

0:00
Hello everybody and welcome back. It is
0:03
yet another horrible day in Chicago with
0:06
40°ree weather in May. Fortunately, I've
0:08
loaded up on so I'm good to stay in all
0:10
day and do absolutely nothing. Anyways,
0:12
let's make some systems design videos.
0:14
I'm going to get out the iPad and we can
0:16
get started by talking about leaderless
0:17
replication. All right, so let's get
Leaderless Replication
0:19
back into it. I've got leaderless
0:21
replication up on the iPad and let's
0:23
talk about it. So for starters,
0:25
basically the gist is if you recall
0:27
leader list replication is when you have
0:29
one guy on the left over here. He can
0:31
write to multiple database nodes. So as
0:32
you can see he's writing to two of them.
0:34
I got this guy over here and this guy
0:36
over here. And then a different reader
0:38
can read from any arbitrary number of
0:40
database nodes. So in that case he's
0:42
going to read from this guy again and
0:43
also the one on the top. When he does a
0:46
read such as that, he might notice that
0:48
this guy on the top was not written to.
0:50
So what he can actually do is perform a
0:52
read repair in order to update it with
0:55
proper data and also in addition to that
0:57
just over time uh you know kind of as
1:00
time flies the databases will actually
1:02
communicate amongst themselves in order
1:04
to pass information and make sure that
1:06
reads aren't too stale that is known as
1:08
anti-entropy. As you can see we've got a
1:11
Merkel tree located over here to
1:13
indicate how these databases actually
1:14
compare their state and to see the
1:16
discrepancies between them. So, we've
1:18
gone ahead and done our kind of review.
1:21
Let's move on to the new content for
Quorums
1:23
today. So, the new content that we're
1:25
going to be talking about is quorums.
1:26
So, I teased last time that basically
1:28
there's a way that you can write in a
1:30
leader list replication schema and then
1:32
somebody else is actually going to
1:34
instantly be able to read that instead
1:35
of having to rely on read repair and a
1:38
bunch of anti- entropy in order to
1:39
propagate those changes around. So, what
1:42
is a quorum read and a quorum write?
1:45
Well, let's start out with a
1:46
hypothetical situation. In this case,
1:48
there are nodes in the cluster. So,
1:50
let's call this variable n equal to
1:52
five. And uh that's you can see there
1:55
are basically five database nodes. Okay.
1:57
So, our writer on the left over here is
1:59
going to perform writes to three of
2:01
them. So, as you can see, we've got a
2:03
right here, a right here, and a right
2:06
here. And let's call that number of
2:08
nodes that we have to write to W. In
2:10
this case, W is basically saying, okay,
2:13
as a client, once I get three
2:15
confirmations from database nodes that
2:17
they've received my right, I will
2:19
consider my write successful. Okay, so
2:21
it's basically just waiting on three
2:22
successful writes to be like, okay, I'm
2:24
good. My right is in the system.
2:26
Similarly, we've got another guy over
2:28
here on the right side of the screen. He
2:30
wants to read from R nodes. So, let's
2:33
say that R is equal to three, right?
2:34
He's going to try to read from three
2:36
different database nodes. So, let's say
2:38
he picks these two as the first, right?
2:41
Oh, no. That's not very good because
2:43
they don't have the updated value. How
2:44
is he going to see the guy on the left's
2:46
updated value? Well, now he has to pick
2:49
one more node. And all three nodes that
2:51
he has to choose from have already been
2:53
written to. So, in this case, regardless
2:56
of which one he actually picks, you
2:58
know, he's going to be reading from at
2:59
least one node with the most updated
3:02
value that was just written by the guy
3:03
on the left. So, why does this actually
3:06
work? or rather when does this actually
3:08
work? We recall that n is the number of
3:11
nodes in the cluster. W is the number of
3:13
nodes that we'll write to and r is the
3:15
number of nodes that we'll read from.
3:17
When w + r is greater than n, we have
3:21
what's known as a quorum read and a
3:24
quorum write. In that quorum read and
3:26
quorum write, we know that the two sets
3:28
of nodes that are both written to and
3:30
read from will have at least one node in
3:32
overlap. Why? Because of this phrase
3:34
right here. It's simple math. Because of
3:36
the fact that W plus R is greater than
3:38
N, there needs to be at least one node
3:40
overlapping between W and R. Hence, we
3:43
can always see the most update date
3:45
value at least once and we'll have a
3:47
correct read. But let's move onwards.
Consistency
3:51
So the question now and you might have
3:54
been thinking this is hey wait a second
3:56
with quorum writes didn't we just
3:57
achieve strong consistency and to remind
4:00
you all what strong consistency is it
4:02
basically means that everyone who's
4:03
reading from our database pretty much
4:05
any node or any type of read is going to
4:08
return the most up-to-date value
4:11
everyone's going to agree on what that
4:12
value is right so regardless of which
4:15
nodes I read from as long as I have a
4:17
quorum of nodes that I'm reading from
4:19
aka at least our successful reads, then
4:22
I should in theory see the most
4:24
up-to-date value in our database. So, is
4:26
this actually the case here? And it
4:28
turns out that even though it seems that
4:29
way at first, it's actually not. So, I'm
4:32
going to give a few examples of where
4:34
kind of quorum writes as potentially
4:36
strongly consistent databases fall
4:38
apart. So, the first one is actually
4:41
going to be a race condition. Imagine
4:43
we've got three databases and at the
4:45
same time three people writing. So the
4:48
first guy is going to write to the first
4:50
database and actually all three people
4:52
are going to write to all three
4:54
databases. But due to the rate condition
4:56
that is present when you send out a
4:58
bunch of writes, those rights are going
5:00
to come in in a different order. So you
5:02
can see that you know we've got version
5:04
one over here. These are the earliest
5:06
rights to arrive at the database. And
5:08
then version three, these are the latest
5:09
rights to arrive at the database. And so
5:11
what ends up happening is due to this
5:13
race condition, all three databases
5:16
actually disagree on which write has the
5:19
latest version number. And that's a
5:20
problem. Why? Because now if I'm a guy
5:23
over here and I'm trying to read from
5:25
these three databases, right? Let's
5:28
imagine that I have to choose two of
5:29
them. Let's say we use two and two as
5:31
our quorum. So the number of nodes that
5:33
we have to read to guarantee that we
5:35
have a quorum read is two. This guy is
5:37
going to choose from database 2 and
5:39
database 3. And so all he knows now is
5:42
that W1 or W2 is the answer. And that's
5:46
not even conclusive. But if I were
5:48
another guy over here and I also did a
5:50
quorum read to database 1 and database
5:53
2, I would have a completely different
5:55
result. And so even though these two
5:57
guys are reading at the same exact time,
5:59
they are not getting the same answer.
6:01
And that is obviously a problem. In
6:03
fact, the database isn't even conclusive
6:05
because a majority of the nodes don't
6:07
agree on what the value is. So obviously
6:10
leaderless replication even with quorum
6:12
rights is still prone to write
6:14
conflicts.
When rights fail
6:16
Let's move onwards to another case which
6:18
is actually just going to be when writes
6:20
fail. So let's say again we have a three
6:22
node setup. So in this case n is equal
6:25
to 3, w is equal to 2 and r is equal to
6:29
2. So 2 + 2 is greater than 3. So that's
6:32
how we know we have a successful quorum.
6:34
So this guy on the left is going to now
6:36
write to two nodes. He attempts to write
6:39
two nodes and one of them succeeds over
6:41
here on the top and the other is going
6:43
to fail. So let's say beforehand all
6:46
three databases in the cluster agreed
6:48
that this value x was equal to 6 and
6:50
this guy over here was trying to write
6:52
that x is equal to 10 and he succeeds on
6:54
just one node. Now the problem is that
6:57
when this guy over here on our right
6:59
tries to read, not only does he see the
7:02
fact that x equals 10, even though this
7:04
write technically wasn't valid, why was
7:06
the right not valid? because it didn't
7:08
successfully get to two nodes. It only
7:10
got to one node, but it never got
7:12
overturned. So, that's a big problem.
7:14
And the reason this is a problem is
7:15
because this guy here thinks that the
7:17
value is x= 10. But if I have another
7:19
guy over here, and he reads from these
7:23
bottom two nodes, he is going to think
7:25
the value is x= 6. So, it's possible for
7:29
two people who are reading from our
7:30
cluster to actually disagree on the
7:32
value. Hence, our quorums are not
7:34
strongly consistent. If there were a way
7:37
somehow for us to roll back this right
7:39
and say okay well it didn't succeed
7:41
everywhere so x clearly is not equal to
7:43
10 then of course we would be strongly
7:45
consistent but that problem and ability
7:47
to be able to roll back is of course not
7:49
guaranteed. It would require this guy
7:51
sending another network request to the
7:53
top database node which is not
7:55
guaranteed to get there. It could fail
Sloppy quorum
7:57
too. And then one final case that is
8:00
worth mentioning is something known as
8:02
sloppy quorums. So the gist of sloppy
8:04
quorums is that often times people have
8:06
different database clusters, right? So
8:08
for example, if you have one in America
8:10
for your North American users and then
8:11
you have one in APAC for Asian and
8:14
Australian users. Basically the gist
8:16
here is that you know sometimes one
8:18
cluster in a geographical region can
8:20
just go down for a variety of reasons.
8:22
So you can see that's happened with
8:24
cluster one. And now as a result what a
8:27
smart system might do that's actually
8:28
resilient is they start routing a rights
8:30
from an American user to the APAC
8:33
cluster. And so these are still actually
8:35
going to be quorum rights because as you
8:37
can see n is equal to three
8:40
and w is going to be equal to two. So
8:43
we're still writing to two nodes and
8:44
those are going through successfully.
8:46
But let's say all of a sudden that
8:48
cluster one actually comes back up. You
8:50
know someone plugs the data center back
8:52
in. Everything's good to go. And now
8:54
this guy reads from cluster one because
8:56
that's where his rights are actually
8:58
being sent. So these are reads right
8:59
here. He is not going to see the rights
9:02
that he made before because they're in
9:03
cluster 2. And so that is kind of the
9:06
concept of a sloppy quorum. And the gist
9:08
here is that for this situation to kind
9:10
of fix itself, what we need to do is
9:12
actually take the data from cluster 2
9:14
and transfer it back over to cluster
9:17
one. That is known as a hinted handoff.
9:22
And so if we perform that now we're in
9:24
good shape again. But again it's not
9:25
strongly consistent simply due to the
9:28
fact that I can just read that left
9:30
quorum after I make quorum rights and
9:32
now we're still not good to go. Okay. So
Conclusion
9:35
basically in conclusion quorums are
9:38
really useful right the majority of the
9:40
time they are actually going to result
9:42
in behavior that kind of resembles
9:44
strong consistency. However strong
9:46
consistency is not truly strong
9:48
consistency unless there are no edge
9:50
cases. Unless you know with 100%
9:52
certainty and like mathematical
9:54
guarantees pretty much that if you're
9:56
reading data at the same time as someone
9:58
else, you're both going to agree on the
10:00
value that you're getting. So basically
10:02
leaderless setups can be really really
10:05
good for kind of these let's say
10:08
relatively chill client side
10:09
applications. Something like a social
10:11
media app where it's not the end of the
10:12
world if some data gets lost. However,
10:14
if we're really talking about protected
10:16
data that it's super sensitive and you
10:18
know if it goes missing, we're in a lot
10:20
of trouble, then maybe quorums aren't
10:22
the best thing for you. If everyone
10:23
needs to be able to agree on what the
10:25
current value of the data is, then
10:28
leaderless replication setups probably
10:30
are not the move. In fact, single liter
10:33
nor multiler setups are the move either
10:35
for us to really discuss what the right
10:37
thing is there. We're going to have to
10:38
wait a few more videos, but it's going
10:40
to take distributed consensus. So guys,
10:43
I hope you enjoyed this video. I am now
10:45
going to wait out the cold in my room
10:47
alone. And have a good night.

##v24:

0:00
what's up fellas Mark cockerbeard here
0:02
master of Jiu Jitsu back for another
0:04
video today we are going to be
0:06
summarizing up replication in hopefully
0:09
10 minutes or less so I can make a nice
0:10
little title and click bait you guys so
0:12
let's go ahead and get into it because I
0:14
am wasting time already the iPad is out
0:17
I'm ready to go someone in my comments
0:19
recently asked me if I could make this
0:21
video and guess what I was already
0:22
planning on doing it anyway so I asked
0:24
them if they wanted to make out still
0:26
haven't heard back yet let's see how
0:27
that goes for me so anyways let's
0:29
conclude replication what is the point
0:31
of replication well if we go here over
0:33
to the draw Tab and I get out my little
0:34
marker the point is now that instead of
0:36
having one database we have a bunch of
0:39
them right we are no longer just reading
0:41
or writing to necessarily one place but
0:44
we could be potentially reading from
0:45
many places we could potentially be
0:46
writing too many places so what does
0:49
this afford US firstly and most
0:51
importantly it affords us durability if
0:53
I go ahead and nuke this data center
0:55
right here we've still gotten many other
0:57
databases left to read from and write to
0:59
so of course we also have throughput
1:01
instead of just having to write to one
1:03
place if I have many clients who are all
1:06
writing to the same database node guess
1:08
what the next thing they can do is start
1:10
writing to different database nodes and
1:13
what that means
1:14
is that you've spread out the throughput
1:15
you can effectively make your whole
1:17
system faster and perform more rights
1:19
without giving users a hard time and
1:22
lastly of course this is really good if
1:23
you have a geography of many users you
1:26
know we've got some Indian guys some
1:28
Australian guys and they can all write
1:30
to their own special Data Center and so
1:32
of course that is going to speed things
1:34
up as well so let's move on to some
Single Leader Replication
1:36
types of single leader replication that
1:38
we covered the pros and cons of them and
1:40
then we're going to conclude this thing
1:41
so first off we have single leader
1:43
replication so the point is here that of
1:45
course we've got a master and the rest
1:47
of them are going to be followers slaves
1:50
whatever you want to call it this guy
1:51
could also be a leader because it's
1:53
2023.
1:55
um so the point is All rights go to that
1:58
master all reads can come from any of
2:00
the nodes and typically this will be
2:02
eventually consistent if it isn't
2:03
eventually consistent it means that
2:06
pretty much you're writing to all of the
2:07
nodes at the same time before a write
2:09
technically goes through and that will
2:11
take forever so it's very impractical
2:13
this is probably eventually consistent
2:15
so what are the pros and cons of this
2:17
type of setup well the biggest Pro of
2:19
course is that there's no red conflicts
2:20
because you're only writing to one
2:22
single leader on the other hand when you
2:25
only write to one leader it means that
2:27
you now have a single point of failure
2:29
in your system AKA The Leader a follower
2:32
can go down and you know whatever you
2:34
can just set up another follower and and
2:35
start sending rights to it but at the
2:37
same time if your leader goes down then
2:39
you're really in trouble because who do
2:41
you write to you can designate one of
2:43
the followers to become a leader but now
2:45
you're running the risk of something
2:46
like split brain where you're writing to
2:47
multiple places at the same time there
2:50
are certain distributed consensus
2:51
mechanisms that do solve this problem
2:53
but that is a topic for a subsequent
2:55
video and of course in addition to that
2:57
by virtue of also having one single
2:59
leader we have low right throughput in
3:02
general if we're all writing to the same
3:04
node it means that all the rights have
3:05
to go through one single bottleneck
Multi Leader Replication
3:07
let's go ahead now and move on to
3:10
multi-leader replication so you've got
3:11
my beautifully drawn picture over here
3:13
of a bunch of nodes in Harmony and
3:15
basically the point is they're all
3:17
sending rights to and from one another
3:18
it's complete chaos the beauty of that
3:21
is if I have many people writing they
3:23
can write to any single one of these
3:25
nodes and they can also read from any
3:27
single one of these nodes so what does
3:29
that mean it means that we have high
3:30
right throughput this is a really really
3:32
useful setup if we have many users in
3:34
many different Geographic areas because
3:36
now we can each write to our own Data
3:38
Center
3:39
at the same time we also now have to
3:41
deal with right conflicts so I made a
3:43
whole video devoted to write conflicts
3:45
and why they suck and how they're hard
3:46
to deal with the point is you can't just
3:48
use a timestamp to decide which right
3:49
was later because clocks are bad they're
3:52
unreliable
3:54
and there's clock drift so again they're
3:57
not that useful what can you do instead
3:58
you could use something like version
4:00
vectors
4:01
in order to detect whenever we have a
4:04
concurrent right and whenever we have a
4:05
concurrent right we basically have two
4:07
options one option is to store both of
4:09
those concurrent rights which is known
4:11
as storing siblings
4:13
and then eventually some other user can
4:15
come along and basically check those out
4:18
and say okay here's the one that this
4:20
value should actually be and the other
4:22
option is to use something like a crdt
4:24
where a crdt effectively is the database
4:27
merging those rights for you obviously
4:30
this doesn't work in every situation but
4:31
there are some data structures that you
4:33
can easily represent with the crdt like
4:35
a counter or a set or things like that
Leaderless Replication
4:38
and then of course finally we have the
4:40
most cracked of all of these leaderless
4:42
replication so in a leaderless
4:44
replication instead of just writing to
4:46
one node at a time we can write to many
4:48
nodes at a time and the main thing to
4:50
know about leaderless replication is the
4:52
concept of a quorum so in this case I've
4:54
got three database nodes so that means
4:57
that n is going to be three and now if
5:00
every single time that I write to my
5:02
setup I'm able to write to two nodes and
5:04
every single time that I oh my God what
5:06
was I writing there and every single
5:08
time that I read from my setup I'm going
5:10
to read from two nodes it means that
5:13
we're guaranteed to see at least one
5:15
node with the most up-to-date right
5:17
every single time that we perform a
5:19
write and a read right because if I
5:21
write two nodes and then I read from two
5:24
nodes we're going to have at least one
5:25
node in overlap and then this guy over
5:28
here can pick the right with the highest
5:30
version number
5:35
and so by picking the right with the
5:37
highest version number for a given key
5:39
you know he might see Jordan is a 10 out
5:43
of 10 on one with a version number of
5:46
you know let's say 26 and then Jordan
5:48
might also be from the other node uh six
5:51
out of ten
5:53
oh I stopped writing for some reason a
5:55
six out of 10 with a version number of
5:57
25 it means that the one where I'm a 10
6:01
out of 10 wins because that's version
6:02
number 26. so that is kind of the gist
6:04
between leaderless replication and in
6:07
the background these things stay
6:08
consistent with one another via read
6:10
repair which is basically the most up to
6:13
database the most up-to-date database
6:16
correcting the other databases and then
6:18
there's also anti-entropy
6:21
in the background and that's basically
6:23
the database sending each other their
6:25
changes oftentimes through a data
6:27
structure like Merkle trees and that's
6:28
just a process that happens
6:30
asynchronously in the background so what
6:32
are the pros and cons of a setup like
6:34
this well the main Pros are that we have
6:36
relatively high ride throughput why is
6:39
that even though we have to write to
6:40
many nodes at once which obviously is
6:42
going to bottleneck us it would be a lot
6:44
quicker if we could just write to one
6:45
and say okay we're good
6:47
it is the case that we now get to write
6:50
to many nodes instead of just one place
6:52
and so instead of having one single
6:54
bottleneck we can distribute these
6:56
rights amongst many nodes and we're in
6:58
better shape for doing those so probably
7:00
a lower right throughput than something
7:02
like a multi-liter replication but a
7:05
higher right throughput than single
7:07
leader replication at least in theory
7:09
and then of course we also have Quorum
7:11
reads and writes so that's what I
7:13
mentioned which is that we can almost
7:15
guarantee the correctness of our system
7:16
when we use quorums where basically the
7:19
number of nodes that you write to and
7:21
read from have to be greater than the
7:23
number of total nodes in your system
7:25
then on the other hand we also have low
7:27
read throughput why is that well for
7:30
starters you're now reading from a bunch
7:32
of different places so if you have to
7:34
read from say five different places
7:35
instead of reading from one different
7:37
place it's going to take a lot longer to
7:39
ensure that you are going to get all of
7:41
that data you can read in parallel but
7:43
it's likely that one of those nodes
7:44
might be a little bit slow and then
7:46
that's going to slow things down
7:48
Additionally you also still have to deal
7:50
with right conflicts it's very very
7:52
possible that you know I could be
7:54
writing here writing to the same exact
7:56
nodes as this first guy and it's the
7:58
case that this right is going to win on
8:01
the middle node but this right is going
8:03
to win on the top node so again right
8:05
conflicts still very possible in a
8:07
leaderless replication setup and it is
8:09
because of things like write conflicts
8:11
that Quorum reads and writes are not
8:14
perfect right they're very good but
8:16
there are still times where they fail
8:17
they can also fail due to things like
8:19
sloppy quorums which I mentioned the
8:21
leaderless replication video and they
8:23
can also fail due to basically just
8:26
having a right that only partially goes
8:28
through but it doesn't hit a quorum
8:30
right threshold
8:32
okay so that is pretty much going to
8:34
conclude this video guys I hope this
8:36
summarizes things very concisely
8:38
obviously I did Breeze through things on
8:40
purpose and part of that is because I
8:42
just spent the last like 10 videos
8:43
explaining all of them so if there is a
8:45
part of this one you don't fully
8:47
understand or you say oh he really
8:48
breathes through that I highly highly
8:50
recommend just going back and watching
8:52
the entire video for that replication
8:54
schema anyways guys I hope you have a
8:56
great weekend I will try and do the same
8:58
if the Knicks lose tonight I will not
8:59
have a great weekend and uh yeah I'll
9:01
take it from there so see you guys in
9:03
the next one

##v25:

0:00
what's up everybody it is your local
0:02
chat GPT sexbot Enthusiast Sam crankman
0:05
freed coming back at you with another
0:07
video today we are going to be covering
0:08
partitioning you may be wondering why I
0:11
have a hat on indoors it's because the
0:12
Jew fro is coming back so obviously I've
0:15
got to cover it up for the sake of the
0:16
video so let's get into it so that I can
0:18
go to bed
What is partitioning
0:21
all right my iPad just tried to get me
0:23
to upgrade to iOS 16 beta which I refuse
0:26
because I am no beta so let's get
0:28
started with our introduction to
0:30
partitioning so the way this is going to
0:32
work is let's imagine that you finally
0:34
get off your lazy ass and start a
0:36
startup here right this is the database
0:37
representing your startup and all of a
0:40
sudden by the good luck of God you now
0:43
have a ton of users here they are right
0:45
over here to the point that actually
0:47
your startups database is starting to
0:49
get clogged up maybe it's got hundreds
0:52
of terabytes maybe even more data on it
0:55
and eventually that becomes infeasible
0:57
for a single system so what do we have
0:59
to do well replication isn't going to
1:01
solve this because even if we did do
1:03
some sort of replication it wouldn't
1:05
actually allow us to kind of split up
1:07
our data set into many pieces the entire
1:10
data set would still have to be able to
1:11
fit on one note and when that's no
1:13
longer possible we need to resort to
1:15
partitioning also known as Chardon which
1:18
is basically taking our original data
1:20
set right here and breaking it up into
1:22
multiple little pieces Each of which can
1:24
be stored on individual database nodes
1:27
so how does partitioning work well
1:29
obviously we have to break up our data
1:31
but how can we do it if we just do it
1:33
randomly that's not a great idea because
1:35
we can randomly throw our keys
1:37
everywhere that we want but then how are
1:39
we going to know where to find them when
1:40
we need to read them back so obviously
1:42
we need to distribute our data a little
1:43
bit better than that let's go ahead and
1:45
talk about how we can do this so the
Rangebased partitioning
1:47
most obvious approach is going to be
1:49
range-based partitioning so let's
1:51
imagine a scenario where I'm storing a
1:54
bunch of people's names based on their
1:55
first name and how many dollars they
1:57
currently have on their wallet so an
2:00
easy way of doing this would be to
2:01
literally split up all of our partitions
2:03
over here on the left basically by the
2:06
letter of their first name and so all
2:09
the people whose name start with a
2:10
through C go on the left in this top
2:12
database node over here and then you
2:14
know D through F in the next One X
2:16
through Z and the last one didn't draw
2:18
out everything
2:19
so what is a pro of this approach well
2:23
it's pretty obvious in the sense that
2:25
when we have similar Keys they're going
2:27
to be on the same node and so if we want
2:28
to do something like a range query this
2:30
is going to give us really nice data
2:31
locality remember that all of these
2:33
partitions are going to be on physically
2:35
different computers or at least some of
2:37
them are likely to be unphysically
2:39
different computers and what that means
2:41
is that we have to read to multiple
2:42
places over the network which is going
2:44
to slow us down it's always optimal to
2:46
be able to read from just one database
2:48
node and similarly it's always optimal
2:50
to be able to write to just one database
2:52
node so that is a big Pro on the other
2:55
hand there is a big con present and that
2:57
is going to be hot spots so in reality
3:00
like I did with this example probably
3:03
not too many people have their first
3:04
names starting with x through Z at least
3:07
in America and so as you can see here
3:09
we've got zero entries in the X through
3:11
Z partition which effectively just
3:13
wastes compute for us on the other hand
3:15
in the a through C partition we've now
3:17
got five names and so what that means is
3:20
that the a through C partition is known
3:22
as a hotspot in the sense that not only
3:24
does it have more people writing to and
3:26
reading from it but is also going to
3:28
store significantly more data than the
3:31
emptier partitions and what that means
3:32
is that we might even have to further
3:34
partition this partition
3:36
so it would be great if we could shard
3:38
in a more intelligent way it's such that
3:40
we don't have to do this and out of this
3:42
complication arises hash ranged based
3:45
partitioning let me go ahead and scroll
3:47
okay so let's imagine that now instead
3:51
of um just sharding by the first letter
3:53
of your first name we have this kind of
3:56
arbitrary sharding at the bottom here on
3:58
our left you can see their values from 1
4:00
to 250 251 to 500 501 to 750 and 751 to
4:04
a thousand so let's imagine that the
4:06
reason we're doing this is because we
4:08
have a hash function which takes in a
4:10
string
4:11
and it is going to return us a number
4:14
from one to a thousand and so what we're
4:18
going to do to actually figure out where
4:19
to put a given key and value is we are
4:22
going to take the hash of the key so
4:24
let's imagine we have Jordan is equal to
4:25
10. we're going to take the hash of it
4:27
let's say that spits out 821 and then
4:30
we'll find the node that corresponds to
4:32
that hash range so in that case 821 is
4:34
between 751 100 hence why we put Jordan
4:38
equals 10 over there
4:40
so what are the pros of this setup well
4:43
the whole reason that we did this in the
4:44
first place was to get rid of hot spots
4:46
and technically speaking this does work
4:48
pretty well with that if it's a good
4:50
hash function it should distribute the
4:52
keys relatively evenly around our hash
4:54
range on the other hand of course
4:56
nothing is perfect right if I were to
4:58
say you know let's say I was running
5:00
Instagram and I was trying to basically
5:03
hash all of our posts based on the post
5:06
ID but then all of the comments were
5:08
stored with each post ID if I were
5:11
Cristiano Ronaldo and all these women
5:13
wanted to uh hit on me from my post and
5:16
we're all commenting on it then we are
5:18
going to have a ton of comments on one
5:20
post and we may have to actually even
5:22
reshard those so again even hash range
5:24
partitioning isn't perfect for avoiding
5:26
hot spots if certain keys are just
5:28
extremely active and then what is the
5:31
con well again the main Pro of range
5:34
based practitioning was that we get good
5:36
range queries and in the case of hash
5:38
based partitioning we don't really so
5:41
what can we do to possibly Rectify in
5:43
that situation well we could use a
5:45
secondary index
Secondary indexes
5:47
so we've spoken about secondary indexes
5:49
a little bit in the past I believe at
5:51
least but the general gist is a
5:53
secondary index is an additional index
5:56
to your primary index it's a second copy
5:58
of the data effectively where you're
6:00
just storing it in a different sort
6:01
order so let's talk about two
6:04
possibilities of maintaining secondary
6:06
indexes in a partition database where
6:09
the first one is known as local
6:11
secondary indexes so the problem I'm
6:14
going to present to you guys is this
6:15
let's say we have a database of NBA
6:17
players and right now they're sharded on
6:19
their name let's just say it's a range
6:21
of the names or something like that
6:23
but in addition to that we also want to
6:26
be able to Shard on height and so that
6:29
is very important that we need to
6:31
basically store a second copy of the
6:33
data so in the case of a local secondary
6:35
index we basically take all of the data
6:38
on a given node and we would go ahead
6:41
and store a second copy of it on that
6:43
same node ordered in the manner that we
6:45
want so in the case of Shard one what
6:47
that would look like is I would reorder
6:49
it such that Mugsy comes first because
6:52
he's 5'3
6:54
then Alan would go second because he is
6:57
six feet and then jaw would come last
7:00
because he's six three and on Shard two
7:02
that secondary index would look like
7:05
D Aaron first
7:08
Vincent II
7:10
and LeBron third and of course these
7:13
would all be keyed by their height
7:15
so that is going to be the most
7:17
important thing there
7:18
so let's say I wanted to find all of the
7:21
people who were six three well it's very
7:24
useful that we have this Index right
7:27
because I can binary search on each node
7:28
and quickly find that you know we've got
7:30
jaw is 6'3 on Shard one but for me to
7:33
find all of our NBA players who are 6'3
7:36
I still have to read from every single
7:38
note and see that we've got a guy on
7:40
both nodes and the problem with that is
7:42
of course again that when you have to
7:43
read for many nodes things take longer
7:46
there are possibilities that that read
7:47
May Fail on one of the nodes and
7:49
ultimately there are just more points of
7:51
failure that we have to deal with
7:52
so that is definitely a big con on the
7:55
other hand the pro of this scenario is
7:58
that when you make a right you don't
7:59
have to do any extra work right all of
8:02
the additional work to create that
8:04
secondary index is maintained on one
8:06
single database node that is of course
8:08
in contrast with the global secondary
Global secondary index
8:11
index quite a useful thing but also
8:14
quite precarious so let's talk about
8:16
that a bit so we're going to do here is
8:19
instead of maintaining a second copy of
8:22
the data on each node where all of the
8:25
rows are local to that node the global
8:27
secondary index is basically going to
8:29
take the entire index of all of the data
8:32
in our system regardless of what Shard
8:33
it's on and then effectively Shard that
8:36
so let's give an example so similar to
8:39
last example we are now going to create
8:41
a global secondary index of all those
8:43
NBA players so we might what we might do
8:45
is say Shard one is going to keep the
8:48
global secondary index of all players
8:51
that are 6'3 or yes
8:53
and so as you can see I have them all
8:55
right here and this would be stored in
8:58
addition to the original copy of data on
9:00
the other hand I could say that Shard 2
9:02
is going to maintain all of the players
9:04
who are 6'4 or greater
9:06
and of course again the whole point is
9:09
this is in addition to the data that's
9:10
already stored on there so keep in mind
9:13
that this stuff is still on Shard one
9:15
and this stuff is still on Shard too the
9:18
global secondary index is in addition to
9:20
that
9:21
and so now if we want to find all of the
9:23
players that are 6'3 it's only going to
9:25
take reading one note we just have to
9:28
read this guy right here and now we see
9:30
that D Aaron and jaw are both six foot
9:31
three
9:32
on the other hand there is a pretty
9:34
significant and major con here right so
9:38
let's say that I were to create another
9:40
six three player uh I don't know let's
9:43
call him Dwyane Wade
9:47
and he is going to go to that area of
9:49
the global secondary index but the issue
9:52
is that when Dwyane Wade actually gets
9:55
hashed we find that his hash function
9:57
for where he should actually be stored
10:00
in the primary index is over on shard 2.
10:04
and now all of a sudden we need to write
10:07
to one node for the primary index and a
10:10
second node for the secondary index not
10:13
only does that mean that rights are
10:14
actually going to take much longer but
10:17
it's very important that both of them go
10:19
through because what if this right
10:20
didn't work then all of a sudden our
10:23
secondary index and our primary index
10:25
are inconsistent with one another and
10:27
that is a state that we absolutely do
10:29
not want to be in so what does that
10:31
require
10:32
well if you're looking at the bottom of
10:34
the screen here you can see that is
10:36
going to require distributed
10:37
transactions and if we need distributed
10:39
transactions things are going to get a
10:42
lot more complicated so that is going to
10:44
be the topic of the next video anyways
10:46
guys I hope you enjoyed this one looking
10:48
forward to seeing you in the next one
10:50
and we will be talking about distributed
10:52
transactions and two-phase commit


##v26:

0:00
hello everyone and welcome back to the
0:02
channel this is your host famous Tick
0:04
Tock influencer Frank Jew here again
0:06
today to talk about some systems design
0:08
today we'll be talking about two-phase
0:09
commit which I personally use a lot in
0:12
my day-to-day life especially with the
0:13
lovely ladies out there in the first
0:15
phase of the commit I tend to tell them
0:18
that uh I am ready to commit to them and
0:20
in the second phase I break that bow and
0:22
go back to being a sigma male so let's
0:24
get into the content of this video and
0:26
uh yeah get started okay so as I
Two Phase Commit
0:29
mentioned today we would be talking
0:30
about two-phase commit so what exactly
0:32
does that word mean or that term rather
0:34
well basically uh last episode we
0:38
introduced the concept of partitioning
0:39
our database which is something that we
0:41
do when our data set becomes too big to
0:43
be stored on one individual node and so
0:46
what that means is that basically now we
0:48
often find ourselves having to write to
0:50
multiple physical computers at one time
0:52
for a variety of reasons the first just
0:55
being cross partition rights right
0:56
sometimes you make a right and it needs
0:58
to go to multiple different places and
1:00
the second is global secondary indexes
1:02
where instead of just having a local
1:05
secondary index where we basically index
1:07
all of our data per node we actually
1:09
take all of the aggregate data across
1:11
partitions and we split up that Global
1:13
index such that a piece of the index is
1:16
on every single node feel free to go
1:18
back to the last video if you need a
1:19
refresher on that so again why do we
1:21
need it distributed transactions we need
1:23
atomicity here because when we want to
1:25
write to multiple places let's say this
1:27
is node one
1:28
and this is node two and those guys
1:30
represent different partitions if this
1:32
guy goes through but this right fails
1:35
we're in trouble our database is now
1:37
going to be in an inconsistent State and
1:39
we are going to probably have some
1:40
incorrect reads which generally speaking
1:42
we don't necessarily want eventual
1:45
consistency is okay because we know it
1:47
will resolve itself but incorrect reads
1:49
will not those are going to be persisted
1:51
forever
How does it work
1:53
so how does two phase commit actually
1:55
work well first thing I'm going to do is
1:57
show off the phase where it doesn't work
1:59
so let's say we have one node right here
2:01
this is going to be our coordinator node
2:03
and even though I'm calling it a node
2:04
what this might end up being is just an
2:06
application server
2:08
right like we have a client who wants to
2:11
perform a right and the client is
2:12
reaching out to our application server
2:14
in the application server is sending two
2:16
different rights to our two database
2:18
partitions so let's say we're going to
2:20
call this guy a coordinator node that's
2:22
going to be a new vocabulary term and
2:23
the first thing that coordinator node is
2:25
going to do is say all right I'm trying
2:27
to start out a two-fizz commit right
2:29
because I want to write to two different
2:31
partitions so the first thing it does is
2:33
right over here it's going to say
2:35
I'm going to reach out to node number
2:37
one and say I'm sending you message one
2:39
are you ready for it node number one is
2:41
going to look at itself and say hmm can
2:44
I actually go ahead and Commit This
2:45
thing I'm going to run a local
2:46
transaction here's my right ahead log
2:48
can I write it down is it going to cause
2:50
an error and if not everything is good
2:53
it's going to grab the locks for that
2:54
row so that nothing else can modify it
2:56
and it's going to respond back to our
2:58
application server with an OK and so in
3:01
the meantime from when this guy responds
3:03
okay until it hears back from the
3:05
coordinator node it's just waiting and
3:07
the locks are still grabbed now the
3:10
coordinator node or probably at the same
3:12
time in parallel is going to reach out
3:14
to node number two over here
3:16
with another message saying hey are you
3:18
ready to possibly commit message 2. and
3:21
so node 2 is going to look locally it's
3:23
going to see this message too and it
3:25
might say you know what I'm actually not
3:28
sure I can commit this either it's going
3:30
to conflict with some other right that I
3:31
have or perhaps I don't have enough
3:33
space for it and then it might respond
3:36
back to the coordinator node saying no
3:39
I'm not good with this so what the
3:41
coordinator mode has to do is actually
3:43
go and write back to Node 1 and say
3:46
abort
3:47
and it's only then that Node 1 can
3:49
unlock
3:51
so now I'm going to erase some things
3:52
because that is how this would work in
3:54
the case where we can't go through with
3:55
a two-phase commit right so I'm going to
3:57
erase this guy here I'm going to erase
3:59
the fact that we grab some locks I'm
4:01
going to erase the no message so let's
4:03
say now that we actually can go through
4:04
with the two-phase commit so again we
4:07
start with ready message one we start
4:09
with ready message two and let's say
4:11
this guy gives the okay
4:12
now what the coordinator node is going
4:14
to do is the following in its own local
4:17
commit log it's going to say hey we have
4:19
a transaction that I know I want to be
4:21
able to commit with message one and
4:23
message 2. and from now on if I happen
4:26
to go down you know let's say this guy
4:27
crashes it can read back from the commit
4:30
log to know that we can recommit this
4:32
thing so even if our coordinator node
4:34
goes down keep in mind that these two
4:36
are now both waiting to hear back from
4:38
the coordinator node and while they're
4:40
waiting they've maintained grabbing the
4:42
locks for all of the rows that are going
4:43
to be part of this commit then let's say
4:45
the coordinator node is ready to finally
4:47
send a commit and now it's going to do
4:49
the following
4:51
commit
4:52
and it's going to do the same thing here
4:54
to node number two
4:55
commit
4:57
and then now Node 1 and node 2 can go
5:00
ahead and commit that local transaction
5:02
so you know they're going to do that
5:04
they're going to put it in the right
5:05
ahead log blah blah it's committed blah
5:07
blah
5:07
and now they can unlock their local
5:09
locks
5:10
you know erase these guys right here
5:13
and then once they do that they can
5:15
respond back to the coordinator node
5:17
saying okay we're done
5:19
and that is all it is right there guys
5:22
we just have one coordinator node and
5:23
all the coordinator node is doing is
5:24
ensuring that both of these two things
5:26
either go through or both of the
5:28
transactions do not go through it's
5:30
important that they are Atomic so this
5:32
is not too complicated of a process but
5:35
it does have some caveats and some
5:36
complications that arise with it
5:39
so what are some problems that we
5:41
encounter when we see two-phase command
5:42
well for starters there are a lot of
5:45
points of failure so the first thing is
5:47
this we have a single coordinator node
5:49
and if this guy goes down nothing is
5:51
getting committed and if this guy goes
5:53
down after the commit point where the
5:55
commit point is the first time these
5:58
guys respond to okay now they're waiting
6:00
and they have all of these locks grabbed
6:02
and while these locks are grabbed no
6:04
other transactions can go through on
6:06
those same rows so obviously that is
6:09
going to be a problem that no
6:10
transactions can receive and that locks
6:12
are being held and again those rows are
6:14
basically Untouchable during that period
6:16
of time what if one of these receivers
6:19
goes down so our coordinator node is
6:20
going to be back up
6:22
right here oops accidentally deleted the
6:24
commit log let me draw that guy back
6:27
but basically let's say this guy right
6:29
here geez I gotta get my marker back
6:32
this guy right here is going to go down
6:36
if our Node 1 goes down
6:38
the issue there is that now the
6:40
transaction can't actually commit
6:42
because we can't get an OK from both of
6:44
those nodes after that commit point when
6:46
the first node said hey I'm good to
6:47
commit this
6:48
but now it went down for some reason so
6:51
what's going to happen then is our
6:53
coordinator node is just going to have
6:54
to repeatedly over and over and over
6:56
again send messages until node One
6:58
Forever Until It actually responds and
7:01
completes the commit so obviously this
7:04
is a problem too we have very little
7:05
fault tolerance here we've basically
7:07
said if we're past the commit point we
7:10
need to get this thing done no matter
7:11
what it takes we're going to try it
7:13
forever basically until we can get it
Conclusion
7:15
done
7:16
so what's actually the conclusion of
7:18
two-phase commit well basically for
7:20
distributed transactions which are
7:22
something that is a necessity for things
7:24
like cross partition rights or Global
7:25
secondary indexes they're very dangerous
7:27
because we run the risk of having a
7:29
failure and when we have a failure our
7:31
system is basically unable to proceed
7:33
thus things like cross partition rights
7:36
and Global secondary indexes in
7:38
distributed systems are generally things
7:40
that we want to avoid when possible
7:42
there are definitely other ways of being
7:44
smarter about how you Shard your data or
7:46
possibly even improving your data
7:48
locality with something like a nosql or
7:50
like a document store database that are
7:52
going to allow us to generally be able
7:54
to avoid these types of cross-partition
7:56
Rights so this is something to
7:58
definitely keep in mind as you think
8:00
about designing your own systems these
8:01
types of rights are very dangerous and
8:03
while two phase commit can be improved
8:05
and we'll talk about how you can do that
8:07
when we cover things like distributed
8:08
consensus and things along those lines
8:11
it's definitely something that generally
8:14
you want to avoid anyways guys hope you
8:16
enjoyed the video see you in the next
8:18
one

##v27:

0:00
hello Sigma males and welcome back to
0:02
the channel so I am actually pretty
0:04
tired today and I don't really have any
0:06
energy to make up some new cringe 4chan
0:08
joke so as a result I am just gonna go
0:11
get right into the video I should
0:13
mention that I will be posting the
0:14
Banger of the century this Sunday so do
0:17
prepare yourselves to repost that to
0:19
Blind and watch it with an audience
0:22
anyways let's get into this thing we've
0:24
got to talk about consistent hashing
0:26
okay so I'm going to start off this
0:28
video by basically talking about
0:30
partitioning rebalancing and just kind
0:33
of one General schema that naively we
0:36
might use to partition some of our keys
0:38
so let's imagine we have got a bunch of
0:40
different Keys you know like Jordan
0:42
Karina
0:45
Kate
0:46
and we want to be able to go ahead and
0:49
Shard those to a bunch of different
0:51
nodes so naively you might do something
0:53
like this well what we would say is we
0:55
would take a hash of a key and since
0:58
we've got four partition nodes as shown
0:59
below we are going to take modulus of
1:02
four and then put it in the node
1:04
corresponding to that so let's imagine
1:05
the first key is 16 and then you know
1:08
that goes to node 0 16 divided by four
1:10
is you know take the modulus of that so
1:13
zero same thing with 28 and then we've
1:15
also got 12 and 19 also shown on the
1:18
screen but what if we were to change
1:20
things up a little bit because I were to
1:22
go ahead and nuke node three and so now
1:26
instead of being hash of key mod 4 we do
1:28
hash of key
1:31
mod 3.
1:33
so now all of a sudden where is 16 going
1:36
16 is going to Node 1 28 divided by 3
1:39
also actually going to go to Node 1 12
1:43
divided by 3 going to node 0 and then 19
1:47
mod 3 is also going to be going to node
1:51
1. so all of a sudden as you can see we
1:54
just had to move around a ton of our
1:56
keys and basically just move around a
1:58
ton of the data by using this modulus
2:01
function and so I guess the general
2:03
opening point of this video is if we are
2:06
trying to partition keys in a way that
2:08
is easy to kind of rebalance them when
2:10
we add new nodes or remove nodes from
2:12
the cluster we certainly should not be
2:14
doing this mod n partitioning right it
2:17
is not efficient because what that
2:18
results in is whenever the cluster
2:21
basically changes in size we have to
2:23
send the majority of our keys over the
2:25
network and that puts in unnecessary
2:26
strain on our system
2:29
so like we said modulus doesn't work
2:31
well then what does work what does work
2:34
is consistent hashing and that's what
2:36
we're going to be talking about in this
2:37
video along with one or two other quick
2:39
basically rebalancing schemes that we
2:42
can do so what's the point of consistent
2:44
hashing while consistent hashing is a
2:46
method of partitioning basically certain
2:49
values evenly amongst nodes in a way
2:51
that if the size of our cluster changes
2:54
a minimal amount of data is sent from
2:57
one node to the others so we'll see what
3:00
that looks like in a bit but you know
3:01
that's generally the point here which is
3:03
that we don't want to be doing too much
3:05
rebalancing if we can avoid it and not
3:07
only is this great for partitioning but
3:09
it's also great for load balancing load
3:11
balancing is a topic for another video
3:12
but the gist is sometimes we have many
3:14
application servers and we want to send
3:17
requests from our clients to different
3:18
application servers and so consistent
3:20
hashing is also useful for that again
3:22
the topic for another video
3:24
okay so let's actually go ahead and
3:27
demonstrate our algorithm so the first
3:28
thing we want to do is pick out some
3:30
value K and I'll explain the
3:31
significance of K later but right now
3:33
let's imagine k equals three so what
3:36
does k equal 3 here mean it means that
3:38
on this ring that I've demonstrated down
3:40
below for every single partition we're
3:43
going to pick three points we're going
3:45
to pick K points and so what the ring
3:47
represents is basically our hash range
3:50
remember hash range partitioning
3:53
which is basically taking uh the hash of
3:56
each key and then sharding it to a node
3:58
corresponding with a range of that
3:59
hashing
4:00
so as you can see Zero is at the top of
4:03
the Ring 250 is the right side 500 at
4:06
the bottom 750 on the left it's
4:08
effectively a clock and so for every
4:10
single one of our partitions as you can
4:12
see we've got partitions one through
4:13
four we're gonna pick three points on
4:15
this ring so now let's answer a couple
4:17
of questions let's say I'm talking about
4:19
node three what keys actually belong in
4:22
node three to figure that out we look at
4:24
our ring and we say okay well I see a
4:26
node 3 point right here and that is
4:29
going to contain all of these Keys along
4:31
this part of the circle so for the sake
4:33
of this video Let's imagine that's like
4:35
zero to a hundred
4:37
so those are going to be in node three
4:39
but similarly we've also got a point
4:41
over here
4:43
which is also on node three and so this
4:45
range of keys is going to be in node
4:47
three so that's going to be let's say
4:49
200 to 250.
4:51
and then also node 3 is going to be here
4:54
as well and so that is going to be let's
4:57
say I don't know 700 to 800. and so
5:01
that's actually going to be the range of
5:04
hashes of keys that are going to be
5:06
contained on partition three
5:08
and so you see the reason that we can
5:11
kind of generalize this out is that for
5:13
every single one of these nodes all you
5:15
have to do is go clockwise until the
5:18
next node Point comes up and you know
5:19
that range of keys is valid so again you
5:22
know like for node one for example this
5:24
range of keys will be on node one and
5:26
you know so will two others okay so now
5:29
the point here is y is consistent
5:32
hashing so useful what's so good about
5:33
it well I said the entire point is not
5:36
only does it distribute things evenly
5:37
but also it is going to basically
5:41
minimize the amount of things that we
5:43
have to send over the network when a
5:45
node is added and deleted okay so let's
5:48
start with say deleting a node I'm going
5:50
to first start by deleting node four so
5:53
I'm going to get rid of this oh god I've
5:55
really messed up now haven't I let me
5:57
get rid of this here let me get rid of
5:58
that there get rid of this here get rid
6:01
of that there
6:02
and get rid of this here so as you can
6:05
see there were a bunch of things that
6:07
were on node 4 right they were over here
6:10
and over here but now those are just
6:13
going to be extended into node one
6:15
they're going to be extended into node
6:17
three they're going to be extended into
6:19
node 3 again and you'll see that even
6:21
though node 4 was actually removed here
6:24
we're not rebalancing any of the data on
6:26
the other nodes that were not touched
6:28
we're just taking node Force data and
6:30
distributing it in a relatively even
6:32
manner amongst our other nodes let's now
6:35
go ahead and say I added node 4 back so
6:38
we're going to add node 4 back in a
6:39
bunch of random places
6:41
let's say I added here and remember we
6:44
have to pick three points I added back
6:46
here and then I will add it over here so
6:50
now instead of basically requiring all
6:54
of the keys to shift around again we're
6:55
only forcing a small portion of the keys
6:58
to actually be shifted to node four so
7:00
now node four is gonna in this case it's
7:02
gonna steal these or rather it's going
7:04
to steal these Keys over here from node
7:06
one it's also going to basically steal
7:09
these Keys over here from node two and
7:12
then finally it's going to steal these
7:13
Keys over here from node two so by using
7:16
this consistent hashing ring we can
7:18
ensure that we're not over rebalancing
7:20
like we were in the first example recall
7:23
that in the first example we were taking
7:25
keys on nodes that weren't even really
7:27
being touched and we were sending them
7:29
all over the place there's no reason to
7:30
have to do that if we can avoid it and
7:32
that is what consistent hashing is
7:34
accomplishing for us
7:36
so another method or basically an
7:39
analysis of consistent hashing is that
7:42
the way we can think of each node is
7:44
actually having a fixed number of
7:45
partitions so in this case the fixed
7:47
number of partitions was actually going
7:49
to be that variable k
7:51
so we've got K over here we set it to 3
7:53
and K is basically the number of
7:55
partitions per node so there are
7:58
actually some mathematical guarantees
7:59
about consistent hashing in terms of the
8:01
distribution of the keys you're welcome
8:03
to look them up on Wikipedia frankly I
8:05
don't think it's really that important
8:06
for the sake of this video but it is
8:09
cool if it's something you're interested
8:10
in Okay so we've discussed now the
8:12
concept of having a fixed number of
8:15
partitions
8:16
per node
8:19
but another possible partition
8:22
rebalancing method that you'll often see
8:24
is actually just doing a total fixed
8:27
number of partitions and that's not per
8:29
node but it's per system right so like
8:32
our entire back end has a total fixed
8:34
number of partitions so let's imagine in
8:36
this case that we have 12 partitions
8:38
here's what it would look like if we
8:40
lose a node
8:43
basically what's going to happen here is
8:45
you know originally all of these guys
8:46
start out with four partitions and then
8:49
once uh our third node is deleted we can
8:52
take a and b
8:54
and send it to the first guy and take c
8:57
and d and send it to the second guy
8:58
similarly another option is that you
9:01
know if we gain a node because all of a
9:04
sudden we want more partitions we have a
9:05
lot of data we can actually take you
9:08
know a and b and c and d and you know
9:12
basically distribute them out evenly so
9:14
I drew this out wrong but the point is
9:15
as you can see from our fourth node over
9:18
here it's going to take the d partition
9:20
from all three of these guys so we're
9:22
going to borrow this we're going to
9:24
borrow this we're going to borrow this
9:26
and that's what happens when we gain a
9:28
node so basically using a fixed number
9:30
of partitions is very viable in the
9:31
sense that it's simplistic to think
9:33
about right we know at all times how
9:36
many partitions there are total and so
9:38
we can easily assign them from node to
9:40
node however it also does come at a
9:42
downside which is that we actually have
9:44
to choose a pretty good number so what
9:46
happens if there are too few partitions
9:48
well let's say we have I don't know 10
9:50
partitions in our system but we also
9:52
have an exabyte of data well that means
9:54
that every single partition is going to
9:55
be an exabyte divided by 10 so I guess
9:58
100 petabytes and you can't fit 100
10:00
petabytes of data on one hard drive so
10:03
you're basically just taking an L there
10:04
if you only choose 10. at the same time
10:06
if you were to do too many
10:09
basically now we have a bunch of
10:11
overhead on our hard drives of you know
10:13
keeping track of what partition means
10:15
what so for example you know I have to
10:17
keep track here that partition one is
10:19
corresponding to the range 0 to 72
10:21
here's the same thing with Partition two
10:22
all the way through partition n so if we
10:25
have a bunch of those you know this
10:26
table could in theory take up some extra
10:28
space on our disk and we don't really
10:29
want to be doing that
10:31
okay so the last thing I'm going to
10:33
touch upon in this video is the concept
10:35
of dynamic partitioning so even though
10:37
all of these partitioning schemas allow
10:39
us to rebalance our nodes it doesn't
10:42
necessarily mean that that's going to be
10:43
happening on its own oftentimes there's
10:45
probably going to be some sort of data
10:47
center kind of Representative or you
10:50
know person who's really trained in this
10:51
making sure that load is getting
10:53
balanced properly and if not making the
10:54
proper adjustments that being said it is
10:57
possible that the database could
10:59
actually manage its own rebalancing
11:00
however this does run a risk which is
11:03
that if you do it too often as in you
11:05
know let's say you rebalance when you
11:07
don't necessarily need to the nodes are
11:09
just fine but you know maybe you
11:11
accidentally think one is down well then
11:13
all of a sudden we start sending a bunch
11:15
of rows of our data over the network we
11:17
don't need to and we're actually putting
11:18
a greater cost on our system in order to
11:21
do that and so I guess the question then
11:24
kind of becomes well how do we even know
11:26
when our system is down how can we agree
11:28
upon this type of thing and of course
11:30
what do we we do about it well
11:33
it's not so easy to know when a system
11:35
is down and frankly this type of video
11:37
begs many many others and of course
11:40
that's what we'll be doing next so look
11:42
forward to distributed consensus guys
11:44
because that's what's next on our plate
11:47
anyways have a great night everyone I am
11:49
going to pass out and uh yeah enjoy
11:52
yourselves

##v28:

0:00
hello gigachads and welcome back to the
0:02
channel sorry I missed a video this past
0:04
week on Thursday I was starting to make
0:07
it on like Tuesday and then I thought I
0:08
came up with a distributed consensus
0:10
algorithm and I spent like
0:12
two hours trying to figure out if I
0:14
actually did and it's still kind of
0:15
unclear to me whether I did so I'm
0:16
either going to be a billionaire or I
0:18
wasted two hours either way the EV is
0:21
pretty good but uh yeah without a doubt
0:23
now I actually have to make a YouTube
0:24
video so let's go ahead and get into it
0:26
for today all right so the topic of
0:28
today's video is going to be a
0:30
linearizable storage so what is
0:33
linearizable storage why do we need it
0:35
how is it relevant for the subject
0:38
matter that we've covered so far well
0:40
basically we need it for let's say
0:42
correct reads so imagine that I'm
0:45
building a distributed lock meaning that
0:48
we have one node that uh you know kind
0:51
of holds the lock on it but a bunch of
0:52
different clients need to be able to
0:53
grab it and if that node goes down we
0:56
need to make sure that basically the
0:58
person who is holding the lock is still
1:00
holding that lock right we need to be
1:02
distributed and tolerant in the face of
1:04
faults so that is going to be you know
1:07
let's say just one person can hold that
1:09
lock and that invariant needs to stay
1:11
true additionally for something like a
1:13
database leader it needs to be the case
1:14
that there's only one database leader
1:16
and if for some reason that leader were
1:18
to go down that we don't switch in a way
1:21
that is going to kind of contradict what
1:23
everyone in the system believes and
1:25
understands that leader can't come back
1:26
up and then be a second leader all of a
1:28
sudden so linearizable storage for me to
1:31
kind of summarize it is this kind of
1:33
black box here of a database system
1:35
where it is both fault tolerant and all
1:38
of the rights are ordered so what does
1:41
it allow us to do if all of the rights
1:43
are ordered well it basically means that
1:45
if we know the order of the rights we
1:47
can make sure that our reads never go
1:48
back in time right if right one is
1:51
saying uh you know like node a is leader
1:57
and then you know all of a sudden I read
2:00
write two saying node B is leader
2:04
there should be absolutely no
2:06
possibility that I later then read that
2:08
node a is leader or else our storage is
2:11
not linearizable I kind of just went
2:13
back in time in my system and now our
2:15
entire constraints and invariance
2:16
forcing everything to be correct have
2:18
been completely messed up so how do we
2:20
actually order our rights let's look at
2:23
a few examples that we've spoken about
2:25
uh so let's start with single leader
2:28
replication for example the way that we
2:30
order our rights within our nodes is a
2:32
replication log the replication log
2:34
basically says you know we've got to
2:36
write one and a right two and a right
2:38
three and you send that replication log
2:41
from the leader
2:42
to the followers and by doing so we know
2:46
that the leader and the followers so all
2:48
of the nodes in our cluster agree on the
2:50
order of all the rights what about
2:51
multi-leader and leaderless replication
2:53
well obviously this is going to be a
2:55
little bit more challenging simply
2:56
because of the fact that now our rights
2:58
can go to a bunch of different places
2:59
and we can have concurrent rights so how
3:02
can we establish an order across them we
3:05
can't really establish a correct order
3:06
right it's not really possible to say
3:08
like hey I know for a fact that the
3:10
right on one node came before another
3:12
node but we can establish an order that
3:15
is consistent among the nodes right so
3:17
we can get all the nodes to agree on The
3:19
Ordering of the rights and how can we do
3:21
that well we could use something like
3:22
version vectors or a lan Port clock so
3:26
just as a reminder to everyone a version
3:27
Vector is what we have shown over here
3:30
where as you can see we've got say like
3:33
the version Vector on the left says
3:34
three comma one and the version Vector
3:37
on the right says two comma two so on
3:38
the right database node you've seen two
3:41
updates from the left database node and
3:43
two updates from the right database node
3:44
and on the left database node we've seen
3:46
three updates from the left database
3:48
node and one update from the right
3:50
database node now it's important to note
3:52
that because three comma 1 and 2 comma
3:55
two are kind of interleaved right like
3:57
three is greater than two but one is
4:01
less than two that these two version
4:03
vectors are concurrent and so
4:05
technically there's no complete order
4:07
right we can assign a complete order
4:09
where we would say like okay in a
4:11
tiebreaker choose the version Vector
4:13
where you know the left kind of index is
4:16
greater right so we could say in tie
4:18
Breakers we arbitrarily choose an
4:19
ordering and that's effectively what we
4:21
do with lanport clocks as well the one
4:24
big difference with Lamport clocks is
4:26
that version vectors take o of n space
4:28
where n is the number of replicas so if
4:30
I added a third guy over here now all of
4:34
a sudden our version vectors need three
4:36
elements Lamport clocks always
4:38
exclusively take two elements and so as
4:41
a result they're a bit more compact to
4:43
determine the ordering in multi-leader
4:45
and leader list replication so let's
4:47
quickly learn how those work so this is
4:49
going to be a little bit of a
4:50
complicated slide but let's go ahead and
4:53
talk about it so I mentioned that
4:55
lampord clocks take constant space of
4:57
one so how do they work let's imagine
4:59
imagine we have one client over here on
5:02
the left side of our screen another
5:04
client on the right side of our screen
5:05
and the point is they're going to be
5:07
making concurrent rights and we want to
5:09
be able to order them so let's call this
5:11
database B we'll call this database a
5:14
and so the point here is that every
5:16
single kind of element of our system uh
5:19
both the client the databases and the
5:22
other client all have a local counter
5:24
and so as you can see that's all going
5:25
to start at zero I have them lined up
5:27
right here b0 and the point is every
5:30
single time that you make a right you're
5:33
going to increment your counter both on
5:35
the client and the database however the
5:37
kicker is that you don't just increment
5:39
your counter by one oftentimes you do
5:42
but you actually take the max of the
5:44
counter that's currently on the client
5:46
and the database that the right is going
5:48
to and you add one to that so just to
5:51
show things off since clients are both
5:53
starting let's start over here since
5:56
both clients are starting with a counter
5:58
of zero and both databases are starting
6:00
with a counter of zero when you perform
6:01
the right you perform a right and
6:04
everyone increments their counter to one
6:05
because you're going to say well this
6:08
guy was at zero this guy was at zero
6:10
they're writing to one another so
6:11
increment both the client and the
6:13
database counter to one do the same
6:15
thing on the top now what's going to
6:18
happen is that client 2 is going to
6:20
write to database B again so as you can
6:22
see this right is now going to be B
6:24
comma 2 because the right is going to
6:26
database B and the counter on the client
6:29
is two now what's going to happen is
6:32
that this client is going to write again
6:34
over here but this time to node a and so
6:37
you can see that the counter is going to
6:39
be a comma 3. so why is it a comma 3
6:42
instead of a comma 2 because keep in
6:44
mind that the counter on node a was
6:46
still only one the reason it's three is
6:48
because the counter on client 2 was
6:51
already two so what we do is we take the
6:54
max of the two possible counters we add
6:57
one to it and that is our new Lamport
6:59
clock number see we have a comma 3 and
7:01
then the same thing over here
7:03
when client 0 or client 1 rather is
7:06
going to write to node a we're going to
7:09
take the max of the two counters so
7:11
recall that a already at a counter of 3
7:13
at this point from the last right and
7:16
client one had only a counter of one
7:18
from over here and we're going to add
7:20
one to it and now we have four so this
7:22
all seems very arbitrary what am I
7:23
getting at here the point is you can
7:25
assign a lan port timestamp to every
7:27
single right and then once we've
7:29
assigned those Lamport time stamps to
7:30
every single right we can actually
7:32
Express an ordering over our rights that
7:35
is total we don't have a concept of
7:37
concurrency here because what we can do
7:39
to settle ties when things have the same
7:41
counter is we can just pick an order of
7:43
the notes so let's say the rule is
7:45
basically that first we're going to sort
7:46
by counter and then if there's a tie
7:49
encounter we sort by node so that means
7:51
that A1 this guy over here is our first
7:54
right then we have B1 this guy over here
7:57
then we have B2 which makes sense
8:00
because 2 is the next highest counter
8:01
rather you know the next lowest count
8:03
then we have a comma 3 because 3 is
8:06
going to be the next lowest one and then
8:08
finally a comma 4 because 4 is the next
8:10
lowest number notice that when we have
8:13
two things with the same counter value
8:14
A1 and B1
8:17
that the fact that we use the node tie
8:19
breaker there means that A1 comes first
8:21
because we will choose a first since
8:23
that is our arbitrary node ordering that
8:25
we've chosen so this is one way that we
8:27
can actually Implement a complete
8:29
ordering over all of our rights in a
8:32
leaderless or multi-leader replication
8:34
setup however it still does not create
8:36
linearizable storage the reasoning being
8:40
because of the fact that in this setup
8:43
while we are able to create an ordering
8:46
over our rights the ordering is kind of
8:49
after the fact okay so let's go ahead
8:52
and go through this example of how
8:54
things might not necessarily be
8:56
linearizable in a multi-leader
8:58
replication setup even if you are using
9:01
Lamport clocks to order the rights let's
9:03
imagine I have a client and he is going
9:06
to be hanging out right here so the
9:08
first thing that's going to happen is
9:09
we've got a couple of rights that have
9:11
gone to each of our databases one is x
9:14
equals one to the left database and then
9:16
the other is going to be X is equal to 5
9:19
on the right database so you can see now
9:21
that the x is equal to 5 is technically
9:23
the later right because it has this b
9:25
equals one Lamport timestamp so this is
9:28
the later right
9:30
so let's imagine basically that I first
9:33
read from this node over here and I get
9:35
that X is equal to 1.
9:38
then I now go ahead and read from this
9:42
node over here and get X is equal to 5.
9:44
and then one more time I'm going to read
9:46
from my left node and get that X is
9:48
equal to 1. even though eventually once
9:51
these nodes kind of converge and
9:53
replicate their state to each other
9:54
where we see X is equal to five and it
9:56
gets over here then we'll be in good
9:58
shape but until that replication
10:00
actually happens we can read these
10:02
rights out of order because we know that
10:04
X is equal to 5 comes after X is equal
10:07
to one because it is the later right so
10:09
as long as we have the propensity to be
10:11
able to read these rights out of order
10:12
our storage is obviously not going to be
10:14
linearizable
10:16
so let's actually go ahead and talk
10:19
about single leader replication because
10:20
you might be thinking yourself well
10:21
obviously if all the rights go through
10:23
one node that's got to be linearizable
10:25
right we discussed how there's a
10:26
replication log but actually it's not so
10:29
how is it not linearizable well let's go
10:32
ahead and take a look so let's imagine
10:33
the first thing that's going to happen
10:35
is we write to our left database over
10:36
here let's call this the leader
10:38
we're going to write X is equal to 5 to
10:40
it and then we're going to write X is
10:42
equal to 10 to it so the replication log
10:44
looks something like this
10:45
x equals five x equals ten and so we're
10:50
going to send over X is equal to 5 to
10:52
our follower
10:54
and then once we basically do that what
10:57
we can do is have our client over here
10:59
the first thing our client is going to
11:01
do is read X is equal to 5 from the
11:03
leader the second thing they're going to
11:05
do is do another read from the leader
11:07
and now you can see oh wait X is
11:09
actually equal to 10. however if our
11:12
leader goes down during this time and X
11:15
is equal to 10
11:17
has not yet actually gotten to the
11:20
follower
11:21
when you read again from the follower
11:23
you're going to see that X is equal to
11:24
5. because the right has not yet been
11:27
propagated so this is not a fault
11:29
tolerant linearizable storage solution
11:32
even though a single node is itself
11:35
linearizable the whole point is this is
11:37
distributed systems we need to figure
11:39
out a way such that when nodes fail we
11:41
can still be sure that our rights are
11:43
only being read in that same order
11:46
so what we actually need is something
11:49
called total order broadcast and what
11:51
that means is that everything every
11:53
single right that is published to the
11:54
system is agreed upon by every single
11:57
node not necessarily every node but it's
12:00
agreed upon by the storage system in a
12:03
way it's such that it exhibits
12:04
linearizable reads meaning that your
12:06
reads are never going back in time
12:08
because again if you're holding a lock
12:10
and you're basically just holding that
12:13
and then all of a sudden the system
12:15
thinks that a previous owner of the lock
12:16
is the one holding it you're in huge
12:19
trouble so ultimately what does this
12:21
come down to we need something called
12:22
distributed consensus so that is going
12:25
to be the topic of the next video this
12:27
was mainly just a primer for it why we
12:29
need distributed consensus what it's
12:31
useful for but yeah hopefully that makes
12:33
things very clear so guys I will see you
12:36
in the next one I've got to run to the
12:37
gym because I just ate a bunch of donuts
12:39
and I'm feeling pretty thick and uh yeah
12:41
have a great weekend everyone

##v29:

0:00
hello everyone welcome back to the
0:02
channel today we are going to be talking
0:04
about distributed consensus now this is
0:06
only consensus in the computer term if I
0:09
could actually solve consensus my
0:10
parents wouldn't be divorced but
0:12
nonetheless here we are today so let's
0:14
get into some content because I have to
0:16
leave the house soon
What is Raft
0:17
all right so as I previously mentioned
0:20
in the last video the entire point of
0:23
doing all of this is to basically build
0:25
linearizable storage and what
0:27
linearizable storage is going to allow
0:28
us to do is build applications on top of
0:31
that such as distributed locking or
0:33
service Discovery mechanisms obviously
0:35
we'll cover those in a later video so
0:37
the algorithm I'm actually going to be
0:39
talking about today is called raft and
0:41
what raft allows us to do is build a
0:43
distributed log why do we want a
0:45
distributed log because logs are ordered
0:47
hence they are linearizable and that is
0:50
extremely important for us so how does
0:53
raft actually work and I guess
0:54
additionally why am I not talking about
0:56
paxos or some other distributed
0:57
consensus algorithm well raft is just a
1:00
little bit simpler to teach hence why
1:02
it's popular and easier to understand so
1:05
doesn't that work out for all of us
1:06
bozos okay so how does raft actually
1:09
work from just like a very high level
1:11
perspective again we're building a
1:12
distributed log and what the log
1:14
actually contains is we have an
1:16
operation and and we have something
1:18
called a term number and we'll touch
1:21
into what the term number really
1:22
signifies and what it means a little bit
1:24
later in this video but the gist is that
1:26
we're going to have a leader
1:28
and the leader is asynchronously
1:30
replicating over to the follower notes
1:32
and keep in mind that this is
1:34
asynchronous replication so it is
1:35
possible for one follower to be behind
1:37
as you can see this log is not as up to
1:39
date as the one on the leader it's not
1:41
possible for all of the logs to be
1:42
behind as we'll talk about probably
1:44
mostly in the next video but yeah for
1:46
this video mainly I want to focus on one
1:49
of two steps of raft which is actually
1:51
picking which node is going to be the
1:53
leader because that in and of itself is
1:55
quite an interesting process and in
1:57
picking the leader we can kind of Ensure
1:58
a bunch of invariants about our system
2:00
that are going to be important when it
2:01
comes time to actually start making
2:03
rights
Raft Leader Election
2:04
so let's look at raft leader election
2:06
and how does it work so basically our
2:09
raft leader which we can see right here
2:11
on the left of the screen has something
2:12
called an epoc number and in addition to
2:15
that we'll we'll touch more upon what
2:17
this Epoch number actually means but as
2:19
a result of just kind of how raft Works
2:22
we're going to be constantly sending
2:23
heartbeats or pings over to our
2:25
followers on some interval and basically
2:28
eventually you know if this guy decides
2:30
to go down one of our followers is going
2:32
to say hey I haven't received heartbeats
2:33
anymore it's time for me to complain
2:35
obviously we don't want them all
2:36
complaining at the same time because
2:38
then it's just going to be bad for our
2:39
system we're going to have a lot of
2:40
network traffic a bunch of other stuff
2:42
so let's say you know we randomize the
2:44
amount of time it takes for each
2:45
follower to complain this guy will
2:47
complain after 10 seconds this guy will
2:49
complain after five seconds
2:50
so obviously because the bottom node is
2:52
going to complain sooner than the top
2:54
one it is going to be the one that
2:56
ultimately proposes a new election it's
2:58
going to say hey I haven't heard from
2:59
the leader in a little bit so let's
3:01
start a new election and what about me
3:03
as the candidate so what this guy is
3:05
known as is the candidate
3:08
and as you can see because the epoch
3:10
number before of the previous leader was
3:12
28 this guy is going to say okay well I
3:14
am candidate for term 29. and so that is
3:18
going to be how the election actually
3:19
gets started so what happens during the
3:22
election let's scroll on to our next
3:24
screen here this one has a lot going on
3:25
so I'm going to try and show it all
3:27
properly so there are a few actual
3:29
possibilities of things that can happen
3:31
and I'm going to show them all off so
3:33
let's say this is the candidate right
3:34
here over on the top left
3:37
so the candidate is now going to propose
3:39
a term number 29 and let's say it's got
3:41
a log like so where it has two
3:43
operations and you can see the epochs
3:45
that those operations were written from
3:46
so let's say the message actually gets
3:50
to the previous leader right if the
3:52
previous leader receives message from a
3:55
potential candidate saying hey you're no
3:57
longer the leader well then the only
3:58
thing that that leader can do is say
4:00
shoot I guess I'm no longer the leader
4:01
so it's going to change its status to a
4:03
follower for term 29. another
4:05
possibility of what's going to happen is
4:07
that the node that receives this kind of
4:09
proposal
4:10
is just going to be a follower from a
4:13
previous Epoch and what that's now going
4:15
to do is even still as long as basically
4:17
the term number is going to be lower
4:20
than the one being proposed it's going
4:21
to increment its local term number to
4:24
the term number of The Proposal even
4:26
still it doesn't necessarily have to
4:27
vote for the candidate yet but it does
4:30
need to increment its number to that
4:31
term and we'll see why and then next
4:34
another possibility is that you know if
4:37
we go to a node with a higher term
4:39
number a greater than or equal to term
4:41
number than the one being proposed so in
4:43
this case it's a follower from term 29.
4:45
that implies that there was already a
4:47
leader for term 29 and if there was
4:49
already a leader for term 29 then we are
4:51
going to go ahead and say no to our
4:53
candidate over here so that is why we
4:55
have this no operation over here as you
4:57
can see we've already processed a write
4:59
during this term
5:00
and then finally another possibility is
5:03
that we reach out to a follower from
5:05
term 28 and the follower is going to say
5:07
oh okay well I can see there's a new
5:09
election going on let me change my term
5:10
number to turn 29 and because
5:13
your log here's the follower log right
5:16
down here here is the candidate log
5:18
because the candidate log is greater
5:20
than or equal to as updated as my local
5:23
log I am going to respond yes and it's
5:26
very simple basically if you have a term
5:29
number that was equal to the term number
5:31
being proposed or rather if you have a
5:33
term number that was lower locally than
5:35
the one being proposed and the log that
5:37
you have locally is either the same as
5:40
the one being proposed or it is less up
5:42
to date then you can go ahead and say I
5:44
will give you my vote otherwise you will
5:46
not give them your vote but you will
5:47
still of course update your term number
5:49
to the one being proposed if it's higher
5:52
than your local term number so a lot of
5:54
steps yeah but hopefully that generally
5:55
makes sense okay so what actually
5:58
happens when the candidate receives some
6:00
votes well if they hear yes from a
6:02
quorum
6:03
keep in mind from our leaderless
6:04
replication videos that means a majority
6:07
of notes it has won the election and it
6:09
can be a leader
Why does it work
6:11
so why does this system actually work
6:13
for you know kind of ensuring the
6:15
Integrity of our logs such that we can
6:17
make sure that we only have one leader
6:18
at once well for starters we obviously
6:21
cannot elect two leaders at the same
6:22
time because of quorums if we have three
6:25
nodes you know say I get these two votes
6:27
I can't also get these two votes because
6:29
there's overlap between them so a quorum
6:32
is not going to solve our issues there
6:33
in addition uh for number two old
6:36
leaders cannot come back due to this
6:39
fencing token slash Epoch number what is
6:42
a fencing token well the fact that we
6:44
have this Epoch number basically means
6:46
that if an older leader proposes a right
6:48
with a lower Epoch number than the
6:50
current term we know that it is an old
6:53
leader and it shouldn't be proposing
6:54
rights and then we can say I'm not going
6:56
to accept this that's called a fencing
6:58
token that is a term used in distributed
7:00
systems where basically you assign a
7:02
number to the current leader and that
7:04
way if an older leader tries to do
7:05
something you can say well it's got a
7:07
lower fencing token I don't care about
7:08
this and then finally the leader has an
7:11
up-to-date log and it can backfill stale
7:14
nodes so if you have a node that
7:16
basically is not completely up to date
7:18
in its log and the current leader goes
7:21
down so it's not able to basically fill
7:22
it up you know that the new leader is
7:24
going to take over and have an
7:26
up-to-date log and that way it can
7:28
actually go ahead and you know kind of
7:30
get the other nodes up to speed which is
7:31
a good thing if it is completely
7:34
possible that you would have another
7:36
node basically that is more up to date
7:38
than the leader however if that node is
7:41
more up to date than the leader it means
7:43
that that write must not have gone to a
7:45
majority of the nodes because if it had
7:47
gone to a majority of nodes then the
7:49
leader could not have been elected in
7:51
the first place recall that the leader's
7:52
log needs to be more up to date or equal
7:54
to a majority of nodes so any write that
7:57
is basically more up to date than the
7:59
leader can't be on a majority of nodes
8:00
hopefully that makes sense not that
8:02
important for the proof but interesting
8:04
stuff nonetheless so again this is a
8:06
pretty short video because mainly I want
8:08
to cover these two fundamental steps of
8:09
raft where the first one is leader elect
8:11
the second one of course is where once
8:14
we have a leader we actually start
8:16
broadcasting some rights and that's not
8:18
too complicated either but I think that
8:20
it makes a lot of sense in order to kind
8:22
of break these down into manageable
8:23
chunks because there is a lot of
8:25
thinking to be done to kind of wrap your
8:26
head around these topics and why they
8:28
actually work and Achieve consensus so
8:31
guys I hope you enjoyed the video talk
8:33
to you in the next one and have a good
8:35
rest of the weekend

##v30:

0:00
hello Giga Chads and welcome back to the
0:02
channel uh last video I blue balled you
0:05
guys harder than Margot Robbie and the
0:07
Wolf of Wall Street by only finishing
0:09
half of raft so today why don't we be
0:11
better than her and finish off the rest
0:13
of it let's go ahead and get into things
0:15
okay so let's get started so starting
0:18
off with this video I'm just gonna do a
0:20
quick overview of raft rights or more so
0:23
I guess just the setup for this type of
0:24
thing so as we recall from last time
0:27
there's a leader all the rights are
0:29
going to be going through that leader
0:30
and then we've also got some followers
0:33
and the key thing to note here is that
0:35
in a follower there's not necessarily a
0:37
guarantee that every single follower in
0:39
raft is going to have the most
0:41
up-to-date lock a certain amount of them
0:43
must and we'll touch upon why that's the
0:45
case however it is possible that you
0:47
have an behind follower like this guy
0:50
right here where the log is technically
0:52
stale because it doesn't include both
0:54
the operation and term number for a
0:57
given index as you can see the actual
0:59
operation and term numbers of the leader
1:01
look like this and so we're missing c22
1:04
which means that in the 22nd term so
1:07
meaning this leader right here we wrote
1:09
C in that uh basically area of the log
1:12
so
1:14
what does that actually mean about raft
1:16
rights well not only do rights have to
1:19
actually write to the log but more
1:21
importantly they also have to be able to
1:24
backfill the log so let's go ahead and
1:26
talk about how they would do that so as
1:29
you can see let's start on the left over
1:31
here we've got a leader and we have a
1:34
follower which has a non-up-to-date log
1:37
so let's imagine that the leader has
1:39
this right here on the left where this
1:43
is representing again the operations on
1:45
the top and the epoch number of the
1:47
leader that wrote them on the bottom and
1:51
similarly that means the follower is
1:53
just starting with this right here where
1:55
you have from the 20th term D was
1:57
written so something like that is
1:59
possible if this were a previous leader
2:00
that died in the middle of a right or
2:03
even just a follower of a right that
2:05
didn't go completely through the point
2:07
is we have to overwrite this incorrect
2:08
value and also write the new values as
2:11
shown right here
2:12
so like I mentioned rights in addition
2:16
to just writing the new value also
2:18
backfill logs so let's now talk about a
2:22
special invariant in raft that is very
2:24
important to keep the correctness of
2:26
this entire algorithm so it is going to
2:29
rely on a couple of facts one there is
2:32
only one liter per term we covered that
2:34
last video the reason there's only one
2:36
liter per term is because we need a
2:37
quorum of nodes to be elected leader and
2:40
within a term you can't obviously have
2:43
two quorums agreeing on the leader so
2:45
again one liter per turn additionally
2:48
like I just said before rights back fill
2:51
log any successful write that goes
2:54
through to a follower is going to
2:56
absolutely fill the log fully up to date
2:59
so what that means is that let's say we
3:02
have a leader and a potential follower
3:04
that we want to write to if those two
3:06
logs on the leader and the follower have
3:09
the same term number at the same index
3:11
they must be identical prior to that
3:14
index so let's say this is index I don't
3:17
know 10 and this is index 11 in this log
3:20
of the leader and then over here we've
3:23
got index 10 and index 11 on the log the
3:26
follower because index 10 has the same
3:29
term number
3:31
on both the leader and the follower we
3:34
know that everywhere to the left of
3:36
index 10 and everywhere to the left of
3:38
index 10 on both the leader and the
3:40
follower must be the same and the term
3:43
that we use to describe this part of the
3:45
log in raft is called the prefix at the
3:48
same time you can see that they start to
3:50
differ on the index right after that and
3:52
as a result we call this area the suffix
3:55
so these are two terms to keep in mind
3:57
but the point is keep this invariant in
4:00
your head if two logs are the same at a
4:03
given point they must be the same
4:05
everywhere before that point because
4:07
rights backfill logs and there is only
4:10
one liter which means that it is
4:13
inherently going to be the same leader
4:15
that wrote this index so it's going to
4:17
be the same leader that wrote all of the
4:19
log before it if it was out of date
4:22
okay
4:24
now that we have covered that let's look
4:26
at how rights actually work
4:28
so we're going to start with a leader
4:31
right here who is going to propose a
4:32
right
4:34
because it gets it from some client
4:38
and the client can just send that right
4:40
right over to the leader easy stuff okay
4:43
so the leader says I have the following
4:46
right c21 meaning that
4:49
basically I am c21 in the position that
4:54
is highest in the log up to this point
4:56
so that's right here
4:58
I have this as my most recent entry at
5:02
index 2 because this is 0 1 2.
5:06
and then now in addition to that right
5:08
d22 so the first thing that it's going
5:11
to do is send this to the top replica
5:13
over here and the top replica is going
5:16
to project this right why because it
5:19
doesn't actually have
5:20
at 0 1 2 it doesn't have c21 so it's
5:25
going to say no I don't agree with you
5:27
up to this point you cannot send me the
5:29
right please try again
5:31
and so now what the leader is going to
5:33
do is it's going to try again but like
5:36
so it's going to move the index one back
5:38
so instead of trying to say here I have
5:41
c21 it's going to say hey I have B20 so
5:45
my prefix is going to be B20 and the
5:48
suffix is c21 and d22 and then it's
5:52
going to send that over right so prefix
5:56
is going to be a B20 and then the suffix
6:00
is going to be C and D
6:03
and then this time around because of the
6:05
fact that they agree on their prefixes
6:07
we know that the follower and the leader
6:09
have the same log from B20 and before so
6:13
we only have to send over our suffix and
6:16
the reason this is useful the reason we
6:18
do this whole thing instead of just
6:19
sending the whole log in the beginning
6:21
is because of the fact that it just
6:23
saves a ton of network latency if we had
6:25
to send the whole log every time we
6:26
would be sending a ton of data over the
6:28
network so instead what we just send is
6:30
the suffix and now this guy can actually
6:33
respond yes instead and so the leader
6:36
says okay I've adjusted what rights I'm
6:38
sending to you I'm good to go
6:40
additionally it is now also going to
6:43
send out c21 like before
6:46
as the prefix
6:48
and d22
6:51
as the suffix to this bottom node since
6:54
the bottom node has already been
6:55
backfilled sufficiently it already has
6:58
c21 at index 2. we can go ahead and
7:01
respond yes right here and the leader
7:04
can keep track of that so basically how
7:06
this works is like so if the leader
7:08
hears yes from a quorum of nodes it can
7:11
commit that right locally and it can
7:13
also tell the other nodes to commit that
7:16
right until then it's like a two-phase
7:18
commit where you know once you respond
7:20
yes for the first time you're waiting
7:22
you have the right locally but it's not
7:24
committed and then finally once you hear
7:26
back saying commit
7:29
then you go and do d22
7:33
so it's pretty simple stuff actually the
7:35
whole point here is that for a right to
7:37
survive it needs to go to a majority of
7:39
nodes and that allows us to keep our
7:41
invariant intact as long as we have a
7:43
right on a majority of nodes it means
7:45
that any leader that gets elected in the
7:47
future will have that right why because
7:50
a leader needs a majority of nodes to
7:52
get elected and when you have a majority
7:54
of nodes that are willing to elect you
7:56
because your log is equally or more up
7:59
to date than theirs that means that the
8:01
leader's log must include every single
8:03
right that has been committed hence why
8:06
this thing is considered technically
8:08
correct
8:09
so let's talk about some conclusions of
8:12
raft because obviously it is a
8:15
complicated system and it has its uses
8:17
so one raft creates fault tolerant
8:20
linearizable storage the entire point of
8:22
this thing is to build this guy right
8:24
here a distributed lock because when we
8:27
can order our rights and we can make
8:29
sure that those rights are never going
8:30
away we have a ton of super useful
8:33
properties of our database that allows
8:35
us to ensure correctness and build
8:37
systems on top of that those are going
8:39
to be for future videos but I'm looking
8:40
forward to covering those another thing
8:42
is that raft is slow going back to the
8:45
previous diagram everything has to go
8:48
through our single leader All rights and
8:51
depending on the raft implementation all
8:53
reads as well and so if that's the case
8:55
it means that you're basically
8:57
bottlenecked by one single node even
8:59
though your system is correct and even
9:01
though it's fault tolerated it's not
9:03
performing which means you don't want to
9:05
generally use something like raft as a
9:07
kind of General database implement
9:09
education for your application it's
9:11
better as a very specific kind of
9:14
nuanced piece of your application for
9:16
code that specifically needs to be
9:18
correct
9:19
and then finally even though raft is
9:22
Fault tolerant it does not replace
9:24
two-phase commit so recall that
9:26
two-phase commit is one where instead of
9:28
needing the majority of nodes to say yes
9:31
we need every single node to say yes and
9:34
so if a node says no
9:37
things are not going to go through this
9:40
right is not going to happen why does
9:42
rafts not replace two-phase commit
9:43
because raft is made to create a
9:46
distributed lock where the distributed
9:48
log is equal on every single system on
9:50
the other hand two-phase commit can
9:52
actually deal with heterogeneous rights
9:54
meaning that as opposed to just making a
9:57
log although you could and it's not very
9:59
fault tolerant so you probably shouldn't
10:01
you can actually send different rights
10:03
to different nodes and what that allows
10:05
you to do is something like cross
10:07
partition
10:09
distributed transactions
10:12
so feel free to watch the sharding video
10:15
but the point is oftentimes if you need
10:17
to make two different rights to two
10:19
different partitions you would have to
10:21
use something like two-phase command now
10:23
again you could use two-phase commit
10:25
combined with raft if you wanted to use
10:28
raft to basically deal with your
10:30
replication to be strongly consistent
10:32
there but even still you are eventually
10:35
just going to have to deal with
10:36
two-phase commit at some point
10:38
so yeah that is pretty much all for this
10:42
video guys
10:43
I am extremely tired as per usual
10:46
whenever I make a video on the weekday
10:48
so I am probably going to knock the
10:50
out but I will see you guys in the next
10:53
one

##v31:

0:00
hey guys welcome back to the channel So
0:01
today we're going to be talking about
0:03
coordination Services which should
0:05
really wrap up this whole concept of
0:06
consensus and once we're done with this
0:08
video allow us to compare and contrast a
0:10
bunch of different database Technologies
0:12
and you know just really understand why
0:14
it is that they perform the way that
0:15
they perform I don't think the video
0:17
should be more than a couple minutes
0:18
long which you know if you ask me
0:20
personally is a pretty long time I don't
0:22
know my ex-girlfriend might not agree
0:24
but that is an argument for a different
0:25
day so let's go ahead and get into it
What is Coordination Services
0:28
all right so like I mentioned today
0:29
we're going to be talking about
0:30
coordination services so there's not a
0:32
ton of technical content to cover in
0:34
this video the reasoning being that we
0:35
just did it in the last
0:37
two coordination services are basically
0:39
just thin layers that are built on top
0:42
of some distributed consensus algorithm
0:44
like raft in order to basically help us
0:46
with all of this configuration that we
0:48
need within our distributed backend so
0:51
what type of configuration could that be
0:53
well we have IP addresses for things
0:55
like our servers our databases our load
0:57
balancers our CDN anything along those L
1:00
are replication schema what database is
1:02
sending rights to which where are those
1:05
databases located who is the leader
1:07
currently all super important stuff and
1:10
then also something like a partitioning
1:12
breakdown what partitions are located on
1:14
which node what range of keys does that
1:16
include or what hash range of keys does
1:18
that include we have tons of
1:19
configuration that if we were to mess it
1:22
up via you know something that allowed
1:24
us to have right conflicts or race
1:26
conditions or just stale reads in
1:28
general then obviously viously the
1:30
basically correctness of our service
1:32
would be hugely jeopardized and this
1:34
would be way more you know kind of
1:36
damaging to our user base than
1:37
potentially one single lost comment so
1:41
kind of the the logic here is that even
1:43
though consensus is slow for things like
1:45
uh the configuration of our application
1:48
we're willing to make that trade-off
1:49
because it's extremely important to get
1:51
it right so the typical pattern that you
1:53
would use is you would put this
1:54
configuration in something like a
1:56
coordination service which again is just
1:58
a small key value store and then for
2:00
your actual application data you know
2:02
user Post history comments anything like
2:05
that you would use a different type of
2:06
database that itself may be relying on
2:09
the coordination service to be correct
2:12
so what are some examples of modern-day
2:13
coordination Services well the two that
2:15
you've probably heard of or at least may
2:17
sound familiar would be zookeeper or
2:20
etcd uh etcd or whatever it's pronounced
2:23
uh runs on raft zookeeper runs on its
2:25
own thing called Zab that's similar to
2:26
Raft but the point is they're using
2:28
distributed consensus so if there is any
Technical Content
2:31
technical content in this video it would
2:33
basically just be how reads work because
2:35
we've covered how wrs and leader
2:37
election work in consensus but how will
2:39
we actually read the data to make sure
2:41
that we're getting linearizable reads
2:43
because if I were to write a piece of
2:44
data and then not be able to read it
2:46
right after from some replica that would
2:48
be problematic that would make our
2:50
application prone to incorrectness and
2:52
cause problems down the line so like
2:54
I've mentioned multiple times now we
2:55
were built on top of some distributed
2:56
consensus layer and if you remember from
2:59
me drawing drawing this pretty much for
3:00
the last three or four videos that
3:02
basically means that we've got some sort
3:03
of leader and then a couple of follower
3:05
nodes and the follower nodes are not
3:08
necessarily completely up to date right
3:10
as you can see on the bottom here this
3:12
follower node is a bit behind so that is
3:15
a possibility in all of our distributed
3:17
consensus algorithms but there are still
3:19
ways to make sure that your reads are
3:21
linearizable what we don't want is a
3:23
client making a read right here so this
3:25
would be read one where we see xal 5 and
3:28
then that X equal 5 is it index one in
3:31
the log right because we go 0 1 2 and
3:34
what we don't want is for our client to
3:36
then go ahead and read from the node
3:39
that's behind over here and then see xal
3:43
3 because then our reads would not be
3:45
linearizable we can't be having that so
3:48
what can we do to avoid this situation
3:50
well we've got two easy options one we
3:52
can always just read from the leader
3:54
that's a super easy option however it
3:56
comes at the price of well if we're
3:58
always reading from the leader that
4:00
means that all writes and all reads are
4:02
going through the leader and that is
4:03
going to be slow another option is that
4:07
sometimes we can actually read from
4:08
different follower nodes the key thing
4:10
to note is that again we want those
4:12
reads to be linearizable so how can we
4:14
ensure that they actually are well at
4:16
least in Zookeeper there's some
4:17
functionality called the sync keyword so
4:20
again we have our client here let's
4:22
imagine that we read from the leader and
4:24
the re the leader is going to uh
4:26
basically report back that X is equal to
4:27
5 and that is an index one of the log
4:31
right like you're updated to index one
4:33
so what the leader or basically what the
4:35
client would then go ahead and do is
4:37
they say okay well I want a read from
4:39
this guy but I'm afraid that the data
4:41
there is stale and my read is not going
4:43
to be linearizable so I'm going to write
4:45
a keyword sync into the log and you can
4:47
see that goes over here at index 2 and
4:51
so sync is now going to get
4:53
propagated to these
4:56
nodes and so now since the client knows
4:59
that it's seen index one until it
5:01
actually reads back and now you know
5:03
eventually some more time passes and
5:05
this guy gets filled up to date blah
5:07
blah blah blah
5:08
blah and until it reads back and sees
5:12
sync at index
5:15
2 it knows that the data on the follower
5:18
node that it wants to read from is stale
5:20
once it does see sync then it can start
5:22
reading from that follower and you can
5:24
basically keep reading from that
5:25
follower until you either make another
5:27
right or until you BAS basically go
5:30
ahead and switch reading from a
5:31
different follower so yeah the fact that
5:34
you can do this means that we can have
5:36
greater read through put because once we
5:38
sync once we're going to start being
5:39
able to make linearizable reads from
5:41
that follower node and as a result of
5:43
being able to do that we take some of
5:45
the stress off of our leader so this
5:47
does allow us to have a little bit
5:49
greater of a read through put so let's
Conclusion
5:51
quickly do a conclusion for coordination
5:53
Services basically they're too slow to
5:56
be used for most of our application data
5:58
in a real massive service like Facebook
6:00
or Twitter or anything like that if
6:02
you're sending all the rights through a
6:03
single leader and basically that has to
6:06
effectively go through some sort of
6:07
two-phase commit we're running into some
6:09
serious performance problems that
6:11
probably are not going to be feasible
6:13
for the scale of our application at the
6:15
same time all of these apps have key
6:17
pieces of configuration which we
6:20
mentioned before are backend needs in
6:22
order to be able to run we need to know
6:24
the location of all of our nodes in our
6:26
cluster we need to be able to know what
6:28
data is stored on what partition things
6:29
like that and if we don't have that in a
6:31
reliable setting in a way that you know
6:34
we can access it and be sure that it's
6:36
correct then we're running into some
6:37
serious issues as well so typically the
6:40
solution would be to use something that
6:42
is a bit more scalable for application
6:44
data but then something like
6:45
coordination service for this
6:47
configuration and of course the reason
6:50
why we can rely on it is because it is
6:51
built on top of consensus algorithms
6:54
being able to read in a linearizable way
6:56
means that we can be sure that the data
6:58
that we're reading even though it could
7:00
technically be a little bit outdated
7:02
either a we could always read from the
7:03
leader or B at minimum our reads are
7:06
going to be linearizable so we're never
7:07
just going to like be jumping backwards
7:09
all of a sudden and seeing some previous
7:11
state that we weren't already aware of
7:13
and thinking it was more up to date than
7:15
our current state anyways guys I hope
7:18
that this helps understand what
7:19
coordination services are actually used
7:21
for only just a little bit of a pit stop
7:23
from you know continuing to talk about
7:25
databases and then in the next video we
7:27
will do just that yet again see you guys
7:30
then

##v32:

0:00
hey everyone and welcome back to the
0:01
channel so in today's video I've
0:03
completely click baited you guys because
0:05
I said I was going to be talking about
0:06
SQL versus nosql databases however if
0:09
you've watched kind of the first
0:10
iteration of my system design videos
0:12
you'll know that I really don't like
0:14
those terms the reason being that just
0:17
kind of generalizing about a database
0:18
based on its query language is stupid
0:20
there are plenty of SQL databases that
0:23
do act a certain way but there are many
0:24
other implementations of databases that
0:27
use SQL that act very differently and
0:29
the same goes for databases that don't
0:31
use SQL as their query language hence
0:33
why I don't like the term SQL and nosql
0:35
what I prefer to use instead is
0:37
relational and non-relational databases
0:40
so let's go ahead and talk about those
0:42
discuss the differences and then move on
0:44
to subsequent videos where we can look
0:45
at actual real world examples of
0:48
databases okay so we're going to start
Relational Databases
0:50
by talking about relational databases
0:52
what are they now you definitely may
0:55
think of a database like MySQL or
0:57
postgres when I'm talking about
0:58
something like relational databases and
1:00
if you do you are correct however MySQL
1:04
and postgres have other stuff going on
1:06
between them other than the fact that
1:08
they just are relational databases which
1:10
is why I'm going to keep this video
1:12
pretty General and then make dedicated
1:14
videos for each type of database so what
1:16
is a relational database well basically
1:18
the whole point of these are we have a
1:20
bunch of different tables where each
1:22
table represents one type of data model
1:24
so let's imagine I'm talking about
1:26
trains and stations because trains and
1:28
stations have relationships between them
1:30
so as you can see in the trains table
1:32
I've got red line Blue Line pink line
1:34
and the stations I've got Broadway
1:36
Yankee Stadium and your mom because I
1:39
can't resist the low-hanging fruit of
1:40
making a your mom is getting trained
1:42
joke so then of course what aspect of
1:44
this involves relationships well we know
1:46
that a train can be at multiple stations
1:49
and a station can have many trains going
1:51
to it and so as a result what we have
1:53
here is actually a many-to-many
1:55
relationship and so that is exemplified
1:57
by the train stations table and what
1:59
we're using are something called
2:02
foreign ideas sorry for the siren that's
2:05
just Chicago for you so we have foreign
2:07
IDs and what the those basically say for
2:10
us
2:10
are it creates the relationships between
2:12
two rows of two different tables or they
2:15
could even be in the same table if we
2:16
really wanted to but basically this row
2:18
right here is saying uh train with
2:22
ID one at station
2:27
id1 so it's saying that the red line
2:30
stops at Broadway and what this is
2:32
called is called normalized Data because
2:34
for each piece of data that we want to
2:36
represent we just put it in our tables
2:38
once and then using foreign Keys we can
2:40
establish relationships between them in
2:42
SQL we could leverage something like the
2:44
join keyword in order to basically take
2:47
one of these things like the red line
2:49
and then merge it with keys one two and
2:51
three based on the fact that these guys
2:53
are lined up over here but again we're
2:56
not worried about the query languages
2:57
here we're more so worried about how
2:59
data is actually organized so what are
Downsides of Relational Databases
3:01
the downsides of relational databases
3:03
well mainly they just have poor data
3:05
locality so what do I mean by that well
3:07
let's imagine that all three of these
3:09
tables were in one place realistically
3:11
those tables are not going to be lined
3:13
up to one another on disk you know they
3:15
could be here and here and here and so
3:17
when I'm actually seeking I have to go
3:18
to a bunch of different places on my
3:20
hard drive but this is a distributed
3:22
systems focus and even more so a more
3:24
catastrophic case would be there on
3:27
physically different nodes in our
3:28
cluster
3:29
so what that means is we might have to
3:31
end up using distributed transactions in
3:33
order to perform rights let's say I
3:36
wanted to add a new train station and
3:39
you know we know that certain trades go
3:40
to it now I have to write to both the
3:42
stations table and the train stations
3:44
table which are on different computers
3:46
in the same right and that means that I
3:48
would have to use something like two
3:49
phase commit which is slow even if we're
3:52
not performing rights if I simply want
3:54
to perform a join now I have to read
3:56
from the trains table the stations table
3:58
and the train stations table and as a
4:01
result of that my reads are going to
4:02
multiple different systems that's just a
4:04
lot of extra latency and so distributed
4:07
reads are also going to be slow
4:09
so what can we do to actually go ahead
4:11
and mitigate the cost of having poor
4:13
data locality well we could organize our
4:16
data differently so that we have better
4:17
data locality and the way we would do
4:19
that is with a non-relational database
4:21
so traditionally most nosql databases
4:24
are non-relational however that's not
4:26
always the case which again is why I
4:28
don't love the term nosql but if you see
4:31
it that's probably what they're talking
4:32
about so instead of using normalized
4:35
data no sqlized databases use
4:37
denormalized data which means that we're
4:39
keeping our data effectively in
4:41
something called records just think of
4:42
it as a key value store or something
4:44
similar to that
4:46
and as opposed to you know having
4:48
relationships where one row can
4:50
explicitly reference another we actually
4:52
keep all of the data that we need in
4:54
every single record so imagine that the
4:57
keys were the train names now all of a
4:59
sudden the values are all of the
5:00
stations so you can see your mom is
5:02
repeated for the red line blue line and
5:05
Brown Line because it is a station that
5:07
all three of those trains go to so now
5:09
we do have better data locality but
5:12
obviously that has to come at a cost
5:13
right we have repeat data and so what
5:16
are the trade-offs of something like
5:18
this well for starters we do avoid cross
5:20
partition reads right because let's say
5:22
I wanted to know all of the stations
5:25
that the red line stops at it's all
5:27
stored right together which is great
5:28
however this comes at a big cost which
5:31
is that if I wanted to say hey your mom
5:33
is out of commission for the week I
5:36
don't know maybe uh she's been having
5:38
too many trains then we're going to have
5:40
to remove that from three places and
5:42
that right there might be a distributed
5:44
transaction in and of itself because all
5:47
three of those deletes need to go
5:48
through so it's important to note that
5:51
rights can be extremely complicated if
5:53
you have to modify the same thing in
5:55
multiple places because the data is
5:57
denormalized instead of normalized
5:59
and then additionally let's imagine that
6:02
this contained a bunch of extra data
6:04
right here depending on the type of
6:06
non-relational database it's possible
6:08
that you may have to load all of that
6:10
other data instead of just the portion
6:12
that you want whereas in SQL you can
6:14
typically just grab the rows that you
6:15
want and any other relationships that
6:17
you need you would explicitly use the
6:19
join keyword to fetch them the point is
6:21
that you may have a little bit less
6:23
flexibility in terms of how much data
6:25
you have to load and send over the
6:27
network but I think there are actually
6:29
certain databases that will let you make
6:31
that a little bit more granular so you
6:32
can send a bit less
6:34
so what's our conclusion here again I
6:37
don't want to basically assume any
6:40
particular type of locking or database
6:43
index type usage or replication schemas
6:46
or anything along those lines because
6:48
the truth is there are many many
6:49
different types of relational databases
6:51
there are many many different types of
6:53
non-relational databases so even though
6:55
I could go ahead and say like oh you
6:57
know generally relational databases use
6:58
B trees that's not completely true and
7:01
it would be misleading to say such a
7:03
thing that's why we're going to go
7:04
through specific databases so what is
7:06
the general case where you actually want
7:08
to be using non-relational databases
7:09
versus relational ones well when there's
7:12
non-relational data if your data is all
7:15
disjoint right and I can keep it as
7:17
separate messages or separate records
7:20
within a database table and they don't
7:22
really relate to one another at all
7:23
think about like separate I don't know
7:25
Facebook posts I don't really ever have
7:27
a relationship from one Facebook post to
7:29
another Facebook post they're completely
7:31
separate different users post them at
7:33
different times and things like that and
7:35
so they're good to just be their own
7:36
tables at the same time if I wanted to
7:40
basically represent a relationship in my
7:42
data let's say we've got a bunch of
7:43
different books
7:45
right and each book could be pointing to
7:48
a separate author
7:49
author one or author two that's a good
7:53
example where you may want to use a
7:55
relational database because we have data
7:57
that is naturally well represented by
7:59
relationships so of course when choosing
8:02
a database you need to really think
8:03
clearly about how the organization of
8:06
your data is going to look and then
8:08
making that decision between a
8:09
relational or a non-relational database
8:12
is oftentimes going to be the first
8:13
decision that you need to make anyways
8:16
guys hope you enjoyed this video I will
8:17
see you in the next one and uh yeah have
8:19
a good week

##v33:

0:00
hey guys and welcome back to the channel
0:01
sorry for the delay on my end making new
0:04
videos I've been traveling a little bit
0:05
uh just like back home for the week and
0:08
uh just had a ton of errands my ceiling
0:10
is leaking a bunch of water got all over
0:12
my tech and I almost flipped a so
0:14
yeah stupid delays stuff like that
0:16
anyways let's go ahead and get into this
0:19
video
MySQL vs PostgreSQL
0:20
all right so today we're going to be
0:21
talking about SQL databases so just
0:24
before I really get into things as a
0:26
quick 30 second cautionary rant please
0:28
skip over this if you don't care I am
0:30
going to make a lot of generalizations
0:32
about both MySQL and postgres in this
0:35
video and the truth is these are
0:36
technologies that are open source
0:38
they're constantly changing and pretty
0:41
much anything I say about them is
0:44
pretty much falsifiable like
0:46
objectively even though I'm going to say
0:48
certain things about these Technologies
0:49
they change literally all the time and
0:52
in addition to that people are just
0:53
adding garbage features to them all the
0:55
time so I might say that you know you
0:56
tend to do one certain type of
0:58
replication with them but the truth of
1:00
the matter is probably all different
1:01
types are supported because they're open
1:03
source and some Bozo at some point in
1:05
time was like I want to do later list
1:06
replication with my sequel don't know
1:08
why you would but they probably did it
1:10
so let's go ahead and get into things
1:13
talk about this and get started so SQL
1:15
databases we went over these in the last
1:17
video and we know that they're good for
1:19
relational data normalized data where
1:21
you basically want to have one reference
1:22
to your piece of data and have it stay
1:24
consistent throughout all of your data
1:26
you don't want to denormalize your data
1:28
where you'd have to potentially have
1:29
multiple copies of a given right and
1:31
then that would be problematic in terms
1:33
of you know having to write to your data
1:34
multiple times you might even need
1:35
distributed transactions if you want to
1:37
guarantee correctness of all of your
1:39
data
1:39
so just as an example of that we've got
1:41
our people table we've got our
1:42
attractions table as you can see I'm
1:45
primary ID number one Jordan and then we
1:48
have three lovely ladies over here who
1:50
are all attracted to me checks out
1:52
pretty consistent with real life the
1:54
question is though and we started to
1:56
talk about this last video obviously we
1:58
want to be using a relational database
2:00
table when we have relational data that
2:03
should be normalized but are there ever
2:04
cases where we should do it even when we
2:07
don't care about having relational data
2:08
and my answer to that is yes albeit only
2:11
sometimes so let's talk about why we
SQL Architecture
2:13
would based on the architecture of both
2:15
MySQL and postgres and just other
2:17
relational databases in general so
2:20
generally speaking because SQL databases
2:22
are a little bit older than nosql ones
2:25
they were kind of the predominant type
2:27
of database from like the 1980s onwards
2:29
they tend to use slightly older
2:31
architectures and I guess that has
2:33
certain performance uh kind of
2:35
characteristics at least in theory in
2:37
practice there are all sorts of random
2:39
optimizations and edge cases that all of
2:41
these different types of databases have
2:42
implemented and so you know to actually
2:44
go and be like oh you know this thing is
2:46
going to have this many transactions per
2:48
second because it uses a b tree or an
2:50
LSM tree I won't do that I can't do that
2:52
I would be a sham if I tried to do that
2:54
but in an interview you can get away
2:56
with saying stuff like this because it
2:57
shows that you understand the concepts
2:59
so let's go ahead and do that so what
3:01
are some common features of most SQL
3:03
databases well for one they tend to be B
3:05
tree based indexes so as a quick
3:07
reminder for everyone a b tree based
3:09
index is pictured here on the right and
3:11
it's where you actually have a tree on
3:12
disk for both your reads and your rights
3:14
that you are basically directly writing
3:16
to and from in contrast to an LSM tree
3:19
and SS table based index where we have a
3:22
basically memory based tree plus a bunch
3:25
of different tables on disk reads in
3:27
theory should be a little bit faster on
3:29
the B tree because we just jump right to
3:32
our thing as opposed to an LSM tree
3:34
based table where first we check here
3:36
and then we check here and then we check
3:38
here and then we check here so again
3:40
could be better for reads could be worse
3:42
for rights in practice again tons of
3:44
software optimizations that can be done
3:46
and you would really just have to try
3:47
them out for your own setup and figure
3:49
out what is best based on benchmarking
3:51
number two single leader replication now
3:54
like I mentioned it is the case that you
3:56
can do any sort of replication with any
3:57
of these databases it just tends to be
3:59
the case that I think most people using
4:01
relational databases are using single
4:03
leader replication just because I don't
4:05
know that's kind of the traditional way
4:06
of doing it I feel like that's more of
4:08
like the Mantra of the relational
4:09
database system feel free to call me out
4:12
on this but uh no one ever does so here
4:14
we are I'm gonna say it anyway
4:16
single leader replication
4:18
multi-leader replication this guy can
4:21
have right conflicts which we can deal
4:24
with using things like version vectors
4:25
or crdts but at the end of the day that
4:28
doesn't necessarily get rid of the
4:30
conflicts it just gives us a way of
4:32
ensuring that all of our databases agree
4:34
on the result it doesn't necessarily
4:36
make the result correct whereas single
4:38
leader replication we've got basically
4:40
one bottleneck a single database that
4:42
all the rights have to go through and
4:43
thus we can achieve an ordering on our
4:45
rights finally we have configurable
4:48
isolation levels now a lot of nosql
4:50
databases and we'll touch upon this in
4:52
the next few videos don't necessarily
4:54
give you the ability to have fully acid
4:56
compliant transactions they're not
4:57
necessarily completely isolated and we
5:00
can't necessarily establish an ordering
5:01
over all of them as if they're running
5:03
on one thread on the other hand for
5:05
these relational databases you do at
5:07
least have the option to do that however
5:09
it does come at a performance cost
5:11
obviously because it involves either
5:13
locking or serializable snapshot
5:16
isolation both of which we will talk
5:18
about right now out so this is kind of
5:20
the main difference that I've decided to
5:22
pick out between my Sequel and postgres
5:24
which is that yeah obviously you can go
5:26
look at the feature sets of all of them
5:28
then you'll see that postgres has like a
5:30
few more supported index types but I'm
5:32
really trying to think of like the core
5:33
functionality of the two systems here
5:35
and you know this was kind of the main
5:37
one that I picked out their indexes are
5:39
generally similar MySQL uses nodb I
5:41
don't think postgres does but uh yeah I
5:44
picked this out sorry you're gonna have
5:45
to listen to me here so for my sequel we
5:48
use two-phase locking and two-phase
5:50
locking is where basically every single
5:51
row has locks in order to read a row in
5:54
a transaction that's read only you can
5:56
grab the lock in a shared mode but in
5:59
order to write you have to get it in an
6:00
exclusive mode and so that makes reads a
6:02
little bit more optimized than rights
6:03
that being said you still do have to
6:05
grab a lot of locks at the end of the
6:06
day and with all of those locks we can
6:09
have transactions that grab the same set
6:11
of blocks thus causing Deadlocks which
6:13
we would have to get rid of and hurt our
6:14
performance even more on the other hand
6:16
postgres uses serializable snapshot
6:18
isolation which is a bit newer of a
6:21
technology I should also mention that I
6:23
think MySQL is starting to get into this
6:25
as well but like again you know these
6:27
feature sets change all the time if
6:28
you're watching this video in a year
6:30
from now who knows how true any of this
6:31
will be so that's why I make these
6:33
sweeping generalizations which could be
6:35
wrong but either way it serves as a good
6:37
case study for our point so postgres
6:39
uses SSI which I have a dedicated video
6:42
on this if you need more information on
6:43
it but the overall summary is that
6:45
transactions will read from a data
6:47
snapshot and of course if a transaction
6:50
reads a value from a given snapshot that
6:52
by the time it's trying to commit has
6:54
since been modified by a second
6:56
transaction we need to roll back the
6:58
original and so there are going to be
7:00
some transactions that get rolled back
7:02
but this is ultimately a form of OCC
7:04
which is optimistic concurrency control
7:07
because we're not locking assuming that
7:09
everything can go wrong we're acting as
7:11
if nothing can go wrong and then when it
Conclusions
7:12
does we roll back
7:14
okay so what are the conclusions of
7:16
using SQL databases well I did click the
7:18
you guys in the sense that you know
7:20
mainly I kind of wanted to just talk
7:22
about SQL databases and I figured my SQL
7:24
versus postgres would be a better title
7:26
but the point is in addition to needing
7:29
normalized data which is a really good
7:30
use case for when you want a SQL
7:31
database another good use case is when
7:33
you just need data that has to be
7:35
correct if you need acid compliant
7:37
transactions because otherwise you could
7:39
have conflicting rights and race
7:40
conditions then you basically need to
7:43
use the SQL database most of the nosql
7:45
ones don't really support these
7:46
isolation levels again I kind of say
7:48
that take that with a grain of salt
7:49
because they can all eventually
7:51
Implement them who knows what's going to
7:53
happen
7:54
that being said when you do have to
7:55
choose between those two SQL databases
7:57
which are mainly MySQL and postgres I
8:00
feel like those are the two most popular
8:01
open source ones even though postgres
8:04
does use SSI if there are potentially a
8:07
lot of kind of conflicting transactions
8:09
to be had then that means you're going
8:11
to be doing a lot of rollbacks which
8:12
ultimately might be more costly than
8:14
just locking pessimistically so that is
8:16
something to keep in mind you have to
8:18
think about your actual data use case if
8:20
you're like building a counter and
8:21
that's the only thing your database is
8:22
doing and so every single thing is like
8:24
a read modify update cycle where those
8:27
two rights are overlapping with one
8:29
another then maybe you'd actually just
8:30
be better off with locking than rolling
8:32
back 90 of your rights so in that case
8:34
pessimistic locking could actually be
8:36
better but hopefully this makes sense
8:38
guys generally yeah if you care about
8:40
data correctness you probably want
8:42
single leader replication you probably
8:43
want acid transactions and then at that
8:46
point a SQL database mostly makes sense
8:48
the B tree versus lsm3 thing is a little
8:51
bit different I guess that's more of
8:52
like whether you care about prioritizing
8:54
first rights But ultimately it is still
8:56
something to think about too anyways
8:58
guys have a great rest of the weekend I
9:00
will see you in the next one and looking
9:01
forward to it

##v34:

0:00
what's up everyone it's your local Giga
0:02
Chad back here with his new fresh
0:06
fade haircut because every single time I
0:08
get a haircut or decide to style myself
0:11
I want to look like one of my Jewish
0:12
icons so basically this time I went from
0:14
sandbagm and freed over to Drake anyways
0:17
as you can see I'm feeling sexy and I'm
0:19
ready to talk about databases so let's
0:21
get into it alrighty so in our last
0:23
video we talked about different types of
0:25
SQL databases what I really mean is
0:28
relational databases but this is the
0:30
term that everyone uses so it is the
0:31
term that I will use in order to stay
0:33
consistent So today we're going to
0:35
introduce another term which I've talked
0:37
about in this channel in the past but
0:39
not in this series and that is going to
0:40
be new sequel so whereas our traditional
0:43
SQL databases are things like my Sequel
0:45
and postgres SQL new SQL databases have
0:48
kind of arisen during the era of nosql
0:51
databases but they've kept that
0:52
relational mentality and the reason
0:54
they've done this is because they offer
0:56
some type of extra twist to the typical
0:58
SQL database that makes them worth
1:00
discussing so today obviously based on
1:02
the title little video we're going to be
1:04
talking about volt DB and then I'll
1:05
probably do spanner which is Google's
1:07
version of a new SQL database in maybe
1:10
the next video
1:11
so the question really boils down to
1:13
this how do we speed up transactions
1:16
well if you remember from last video I
1:19
basically insinuated that MySQL does
1:21
two-phase locking where every single row
1:23
has a lock that can be grabbed in either
1:25
shared or exclusive mode
1:27
shared mode is for reading transactions
1:30
or read-only transactions exclusive mode
1:32
are for transactions that include rights
1:35
similarly postgres has serializable
1:37
snapshot isolation where you read from a
1:39
consistent snapshot the database keeps
1:41
track of the other transactions that are
1:43
also basically using that piece of data
1:46
in order to fulfill their own needs and
1:49
then if one of them commits you might
1:51
have to roll back one of those
1:52
transactions of course these are
1:55
somewhat slow and obviously they're kind
1:57
of the main bottleneck to getting better
1:59
performance within a single database
2:00
node so whole DB has actually come
2:03
around and tried something new which is
2:05
the following actual serial execution so
2:08
as opposed to you know using locking
2:10
trying to do multi-threading or anything
2:12
like that it has just gone ahead and
2:15
literally created a queue of things to
2:17
do these are our operations and they're
2:19
literally going through one single CPU
2:22
thread so the problem here obviously is
2:25
that if we've only got one single CPU
2:27
thread then the bottleneck of our system
2:29
is actually going to be the CPU
2:32
and it means that as a result of that we
2:35
need to be able to finish every single
2:37
operation as quickly as humanly possible
2:39
and so how can we actually go ahead and
bottlenecks
2:42
do that well first we need to evaluate
2:44
what our bottlenecks are other than the
2:46
CPU of course because we want to be able
2:48
to make all of those operations on the
2:50
CPU as fast as possible so hopefully two
2:53
main ones should stick out to you guys
2:56
the first being this guy right here what
2:58
is this obviously it is our hard drive
3:01
hard drives are pretty slow to write to
3:03
simply just because they're not really
3:04
part of your computer they're kind of an
3:06
add-on and it's also just a metallic
3:08
disc that literally spins around and we
3:10
have to jump around this chode thingy
3:12
and basically find where our data is
3:15
that we want and then the second one is
3:18
going to be Network latency right if I
3:21
am someone who's writing to the database
3:23
and I want to do that multiple separate
3:25
times all within the same transaction
3:27
that is going to seriously bog us down
3:29
it would be a lot better if we can keep
3:31
every single operation or every single
3:33
transaction to One Singular interaction
3:35
with the database over the network we'll
3:37
talk about how we can do that later in
3:39
the video
speed
3:40
so how do we deal with disk in terms of
3:42
speeding things up such that we can
3:44
improve our performance and avoid the
3:46
overhead associated with disk operations
3:48
well Vault DB said screw disks we're
3:52
putting every single thing in memory
3:54
it's effectively like a cache or a redis
3:56
instance really but as opposed to just
3:58
being a typical key value store it's
4:00
still a relational SQL type database so
4:03
what is the pro of doing something like
4:05
this well the biggest one that should
4:06
Stand Out is that now we have hash
4:08
indexes we can basically keep all of our
4:10
data in a hash map and that means that
4:13
we now have o of one reads and writes of
4:16
course it's worth noting that you know
4:17
just by nature of having a hash map you
4:19
keep all of your stuff in different
4:21
places on memory and as a result if you
4:23
wanted to run a range query that would
4:25
be tough for that instead you could do
4:27
an optional tree set index or a sorted
4:29
set and that would make your operations
4:31
of log n
4:33
of course as well you might be thinking
4:35
well shoot if all of our operations are
4:36
going into memory how are they going to
4:38
be durable how can we actually ensure
4:41
that if our databases to go down these
4:42
things aren't going to break well we do
4:44
have the option for a right ahead log
4:46
however of course if that log is going
4:49
to be on disk that is going to slow us
4:50
down too hence why it's optional
4:53
so what's the main con of having
4:55
everything in memory well of course
4:57
memory is expensive and what that means
4:59
is that now you cannot have as much of
5:01
it on a single node and of course that
5:03
means that if you want to have the same
5:05
size data set you need more partitions
5:07
now we've spoken about why having a ton
5:09
of partitions with a SQL database in a
5:12
distributed setting can be pretty
5:13
inconvenient it means that for a lot of
5:15
your reads and writes you're probably
5:17
going to have to be reading from and
5:19
writing to multiple places especially if
5:21
you need your data to be consistent and
5:23
accurate All rights that go to multiple
5:25
partitions are going to require
5:27
distributed transactions and thusly
5:29
two-phase commit which we know is really
5:32
slow because it requires multiple round
5:35
trips to every single database because
5:38
of course we need to basically propose
5:40
get a response
5:43
and then after that we can finally
5:45
commit so that's three trips between the
5:47
two databases so obviously two-phase
5:49
commit is really going to slow things
5:51
down we want to be running that as
5:52
infrequently as possible and if we're
5:54
constantly doing cross partition rights
5:56
that is going to be a problem
5:58
of course if you do use Vault DB the aim
6:01
should be to be doing as little of that
6:02
as humanly possible
6:04
so how can we also deal with network
network latency
6:06
latency because we mentioned that this
6:08
is a bit of a problem as well well let's
6:11
first present on the left over here the
6:14
bad case let's say we as as opposed to
6:17
the client maybe this should be better
6:18
if I represented it as the application
6:21
server
6:22
but either way the point is we're
6:24
telling the database to do something
6:26
the database responds with some value
6:28
and as a result we reach back out to the
6:30
database asking it for some other query
6:32
at the same time what we could do
6:34
instead is in advance
6:37
we could send all of that logic
6:40
to the database
6:42
you know we have our entire script here
6:44
with the conditional if else oops sorry
6:46
I got my Eraser out
6:48
we have our if else right here and as a
6:51
result now all we have to do is actually
6:54
induce the script on our database as
6:56
opposed to doing multiple round trips
6:58
and that right there is known as using a
7:01
stored procedure now stored procedures
7:04
are kind of looked down upon I think
7:06
these days simply just because you know
7:08
it's kind of hard to manage that code
7:09
it's not really treated as you know full
7:12
application code but when you are kind
7:15
of strapped your time on each operation
7:17
you do basically have to make some
7:19
sacrifices and using stored procedures
7:21
in this case is going to be one of them
conclusion
7:24
so what's our conclusion well volt DB
7:26
within an actual systems design
7:28
interview probably isn't something that
7:30
you're ever going to bring up most
7:32
likely just because your interviewer
7:33
isn't going to know about it and you're
7:34
going to sound like you're a crazy
7:36
person if you start talking about it
7:37
however it is very important as a case
7:40
study in terms of other ways that you
7:42
can achieve isolated transactions
7:44
achieving acid transaction is basically
7:47
the main bottleneck to any database that
7:49
is attempting to use them and so as a
7:52
result of that this approach of
7:54
literally running every single thing on
7:55
a single thread is very interesting of
7:57
course it makes us have to give up
7:59
certain functionality in order to be
8:01
able to do it and there are a lot of
8:03
concessions that we need to be to be
8:05
able to make but nonetheless it is worth
8:07
talking about anyways guys have a good
8:10
week and I'm looking forward to making
8:12
the video about spanner

##v35:

0:00
hey everyone and welcome back to the
0:02
channel for those of you of my viewers
0:04
who are American happy Fourth of July
0:05
weekend for those of you who are not
0:07
America is number one and uh yeah let's
0:10
learn about some systems design in the
0:12
American Spirit so I spent about three
0:15
hours preparing to make this video
0:17
because I couldn't remember for the life
0:18
of me why spanner was so special and uh
0:21
after a bit basically I finally did so
0:23
let's go ahead and talk about it
0:25
alrighty so spanner is a relational
0:27
database and the main problem that it's
0:30
going to help us solve is performing
0:32
distributed reads in a manner that is a
0:34
lot more efficient so let's go ahead and
0:37
give everyone some backgrounds so we can
0:39
all get up to speed here what is a
0:41
distributed read well in relational
0:43
databases we tend to partition our data
0:46
and frankly we even do that in certain
0:47
nosql databases but the general gist is
0:50
that there are you know relationships
0:52
between pieces of data that might be on
0:55
different partitions and as a result of
0:57
that we have to be able to basically
0:59
perform reads on both of those
1:01
partitions that keep those relationships
1:03
intact so for example let's say I wanted
1:06
to read all of these comments on both
1:08
partition a and partition B over here
1:10
and every single comment can also have a
1:13
parent and that's going to be shown by
1:14
this parent ID and so for example if I
1:17
were to read partition B I see that this
1:20
comment over here go next has a parent
1:22
comment with ID A1 where A1 is held on
1:25
partition a and that is the comment
1:27
Celtics suck so we need to be able to
1:30
make sure that we are maintaining our
1:32
causal relationship here when we perform
1:34
reads meaning that if I see this comment
1:37
right here B1 I better also see A1 or
1:40
else we're going to have a problem our
1:41
data is not going to make sense and
1:43
we're going to say what the hell is
1:44
happening
1:45
so again that's kind of the point of
1:47
this next little drawing here to Define
1:49
causal consistency in a more clear way
1:51
if we have two rights A and B and B
1:54
basically depends on right a and I have
1:57
a read from a database that contains
1:59
write B my read better also contain
2:01
write a or else my read is not causally
2:04
consistent so what's an example that is
2:07
not causally consistent
2:11
well it basically has these following
2:14
steps right here the first is that we
2:16
have a transaction one which is going to
2:17
see some comment comment one on
2:19
partition a
2:21
and then we also have partition B on the
2:24
right so the next thing that's going to
2:25
happen the second step is that we have
2:27
some transaction two which is going to
2:29
write a comment two and then in the
2:31
third step transaction three is going to
2:33
write comment three that responds to
2:36
comment two which means that 3 is
2:38
dependent
2:40
on two so there's a causal relationship
2:43
there and then finally in step four T1
2:46
is going to C comment three and it's
2:48
going to see hey this thing is dependent
2:50
on comment two and then it's going to
2:52
say well I never saw a comment two the
2:54
first time I read partition a over here
2:56
because it happened in between steps one
2:58
and step four in step two so we need to
3:01
make sure that when we do our read from
3:03
T1 and T1 is going to be reading from
3:06
here and also from here that we have a
3:09
causally consistent State between the
3:11
two of them
3:12
so can we solve this problem with
3:15
snapshots because you know you may be
3:17
thinking oh well if I take a snapshot
3:19
from one database and I take a snapshot
3:20
from the other database and they're kind
3:22
of you know the snapshots that
3:23
correspond with each other then we
3:25
should be good to go they'll be causally
3:27
consistent and yes technically that's
3:29
true however the question is how do we
3:31
know which snapshots they are because
3:33
these are different partitions the
3:35
transactions that interact on those
3:37
partitions are not ordered or maintained
3:39
in any similar grouping and as a result
3:41
of that we could have something like
3:42
transaction 101 and transaction 102 over
3:45
here and at the same time on partition B
3:47
you could have something like
3:49
transaction 25 so there's no like you
3:52
know kind of syncing of transaction
3:54
numbers that goes on between partitions
3:56
and if there were it would greatly slow
3:58
down the database so it's really hard
4:00
for us to get a sense of you know kind
4:02
of aligning these snapshots on different
4:04
databases in order to get a causally
4:06
consistent read and even if we could
4:08
eventually do that you know maybe I was
4:11
able to say oh you know snapshot 25
4:12
competition B happened at the same time
4:15
as snapshot 101 on partition a that
4:18
wouldn't even have all necessarily the
4:20
most up-to-date data it might be
4:21
causally consistent but we might still
4:23
be missing some rights that occurred in
4:25
the meantime such as write number 102
4:28
right there because we wouldn't need
4:30
that we would only say I want to read
4:31
from snapshot 101. so the point is that
4:34
would not be a sufficient solution for
4:36
this problem so what do we actually do
4:38
in practice in most SQL or relational
4:40
databases
4:41
well typically what we will do is use
4:44
locking so let me zoom in a little bit
4:46
here and so unlike before in our kind of
4:49
bad read where we did not maintain
4:51
causal consistency this time around if
4:54
you want to do a read of multiple notes
4:55
we're basically performing two-phase
4:57
locking right we're in two phase locking
5:00
readers grab
5:02
a shared lock
5:04
and so that's exactly what we're going
5:06
to do right here in Step One basically
5:08
we are going to grab the lock on all the
5:11
database rows that we're reading which
5:13
is going to basically be the entire
5:15
table because the point is we want to
5:17
read every single row on our table and
5:19
in this case that would use something
5:20
like a predicate lock in order to make
5:22
sure that no new rows can be written
5:24
and so we have our predicate lock on all
5:27
rows
5:28
and so now when transaction two comes
5:31
along and tries to write comment two it
5:33
is going to attempt to grab a row that
5:35
is already grabbed by the predicate lock
5:37
and it's going to fail and so now in
5:39
step three when T1 is going to read all
5:41
comments from partition B again it's
5:44
going to have to grab all the locks to
5:45
do so again via a predicate
5:48
and there is not going to be a fail
5:50
anymore we're going to see causally
5:52
consistent data what's the problem with
5:54
this well grabbing locks is freaking
5:56
slow not only is it slow to literally
5:59
grab blocks because that just takes
6:01
resources in terms of CPU Cycles but
6:04
it's also slow in the sense that it
6:07
prevents new rights
6:09
so if we're trying to read our entire
6:12
database right if we want to do
6:14
something like an analytical query and
6:15
we have to read our entire distributed
6:17
database we are locking literally every
6:19
single row on that database and now not
6:22
a single write can occur in the meantime
6:24
and so that is going to quite literally
6:26
stop our system from progressing every
6:28
single user is going to get pissed off
6:29
and you're going to hear a lot of
6:31
complaints so how does spanner address
6:33
this issue well spanner actually does
6:36
allow us to make causally consistent
6:38
reads from snapshots however as opposed
6:41
to using snapshots that are based off of
6:43
transaction number it actually uses them
6:46
based on timestamps so that means that
6:49
we don't have to perform any locking
6:51
because if I say you know here's a right
6:53
at 1 50 pm
6:56
get me all rights before them you know
6:58
get me all rights with the timestamps
7:00
that are less than that and that's going
7:02
to work actually so let's go ahead and
7:04
show you guys how that does
7:06
so let's imagine we've got two
7:07
partitions here partition one and
7:09
partition two and we're going to come
7:10
across some rights that have a causal
7:12
dependency
7:13
so what spanner will actually do is the
7:15
following it's going to receive a write
7:17
number one and it's going to say okay
7:20
we know that time stamps in distributed
7:22
systems are not perfect this is
7:24
something we've talked about a lot the
7:25
clocks can drift there's Network latency
7:27
all of this other stuff so what we're
7:29
going to do is assign it an uncertainty
7:31
interval where we're saying 99.999 sure
7:34
that the time stamp of the right is
7:36
within that value so in this case let's
7:38
say that value is 100 at 102. so we're
7:41
99 certain that that right came in
7:43
between time 100 and time 102. so that
7:46
time interval has a Delta of two seconds
7:49
right basically the width of the
7:51
interval is two seconds so what spanner
7:53
will actually do is it'll wait two
7:55
seconds and then commit the right and so
7:57
what that means is that the actual
7:59
timestamp that is assigned to the right
8:00
will absolutely be greater than 102
8:03
right because no matter what time the
8:05
right came in you know right comes in
8:08
between
8:09
uh 100 and 102 and any number between
8:13
100 and 102 plus 2 is going to be
8:16
greater than 102. so that's simple right
8:19
there so we know that actual time stamp
8:21
that this right is going to be assigned
8:23
is going to be greater than 102 so let's
8:26
go ahead and call that T1 for now now
8:28
let's imagine we had a second right on
8:30
partition two where the second right has
8:32
a causal dependency on the first right
8:34
so it's going to read it at some point
8:36
and then it's actually going to go ahead
8:38
and write to another partition well
8:40
first of all we know that if a second
8:42
right reads our first right it is going
8:44
to have to read it at time T1 or later
8:48
because of the fact that while that
8:51
right wouldn't have been committed
8:52
otherwise it wouldn't have been visible
8:53
so obviously it's going to be red only
8:55
after it's been committed so W2 is going
8:58
to read write one right to partition two
9:00
which again clearly happens after time
9:02
102.
9:04
so the uncertainty interval that's going
9:06
to be assigned to time W2 by a partition
9:08
two let's call it X comma Y what do we
9:12
know about X comma y well we know that Y
9:14
is obviously going to be greater than T1
9:16
this is very important we know that
9:19
since this right occurs in Real Life
9:21
After Time T1 that obviously the maximum
9:25
bound of the uncertainty interval is
9:27
going to be after T1 because it's got to
9:29
include T1 in it right hopefully that
9:31
makes sense if this write happens at
9:33
time 103 we certainly know that the
9:36
upper bound of the time interval is
9:37
going to be greater than T1 whatever T1
9:40
is so what are we going to do like
9:42
before our Delta is going to be y minus
9:45
X because that's the size of the
9:47
interval so we're going to wait y minus
9:49
X seconds and then we're going to commit
9:50
and so regardless of what this interval
9:53
is X comma y let's say we have T1 here
9:56
and now we have X comma y
9:59
and then you know who knows T2 could be
10:02
here or something once we wait x minus y
10:07
we know with 100 certainty that T2 is
10:10
going to be greater than T1 and so if
10:13
that's the case it means that any two
10:15
rights where there is a causal
10:16
dependency between them the one that is
10:19
dependent on the first right is going to
10:20
have a later time stamp than the first
10:22
right
10:23
and so because spanner established this
10:25
is invariant what it means is that we
10:27
can actually do things like this where
10:29
we say give me all rights with a
10:31
timestamp less than or equal to a
10:33
certain timestamp and we know that it's
10:35
going to be causally consistent which is
10:37
a super super useful principle however
10:40
at the same time you might be thinking
10:42
to yourself wait if all of our rights
10:45
have to weight the length of the time
10:47
interval Delta before we actually commit
10:49
them that is going to significantly slow
10:51
down the performance of our database
10:53
right well you would be right if Delta
10:55
was big if Delta is super super small if
10:58
we're very confident about the time
11:00
interval that each right is in then we
11:02
actually don't have to wait a lot of
11:03
time at all and it's not a big
11:05
performance hit so how can we be super
11:07
certain about the time interval that
11:09
every single one of our rights reaches a
11:12
database partition well what we could do
11:14
is what spanner does which is this right
11:17
here a GPS clock and so in every single
11:20
data center that spanner databases live
11:22
in we have an actual GPS clock which is
11:25
as synchronized as humanly possible to
11:28
the real time so that we can be as
11:30
accurate as possible in our timestamps
11:32
of course this doesn't remove all
11:34
uncertainty from our timestamps they're
11:36
still clock drift and there's still some
11:38
Network delay but at the same time by
11:40
making this Delta range as small as
11:42
humanly possible we go ahead and make
11:44
sure that each right is waiting a very
11:46
little amount of time so again for every
11:49
single Data Center
11:50
we have one of these clocks in there
11:53
what's the con of this well on one hand
11:55
even though when we have these kind of
11:58
clocks in every single data center we
12:00
can perform really really fast reads
12:01
without needing to lock it means that
12:04
these databases are a lot more expensive
12:06
spanner is not an open source database
12:08
it is something that you very much have
12:10
to get through Google Cloud because
12:11
you're using Google data centers and as
12:13
a result of that it is a lot more
12:15
expensive to operate one of these and
12:17
you know basically pay to have your
12:18
service running on them than it is to
12:20
just say you know take a MySQL instance
12:22
and throw it on AWS so with that in mind
12:25
even though these are super amazing
12:26
systems and super useful oftentimes for
12:29
some companies barring very very
12:31
specific and stringent performance
12:32
requirements it's not that practical
12:35
that being said I still of course find
12:37
it a cool video I think it's an
12:38
interesting topic and I definitely think
12:40
it is worth talking about hence why I've
12:42
wasted your 10 minutes of time doing so
12:44
anyways guys have a great weekend and I
12:47
will see you in the next one

##v36:

0:00
hello everyone and welcome back to
0:01
Jordan has no life my name is Jordan and
0:04
as you probably could have guessed I
0:05
have no life because I am making this
0:07
video on July 4th instead of hanging out
0:09
with my friends so I gotta go do that
0:10
after I bust this one out anyways
0:13
thinking of renaming the channel to
0:14
clickbaiters Incorporated simply because
0:16
the majority of this video is going to
0:18
be spent covering Cassandra not mongodb
0:20
which takes about 30 seconds to explain
0:22
so let's go ahead and knock that out and
0:24
get started alright so as promised I
MongoDB
0:27
mentioned that we were going to talk
0:28
about mongodb first so let's go ahead
0:30
and do that so mongodb is one of those
0:33
databases that I think in you know kind
0:35
of actual like pragmatic scenario is
0:37
pretty easy to use it's well documented
0:39
it's got a lot of nice features that
0:41
make it good as developer but at least
0:43
from like a systems design interview
0:44
perspective
0:46
it's nothing that crazy and so that's
0:48
why we can go through it pretty quickly
0:49
typically uses a b tree index it
0:53
uses acid transactions if you want them
0:55
and typically you would use it with
0:58
single leader replication and that would
0:59
just be sharded in order to get better
1:01
right throughput and so all of this
1:03
stuff is pretty pretty similar to your
1:05
typical SQL database
1:07
now obviously I shouldn't say Obviously
1:10
but in reality a lot of these features
1:11
are configurable so you can kind of plug
1:13
and play them as you want but the point
1:15
is I think this is probably generally
1:16
how people are using mongodb
1:18
even still the biggest difference
1:20
between mongodb and a SQL database which
1:23
is why mongodb gets the title of a nosql
1:25
database is that mongodb is document
1:28
oriented so what is a document well it's
1:31
effectively just a nice deeply nested
1:33
Json structure of data that you can
1:35
store in your database and what that
1:36
allows you to do is have a little bit
1:38
more flexibility in terms of what you're
1:39
actually storing so for example if we
1:41
wanted to store like a person object
1:43
here would be the ID of it and then we
1:45
could have a nice little Json document
1:47
of a name and a link God knows of what
1:50
but that guy Jordan has a long life so
1:52
again that offers us some flexibility
1:54
beyond the traditional rigid SQL
1:56
relational table model where everything
1:58
has to have the same exact columns
2:01
so that's pretty much mongodb we'll talk
2:03
about how it compares to Cassandra but
2:05
in order to do so we have to actually
2:06
talk about Cassandra itself so Cassandra
2:09
uses something known as the wide column
2:11
data model so instead of being a nested
2:13
structure really the only requirements
2:15
in Cassandra for your data is that you
2:18
have these two Fields right here and
2:20
frankly really only a cluster key the
2:21
sword key is optional but basically
2:23
we've got a cluster key we've got a sort
2:25
key and then pretty much everything else
2:27
in every single row is optional and you
2:30
can either have them there or you don't
2:31
have to it's really not too big of a
2:33
deal so let's go ahead and keep talking
2:36
about this
Partitioning
2:38
first we're going to start by talking
2:39
about partitioning Cassandra so if you
2:41
recall we've got a cluster key and a
2:43
sort key and that is going to do things
2:45
for us in partitioning what it basically
2:48
means is that we are going to decide how
2:50
we're partitioning each row based on the
2:52
value of its clustering key and so that
2:55
configuration for partitioning is
2:58
actually going to be shared via gossip
3:00
protocol so every single node can go
3:03
ahead and just like gossip
3:05
if you recall from our consistent
3:07
hashing video this would be like our
3:08
hash ring and this is going to say which
3:11
keys are going on which node so in this
3:13
case all the keys in this range are
3:15
let's say on this node over here and so
3:18
just in general our hash ring is going
3:20
to tell us which notes go or rather
3:22
which rows go where and each node is
3:24
going to share that with one another via
3:25
a gossip protocol if a node were to go
3:28
down
3:28
these guys would both start gossiping
3:30
not to one another and eventually
3:32
everyone would agree on the partitioning
3:34
state of the whole system and then of
3:36
course I did even forget to write this
3:37
but we've got a local index
3:41
with a sort key
3:44
So within each partition the rows are
3:47
sorted based on the value of this guy
3:49
here a sword key and keep in mind the
3:51
reason I call that a local index is
3:53
because they are only sorted within that
3:54
single partition if we're looking at a
3:56
different partition then the sort key is
3:58
pretty much irrelevant across them so in
4:00
Cassandra it's actually a very very
4:03
opinionated system about how they want
4:05
reads and rights to go and typically it
4:07
is very strongly recommended that all
4:09
reads and writes go to Just One
4:12
partition there is very little support
4:13
for distributed transactions if you're
4:15
running Cassandra you don't want to be
4:17
running two-phase commit ideally all of
4:19
your reads are coming from one partition
4:21
at a time and all of your rights are
4:23
going to one partition at a time so it's
4:26
very important to keep in mind now let's
Replication
4:28
go ahead and talk about replication
4:30
because replication is probably what
4:32
makes Cassandra the most unique out of
4:34
all the systems that we've discussed so
4:36
far so first off we're actually using
4:38
leaderless replication so this is the
4:40
first time we're discussing a database
4:41
that is kind of generally used in this
4:44
type of fashion and if you recall what
4:46
that means is that you can do things
4:48
like have quorums so you would write to
4:51
and read from a majority of nodes and
4:53
although this doesn't technically
4:54
achieve strong consistency it does mean
4:57
that generally speaking when you write
4:58
and then you read using a quorum node
5:01
right after that you should be able to
5:03
see that written value in at least one
5:04
of the nodes of course that is
5:06
configurable though if you don't want to
5:08
have to use quorums you can say rights
5:10
can only go to a single node reads can
5:12
only come from a single node and that's
5:13
really all just depending on how
5:15
comfortable you are with eventual
5:16
consistency and Stillness of data in
5:18
order to make sure that there is less
5:20
stale data on each node Cassandra will
5:22
do things like read repair and
5:24
anti-entropy so read repair if you
5:26
recall is basically saying like oh shoot
5:28
you know this guy doesn't have the value
5:30
from our original right over here so
5:32
once this client sees the value he's
5:35
going to write back to this database and
5:37
read repair it anti-entropy on the other
5:40
hand would be the occasional sending of
5:42
data via a Merkle tree
5:44
from one database to the next in order
5:46
to make sure that they have consistent
5:48
States using a Merkle tree allows
5:49
sending lesser data over the network
5:51
because you only compare the differences
5:53
in data between the two tables
5:55
then in addition of course whenever we
5:57
use leaderless replication anything
5:59
other than single replication opens us
6:02
up to right conflicts and when we have
6:04
right conflicts how do we resolve them
6:06
in particular Cassandra chooses to use
6:08
last right wins or lww so obviously
6:11
there are some problems with this namely
6:13
that we can't trust timestamps in
6:15
distributed systems there's clock drift
6:17
there's Network lag all of this other
6:19
stuff and so as a result we can have
6:21
lost rights if I write at the same time
6:23
as you and my right happens to just
6:25
barely have an earlier timestamp mine is
6:28
effectively just gone from the system
6:29
and I'm going to have no clue what
6:30
happened so keep in mind that when
6:32
you're using Cassandra technically you
6:34
don't have great data Integrity
6:35
additionally
6:37
another alternative to Cassandra which
6:39
is basically the same exact thing is
6:41
called ryak this is another type of
6:43
database system however the one main
6:45
difference between riac and Cassandra is
6:47
that as opposed to using last right wins
6:49
ryak gives us the option to use crdts or
6:52
conflict-free replicated data types in
6:55
order to help us resolve our right
6:56
conflicts and I have a video dedicated
6:58
to those that I made I don't know a
7:00
month or two ago
Single Database
7:01
okay so now let's look at just a single
7:03
database node in Cassandra because we've
7:05
talked about the partitioning the
7:06
replication but at least within a single
7:09
node Cassandra does some nice stuff in
7:10
order to help performance which is that
7:12
it uses an LSM tree and SS tables in
7:15
contrast to a b tree so what does this
7:17
actually help us do well it's a little
7:19
bit better for rights because this guy
7:21
right here aka the LSM tree
7:24
is in memory
7:26
and that means that all rights are first
7:28
going to memory before they have to go
7:30
to disk when they're eventually flushed
7:32
to an SS table this is in contrast to a
7:36
b tree where your right originally goes
7:37
to disk and as a result writes are a bit
7:39
slower but reads are a little bit faster
7:41
on B trees so keep that difference in
7:43
mind as well another thing is that
7:45
Cassandra does not really fully support
7:47
acid transactions it really only likes
7:50
row level locking so they you know
7:51
within a row your value is definitely
7:53
going to be correct but if you wanted to
7:55
do something like a read modify update
7:57
transaction on multiple rows you might
7:59
have trouble doing something like that
8:01
or at least Cassandra wasn't originally
8:03
made with that intention ideally most of
8:05
the rights that you should be doing
8:06
should just be going to one row at a
8:08
time and that is the best way to really
8:10
use Cassandra
Conclusion
8:12
so let's do a quick conclusion so that I
8:14
can go meet up with some friends and
8:15
stop being such a nerd basically mongodb
8:18
is really really good for when you need
8:20
the data Integrity of a relational
8:22
database type of system if you want acid
8:24
transactions if you want to be able to
8:26
run two-phase commit in order to perform
8:28
distributed transactions then mongodb
8:31
does support all of that obviously the
8:34
the speed is going to be more comparable
8:36
to something like a SQL database however
8:38
it's really really nice to be able to
8:39
have the data flexibility that you do by
8:41
using this document oriented data model
8:43
on the other hand Cassandra is extremely
8:46
different than that it's got like a very
8:47
opinionated type of way of using it
8:49
where basically you want to always be
8:52
reading from and writing to one
8:53
partition at a time
8:55
in terms of reads those reads can read
8:57
multiple rows at a time but ideally for
8:59
writes you're probably writing one row
9:01
at a time as well
9:02
but at the same time as a result of this
9:04
you don't have great data guarantees due
9:07
to things like write conflicts you can
9:09
just have rights getting clobbered or
9:10
removed and due to the lack of acid
9:12
transactions and distributed
9:14
transactions if you plan on doing things
9:16
like that you should be very very
9:17
careful and you might even have bugs in
9:19
your code if you're trying to code them
9:20
up on your own so a good case for
9:23
Cassandra in general because I think
9:25
it's good to kind of outline one of
9:26
these would be something like a chat
9:27
application like Facebook Messenger the
9:30
reason being that you're Often
9:31
bottlenecked by rights there because
9:33
everyone's going to be writing so many
9:34
messages all of the reads that you do
9:36
are probably going to be for one chat at
9:38
a time and they're always going to be
9:39
ordered by timestamp and so something
9:42
like using chat ID as the cluster key
9:44
for partitioning so that all of your
9:46
messages are on the same partition could
9:48
be really really useful and then of
9:50
course to make that index read faster we
9:52
can basically just sort by timestamp
9:55
and again this is going to be the
9:56
generalized case which we would be
9:58
reading those messages it's going to be
10:00
very rare that we would ever have to
10:01
write to two partitions at once because
10:02
it's never like you're sending a chat to
10:04
or you're never sending a message to
10:06
multiple chats at once but at the same
10:09
time you're probably always just going
10:11
to be writing one message at a time and
10:13
it's always going to be going to one
10:14
chat at a time so this is a really
10:16
really good use case anyways guys I hope
10:18
this video was useful as you can see
10:20
there are some pretty distinctive use
10:22
cases between Cassandra and mongodb and
10:24
it's very important to understand this
10:26
difference because in an actual
10:27
interview when someone says do you want
10:29
to use a SQL table or a nosql table and
10:31
then you say nosql and they say which
10:32
one you better know which one so have a
10:35
good one guys and I will see you in the
10:36
next one

##v37:

0:00
hey everyone and welcome back to the
0:01
channel sorry about my brief Hiatus to
0:04
make a toolish video about school versus
0:06
software but at the end of the day I had
0:08
a collaboration opportunity and I had to
0:10
take it because no one wants to
0:11
subscribe to my channel even still no
0:13
one wants to subscribe to my channel
0:15
because I'm too ugly so that means I'm
0:17
going to revert to the basics and make
0:18
some more systems design videos let's go
0:20
ahead and get into it alrighty so today
What is Hadoop
0:23
we'll be talking about Hadoop which is a
0:25
distributed computing framework so if
0:28
you're anything like me two years ago
0:30
you've probably seen this term many many
0:32
places and uh well you know maybe you're
0:35
smarter than me but at least I had no
0:36
clue what it was and I thought it was
0:38
just some made up word so let's talk
0:39
about what it actually is Hadoop is
0:42
really useful for a couple of things and
0:44
in this video I'm going to be talking
0:45
about one of two of them the first is
0:48
data storage which it does through the
0:50
Hadoop distributed file system hdfs and
0:53
the second is Big computations which it
0:55
does via things like mapreduce or spark
0:58
both of which deserve their own video
1:00
but for this one I'm going to be
1:01
sticking to hdfs the Hadoop distributed
1:04
file system because it kind of builds up
1:06
the foundation of Hadoop and why it's so
1:08
useful so let's go ahead and talk about
1:09
it hdfs like I mentioned is a
1:12
distributed file store and the thing
1:14
that's so good about it is opposed to
1:16
just having a bunch of different
1:17
computers in a cluster and being you
1:19
know kind of Hardware agnostic treating
1:21
every computer as if it was the same the
1:23
storage is actually rack aware and so
1:26
that means we take advantage of the
1:27
location of every single computer in
1:30
order to minimize things like Network
1:31
latency when sending and reading files
1:34
and so again the fact that it's
1:36
distributed also means that it is Fault
1:38
tolerant I mean not inherently but in
1:40
this case hdfs is Fault tolerant and
1:42
that's very important for why we use it
1:45
and the very basic architecture of this
1:47
thing is we have two types of
1:49
kind of elements in our system one is
1:52
that we have the name node and the
1:53
second or that we have a bunch of data
1:55
nodes so a very high level overview is
1:57
the name node is for metadata
2:00
and the data nodes are for storage
2:04
so let's go ahead and talk about that
2:06
name node a little bit more like I said
2:08
it is a metadata store so kind of a
2:11
couple of things about the name node
2:12
what does it actually tell us well first
2:14
off it tells us all the replicas
2:17
that store a given file and also the
2:20
version of that file on them you can
2:22
actually overwrite a file with a newer
2:24
version and as a result replicas could
2:27
technically have different versions in
2:29
theory this shouldn't be happening very
2:30
often because hdfs claims strong
2:32
consistency but we'll see in a little
2:34
bit that it's possible for things to get
2:36
a little bit out of whack and so the
2:38
name node which stores all of this file
2:40
metadata and it keeps all of this data
2:43
in memory which is just a slight
2:45
optimization to make sure that when a
2:47
client goes ahead and reads from the
2:48
name node or writes to the name node
2:50
that is going to be a little bit quicker
2:52
well what if the name node were to go
2:53
down another nice thing that we have is
2:56
a right ahead log on disk saying all the
2:58
operations that we have this is a good
3:00
middle ground between basically you know
3:02
having to put every single thing in disk
3:04
with an index or something that would
3:07
take a while to write and instead keeps
3:08
it to a nice sequential right which is
3:10
relatively quick while maintaining fault
3:12
tolerance also if we wanted to do an
3:14
optimization here which I think Hadoop
3:16
actually does you can occasionally
3:18
snapshot this guy right here and then
3:21
snapshot the location in the right ahead
3:23
log so wal index and then once you have
3:27
your snapshot and your wlal index you
3:30
can just replay all of the changes from
3:33
the red ad log from that point on but
3:35
that's kind of a small detail it's not
3:36
that important
3:37
so when the name node starts up
3:39
basically it's going to ask each of
3:41
those data nodes recall that the data
3:43
nodes are the ones actually holding the
3:44
files what files it holds and also what
3:47
versions and so in Hadoop you have this
3:49
configurable replication number right
3:51
let's imagine it's three in this case as
3:53
we can see every single file has three
3:55
replicas that hold it and what the name
3:57
node will do is say okay I just started
3:59
up I only see the two data nodes are
4:01
holding this file in particular let's go
4:03
ahead and replicate that to one more
4:05
data mode
Reading
4:07
cool so let's also talk about reading
4:10
files because this is relatively simple
4:12
and then we'll talk about writing after
4:13
that so basically in Hadoop we expect to
4:17
be reading data a lot of times and
4:19
writing it hopefully very few because
4:20
the writes are very expensive we're
4:22
talking about Big Data here and so we're
4:23
writing big files reading them on the
4:26
other hand should be relatively common
4:27
especially if we're doing a lot of data
4:29
computations with the same sets of data
4:31
or if we're building a database on top
4:33
of hdfs
4:35
so again a lot of reads not too many
4:37
writes so step one is pretty simple we
4:40
basically go to the name node and say
4:41
what's the file location now let's say
4:44
this guy says data node a
4:46
so now step two for the client is the
4:49
name node is going to respond with the
4:51
best replica so keep in mind here that
4:53
there are three
4:55
data nodes and the one that's actually
4:57
closest to the client is data node a so
5:00
the name node is actually smart enough
5:01
to realize hey we can actually benefit
5:04
our client a little bit by telling it a
5:06
specific replica that is going to have a
5:08
lower Network latency width for example
5:10
B is further away
5:13
and so we wouldn't want to be reading
5:15
from there that's just going to cost us
5:17
time and so as a result what the client
5:19
can do is so that when it reads this
5:21
file in the future as opposed to having
5:24
to do step one again every single time
5:25
we can just go ahead and cut that down
5:27
because we're going to Cache the file
5:29
location locally and then from there
5:31
every single time we want to read this
5:33
particular file we just go ahead and
5:34
read it from data node a
5:36
simple enough hopefully makes sense
Writing
5:39
let's now talk about writing files this
5:42
is a little bit more complicated but
5:44
still not too bad okay so basically when
5:48
we're writing a file at least for the
5:51
first time not when we're overriding it
5:52
as I try to get the zoom working
5:54
basically what we want to do is say when
5:56
we're picking a location of replicas the
5:59
name node is trying to do so in a rack
6:01
aware manner so step one is going to be
6:04
the client says I have a file I want to
6:06
go ahead and write it to Hadoop it's
6:08
going to ask the name node what to do
6:09
the name node is going to say okay here
6:12
are the replicas that you're going to
6:13
have to write this thing to and one of
6:15
them is going to be designated the
6:17
primary now ideally the name node is
6:19
going to try and pick a primary node to
6:21
write to that is actually close to the
6:24
user right so again the user is located
6:26
over here data node a is over here in
6:29
data center one which is the one that is
6:31
closest to the user so the name node can
6:34
actually be smart about that and then in
6:36
addition another smart thing that it can
6:37
do is actually be smart about replica
6:39
education it would be kind of useless if
6:42
we put one replica in all three of these
6:44
data centers because the truth is the
6:46
likelihood that two data centers are
6:49
going to die is pretty low so what we
6:50
can actually do is pick only just two of
6:53
the data centers right here forget about
6:55
data center three and then we can keep
6:57
two of the replicas in one data center
7:00
so that the network latency is minimized
7:02
between data node a and data node B the
7:05
reason we care about minimizing the
7:07
network latency between data node a and
7:10
data node B is that that file is
7:13
actually going to be written from data
7:15
node a to data node B so you might be
7:17
thinking huh that's weird so the client
7:19
is actually just writing to one data
7:21
node and then that right gets pipelined
7:23
all the way through the replicas as
7:24
opposed to just doing three writes and
7:27
you would be correct the client is only
7:29
going to do one right here
7:31
and we're going to be doing something
7:33
called replication pipeline
Replication Pipeline
7:35
so let's go ahead and talk about that
7:37
the replication pipeline is a pretty
7:39
simple concept basically we have a
7:42
primary a secondary and a tertiary
7:44
replica at least in this case and all
7:46
the client now has to do is write once
7:50
and from there every single replica is
7:52
going to write to the other replicas in
7:55
the chain
7:56
and then they're going to receive
7:58
acknowledgments back through the
7:59
pipeline
8:00
and eventually that's going to be
8:02
getting back to the client now what if
8:05
it doesn't because things can fail so
8:07
what if we're only able to get this
8:09
thing into a so this guy works and then
8:11
right over here instead this guy fails
8:13
so neither B nor C is able to get the
8:16
right the client does not receive an
8:18
acknowledgment and now we're in trouble
8:20
because a actually has the updated
8:22
version of our file and B and C don't
8:25
what this means in this case is that our
8:27
system is not strongly consistent
8:29
because we can have replicas that have
8:32
out-of-date versions of the file now a
8:34
couple of different possibilities exist
8:36
here for one we can just have the client
8:38
give up and accept the fact that this
8:40
thing is going to be eventually
8:41
consistent you know the name node could
8:43
always pull the files on B and C at some
8:47
point see they have outdated versions
8:48
and then tell them to get updated or
8:51
Additionally the client can say
8:53
I didn't
8:56
get an ack
8:59
try again
9:00
and in theory you could try again until
9:02
you do get an act but obviously if for
9:05
some reason you know there just was no
9:07
network connection between A and B then
9:09
that's going to be a problem and you're
9:11
never going to get one and then again
9:12
it's just not strongly consistent so if
9:14
you hear that hcfs is that's a lie but
9:17
it certainly does try to be
High Availability
9:20
okay the final thing we're going to talk
9:22
about is something known as high
9:24
availability hdfs so surprisingly this
9:27
took a while before it was standard in
9:29
Hadoop but uh yeah it pretty much needs
9:31
to be there because otherwise you will
9:33
have a lot of outages So speaking of our
9:36
name node if you've been thinking about
9:38
why the hell is there only one of them
9:40
you would be correct for a long time
9:42
there was only one name node and that's
9:44
a problem because if that thing goes
9:45
down
9:47
we are in trouble you know there's no
9:48
one else to orchestrate reads and writes
9:50
and be a metadata store so we need some
9:53
way of having a backup name node if this
9:55
thing is to go down and the way that uh
9:57
Hadoop has chosen to do so is we use
10:00
something like zookeeper so if we recall
10:02
zookeeper is a strongly consistent
10:06
way of achieving a distributed log via
10:10
consensus
10:11
so we've got three nodes they're running
10:13
a consensus algorithm where basically
10:16
the majority of nodes have to have a
10:17
write before it's considered committed
10:19
and this allows us to create
10:21
linearizable storage so that basically
10:24
we're taking our right ahead log
10:27
from the primary name node and putting
10:30
it into this distributed log that is
10:32
held on zookeeper that way we can just
10:34
have our secondary name node going ahead
10:37
and Performing State machine replication
10:43
can't write and what state machine
10:45
replication really is fancy lingo for is
10:48
just read everything from the write
10:49
ahead log store it in memory you're good
10:52
to go now if for some reason this thing
10:54
goes down zookeeper is going to say
10:55
Europe
10:58
and then the secondary name node can
11:00
take over and everyone else in the
11:01
cluster who can be connected to
11:03
zookeeper because it's a service
11:04
Discovery mechanism can basically just
11:07
say all right I'm going to be listening
11:08
to the secondary name node from now on
11:10
and then we're good to go
Conclusion
11:12
okay so quick conclusion here because I
11:15
have to get to the gym Hadoop is
11:17
basically a huge building block in
11:19
distributed computing it not only allows
11:22
us to work with big data in a rack aware
11:25
way which is very important but it is
11:27
also something that a lot of other
11:29
systems build upon we're going to be
11:31
talking about a database hbase soon that
11:34
builds on top of Hadoop and uses it in
11:36
order to make fast and scalable storage
11:38
and then of course also if we want to
11:41
make massive computations over just
11:43
unstructured data in general things like
11:46
log files or metrics or sensors or any
11:48
of that we're probably going to be
11:50
dumping it into Hadoop first and then
11:52
running a batch job like a mapreduce or
11:55
a spark job and we'll talk about the
11:57
differences between those so guys hope
11:59
you enjoyed this video it should serve
12:01
as hopefully a decent introduction to
12:03
hdfs and I will see you in the next one
12:05
where we talk about applications

##v38:

0:00
hey guys and welcome back to the channel
0:02
so today we are going to be talking
0:04
about hbase which is a database that is
0:06
built on top of Hadoop so this is going
0:08
to be a quick diversion off of the
0:10
course of talking about batch processing
0:12
uh which we're going to be doing right
0:13
after this since you know now we're
0:15
starting to get into all of that fun
0:16
stuff
0:17
um and even though there's plenty to
0:18
cover there let's go ahead and get
0:20
started by talking about hbase I've got
0:22
to get into the gym after this because I
0:24
ate a ton of deep dish pizza this
0:26
weekend and I ruined my cut so let's get
0:28
into it and I will see you on the iPad
Recap
0:30
alright so assuming that you're not a
0:32
phony you've obviously watched last
0:33
video about Hadoop uh but considering
0:36
that most you are phonies you probably
0:38
haven't so in that case uh let's do a
0:41
quick recap and say that hdfs or Hadoop
0:44
distributed file system is effectively
0:46
just a distributed way of storing a
0:48
bunch of different files in a manner
0:50
that is Fault tolerant redundant all
0:52
that good stuff but the issue with it is
0:55
something that we're going to talk about
0:55
which is that when we actually have a
0:58
file stored and we want to make a
0:59
modification to it it's very inefficient
1:01
so here's an example of a file right
1:03
here in Hadoop and as you can see we've
1:06
got some information let's think of this
1:08
as a key Value Store where we've got all
1:10
of our attractiveness levels of some
1:11
common characters that we're all
1:13
familiar with as you can see Jordan 10
1:15
out of 10 as expected but the issue is
1:18
let's go ahead and say that Elon after
1:20
uh you know limiting the amount of
1:21
Twitter posts that we can see has now
1:23
become a 5 out of 10. well in Hadoop at
1:26
least there's no way that we can just go
1:27
ahead and make an ad hoc edit to just
1:29
one file at a time and edit one piece of
1:32
data on disk in fact we would have to
1:34
overwrite being entire file and in
1:37
reality these files aren't just going to
1:38
be four lines long they're going to be
1:40
many many megabytes and as a result of
1:42
that doing such an operation is
1:44
extremely expensive especially when you
1:46
have to consider Network and replication
1:47
costs so in reality if we are operating
1:51
a Hadoop cluster and we want to be able
1:52
to take the data that we already have
1:54
and modify it just using vanilla hdfs
1:57
probably isn't a great solution unless
1:59
we plan on overwriting files all the
2:01
time which like I said is going to be
2:03
slow and expensive
HBase
2:06
so this is going to segue us into hbase
2:08
where hbase is effectively a database
2:10
that we've built on top of Hadoop and by
2:13
we I mean a bunch of rando nerds on the
2:15
internet and so number one is that hbase
2:18
is going to allow us to do a bunch of
2:20
you know kind of in the moment rights
2:22
and key updates because keep in mind
2:24
like I said the issue before is that we
2:27
had to overwrite an entire file and what
2:29
hbase is going to do is use an
2:31
intelligent architecture to make sure
2:32
that we can actually make edits in the
2:34
moment we do so via LSM trees which is a
2:38
type of database index that we've
2:39
discussed plenty on this channel but I
2:42
will do a quick overcap or rather recap
2:45
on the next slide and then additionally
2:47
we can also do a lot of batch processing
2:50
due to the data locality that hbase
2:53
gives us it does this via using column
2:56
oriented storage we've also discussed
2:57
this in the past and also range-based
3:00
partitioning which keeps data with
3:01
similar Keys close together on the same
3:03
partition
HBase Data Model
3:05
so let's quickly talk about the hbase
3:07
data model because fundamentally it's
3:10
very similar to Cassandra but in reality
3:12
these two databases should be used for
3:14
generally different things so again it's
3:17
going to be a wide key column store
3:18
which if you can think about it means
3:21
that we are in fact using a nosql
3:23
database here and again that is similar
3:25
to Cassandra in the sense that every row
3:27
has to have a certain part of
3:29
information and then you've got all this
3:30
other stuff that is pretty much just
3:32
optional and you know you can either
3:35
have it or you don't have to have it but
3:37
we do need certain parts of the row that
3:40
comprise something known as our Roki and
3:42
our row key is basically what determines
3:44
in hbase how things are getting
3:45
partitioned and also the order in which
3:47
they're stored like I mentioned
3:49
everything is done by range based
3:51
partitioning so we're not taking the
3:52
hash of this key we're literally just
3:54
partitioning the data right down the
3:56
segment as if it were ordered now of
3:59
course you could be smart about this and
4:00
like literally take what would have been
4:02
your row key and just like put in the
4:04
hash of that part over there and then
4:07
that effectively becomes hash based
4:09
partitioning but my point is out of the
4:11
box you know it's range based
4:12
partitioning and we'll see why that's
4:14
good in a little bit at least for the
HBase Architecture
4:17
use case that we want so let's start
4:19
talking about architecture because
4:21
that's really what sets hbase apart and
4:23
as I mentioned it is built on top of
4:25
Hadoop so we've got this master node
4:27
right here and if you've watched our
4:28
Hadoop video that's very similar to the
4:30
concept of the name node where we have
4:32
this one centralized place which is
4:34
effectively just a metadata store and
4:37
keeps in memory where all of the files
4:40
that we care about are located where
4:41
their replicas are what versions We have
4:43
etc etc so basically we've got our
4:46
client over here on the top left and
4:48
whenever a client wants to perform a
4:50
right to hbase which is what's important
4:52
it basically goes to the master node and
4:54
says Where do we want to write to the
4:56
master node will then respond with right
4:58
to node two so in this case node 2 would
5:00
effectively be the partition that the
5:03
client should be writing to and then the
5:04
client is going to execute that right
5:06
over here to node 2. now you may see
5:09
that on each of these nodes imagine that
5:12
each of these big boxes is one single
5:14
computer in our Hadoop cluster
5:17
we have two boxes within that a region
5:20
node and a data node so the data node
5:23
is actually a term that we've discussed
5:25
in our Hadoop video and the region node
5:28
is hbase and that the region node is
5:31
going to be a separate process from hdfs
5:34
running in memory likely on the same
5:36
computer as the data node then of course
5:39
we've got all of our high availability
5:41
stuff over here I
5:45
availability
5:47
because of course if the master node
5:49
goes down we don't want to have the
5:51
entire system go down so what we
5:52
typically will do is we'll send all of
5:55
the operations that are occurring on the
5:56
masternode over to zookeeper which then
5:58
can be read by a secondary masternode so
6:01
if the master were to go down the
6:03
secondary can take over
6:04
so again we now have this concept of a
6:07
region node and a data node and keep in
6:09
mind that our rights are being sent to a
6:11
specific region node let's go ahead and
6:13
zoom in on that and learn a little bit
6:14
more
HBase Region Node
6:16
so when we examine our region node
6:18
what's actually happening well basically
6:20
the region node is what is operating our
6:23
LSM tree index so let's again discuss
6:25
this we've got a client
6:27
and to recall the client is going to be
6:29
writing to the region node and the
6:32
region node in memory is going to be
6:34
holding this guy right here which is an
6:36
LSM tree so if we recall an LSM tree and
6:40
SS table is a type of database index
6:42
whereby you write to an in-memory binary
6:44
search stream and then when that tree
6:46
gets too big we flush all of the data
6:48
out to an SS table
6:51
which is basically the data in the LSM
6:53
tree but sorted and that's held on hard
6:56
drive so HDD
6:58
and so basically what will happen is
7:01
once this LSM Tree on the region node
7:03
gets too big you can see that we're
7:05
going to go ahead and flush it to an SS
7:07
table on disk on the data node so keep
7:11
in mind that the data node is part of
7:13
Hadoop right it's part of hdfs and what
7:16
happens to things that get sent as files
7:19
to Hadoop they get replicated how do
7:21
they get replicated through the
7:23
replication pipeline now if you remember
7:25
from last video what that basically
7:26
means is that we've got one data node
7:29
sending a right to another data node
7:32
which sends a right to another data node
7:35
and then you pass the chain of
7:37
acknowledgments all the way back through
7:38
to the original data node and eventually
7:42
you know it gets propagated over to the
7:44
name node which then updates its
7:46
metadata store and so that's exactly how
7:49
hbase is going to do things as well
7:51
basically all of the SS tables that are
7:54
eventually flushed to hdfs are going to
7:56
be replicated through that replication
7:58
Pipeline and that is how we make sure
8:00
that we have fault tolerance in our data
8:02
of course we also have something like a
8:04
write ahead log on our region node to
8:07
make sure that our LSM tree doesn't get
8:08
lost if the region node were to crash or
8:11
something like that but generally
8:12
speaking the point here is that we have
8:15
hbase which kind of manages our LSM
8:18
trees and then hdfs which is going to
8:21
manage the replication of our SS tables
8:24
and then additionally hbase is going to
8:26
be managing our partitioning and
8:28
effectively every single region node is
8:30
going to be a different partition and so
8:32
as you can see this guy would have a
8:34
separate
8:36
lsmetry
8:38
which is then going to flush separate SS
8:40
tables
8:42
and those can be replicated however
8:44
Hadoop sees fit to either this node or
8:47
to this node down here the point is we
8:50
can think of the replication part as a
8:52
black box Hadoop is taking care of that
8:54
for us
Column Oriented Storage
8:55
okay so another key aspect of hbase that
8:58
is super useful is that it uses column
9:01
oriented storage now we've spoken about
9:03
this a decent amount in the past
9:04
especially when it comes to park it
9:06
which is an open source way of kind of
9:08
Performing column oriented storage
9:09
Market files or a type of file but
9:12
basically just to reiterate on the
9:13
difference we've got row oriented
9:15
storage which basically has every single
9:17
row of data next to one another on disk
9:20
and then differently we have column
9:23
oriented storage where we take every
9:25
single column and we put those next to
9:27
one another on disk so this would be the
9:29
name column
9:31
and then below it we would have all of
9:33
the rows in the same order for the
9:36
attractiveness column
9:39
and so what that allows us to do is say
9:41
we want to perform an analytical query
9:43
over the attractiveness column where we
9:44
say okay well what's the mean
9:46
attractiveness over this data set
9:47
instead of having to pull in all of that
9:49
name data we can cancel that out just
9:52
pull in the attractiveness data and then
9:54
say oh well it's 10 plus 5 plus 2 plus 1
9:57
over 4 which is 18 over 4 which is 4.5
10:02
whatever it doesn't really matter
10:04
but even better than that is assuming we
10:07
are using parkit here for our column
10:09
oriented storage we could actually store
10:11
some general stats of the column which
10:14
is kind of nice we can cache those so we
10:16
could have things like the Min the max
10:18
of the column or and even the average in
10:21
general so that would be useful for us
10:23
and of course if these column values are
10:25
super similar as well we can perform
10:27
some column compression to basically
10:29
just speed up our queries and also
10:31
minimize the amount of data on disk that
10:33
we're taking up so just in general the
10:35
kind of gist of column oriented storage
10:37
is this right here which is that it is
10:39
better for analytics queries because we
10:41
have better data locality and in
10:43
addition to that that makes it better
10:45
for batch processes as well because it
10:47
means that all of the data that we want
10:49
is closer to one another on disk it
10:51
means that we have to send less data
10:53
over the network there's less
10:54
coordination that has to be done when
10:56
kind of aggregating and organizing the
10:58
data and sorting it and so as a result
11:01
hbase allows us to organize our data in
11:04
a way that is really really good for
11:06
these batch processes without having to
11:08
sacrifice the fact that you know making
11:10
an individual right to a piece of the
11:12
data requires an entire file overwrite
11:15
which is super expensive additionally
11:17
besides the column oriented storage part
11:19
we're also using range-based
11:21
partitioning and so imagine you know
11:24
we partition data this way right here
11:27
this can be really nice because let's
11:29
say we're handling timestamp data or
11:31
something and we wanted to do a batch
11:32
query that let's say calculated like a
11:35
trailing average of the last five data
11:37
points if we were using hash range based
11:39
partitioning all of our time stamps
11:41
would probably be on different nodes
11:43
organized pretty randomly but when we
11:46
use range based partitioning it means
11:48
that all of the timestamps that are
11:49
similar to one another are going to be
11:51
on the same node and again that just
11:52
means passing less data over the network
11:54
and we can perform our computations a
11:57
little bit quicker that's kind of a
11:58
niche thing but
11:59
even still it doesn't really hurt for
12:01
this type of thing okay so what is the
Conclusion
12:04
conclusion of hbase well generally
12:07
speaking we probably don't want to be
12:09
using it just for a normal client-facing
12:11
application right because at the end of
12:13
the day if we just want to perform a
12:15
bunch of Rights and then read from the
12:17
partition that we've just written to we
12:19
don't really need hbase for that we can
12:21
use something like Cassandra where we're
12:23
still getting all of the benefits of the
12:24
LSM tree for rights we have leaderless
12:27
replication to write and read from even
12:29
faster and just in general you know we
12:32
don't necessarily need column oriented
12:34
storage because generally speaking we
12:36
just want to fetch one row at a time and
12:38
probably all of the values of that one
12:40
row and so row oriented storage happens
12:42
to be better in that case but on the
12:44
other hand if we kind of want a wrapper
12:46
around hdfs which gives us the freedom
12:49
to still do normal database operations
12:51
while also having the ability to perform
12:53
big batch computations then age base
12:56
might be a better system for us this
12:58
could be really useful for things like
13:00
and sensor readings just general data
13:03
points that we may have to modify down
13:04
the line where we're not just writing
13:06
them once and then reading them back in
13:07
the future and so as a result of that
13:10
keep hbase in mind when you see a use
13:12
case like this I imagine it probably
13:14
won't come up too much during the
13:16
system's design interview just because I
13:18
don't know it's kind of a nuanced system
13:19
and a lot of the things that we're doing
13:21
in the interview probably aren't getting
13:23
that in depth but even still I think
13:25
it's important to understand why hbase
13:28
exists in the first place how it's a big
13:30
improvement over something like Hadoop
13:31
and how also it falls short of something
13:34
like Cassandra when it comes to just
13:35
typical reads and writes for your normal
13:37
client-side application anyways guys I
13:39
hope you have a great day hope the video
13:41
was informative and I will see you in
13:43
the next one

##v39:

0:00
hey guys and welcome back to the channel
0:01
today we are going to be talking about
0:03
mapreduce and while I haven't used
0:05
mapreduce too much in my young life I
0:08
have been doing a decent amount of just
0:10
reducing lately as I've managed to
0:12
reduce the number of girls that I'm
0:14
speaking to to zero this has been the
0:16
case for about the last year anyways
What is MapReduce
0:18
let's get into mapreduce okay if you
0:19
would believe it I just recorded this
0:21
entire thing without actually using my
0:23
iPad so now I have to do it again all
0:26
right so what is mapreduce well
0:28
basically mapreduce is also part of that
0:30
whole Hadoop distributed computing
0:32
environment and what it allows us to do
0:34
is perform these massive batch
0:35
computations on data that actually lives
0:38
in Hadoop and is basically already
0:40
stored in hdfs so how do we do this
0:43
what's so useful about mapreduce well a
0:46
couple of really big things for starters
0:48
as opposed to just like running a
0:50
massive SQL pipeline we can actually run
0:52
arbitrary code via defining a mapper and
0:55
reducer function we'll touch upon what
0:56
those mean in a little bit additionally
0:59
we can actually run computations on the
1:02
nodes that hold the data this is huge
1:04
for data locality
1:06
and it's really important in terms of
1:08
ensuring good performance and then
1:10
finally to kind of give you some of the
1:12
lore of mapreduce basically this thing
1:14
was created in the early 2000s and it
1:17
was created to basically run on servers
1:19
that were probably running other jobs or
1:21
other processes at the same time that
1:23
were a lot more important than the batch
1:25
jobs that mapreduce was running and so
1:27
as a result of that the entire system is
1:30
basically built to be super resilient to
1:31
failures where if you know just one node
1:34
or just one part of this batch job fails
1:37
we only have to restart that failed part
1:39
as opposed to restarting from scratch
1:41
which is hugely important when you have
1:43
so many failures and so many preempted
1:45
tasks
1:46
okay so let's move on to mappers and
1:48
reducers what are they if you're not
1:50
familiar with functional programming
1:51
maybe this will be useful for you
1:53
otherwise sorry for wasting your time so
1:55
let's imagine that I have like a
1:57
username or rather a bunch of usernames
2:00
and I have a message that they sent
2:03
and basically we want to say okay for
2:05
every single one of these username
2:07
message combos give me the user ID
2:11
and give me the length of the message
2:15
that's really all a mapper is doing it's
2:16
just some arbitrary function that takes
2:18
in an unstructured log and then spits
2:21
out some type of key value combo that
2:23
you basically want for every single line
2:25
of that log
2:26
should be simple enough the next one is
2:29
going to be a reducer so a reducer is
2:32
going to take many of the outputs from a
2:34
mapper all for the same key and it is
2:37
going to spit out just one value right
2:39
so rather than really list key value it
2:42
should kind of be a key and a list of
2:45
values
2:46
and what it's going to do is spit out a
2:48
single value
2:50
so in this case you know we can see the
2:52
key is going to be 21 the list of values
2:55
is going to be 15 10 and 5.
2:58
and what it's going to do is let's say
3:00
this is a reducer that computes the
3:02
average of those values so I'd say 15 10
3:05
5 you know take the sum of those and
3:09
then divide by 3 and that's how you get
3:11
10 and that is our value up there so
3:13
that's kind of what the reducer is doing
3:15
so basically by just defining a mapper
3:17
and reducer we can express all sorts of
3:19
complicated functionality and later in
3:22
the video I'll Express how to you know
3:24
do basically even more than that so
MapReduce Architecture
3:26
let's look at the actual mapreduce
3:27
architecture
3:29
effectively
3:31
I'm going to get rid of this here
3:33
because it was from the last time I
3:34
recorded sorry about that
3:36
imagine we've got these three nodes in
3:38
our Hadoop cluster
3:41
what this graph is basically showing is
3:43
through the stages of an individual
3:45
mapreduce job how the actual data looks
3:48
different on every single node so to
3:50
start we've got all this unformatted
3:52
data on disk
3:54
and basically the job there is to
3:56
convert it somehow to a more
3:58
standardized format that's useful to us
4:00
and obviously that's going to be the job
4:02
of the mapper so as you can see I've got
4:04
a bunch of different types of keys and
4:06
values that are mapped out of each log
4:08
line it's worth noting that if you see
4:11
something like K3 on two different nodes
4:13
that means they have the same key but
4:15
probably a different value
4:16
so we start with all of these mapped
4:19
values and then what we're actually
4:20
going to do is sort them and I'll
4:22
explain in a little bit while we do that
4:25
but the gist is that now that we have
4:27
all of these sorted values we can
4:29
perform this important step right here
4:31
which is the shuffle so how do we
4:33
actually decide you know something like
4:35
oh you know K3 from this node goes over
4:38
to node three well actually we would
4:40
take the hash of the key
4:43
and then we would basically go ahead and
4:45
send those down to the other node now
4:47
the reason that it's very nice that we
4:49
can actually have our keys be sorted is
4:52
because now what we're doing is sending
4:53
two sorted lists down to every single
4:56
node or actually even possibly multiple
4:58
sorted lists and now we can perform an O
5:01
of n merge join
5:03
because we want to keep our keys sorted
5:06
on the reducer and I'll explain why that
5:08
is on the next slide so again shuffling
5:11
is literally just partitioning it's
5:12
taking a hash of every single key and
5:14
sending it to the proper node so that it
5:16
can be reduced now remember that
5:18
reducing is basically saying okay we
5:20
have multiple values corresponding to
5:22
the same key
5:24
let's compress them down to just one
5:26
value so now we're running our reducing
5:28
function as you can see there's only one
5:30
k6 now with a certain value and before
5:32
there were two K sixes obviously in the
5:35
case of k19 there was only one key or
5:38
rather one value with k19 to begin with
5:40
so it's just going to stay like that in
5:43
the reduction phase and then finally the
5:46
entire point of mapreduce is to get data
5:48
that we can store back in hdfs and so as
5:51
a result the last step is materializing
5:53
and this is going to be in disk and then
5:56
go back to hdfs
5:59
get replicated all that good stuff so
Reducer
6:02
again I keep mentioning that we were
6:04
doing some sorting because we want our
6:06
data on our reducer to be sorted so keep
6:09
in mind this guy is the reducer right
6:11
here so let's explain why we actually
6:13
want that let's imagine that this is my
6:16
reducer and the reduction function that
6:17
I want to do is perform the sum of the
6:20
values for each key so we have to
6:22
perform that in memory right so to start
6:24
it would be like oh a starts at 6. now
6:27
we're adding 8 to it so it's 14 and now
6:29
we're adding 10 to it so it's 24. since
6:32
we can now see oh B is three okay now I
6:36
no longer need to store the value 24 in
6:38
memory I can just say to disk because I
6:41
know that we're done Computing this
6:42
value since we started seeing a new key
6:45
same thing goes with B I can start with
6:47
3 then go to 10 and then go to 14 and
6:51
then I can flush it to disk
6:53
which is what mapreduce is eventually
6:55
going to do if our data is not sorted
6:59
then we don't actually know when we've
7:01
seen the end of a given key and we don't
7:03
know when we can flush to disk so it
7:06
would look something like this B is 3
7:08
now b is 7 oh wait now we have a is six
7:12
a is 16.
7:15
and then again B is now becoming 14 and
7:18
a is becoming 24. keep in mind that
7:21
there might even be a bunch more keys
7:23
here and yet we can't flush any of these
7:25
values to disk we have to keep them in
7:28
memory
7:29
and what that means is that if we have a
7:32
ton of keys it is a ton of extra memory
7:34
overhead which can really affect the
7:36
performance of our batch job which is
7:38
why it's so useful to keep things sorted
Job chains
7:41
okay finally let's talk about Job
7:44
chaining so as of now we can just have
7:46
one mapper function and one reducer
7:48
function but what if we want more
7:50
advanced functionality than that well
7:52
keep in mind that every single mapreduce
7:54
job is literally just going from data on
7:56
disk to different data on disk and so
7:59
there's no reason that we can't take
8:00
this data right here and then do another
8:03
job where we go from data on disk to
8:05
data on disk and that's effectively what
8:07
we're doing right here in theory you can
8:09
just chain infinite mapreduce jobs
8:11
together you know it might obviously be
8:13
slow but it's worth noting that you can
8:15
do this and that's what a lot of people
8:17
will end up doing
Conclusion
8:18
so let's quickly conclude on mapreduce
8:21
so I can get myself into the gym
8:22
basically it is a super super useful
8:25
framework in terms of making big data
8:27
batch jobs that we eventually want to be
8:30
running on a schedule if we wanted to
8:31
run them in real time again that would
8:33
be more like stream processing but again
8:35
batch processing is something that's
8:37
still extremely common all the time we
8:39
have you know like daily jobs that we
8:40
want to be running and so something like
8:42
mapreduce is super useful we can express
8:45
even more complicated functionality in
8:47
mapreduce Via both data joins which
8:50
we'll probably cover in the next video
8:51
and also job chaining and then finally
8:54
it's worth noting that even though
8:57
mapreduce is an extremely fundamental
8:59
aspect of today's Computing landscape
9:02
in reality it's actually not used that
9:04
much and there are some pretty major
9:06
flaws with this design that make it a
9:08
little bit less feasible than some
9:10
Alternatives and of course within the
9:12
next few videos we'll be doing a deep
9:13
dive in that as well so stay tuned guys
9:16
I will see you in the next ones and have
9:17
a great night

##v40:

0:00
hey guys and welcome back to the channel
0:01
so uh it looks like my collaboration
0:04
video did not get me canceled or get me
0:06
fired from work which is huge for me uh
0:09
but in addition to that some good
0:10
channel news is that I actually have
0:12
some kind of cool videos coming up for
0:14
ideally my 10 000 subscriber Mark which
0:16
I should hit and probably I don't know
0:19
one to two years from now so uh when we
0:21
get there uh it should be a fun one but
0:23
until then let's keep doing some systems
0:25
design so let's go ahead and hop into it
0:28
alright so the subject of today's video
0:30
is going to be performing joins in batch
0:33
jobs that's right I said batch jobs get
0:35
your mind out of the gutter so basically
0:37
the premise of this is that a lot of
0:38
times during batch computations we want
0:40
to be joining multiple data sets now you
0:42
can think of this as a typical SQL join
0:44
where we've got two different tables or
0:46
basically two different groups of files
0:47
and they share some common key probably
0:49
the key that you get out of mapping
0:51
those files to just a key and a value
0:53
pair and we want to be able to join on
0:55
that key so for example let's imagine
0:57
that I was doing some sort of experiment
0:59
to try and at the most popular websites
1:01
amongst people with a certain
1:02
demographic for example if I had two
1:05
data sets right here where I had like a
1:07
name to their demographic and also
1:09
another data set with kind of the name
1:11
and some of the websites that they've
1:13
been to you could perform a join that
1:15
actually merges on that common key which
1:17
is the name in this case so how does
1:19
this work in practice because when we're
1:21
talking about big data we have to be
1:23
very very careful about the way that
1:24
we're actually shifting our data over
1:26
the network and shifting our data on our
1:28
hard drive in order to make sure that
1:29
our joins are deeply optimized and that
1:31
we don't spend a ton of wasted resources
1:33
performing them
1:35
so we're going to talk about three
1:36
different types of joins and each of
1:38
them has some pretty big performance
1:39
implications so it's important that you
1:41
understand what's actually going on very
1:43
well so the first type is going to be
1:45
the sort merge joint and this is the
1:47
most general of the three that we'll be
1:48
talking about today we'll see why in a
1:50
little bit so let's imagine that we've
1:52
got our two data sets right here as we
1:54
can see data set one and data set two
1:56
and basically on each of those let's
1:59
imagine that we've just got two
2:00
different partitions in reality of
2:02
course we could have 10 15 20 a million
2:04
partitions but we'll imagine there's
2:05
just two for now and uh you know two
2:08
keys on each partition so the first
2:10
thing that we're going to do is we're
2:11
going to start out with all of our data
2:13
as shown right here this is our first
2:15
step and let's imagine this is like post
2:16
the mapping phase so now all of our data
2:19
has both a key and a value and we want
2:21
to be able to join on that key so the
2:23
first thing that we're going to do is on
2:24
every single node for both data sets
2:26
we're going to perform a sort and then
2:28
finally
2:29
after performing the sort as you can see
2:31
here on every single partition we've got
2:33
sorted data which looks great we're
2:35
going to perform the merge so what the
2:37
merge really means in reality is that
2:39
we're going to do the shuffle stage of
2:40
the mapreduce where we're basically
2:42
taking the hash of every single key and
2:44
then putting it on some partition so
2:46
basically we're just partitioning our
2:47
keys up consistently between the two
2:50
data sets so imagine that what that
2:52
effectively meant was that you know this
2:54
node over here has keys A and B and this
2:56
node over here has keys C and D so the
2:59
reason that it's so helpful to us that
3:01
we have all of those keys sorted is it
3:03
means that we're effectively merging a
3:04
bunch of sorted lists which makes our
3:06
join super easy it also means that we
3:08
can perform the entirety of our join on
3:10
disk so we don't have to worry about any
3:12
potential memory constraints on every
3:14
single system because all of these are
3:16
just a bunch of sorted lists we can go
3:18
through each sorted list and basically
3:20
run our o of n merge algorithm where we
3:23
look at just the first element of each
3:24
list and keep a pointer for each so we
3:27
don't have a lot of memory overhead here
3:28
in fact for something like this we would
3:31
probably actually use like a heap where
3:33
every single list that we're potentially
3:34
merging is in the Heap and then we have
3:36
a pointer to the smallest element or
3:39
rather the current element of each list
3:40
in each of them but again that's kind of
3:43
getting a little in detail the point is
3:44
we can do this all on disk and that's
3:46
really nice for us because the fact
3:48
these lists are sorted
Sword Merge Joint
3:50
so let's talk about sword merge join a
3:52
little bit because it's kind of
3:53
important to understand why it works and
3:55
also maybe sometimes why it's not the
3:57
best choice so my first thing is that
4:00
basically we can always do this the
4:02
reasoning being that we can always
4:03
repartition our data and make sure that
4:06
the two data sets have basically the
4:08
same keys on the same nodes which is
4:10
very important we can always also make
4:13
sure to sort our data because again
4:14
sorting our data allows us to be able to
4:16
perform the merge and the actual join
4:18
itself using only data on disk we don't
4:21
have to have any specific memory kind of
4:23
qualifications for our systems in order
4:25
to perform this type of thing at the
4:27
same time the big issue with assortment
4:29
showing is that they can be really
4:31
really slow the reasoning being that
4:33
first of all we literally have to sort
4:35
all of our data and when we have huge
4:37
data sets that can take a super long
4:39
time keep in mind that sorting is
4:40
typically n log n complexity and if we
4:43
have a data set with bajillions of rows
4:45
bajillion times M log n is really really
4:48
big
4:48
a nice thing here would be if those data
4:51
sets were already indexed especially if
4:52
they were already indexed in the same
4:54
way we could take out the sort step and
4:56
then the fact that we could literally
4:58
just go ahead and merge them on disk
4:59
would actually be pretty easy in fact it
5:01
would even be ideal
5:03
okay another thing that is problematic
5:05
with the sword merch join is that
5:07
basically we have to go ahead and send
5:09
at least one of the two data sets over
5:12
the network assuming that we need to
5:14
re-partition at least one of them right
5:15
because we want to make sure that they
5:17
are partitioned in the same way and
5:19
assuming that uh you know we need to
5:21
re-partition at least one of those data
5:23
sets to make sure that that's happening
5:24
we have to send the entirety of it over
5:26
the network and if that's a big data set
5:28
again that is going to take forever so
5:30
having to kind of deal with that use
5:32
case or deal with that situation where
5:34
we're sending a whole thing over the
5:35
network is really going to slow us down
5:37
and when possible we would like to avoid
5:39
that especially if one of those data
5:41
sets is massive so what could we
5:43
actually do however if one of those data
5:45
sets was massive but the other was
5:47
pretty small well this is where
5:49
something known as the broadcast hash
5:51
join comes in so as you can see we've
5:53
got a small data set and then we've got
5:55
a big data set with multiple shards and
5:57
in this case we're basically assuming
5:59
that we have a data set that is so small
6:01
that it can fit entire alien memory so
6:04
we're joining that small data set with a
6:06
huge data set where we have to have many
6:07
many partitions over a shared data file
6:10
system like Hadoop or something so what
6:13
we can actually do is every single node
6:15
that the data in our big cluster lives
6:17
on we can actually send the small data
6:20
set to it over the network which again
6:22
isn't a huge deal because it's pretty
6:24
small and we can fit it entirely in
6:26
memory which again is not a huge deal
6:28
because that's kind of the assumption
6:29
that we're making so let's imagine our
6:31
small data set is literally just this
6:33
right here where we say key B has the
6:35
value of 21 and Z has the value of 30
6:37
and then again obviously it's the same
6:39
data set on Shard 2. so we're keeping
6:42
that whole thing in memory and then now
6:44
we've got our big data set right over
6:46
here and what you should notice which is
6:49
actually really really nice about the
6:50
broadcast hash join is that we don't
6:52
actually have to sort our big data set
6:54
we can keep it exactly as is because all
6:57
we have to do now is iterate through
6:59
every single row of the big data set and
7:02
then check to see if it matches in the
7:04
hash map so basically we would say oh is
7:06
a in the hash map
7:08
we'd say nope so there's no join there
7:11
is B in the hash map yes it is so
7:14
there's a join that's all o of one so
7:16
it's super easy so basically all we have
7:18
to do now is a linear scan of our data
7:20
instead of having to do a sort which
7:22
saves us a lot of time and effort and
7:24
then we can do the same thing over on
7:26
Shard 2 we would say oh Z in the hash
7:28
map yes it is is y no it's not
7:31
etc etc etc and again
7:34
this is huge because we don't need to
7:36
sort the big data set and sorting is
7:37
obviously worse time complexity than
7:39
just scanning through which is again
7:41
going to be really really nice for us
Partition Hash Join
7:45
that being said again a problem with the
7:49
broadcast hash join is it assumes that
7:50
you have one of your two joining data
7:53
sets that is small enough to fit
7:54
completely in memory on all of your
7:56
machines in your Hadoop cluster and in
7:58
reality this oftentimes isn't the case
8:00
but there is a decent amount of the time
8:03
where it's possible that you can
8:05
actually fit certain partitions of the
8:07
data set in memory if we partition it in
8:09
a small enough way and this is what is
8:12
known as partition hash joins so this is
8:14
really really useful if both data sets
8:17
are too big to fit in memory but they're
8:19
partitioned the same way by key and so
8:22
they don't necessarily have to start on
8:24
the same node but the gist is that you
8:26
send the proper corresponding partitions
8:28
of the small data set over to the proper
8:30
corresponding partitions of the big data
8:33
set and then you can go ahead and do
8:35
another hash join where we go through
8:36
every single row of the bigger table
8:38
linearly and check if it's in this guy
8:41
over here
8:42
and so again what this allows us to do
8:44
is it saves us having to send the big
8:46
data set over the network and in
8:48
addition to that it also stops us from
8:50
having to sort the big data set which is
8:52
very very important as you can see we've
8:54
got basically Shard one over here
8:56
corresponding with Shard one of the big
8:58
data set and then the small data set
9:00
Shard too
9:02
is also on a different node
9:04
corresponding with Shard 2 of the big
9:06
data set and then again we can do our
9:08
linear scan perform our hash join where
9:11
we say Z in here no it's not is y in
9:13
here no it's not it's X in here yes it
9:16
is now we have a join so we can see that
9:18
X goes to 57 21. and so hash joins are
9:22
pretty simple to do
Conclusion
9:25
so what's our conclusion well in an
9:27
ideal case scenario you would have the
9:29
foresight to know what type of joins
9:31
you're going to be doing on your data
9:32
and as a result of that you would
9:34
actually you know start by actually
9:36
partitioning and indexing your data in
9:39
the same way on the same key the
9:41
reasoning being that if your data is
9:43
partitioned and indexed to the same way
9:45
and you want to join it all you have to
9:47
do is send the smaller data set right
9:49
over to the bigger data set and you can
9:51
literally just perform that join right
9:53
on disk and in fact you wouldn't even
9:55
have to do a complete linear scan in
9:57
that case because of the fact that the
9:59
data is already sorted you could
10:00
basically do a binary search and perform
10:02
that join even faster
10:04
however the point is though that
10:06
oftentimes in reality this isn't the
10:08
case a lot of people want to you know
10:09
kind of make joins up after the fact and
10:12
when this comes about we're going to
10:13
have to get creative in order to save a
10:15
lot of time in our data pipelines this
10:17
is legitimately something that I had to
10:19
use in my old job at Google and I was
10:21
ultimately able to take certain
10:23
pipelines that took multiple hours to
10:24
run and make them take minutes to run by
10:27
choosing a better methodology of joining
10:28
so again when we come across a situation
10:31
like this where in theory you might
10:33
think hey I may actually just have to do
10:34
a sort merge join here look for cases
10:37
where you can do either a broadcast or a
10:39
partitioned hash join because they will
10:41
save you significant amounts of time you
10:44
won't have to sort your massive data set
10:46
you won't have to potentially send it
10:47
over the network and that is a huge deal
10:50
so anyways guys hope you enjoyed this
10:52
video this is a topic that I personally
10:53
enjoy talking about and thinking about a
10:55
lot and so yeah hope uh it helped you
10:58
guys as well have a good one and I will
11:00
see you in the next video

##v41:

0:00
ladies and gentlemen welcome back to
0:02
Jordan has no life which is at least a
0:04
top 50 systems Design Channel on YouTube
0:07
today you'll be witnessing me performing
0:10
an sdui AKA systems design Under the
0:13
Influence as I just get back from my
0:15
company happy hour I was supposed to
0:17
record this thing last night and in fact
0:19
I did do so however of course when I
0:21
actually checked the footage my
0:23
microphone was not turned on and I
0:24
immediately raged and threw a tantra so
0:27
let's go ahead and talk about spark one
0:29
more time before I go insane have a good
0:32
one and I will see you in the iPad
Why Spark
0:34
alright so as it turns out today we're
0:36
talking about Apache spark this is a
0:39
tool that a lot of Engineers use but in
0:41
my experience is probably one that a lot
0:43
of Engineers don't understand why it is
0:45
that they're using so let's get started
0:47
by talking about that why would we use
0:50
spark well in order to understand that
0:52
we must first understand why mapreduce
0:55
sucks probably even harder than my
0:57
ex-girlfriend so let's get started there
0:59
mapreduce has three main issues with it
1:02
so let's touch upon all three the first
1:04
being that as I mentioned in a couple of
1:06
videos ago in mapreduce if we want to
1:08
express more complex functionality we'll
1:10
use chain jobs now chain jobs don't know
1:13
about one another effectively you're
1:15
just saying do job number one then do
1:16
job number two then do job number three
1:19
and what that means is that we have lots
1:20
of waiting so for example let's imagine
1:22
we finished this part of our mapreduce
1:24
job one but then this part is like
1:27
lollygagging over here we can't get
1:29
started on this part of mapreduce job
1:32
number two until this guy is done and so
1:35
this guy is just idly waiting right it
1:38
doesn't really do anything and as a
1:40
result we're just wasting our own time a
1:43
second thing is that each job requires a
1:45
mapper and reducer and frankly after
1:47
mapping one time a lot of the time we
1:50
don't really need another mapper
1:51
especially because keep in mind that
1:53
mappers actually perform sorting
1:55
functionality and doing a bunch of
1:57
unnecessary sorting is n log n
1:59
complexity which is super costly when
2:01
it's on a big data set such as the ones
2:03
we're using in batch processing now
2:05
number three is that we have tons of
2:08
disk usage so the issue with having tons
2:10
of disk usage is that obviously it's
2:13
expensive but mapreduce in particular
2:15
uses lots of disk because jobs
2:16
materialize an intermediate state so
2:19
keep in mind that every mapreduce job
2:20
goes from disk to disk and when we're
2:22
chaining them
2:24
we only care about the first and the
2:27
last outcome we don't care about this
2:28
middle guy right here and so wouldn't it
2:30
be great if we just didn't ever write
2:32
that to our hard drive because that
2:33
wastes a ton of time
2:35
so these are three main reasons why
2:37
mapreduce sucks and as a result of that
2:39
spark tries to improve upon all three of
2:42
these things so how does it do it let's
2:44
take a look at the architecture of a
2:46
typical spark job so what spark will
2:49
actually do and imagine we've got three
2:50
nodes in our Hadoop cluster here
2:52
performing a batch computation is it
2:55
will only write things to disk on input
2:57
and on output as you can see which is
3:00
super great but in addition to that as
3:03
opposed to using mappers and reducers
3:05
every single function that we want to
3:06
perform on our data is expressed as an
3:09
operator and operators can basically
3:11
have arbitrary code unlike mappers and
3:13
reducers where there's typically some
3:15
mapping phase a sorting phase a shuffle
3:18
and then a reduction operators can
3:20
basically do anything so you'll see an
3:22
example of an operator right here that
3:24
could be something like a mapping where
3:25
you're taking certain data and then
3:27
putting it into the next phase and then
3:29
here's one where we're actually doing
3:30
some shuffling where we're
3:31
re-partitioning our data and then here's
3:34
another example of a map or something
3:35
like that could be a reduce as well who
3:38
knows
3:39
so what also makes spark special is this
3:42
guy right here in between which is where
3:44
we actually hold our data and this is
3:46
known as an rdd or a resilient
3:50
distributed
3:53
data set I believe that's where it
3:55
stands for don't quote me on that I'm
3:57
drunk but
3:58
assuming that that's what rdd does stand
4:00
for which I'm pretty sure it is the
4:02
important thing about rdds are they are
4:04
in memory and as a result of being in
4:07
memory it means that we can avoid
4:08
writing our intermediate state to disk
4:10
and by doing so we speed up our
4:12
performance significantly in addition of
4:15
course since spark is aware of the
4:16
entire object computation graph for a
4:19
query it can actually just go ahead and
4:21
get started with computations as soon as
4:24
all of the data is available from the
4:26
previous steps so that's very important
4:28
to know
4:29
so spark can speed things up a lot
4:31
however you should now be thinking to
4:33
yourself shoot if spark is doing
4:34
everything in its intermediate States in
4:37
memory what happens if we fail in the
4:39
middle of the way of our spark job that
4:42
is going to be where we spend the
4:43
remainder of this video
4:45
so spark basically looks at a potential
4:47
Quarry plan right and a query plan is
4:49
going to look similar to this last slide
4:51
over here where it basically draws out
4:53
all the dependencies of all the stages
4:55
of that spark job and it's going to
4:57
Define every single operator as two
5:00
types of things basically a narrow
5:02
dependency or a wide dependency so what
5:05
is a narrow dependency a narrow
5:07
dependency is basically when you know
5:09
all computation
5:12
stays on one node
5:16
between two steps of the spark job so
5:19
what would be an example of that let's
5:20
say we've got a bunch of messages here
5:22
with the following keys
5:24
and then we've got some messages
5:25
corresponding to them and we basically
5:27
say for every single message get the
5:29
number of characters in that message
5:30
hence why we have three and four and et
5:33
cetera et cetera et cetera that's going
5:34
to be a narrow dependency because we
5:36
don't have to do any shuffling of data
5:37
to move on to the next step we're
5:39
literally just counting the number of
5:40
characters and that entire step is local
5:43
to the node where the data lives
5:45
so what actually happens in a narrow
5:47
dependency type of situation where we
5:49
have a fault of our Hardware let's say
5:52
that this guy right here
5:54
A3 and B4 goes down
5:57
so keep in mind that again we don't have
5:59
access to this anymore because this was
6:01
in memory but we do probably have access
6:03
to some sort of replica of it so we
6:06
still have the original data that came
6:08
from disk so we'll typically end up
6:10
doing here is because this is a narrow
6:12
dependency we know that all of the
6:14
computation for these steps can be
6:16
re-performed on any given machine and so
6:19
what we'll typically do to make that as
6:20
fast as possible is we'll actually
6:22
parallelize it so typically we would
6:24
move one piece of data over to the other
6:27
nodes in our cluster and basically split
6:29
that up accordingly
6:31
and then we could parallelize the
6:32
computation of that narrow dependency
6:35
such that we basically just go ahead and
6:38
split it up amongst the remaining nodes
6:40
in the cluster and as you can see now
6:42
what we've done is basically just remake
6:45
up all of that compute and that's great
6:47
we can rerun everything it'll be
6:49
relatively fast because if one node
6:51
fails we can split up that work amongst
6:53
a bunch of other nodes and we're good to
6:54
go however things aren't always this
6:57
simple
6:58
sometimes what we have are wide
7:00
dependencies so this is a little bit
7:02
more challenging to explain but the
7:04
example of our wide dependency in this
7:06
case is going to be this guy here the
7:09
reason it's a wide dependency is because
7:10
unlike narrow dependencies where all of
7:13
the data from one step to another is
7:15
contained locally on one node in a wide
7:18
dependency we actually have to rely on
7:20
data from other nodes in order to get
7:22
our computation done for the next step
7:25
so let's say for example that A3 A6 went
7:28
down right here right this is going to
7:31
be node number one
7:32
let's say in t equals three this guy
7:35
goes down so the issue right now is that
7:38
we need to be able to recompute this
7:40
state right here but we can also
7:43
recompute this whole state without also
7:45
having access to this state and this
7:48
state and this state now keep in mind
7:50
this guy is down this entire node and
7:54
more importantly another issue right now
7:56
is that this guy is no longer in memory
8:02
because we moved on to the next step
8:04
over here at T equals three and now we
8:07
no longer have access to our previous
8:09
state
8:12
so what does spark do to actually deal
8:15
with wide dependencies and basically the
8:18
issue of them being hard to recover from
8:20
well it'll say Okay a T3
8:23
we just got past a wide dependency so
8:26
right now what we're going to do is
8:28
write to disk
8:30
so basically whenever spark sees a wide
8:33
dependency and whenever we finish
8:34
dealing with that wide dependency we
8:37
write our data to disk the reason for
8:39
that being that it's very hard to
8:41
recover from these so in the event that
8:44
say a equals 9 goes down what we can
8:46
actually do is we recover our state from
8:50
disk
8:52
and I'm now realizing that that might be
8:54
hard to see so I'll write it again down
8:56
here we recover from disk
9:00
and then what you'll notice is from T
9:02
equals 3 to T equals 4 we only have
9:06
narrow dependencies narrow narrow narrow
9:12
and then we would resolve this problem
9:13
in the same way that we would with a
9:15
typical narrow dependency where I would
9:16
take a03 over here I would take a 6 over
9:20
here and then we would go ahead and
9:22
parallelize that computation as expected
9:25
with a narrow dependency and so the
9:27
general solution or the general point
9:29
I'm trying to make here is four wide
9:30
dependencies will occasionally have to
9:32
check point to disk and that is a little
9:33
bit more expensive but it allows us to
9:35
be fully fault tolerant which is great
Conclusion
9:38
so what is the conclusion in terms of
9:40
using spark what do I really want you to
9:42
take away from this video well for
9:44
number one it's certainly much faster
9:46
than mapreduce right because a nodes
9:48
will do computations as soon as the data
9:50
is available number two is that all of
9:52
the immediate state that uh you know we
9:55
don't really need to be writing to disk
9:57
is generally kept in memory of course
9:59
the exception to this is right after we
10:01
finish a wide dependency in which case
10:03
we temporarily materialize things to
10:05
disk so that we can make sure that we're
10:06
fault tolerant and number three and also
10:09
very important is that we don't have to
10:11
sort our data at every single step if we
10:13
have huge data sets this is extremely
10:15
time consuming at the same time spark
10:17
does use more memory than mapreduce
10:19
whereas mapreduce can basically keep
10:21
things on disk and due to sorting make
10:24
sure that the memory footprint is
10:26
relatively Low Spark is keeping all of
10:28
our computation state in an rdd and as a
10:31
result of that technically our compute
10:33
cluster may be using more memory during
10:35
a spark job than it would during a
10:37
mapreduce job and technically what that
10:39
means is that if we have certain other
10:41
things that we want to be doing with our
10:42
cluster there might be less memory
10:44
available nonetheless there's a reason
10:46
that you see everyone using spark and
10:48
that is because this speed benefit is
10:50
extremely extremely noticeable and as a
10:53
result spark is a great technology
10:55
anyways guys I hope you have a great
10:57
rest of the weekend I am going to enjoy
10:59
this drunkness right now and so I will
11:01
see you in the next one

##v42:

0:00
hello everybody and welcome back to your
0:02
least favorite YouTube channel today
0:03
we're going to be talking about stream
0:05
processing and when I say stream
0:06
processing I certainly don't mean taking
0:08
a leak what I'm talking about is
0:10
real-time event processing so this
0:12
subject has a lot of content in it and
0:14
so I've split it into four hopefully
0:17
relatively small videos partially so
0:19
that I can cover them more in depth and
0:20
partially because I'm lazy and don't
0:22
want to make longer ones so let's go
0:24
ahead and get into it alright so for the
What is Stream Processing
0:27
uneducated what exactly is stream
0:29
processing well the gist is so far in
0:32
terms of passing information around our
0:34
application we've really only spoken
0:36
about this through using a database
0:37
we've got one client or one application
0:40
server writing to a database and then
0:41
down the line another will read from it
0:43
however what if we want to be able to
0:45
react to things in real time as they
0:48
happen wouldn't it be great if one piece
0:50
of our application could pass something
0:52
like an event in real time to another
0:55
and it could react well that's what
0:57
stream processing is so stream
0:59
processing General framework is that
1:01
we've got some piece of our system
1:03
called the producer it is generating
1:05
events which are somehow passed over to
1:08
a consumer so obviously there's a lot of
1:10
different ways that we can do this but
1:12
let's start talking about how we could
What is a Message Broker
1:15
so typically what we will do is use an
1:18
event or message broker so not always is
1:21
this the case actually oftentimes or not
1:24
necessarily often but infrequently what
1:26
you'll see are actually direct TCP
1:28
connections between our producers and
1:30
consumers certain designs do warrant
1:33
this or make sense to actually just
1:35
directly connect between those two
1:36
systems and pass messages from one to
1:39
another the issue with that however is
1:41
if you have many producers and many
1:43
different consumers all listening and
1:45
producing the same types of messages now
1:47
all of a sudden you're maintaining o of
1:50
N squared number of connections and
1:52
frankly that's a lot of load on these
1:54
systems that generally speaking are
1:56
probably going to be doing some other
1:57
type of processing and we'd rather not
1:59
bog them down
2:01
typically instead what we'll use is a
2:04
dedicated system known as a broker which
2:06
sits in the middle of our producers and
2:08
consumers and so this way as opposed to
2:10
having o of N squared connections we can
2:13
actually maintain a linear number of
2:15
connections because kind of the the
2:17
brunt of the work maintaining them is
2:20
actually done by the broker itself and
2:22
the broker's main job is to pass those
2:24
messages from producer to Consumer and
2:27
depending what type of broker you use
2:28
there's obviously going to be some
2:30
additional functionality but for the
2:32
sake of this video I'm actually not
2:33
going to dive too deep into the
2:35
architecture of a message broker there
2:37
are multiple different implementations
2:39
of these but right now what I'm going to
2:40
ask you to do is think of this thing as
2:42
a black box that simply passes messages
2:44
from the producer to the consumer and
2:47
then we're going to talk about certain
2:48
applications of stream processing and
2:50
why we would use it in the first place
Why We Use Stream Processing
2:52
so what are our main reasons for
2:56
actually using stream processing well I
2:58
can think of three of them and these are
3:00
the three that I'm going to touch upon
3:02
in order to introduce the subject in
3:03
this video the first is grouping and
3:06
bucketing of events
3:08
oftentimes by like a time stamp or a
3:12
Time window or a trailing time window
3:13
we'll see how we do that in a second
3:15
another is something known as change
3:17
data capture and then a third is known
3:19
as event sourcing two and three do seem
3:21
relatively similar but I'll explain the
3:23
Nuance in a little bit so let's take a
3:25
look at time windowing certain events or
3:28
metrics or anything like that so that we
3:30
can talk about them a little bit more
3:33
so imagine that we've got ourselves a
3:36
producer over here this could be
3:38
something like a sensor or an
3:40
application server that produces logs
3:43
and of course those messages are now
3:46
being sent right over here to the broker
3:49
which then forwards them to our consumer
3:51
now imagine that what we've got below is
3:54
effectively just a view of the state of
3:56
our consumer which again is doing all
3:58
the processing of these messages so
4:01
let's imagine that we wanted to bucket
4:02
them into something called tumbling
4:04
windows so a tumbling window as you can
4:06
see are non-overlapping windows that
4:10
start at a fixed interval with a fixed
4:12
time size so in this case what we're
4:14
looking at here are one minute tumbling
4:16
Windows starting at the beginning of
4:18
every single minute so how would we
4:21
actually deal with this well at every
4:22
single event is going to have a time
4:24
stamp
4:25
from the time stamp we can extract the
4:28
minute
4:30
and then we can bucket them in our
4:32
bucket we could probably use a hash map
4:34
on this to perform this well and then
4:36
our hash map would probably have some
4:37
sort of list of elements where all of
4:39
the elements are the messages themselves
4:42
so that is known as a tumbling window
4:43
another common task is where we actually
4:46
create a Hopping window where hopping
4:48
windows can actually overlap with one
4:50
another so for example here is one five
4:53
minute hopping window from 12 o'clock to
4:55
1204 but then 1201 to 1205 is a
4:59
different hopping window and 1202 to
5:02
1206 is a different five-minute hopping
5:04
window so how can we actually go ahead
5:06
and get all of the events that are in
5:08
these well if you notice every single
5:10
five minute hopping window is composed
5:12
of five non-overlapping tumbling windows
5:15
so we can effectively do the same thing
5:17
we did before group all of our messages
5:18
into tumbling windows and then when we
5:21
need a given five minute hopping window
5:22
we can just aggregate the five tumbling
5:24
windows that make them up so in the case
5:27
of 12 o'clock to 1204 this guy over here
5:30
we're taking the 12 o'clock we're taking
5:32
the 1201 we're taking the 1202 1203 and
5:36
the 1204 and so we would have events e h
5:39
c d i and G and the last type of task
5:45
that we'll often see in terms of just
5:46
like doing timing on events is known as
5:49
the sliding window where effectively you
5:52
know we just want let's say the last
5:53
five minutes of events so what we would
5:56
use here is an in-memory queue or an
5:58
in-memory linked list and basically as
6:00
events come in
6:02
you know we're adding them to the back
6:03
of our queue and then we have a separate
6:05
thread that's saying oh shoot it's 1207
6:07
now 1201 is no longer valid let's remove
6:10
that from our linked list and now just
6:13
this is going to be our last five
6:16
minutes of data so hopefully that makes
6:19
sense a little bit not overly important
6:20
but it is one common use case of stream
6:22
processing let's look at another called
Change Data Capture
6:25
change data capture now this is
6:27
something I use very frequently in a lot
6:29
of the systems design mock interviews so
6:31
it's important that we understand what
6:32
this really means basically the gist is
6:35
a lot of times we're going to be writing
6:36
to a database right we've got our client
6:39
here
6:40
we've got our database
6:42
and from there we've got a second piece
6:44
of storage that we basically want to
6:46
keep in line with our database right
6:48
we've got some other piece of derived
6:50
data
6:52
so in this case the derived data would
6:55
be our search index you don't really
6:56
have to worry too much about what a
6:58
search index is for now I'll cover this
6:59
in a later video but the gist is when we
7:02
have a write that goes to the database
7:03
we also want that right to be reflected
7:05
in our search index so as you can see
7:08
we've got one right from the database
7:10
it's going into our message broker and
7:12
then the message broker is of course
7:14
going to forward that to our search
7:15
index so that our search index can be
7:18
updated so change data capture is really
7:20
really useful for allowing us to keep
7:22
our derived data in sync with our main
7:24
database which tends to be our source of
7:25
Truth this is good because it allows us
7:28
avoiding things like two-phase commit
7:29
which is very expensive whereas you know
7:32
you wouldn't want to do a two-phase
7:33
commit between our search index and our
7:35
database it's a lot easier to just use a
7:36
message broker
Event Sourcing
7:38
okay another type of thing is event
7:41
sourcing which at first is going to seem
7:44
very very similar to change data capture
7:45
but there is some Nuance here so instead
7:48
of actually writing directly to your
7:50
database in this case what you're going
7:52
to do is you're going to send all of
7:53
these guys right here which are known as
7:56
events directly to a message broker the
7:59
message broker is then going to forward
8:01
those to a consumer and then finally
8:03
those messages are going to get to a
8:04
database where they can be properly
8:06
written so what's the advantage of
8:08
throwing everything in the broker first
8:09
well notice that I called these events
8:12
and not rights the reason they're called
8:14
events is because they use database
8:16
agnostic language as you can see the
8:19
type of things that we're doing here are
8:20
things like me clicking the cart or me
8:23
changing the quantity of an item in my
8:25
cart the reason for this is that in
8:28
change data capture the thing that's
8:30
actually going into the broker is not
8:32
database agnostic this is specific
8:36
to the database
8:39
and so when we have database agnostic
8:41
events that are going into our broker
8:43
basically meaning that you know they're
8:45
not actually specific to what database
8:47
we use or what the state of the database
8:49
was at the time it means that let's say
8:51
20 years in the future I want to use a
8:54
new database
8:57
I can actually just go ahead and read
8:59
from that broker and translate those
9:02
events however I see fit I don't need to
9:04
rely on this data model this data model
9:06
could be outdated
9:09
and if we don't care about it or for
9:12
whatever reason it's no longer working
9:13
for us it's no longer useful for us it's
9:15
a lot more useful to have all of those
9:17
raw events that would be in the broker
9:20
so the main issue here of course is that
9:22
does assume that the broker is actually
9:24
holding on to events which it very well
9:25
may not be again that is one of the
9:28
subjects of next video do we actually
9:30
keep these events do we throw them out
9:32
what goes on it depends really on what
9:34
type of event broker that you're using
Once Message Processing
9:37
so the last topic that I want to cover
9:39
in this video is exactly once message
9:42
processing or event processing so
9:45
processing a message exactly once means
9:47
two things it means that first of all
9:49
you're going to process that message at
9:51
least once how do we know that we can
9:53
process it at least once well we need a
9:55
few guarantees about our message broker
9:57
for starters it has to be fault tolerant
9:59
and typically when I say something is
10:01
fall tolerant what I really mean is that
10:03
there's some sort of like right ahead
10:05
log so you make sure that everything
10:06
that goes in there is on disk in the
10:08
event that your computer just shuts down
10:10
so that is going to be some disk
10:12
resistance and also replication because
10:15
if I come and I smash that computer with
10:17
a hammer you having those rights on disk
10:20
is probably not going to help you very
10:21
much you probably need a second instance
10:23
of that message broker that also has
10:25
access to the message another important
10:28
thing here is consumer acknowledgments
10:30
how is it that I know that a message has
10:32
been processed at least once unless the
10:35
consumer reports back to me on the
10:36
message broker that it has processed it
10:39
that is very important consumer
10:40
acknowledgments are something that
10:42
you'll typically see in just about every
10:43
single message broker
10:45
on the other hand we also need to be
10:47
sure that we don't process these
10:48
messages more than once so there are
10:51
basically two ways that we can do that
10:53
the first is two phase commit now if you
10:56
know every single time we talk about
10:58
two-phase commit in this channel
11:00
generally speaking it's bad we want to
11:02
avoid it wherever possible but in this
11:04
case what would that look like well just
11:07
quickly zooming in we would have a
11:08
coordinator node which at the same time
11:11
reaches out both to the consumer right
11:13
over here and the broker it says to the
11:16
broker hey can you delete this message
11:18
are you good to do that will it break
11:19
anything if you delete it the broker
11:21
will probably say yes I'm fine doing
11:23
that and then it'll also say to the
11:25
consumer hey are you able to handle this
11:27
message and if so are you ready to
11:29
commit it now if both of these systems
11:31
say yes then the coordinator can reach
11:33
back out to them
11:34
and say go ahead and actually commit
11:37
that you're good to go of course
11:39
two-phase commit always very slow and we
11:42
avoid it when possible which is why the
11:44
other nice thing that we can possibly do
11:46
is make our message broker item potent
11:49
or not necessarily our message broker
11:51
but the combination of our message
11:52
broker and our consumer so what item
11:56
potency means is if we were to process
11:58
the message more than once it's the same
12:02
thing as processing ones there are no
12:04
side effects to passing the message to
12:06
the consumer multiple times so what's an
12:08
easy way of doing this well basically
12:10
every single message on the broker gets
12:12
assigned a unique key and when the
12:15
consumer sees a message with said key it
12:17
can just respond saying whether or not
12:18
it's seen the key before and if that
12:21
message comes back again it'll see the
12:23
key one more time and then respond
12:25
accordingly saying I've seen this I'm
12:27
not going to process it again of course
12:29
this does make a key assumption about
12:32
how we're doing our partitioning or our
12:34
consumption of messages in the sense
12:36
that we are assuming that the same
12:38
consumer is seeing the same message
12:40
every single time if it's possible that
12:42
I can have two different consumers read
12:44
the same message from a message broker
12:46
then we're in trouble because one of the
12:48
consumers may have already seen it and
12:50
stored that item potency key but on the
12:53
other hand the other consumer wouldn't
12:54
have seen that key before and then we're
12:56
in trouble we've just processed the
12:57
message twice so again that is something
13:00
to think about in term in terms of how
13:01
you're laying out which consumers are
13:03
getting which message anyways guys hope
13:05
this serves as a good introduction sorry
13:07
I've treated the message broker as a
13:09
black box thus far but the whole reason
13:11
for that is we're going to spend the
13:13
entirety of the next video figuring out
13:15
what's actually going on inside there
13:17
and tearing up that box as they say so
13:19
anyway I will see you in the next one

##v43:

0:00
hello everyone and welcome back to the
0:02
channel as you can see I've been growing
0:04
out this thick voluminous mustache and
0:07
coincidentally I don't know why I'm not
0:09
let into playgrounds anymore but anyways
0:11
today we're going to be talking about
0:12
stream processing and no I'm not talking
0:15
about R Kelly get your mind out of the
0:16
gutter I will be talking about the
0:19
architecture of message Brokers so I
0:21
have to go in about 10 minutes so let's
0:23
get into it and get started alright so
Stream Processing
0:25
let's start this video with a quick
0:27
review of all the stream processing
0:28
stuff that we did in our last video
0:30
since it's been about a week due to my
0:32
10K special so basically to put things
0:35
very simply all stream processing really
0:37
is is we have two sets of nodes in our
0:39
system we've got producers and we've got
0:42
consumers and they communicate with one
0:44
another via events now we could send
0:46
those events directly and some ways of
0:49
stream processing do this you could send
0:51
them directly over TCP for example or
0:53
UDP or something like xeromq which works
0:55
on top of those but the majority of the
0:57
time what we want to be using is
0:58
something called a broker because it
1:00
handles the load of dealing with all of
1:01
those connections for us and we can
1:04
scale it you know kind of independently
1:06
of our producer and consumer nodes which
1:08
is great so there are two main types of
1:10
Brokers that we're going to talk about
1:11
today they've got two fundamentally
1:13
different types of architectures and
1:15
those are in-memory message Brokers
1:16
right over here and also log based
1:19
message broker so as you can see I've
1:21
listed a few different examples of
1:23
implementations of these so if you hear
1:25
someone talk about Kaka for example that
1:27
is a log based message broker
InMemory Message Broker
1:30
okay so what is an in-memory message
1:33
broker let's go ahead and get started by
1:35
talking about that well it's basically
1:37
exactly what it sounds like an in-memory
1:39
message broker is one that operates on a
1:42
server where specifically all of the
1:44
events are kept in memory so the way
1:46
that this works is as you can see we've
1:48
got something like this right here which
1:50
is a linked list
1:52
or we could implement it with an array
1:55
in memory or something like that but the
1:57
general gist is we want to you know be
2:00
representing a queue and so we've got
2:02
this queue of messages right here in
2:04
every single message that's what all of
2:05
these circles are gets sent to a
2:07
consumer and eventually what's going to
2:10
happen is once it gets sent to the
2:12
consumer it's actually going to be
2:13
deleted from the Queue at least
2:15
temporarily and then once the
2:17
acknowledgment comes back from the
2:18
consumer saying this thing is handled
2:20
then it really does get deleted from the
2:23
queue now you might be thinking to
2:24
yourself oh this is great we've got a
2:26
queue of all of these messages this must
2:28
mean that you know if this guy is before
2:31
this guy in the queue that this guy is
2:34
going to get processed before this guide
2:36
gets processed and that's not
2:38
necessarily true why is that the case
2:40
well keep in mind that when this guy
2:43
gets sent to a consumer for example
2:46
consumer one
2:48
this guy can instantly be sent to
2:50
Consumer too as long as consumer 2 is
2:52
ready for it it is not the case that we
2:54
necessarily need to wait for the
2:56
completion of processing of the prior
2:58
message before sending the subsequent
3:00
message to a different consumer we're
3:02
effectively using round robin message
3:05
delivery in order to ensure that we can
3:07
get the maximum possible throughput in
3:09
this situation
3:10
so for example if this network
3:12
connection is slow or it's just you know
3:15
hard to process this event
3:17
maybe it's asking to do something
3:19
particularly taxing on the consumer it's
3:22
possible that a message that is further
3:24
back in the queue gets completed before
3:27
and earlier one does so keep that in
3:29
mind so what's the kind of General
3:31
conclusion of something like an
3:32
in-memory message broker well basically
3:34
again we're using round robin delivery
3:36
in order to maximize our throughput but
3:39
what that can lead to is out of order
3:41
processing the only way to ensure
3:43
getting in-order processing is by doing
3:45
something called fan out where instead
3:47
of having basically
3:49
multiple consumers for a given queue
3:52
what we would actually do is make a
3:54
second cue over here and this could be a
3:58
second partition for example and then we
4:00
would have you know consumer one
4:02
exclusively reading from this top queue
4:04
exclu consumer two exclusively reading
4:08
from the bottom queue but that kind of
4:09
defeats the point because we want to
4:11
maximize our throughput
4:13
okay so the other thing is that messages
4:15
in memory are actually going to be
4:17
deleted like I mentioned when they're
4:18
processed successfully we get rid of
4:20
them we don't think about them ever
4:21
again we literally erase them from
4:23
memory or garbage collect them so what
4:25
that implies is that we have poor fault
4:27
tolerance if this machine were to go
4:29
down unless we have something like a
4:31
right ahead log to write all of our
4:32
events to disk we're just going to lose
4:34
all of these events and additionally of
4:37
course we can't replay these messages
4:38
because we're deleting them once they
4:40
are consumed
4:41
of course instead of using a right ahead
4:43
log though which you know is going to
4:46
slow our rights down a little bit
4:47
because rights to memory are always
4:49
faster than rights to disk what we could
4:51
instead just do is effectively the same
4:53
thing as using a redhead log which is a
Logbased Message Broker
4:56
log based message broker so here's what
4:58
that is going to look like as you can
5:00
see we've got all of this stuff right
5:03
here which is on disk and of course
5:05
those are going to be sequential rights
5:07
and sequential rights on disk are faster
5:09
than random ones so let's say we've got
5:12
you know these four messages and they're
5:14
next to one another on disk
5:16
what a log based message broker will
5:18
actually do is make sure that all of
5:21
these messages are held in the exact
5:22
order in which they came in if a new
5:24
message were to come in message five
5:27
it would be written at the back of the
5:29
queue over here sequentially blah blah
5:32
blah sorry that right is uh not really
5:34
popping through but the point is in
5:36
addition to basically keeping everything
5:38
sequential log based message Brokers
5:41
will also ensure that all consumers read
5:43
the messages within a single queue in
5:46
the same order in which the messages are
5:48
stored so as you can see what the log
5:50
base message broker will do is actually
5:52
store the location of the last message
5:55
that each consumer is has read so for
5:58
example let's say consumer B is now
6:00
going to read message 2.
6:02
so it's going to process this it's going
6:04
to acknowledge that it was processed
6:06
back to the message broker then what the
6:09
message broker will do is now say okay
6:11
if we're going to send consumer B
6:13
another message the next one it's going
6:15
to receive is message three so there's
6:17
no kind of round robin to be done over
6:20
here in fact if we wanted to increase
6:23
our throughput at all between consumer a
6:25
and consumer B what we'd have to do is
6:28
create a second broker up here and then
6:31
consumer a could start reading from that
6:33
and then consumer B would still be
6:35
reading from this guy over here
6:37
now note that because we have to read
6:40
every single message in the queue in
6:42
order that does technically lower our
6:44
throughput the reason being let's say
6:46
that message 3
6:48
is hard to read
6:49
or I shouldn't even say hard to read but
6:51
let's say it's hard to process would be
6:53
the better term you know whatever it is
6:55
that it's making us do is kind of
6:57
expensive and Now consumer B is going to
7:00
do that so it's going to process
7:02
let's say that whole thing takes 60
7:04
Seconds
7:06
it means that it's going to be an
7:08
additional 60 seconds before all of the
7:10
remaining messages in the queue are
7:12
processed so any slow message is going
7:14
to be a bottleneck for all of the others
7:16
so that is very important it slows the
7:19
processing of the rest and we would have
7:21
to partition our queue with additional
7:23
consumers reading from other partitions
7:25
in order to increase throughput
7:28
at the same time the really nice thing
7:30
about the log based message broker is
7:32
that our messages are durable not only
7:34
are they on disk if our machine were to
7:36
go down but more importantly we don't
7:39
actually delete them once we've read
7:40
them and what that means is that if for
7:42
whatever reason we want to add an
7:44
additional consumer in the future to
7:46
reread those messages or perhaps we're
7:48
just convinced that we missed a message
7:50
in one place or another we can actually
7:52
just reread them all and perform all of
7:54
our computations or processing again
7:57
so now that we've pretty much talked
8:00
about everything there is to know about
8:02
our log base message broker or something
Conclusion
8:05
resembling Kafka or AWS Kinesis let's do
8:08
a little bit of conclusion where we talk
8:10
about some scenarios where we would use
8:11
each type of broker
8:13
so keep in mind that in memory is
8:16
basically really really good if we want
8:17
maximum throughput it's really quick to
8:20
read and to write from memory but even
8:22
in addition to that we don't have single
8:24
messages in that queue being a
8:26
bottleneck we're delivering them in
8:28
round robin and as a result of this we
8:30
can ensure that basically every single
8:32
message is going to be processed as soon
8:34
as there's a consumer that's available
8:35
to process it that is really really
8:37
great at the same time though it means
8:40
that those messages are going to be
8:42
processed out of order and they're also
8:44
not durable for later availability this
8:46
is actually really useful for us in some
8:48
circumstances think about for example if
8:51
I'm a user and I'm posting videos to
8:53
YouTube and you know you're also a
8:55
YouTuber and you know your friend is a
8:57
YouTuber and every single time that we
8:59
upload a video to YouTube YouTube has to
9:01
basically encode it on its own back end
9:03
it doesn't really matter to YouTube
9:04
whether my video gets encoded first or
9:07
your video gets encoded first or your
9:09
friends video gets encoded first the
9:11
work just has to get done and then it
9:13
can be stored word in their database
9:14
somewhere or other the point is though
9:16
because that order doesn't matter
9:18
because they're not going to have to
9:19
redo the encoding work in the future and
9:21
they just want to encode as many videos
9:23
as humanly possible to decrease the
9:25
latency between what I post and when my
9:27
video is actually available then the
9:29
in-memory broker is really really good
9:31
for them a similar type of situation
9:33
would be something like Twitter where if
9:35
you're familiar with how you actually
9:36
would design a site like Twitter users
9:39
typically tend to make a bunch of posts
9:40
and those posts are then delivered to
9:43
all of their followers dedicated cache
9:45
which represents their news feed now of
9:48
course if I post you know half a second
9:50
before you it doesn't really matter at
9:53
the end of the day whether my message
9:54
gets into the cache before yours does so
9:57
of course in that case something like an
10:00
in-memory broker is totally fine
10:02
at the same time there are a lot of
10:04
situations where a log-based message
10:06
broker would be really really great the
10:08
first that I'm thinking of is sensor
10:10
metrics the reason being sometimes the
10:12
order of these really matters let's say
10:13
we want to calculate something like a
10:15
trailing average of the last 20 events
10:17
well if I were to start processing the
10:19
events out of order that would be pretty
10:21
problematic for actually ensuring the
10:23
validity of my results this is also good
10:25
if say you know we currently use a
10:28
normal average but eventually we want to
10:30
move to an exponential moving average
10:31
and we want to have all of those metrics
10:33
available still having those messages
10:35
replayable and on disk in Kafka or
10:38
Kinesis means that we can go ahead and
10:40
do additional calculations down the line
10:42
another example would be each write from
10:45
a database that you know we're taking
10:47
all of those rights for example and
10:48
putting them into a search index so in
10:50
our last video this was called change
10:52
data capture so in change data capture
10:54
obviously it's very important that the
10:56
The Ordering of the rights of the
10:58
database are preserved because let's say
11:00
I say x equals five and then I say X
11:02
equals seven well that's very different
11:05
than if I said x equals seven and then I
11:07
overwrote that with x equals five so
11:09
it's very important in a situation like
11:11
change data capture to preserve the
11:13
order of our events and also if you want
11:15
to add new derived data sources down the
11:17
line it would be great if those events
11:19
didn't get deleted the second we put
11:21
them in our search index hence something
11:23
like a log based message queue is a
11:25
really appropriate Choice here anyways
11:27
guys hope this makes sense I gotta run
11:29
because I'm about to go hit some dangers
11:30
have an intramural softball game so I
11:32
will see you all this weekend

##v44:

0:00
everyone and welcome back to the channel
0:02
this is your host Oppenheimer as they
0:04
call me because the way I've been
0:06
farting these days is like I'm dropping
0:07
nuclear bombs uh on a more serious note
0:10
thank you all for 10 000 subscribers
0:12
means a lot to me incredible feedback
0:15
still on the channel which I'm really
0:16
happy about and I hope to do more
0:19
collaborations in the future the more
0:21
subscribers I have the less foot
0:22
pictures I have to sell so that may be
0:24
some bad news for some of you but for me
0:26
probably a nice thing anyways let's get
0:29
into some systems design today we'll be
0:32
talking about stream joins alright so
0:34
like I mentioned today we're going to be
0:36
talking about stream enrichment so
0:39
stream enrichment really just means
0:41
instead of taking an individual stream
0:43
event and passing it around through all
0:46
of these other parts of our system what
0:48
we're actually aiming to do is augment
0:50
that event with more information from
0:52
other pieces of our system
0:54
so again so far what we've looked at is
0:56
you know just having one producer one
0:59
consumer and a broker connecting them
1:01
but the reality of the situation is that
1:04
data is often coupled there are
1:06
relationships between the data and a lot
1:08
of times we might publish an event to
1:10
one consumer but on that consumer we
1:13
might want to you know add other pieces
1:15
to that data so we can pass it to other
1:17
places within our system Downstream and
1:19
you know have that piece of data be more
1:21
useful
1:22
so really what stream enrichment
1:24
effectively means is we want to perform
1:27
a join on our events with some other
1:29
pieces of data so basically what are
1:33
some examples of joins that we might be
1:35
doing in streams we're going to take a
1:37
look at three and talk about all three
1:39
of those so the first is going to be
1:42
stream stream joins so the unique thing
1:44
about these are that we're actually
1:46
matching events from two streams and the
1:48
example that I have absolutely
1:50
plagiarized from designing a data
1:52
intensive applications is basically one
1:55
where we've got one source or one
1:58
producer node that is publishing a bunch
2:00
of Search terms let's imagine I go into
2:01
Google and I type something like tissues
2:04
and a second that every single time I
2:07
click a link from Google is going to
2:10
publish the link that I clicked so that
2:12
we can later do some aggregation down
2:14
the line and look at how certain Search
2:16
terms and links interact with one
2:18
another you know whether a certain
2:20
search term might lead to more clicks or
2:22
anything like that or the average number
2:24
of clicks per search term anything like
2:26
that doesn't really matter so an example
2:28
of a link clicked would be amazon.com
2:31
so let's imagine then that for both of
2:33
those producers they're publishing
2:34
events right this would be an example of
2:36
an event and those events have a key in
2:39
this case it would be the user ID
2:42
and basically we want to be able to join
2:44
those events by key but of course it's
2:48
not enough to basically just handle
2:50
events and then say hey have we seen an
2:52
event from the other producer that
2:54
matches these why because well they
2:55
don't come in at the same time there's
2:58
some arbitrary
2:59
amount of time
3:04
where one event is valid right
3:07
you know let's say we wanted to hold on
3:09
to this guy for five minutes or
3:11
something
3:12
well where are we actually going to hold
3:14
it because if we don't hold it how are
3:16
we ever going to match it with any other
3:18
type of event we need to store it
3:20
somewhere and so typically what we'll
3:22
actually do is go ahead and store that
3:24
in the consumer so let's imagine that
3:26
this guy over here user 22 and tissues
3:29
came in first well what we would
3:31
actually do is cache that guy on our
3:33
consumer so that when 22 Amazon comes in
3:39
we can say oh wait
3:42
let's look at our hash map is there any
3:44
key with the value 22 oh there is let's
3:46
join them and then of course from there
3:48
the whole point is to enrich this data
3:50
augment it and then send it to other
3:52
parts of our system we can put it into
3:54
something like this over here which we
3:57
can call a sync queue so this queue is
3:59
just going to lead to other parts of our
4:01
system with our augmented data Okay so
4:04
we've covered stream stream joins where
4:06
effectively in our consumer we want to
4:08
Cache the results of both streams hold
4:10
on to those and then join them as new
4:12
events come in what are we going to do
4:15
for this stream table joins so stream
4:18
table joins are exactly what they sound
4:20
like effectively now what we want to do
4:22
instead of just using a stream and a
4:25
stream is we want to take the events
4:27
from one stream that are coming in and
4:28
actually join them with data that exists
4:31
in a database table so what would be
4:33
another example of doing this well for
4:35
starters let's imagine we've got a
4:37
similar event to last time right so
4:38
we've got Search terms
4:41
and then let's say we want to actually
4:43
go ahead and join those with the
4:46
demographics
4:47
of the person who is going to be
4:50
searching
4:51
so for example over here the primary key
4:54
is going to be the user ID in both cases
4:57
and so we've got this event
5:01
right from our database the reason we're
5:04
actually able to do this is because if
5:06
you recall from a couple of videos ago
5:07
what we can do with databases is
5:09
something called change data capture
5:15
and change data capture is going to
5:16
serve us in a few ways the reason being
5:19
that the naive solution to a stream
5:21
table join is to forget about this whole
5:24
thing right and instead every single
5:27
time that the consumer receives an event
5:31
it could make a network call
5:34
to the database
5:36
and that has one main issue which is the
5:39
network calls are slow
5:40
we don't want to have to query the
5:42
database every single time we receive an
5:44
event on our consumer because it's
5:46
extremely slow we would rather save much
5:47
more time process more events increase
5:49
the latency and throughput of our system
5:51
and so what we do instead is on our
5:54
consumer a better solution would be this
5:57
guy right here we keep an in-memory copy
6:00
of the database table we actually
6:02
perform some caching and that is going
6:04
to bring up a pretty obvious issue which
6:06
is consistency
6:09
how do we actually make sure that our
6:11
in-memory copy of our database table is
6:13
up to date because I might change the
6:15
demographic info for Jordan I might have
6:17
a birthday and now my age becomes 23 or
6:20
something
6:21
the way we do this again is change data
6:24
caps capture so a write goes to our
6:26
database that's step one the database
6:28
propagates that event step two to a
6:31
message broker
6:33
and then from there what's actually
6:35
going to happen is the message broker
6:37
can then be consumed by the consumer who
6:39
can now actually go ahead and update the
6:43
in-memory copy of the database table so
6:45
that when an event is received from our
6:47
stream we can actually perform our join
6:49
and then send it to some outbound queue
6:52
and this is going to greatly lower our
6:54
latency so using something like change
6:56
data capture turning a source of data
6:59
like a database into effectively another
7:02
stream allows us to make sure that we're
7:04
getting the minimum possible latency and
7:06
the maximum possible throughput in
7:09
processing all of these stream events so
7:11
now we have one more type of join to
7:13
touch upon and that is actually going to
7:15
be table to table joins now you may
7:17
think to yourself well why the hell do
7:19
we need streams for table to table
7:20
joints we can already just do that in a
7:22
SQL database and you would be completely
7:25
correct However the fact of the matter
7:27
is that database tables change over time
7:30
right and so let's say we want to make
7:32
sure that the result of our join is as
7:34
up to date as possible at all times Well
7:37
if we had a SQL database the naive
7:39
solution would just be polling
7:43
every five seconds or something
7:47
we run our query
7:52
and that's not great for a couple of
7:54
reasons for starters it's not real time
7:55
right we have to periodically run our
7:57
result second of all that's running a
8:00
massive query because we're doing a huge
8:02
join across two tables wouldn't it be a
8:04
lot better if incrementally as new
8:07
rights came in we could just join them
8:09
with the other table as need be as
8:11
opposed to having to redo an entire
8:13
massive query every few seconds well the
8:16
answer to that is probably going to be
8:18
yes so what do we do well basically we
8:22
can use change data capture
8:26
twice
8:28
which is pretty huge for us
8:31
so as you can see we've got table one
8:33
over here
8:34
we've got table two over here and every
8:37
single right that comes in is then going
8:40
to be propagated
8:41
to our message Brokers one for each
8:43
table
8:45
and then of course this way what we can
8:47
do is actually go ahead and cache on our
8:50
consumer copies of both tables now you
8:53
may think to yourself and you would be
8:54
correct well Jordan what if these tables
8:56
are too big to be held in memory on a
8:58
single consumer well then we would have
9:00
to basically do some partitioning
9:02
where we would split all of our cues
9:05
into multiple different pieces and then
9:08
probably we would have to have one
9:09
consumer per partition as long as
9:12
everything is partitioned in the same
9:13
way we'll be good to go
9:15
so yeah as you can see table table joins
9:17
are a really effective way of making
9:19
sure that you have up-to-date joined
9:21
data as the rights actually come in as
9:24
opposed to having to run a query on an
9:26
incremental batch job which is huge
9:30
so what are the patterns that we
9:32
actually see with stream joins well in
9:34
all three of those cases that we just
9:36
mentioned above there's one main
9:38
similarity which is that effectively
9:40
we've got some sort of state and we are
9:42
going to Cache it in memory on our
9:44
consumer in memory generally speaking
9:47
because that allows us to have maximum
9:49
performance in theory you could do it on
9:50
disk but sometimes this makes things
9:52
hard for joining unless things are all
9:54
sorted the same way so ideally you would
9:57
keep things in a hash map on memory and
10:00
perform joins via a hash join so this
10:03
leads us to a couple of issues and one
10:06
of them I just touched upon which is
10:07
that whenever you're storing things in
10:09
memory we've got a whole lot less space
10:11
on each consumer which is a problem
10:13
because our database tables are pretty
10:15
big especially if we want to do a stream
10:16
table or a table table join and as a
10:19
result of that we may have to actually
10:21
have many many consumers and many many
10:24
partitions of cues where each consumer
10:26
and each partition of cues are lined up
10:29
with one another as you know we might
10:31
expect so for example you might have all
10:33
the a keys on one cue and one consumer
10:36
all the B keys on another queue and
10:38
another consumer and partition like that
10:40
somehow
10:41
that being said obviously that's still
10:43
just a tough thing to do it's a lot of
10:45
things to keep organized there might be
10:47
a lot of overhead and of course issue
10:49
number two again is that whenever we're
10:51
keeping all of our data in memory
10:53
consumer state is not fault tolerant
10:57
why well because it's in memory so if a
11:00
consumer goes down we lose all of the
11:02
cash data that it had and then we would
11:04
have to somehow get it back which you
11:06
know depending on the type of message
11:07
broker that we're using is not always
11:10
possible even having a right ahead log
11:12
isn't necessarily enough the reason
11:14
being that we have multiple partitions
11:16
of consumers and as a result even if
11:20
we're able to bring back our old State
11:22
on one consumer the other partitions of
11:24
consumers might be far ahead of it and
11:27
have processed more messages and now
11:29
they're basically out of sync with one
11:30
another
11:31
so the kind of question is here well we
11:34
have a ton of partitions to manage and
11:36
we need to be able to achieve fault
11:38
tolerance how can we do it and that
11:40
right there is going to be the topic of
11:42
our next video which is all about Apache
11:45
flank and stateful stream processing
11:47
Solutions so I will see you guys for the
11:49
next one again everyone thank you so
11:51
much for 10K genuinely means a lot to me
11:54
love teaching you guys love getting good
11:56
feedback and I love interacting with you
11:58
all in the comments so let's keep it up
12:00
I'll see you all soon

##v45:

0:00
hello everybody and welcome back to the
0:03
channel I know this is supposed to be a
0:05
systems Design Channel but here is a
0:08
piece of Life advice that is not systems
0:10
design related for a few more days IHOP
0:13
is doing five dollar unlimited Pancakes
0:15
on an unrelated note for some reason
0:18
I've been having really bad shits lately
0:20
but anyways let's go ahead and get into
0:22
the video because today we're talking
0:23
about stream processing Frameworks
Context
0:25
alrighty so like I mentioned today we're
0:27
going to be discussing stream processing
0:29
Frameworks so basically a lot of context
0:32
for this video comes from the last video
0:34
in which we discussed data joins in
0:36
streams and what that really requires
0:39
intuitively is that in our consumer of
0:42
multiple streams we basically need to be
0:44
caching a lot of the results of the
0:46
events that we've seen so far so if you
0:48
can see here for example if we wanted to
0:50
join two streams one for searches from a
0:52
user ID and one for clicks on a user ID
0:54
we would need to effectively make sure
0:56
to cache all of the things that we've
0:58
seen so far place them in some sort of
1:00
cache map and then put them in a hash
1:02
join so that we could join those events
1:04
and then put them into some sync queue
1:08
but of course that does beg the question
1:10
how can we make sure that all of our
1:12
consumers are fault tolerant because
1:13
when you store things in memory that
1:15
consumer can go down and especially when
1:17
we've got a lot of consumers this can be
1:19
a problem fault tolerance is not easy
1:21
and we will discuss why so stream
Fault Tolerance
1:24
processing Frameworks that is hopefully
1:26
going to allow us to be fault tolerant
1:28
and in addition to that even more
1:30
importantly ideally make sure that every
1:32
single event that we see only affects
1:35
the state of each consumer once this
1:37
isn't exactly the same as exactly one's
1:40
message delivery guarantees because in
1:42
theory a message can and will be
1:44
replayed right it's not guaranteed that
1:47
you know if there's another system
1:49
outside of your group of consumers that
1:51
they might not be affected multiple
1:53
times but within your consumers within
1:55
what's managed by your stream processing
1:57
framework each message should only
1:59
affect your state once so what are some
2:01
actual examples of stream processing
2:03
Frameworks well we've got flank we've
2:05
got spark streaming we've got tez we've
2:07
got storm I personally am most familiar
2:09
with Flink just through looking into it
2:11
the most so I'm going to talk about that
2:12
a lot but I can say with certainty at
2:14
least between flank and something like
2:16
spark streaming the main difference is
2:18
that spark streaming uses micro batches
2:20
where from an event queue we might pull
2:22
five or ten elements at a time whereas
2:24
flank is Real Time effectively meaning
2:27
that it handles events as they come in
2:29
which in theory should lower the latency
2:31
of your processing time of each message
2:33
which is good another thing about flank
2:36
and Spark streaming at least are that
2:37
they are declarative meaning that as
2:40
opposed to having to specify every
2:42
single detail of computation if you have
2:45
a partition setup which you likely
2:46
probably will you can simply kind of
2:49
specify the target of your output format
2:52
you know what you're looking for in your
2:53
data what type of joins you want to do a
2:55
little bit but generally speaking you've
2:58
got some sort of job manager and it's
2:59
going to handle a lot of the actual
3:01
logic under the hood for you which is
3:02
very very nice the last thing is that a
3:05
lot of people do confuse stream
3:07
processing Frameworks with the message
3:08
Brokers themselves they are not the same
3:10
when I say stream processing Frameworks
3:12
generally speaking I am referring it to
3:15
the stream consumers
Stream Consumers
3:16
so let's ask ourselves why is it that
3:19
fall tolerance is hard because the
3:21
low-hanging fruit of fault tolerance is
3:23
basically you know just having a bunch
3:24
of replicas of a consumer and you know
3:28
that's easy enough and and every single
3:30
time that a consumer went down we could
3:32
just restore one of the replicas and
3:34
place that in our Flink setup instead
3:37
but uh it's actually not so easy and I
3:40
will explain why right now so let's
3:42
imagine that we've got the following
3:43
setup right we've got one producer node
3:45
which is outputting to two different
3:47
cues then in addition to that we've got
3:49
two consumers of those cues and each of
3:51
those consumers is going to in turn be
3:55
publishing to sync cues which go to our
3:57
last consumer consumer three
3:59
so let's imagine now that we've got
4:01
consumer two over here and the first
4:04
thing that it's going to do is you know
4:05
receive a message from the input queue
4:07
push a message to its sync queue so
4:09
that's step one step two is that
4:11
consumer two goes down so it's going to
4:13
die and it's going to go down before it
4:16
actually has the chance to register with
4:18
this guy over here that it processed the
4:21
message successfully so now this queue
4:24
is not going to know that it is no way
4:25
to know that the message over here has
4:29
actually been put into this queue over
4:30
here and C3 will be able to see it so
4:33
the issue with that is that when C4
4:35
comes up and replaces C2 C4 is going to
4:39
read from this queue it's going to get
4:41
that message
4:42
and it yet again is going to place it in
4:44
this queue and now that message is
4:46
duplicated C3 is going to see it twice
4:48
so how is it within flank that we can
4:52
actually guarantee that every single
4:53
message is going to be processed not
4:56
just at least once but also only once
4:59
well the main answer is that we are
Checkpointing
5:02
going to do this via checkpointing so
5:05
typically what Flink will do is we've
5:08
got all this state in a bunch of our
5:10
different consumers and occasionally
5:12
we're going to checkpoint it right over
5:14
here into S3 that way if a single node
5:17
goes down of our consumers what we can
5:19
actually do is go ahead and restore our
5:22
state from our checkpoint because the
5:24
checkpoint is going to contain the state
5:26
from all of our consumers and then from
5:28
there we can actually replay the
5:30
messages in our cues the reason we could
5:32
do that is because we require replayable
5:35
cues now if you remember from two videos
5:37
ago generally speaking that's going to
5:39
be log based message Brokers things like
5:41
Kafka where effectively all of the
5:43
events stay on disk and are not removed
5:45
from the queue after they are read but
5:48
instead are persistent so how do we
5:50
actually go ahead and take these
5:52
checkpoints well like I mentioned flank
5:54
under the hood has some sort of job
5:56
manager right in that job manager you
5:58
don't really have to worry about it too
5:59
much it's just one of your nodes
6:01
probably attached to a zookeeper
6:03
instance somehow just to keep track of
6:05
which you know consumers are running
6:06
which are up which are down same for all
6:09
of your Kafka cues or anything like that
6:10
and so let's imagine we have a similar
6:12
setup to the previous example that I
6:14
just mentioned where effectively you
6:16
know we've got a producer publishing to
6:19
two consumers and then those consumers
6:21
themselves are publishing to a third
6:23
consumer and we kind of have a join
6:25
there of two cues so what the job
6:27
manager will actually do is the
6:29
following as you can see we've got this
6:31
B right here and what that's called is a
6:34
barrier message so here's how the
6:36
barrier message is actually going to
6:37
work it is going to make its way through
6:40
the queue
6:41
get over here to the end and then once
6:45
any single node receives a barrier
6:47
message for example C1 is going to see
6:50
that b it is then going to checkpoint
6:52
its state
6:53
and place it in S3 simple enough right
6:57
same thing for C2 eventually the B is
6:59
going to come here checkpoint it's state
7:01
place it in S3 now the really really
7:05
cool thing about barrier messages is
7:08
that they allow us to make sure that all
7:10
of our snapshots are causally consistent
7:13
the reason being that a node for example
7:16
such as this one right here C3 is only
7:19
going to take its snapshot once it
7:21
receives a barrier message from all of
7:24
its input cues so it's not enough if we
7:27
only see this guy right here up top we
7:29
have to make sure that we actually see
7:31
every single barrier message from all of
7:34
the input cues and what that allows us
7:36
to do is it basically gives us some
7:38
amount of state or rather some point in
7:41
time where all of the messages that have
7:45
been processed are the same on every
7:47
single node in our system right anything
7:50
else that could have been additionally
7:53
processed we know is not going to be a
7:55
part of our checkpoint and I'll make
7:57
sure to kind of Link the semantic
7:59
reasoning for this below because I don't
8:01
really want to do a full proof in like a
8:02
10 minute video but the gist is that we
8:05
have actually
8:06
we effectively get a consistent state of
8:09
our data where we know that when we
8:11
resume from our snapshot every single
8:14
event that has been played has been
8:16
played in all of our consumers and
8:18
similarly every event that has not been
8:21
played has been played in none of our
8:23
consumers and so as a result of that we
8:26
can actually rely on our snapshots a
8:28
node goes down we back up from our
8:30
snapshot we replay as expected because
8:32
keep in mind these Kafka cues actually
8:35
will keep the state
8:38
of every consumer
8:41
so they remember exactly where each
8:44
consumer was during this snapshot
8:46
because you know we're just going to
8:48
read right after the barrier node so
8:51
wherever the barrier node was from one
8:52
message on right there that's where
8:54
we're resuming from the snapshot which
8:56
is great
8:57
and so
8:58
as a result of that Flink is able to not
9:01
only ensure fault tolerance but let's
9:03
say C3 went down
9:05
as opposed to having to replay every
9:07
single message that was in both of these
9:09
cues in order to restore its state
9:11
instead we can just restore from a
9:14
snapshot
9:15
and then basically go ahead and only
9:17
have to replay a few of those messages
9:19
hopefully this generally makes sense so
Conclusion
9:22
what's the conclusion of a technology
9:24
like Flink well first of all their
9:26
snapshots are super lightweight the
9:28
reasoning being that uh you're not
9:30
actually doing any locking or directly
9:33
writing to the objects or the state and
9:35
memory but flank will actually make
9:37
copies of the state specifically so that
9:39
you don't have to lock when you receive
9:41
barriers which is really great for
9:43
keeping things lightweight and
9:44
relatively quick once the snapshot is
9:46
taken then all of that duplicate State
9:48
can be garbage collected additionally
9:50
this is going to allow us to ensure that
9:52
all messages affect State on our
9:54
consumers exactly once their great
9:57
guarantees about the snapshots which
9:59
ensure fault tolerance but also more
10:01
importantly ensure that we don't have to
10:03
replay every single message of all time
10:06
in the event of a node crash there could
10:09
literally be hundreds of thousands if
10:11
not millions of messages and if a node
10:13
went down and we had to replay a million
10:15
message our entire stream processing
10:17
setup would be down for probably days so
10:20
as a result it's extremely important
10:22
that we can snapshot restore from that
10:25
snapshot and then only have to replay a
10:27
few messages from there to get back to
10:29
where we want to be so again guys this
10:32
is a super useful technology for stream
10:34
processing and it's very important that
10:36
if you come up on a systems design
10:38
interview question where it actually has
10:41
to do with stream processing and
10:42
somebody asks you how you're going to
10:44
make sure that your consumers are fault
10:45
tolerant you want to know how something
10:47
like Flink might work because you never
10:49
know when someone might ask you to
10:51
redesign something similar anyways guys
10:53
have a good day and I will see you for
10:55
the next one

##v46:



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

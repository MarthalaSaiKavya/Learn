##v1:

0:03
Yeah, hi, everyone. I hope you had a nice long winter break and
0:06
did something fun. And yeah, already for the new semester. My
0:09
name is Sebastian Raschka. And I'm an assistant professor of
0:12
statistics working mainly on machine learning and deep
0:15
learning. So I'm particularly interested and excited about
0:18
this class. It's about deep learning, as you may know. So
0:22
and that's very, I have closely related to my research. So in
0:25
this brief video here, I just wanted to introduce myself and
0:30
yeah, what we are going to talk about today. So maybe just as a
Icebreaker
0:34
quick icebreaker. So I actually literally spent some lot of time
0:40
over the winter break on the ice, doing some cross country
0:43
skiing and enjoying Wisconsin and the landscape here. I really
0:48
like yeah, Wisconsin snow and stuff like that. So if you ever
0:52
need a break from studying and want to go outside there are a
0:55
lots of beautiful parks here, state parks and also mostly it's
0:59
not very crowded there. So it's actually a great time now you
1:02
have to hang out outside to do some exercises and have some
1:05
fun next to studying. But yeah, back to back to the lecture here
Course Introduction
1:10
or class. So on today, I will mainly cover a few topics
1:16
related to how the class is organized. I will give you a
1:19
brief overview of what to expect in this course, what topics we
1:23
are going to cover, how we are going to talk to each other
1:26
because yeah, it's all virtual and asynchronous. However, we
1:30
will have live office hours via zoom. So there will be some
1:34
live component and we will also have everything organized on
1:38
canvas where everything is easy to find, there will be an online
1:41
forum to ask questions also asynchronously if you like, or
1:45
prefer. But again, we will also have live office hours for
1:48
questions and things like that. Yeah, I will actually turn off
1:52
the camera very soon when I talk about the remainder of these
1:56
topics listed here, because I'm using an iPad for this class,
2:00
and it lies flat on my desk. So it won't be very interesting to
2:05
watch me taking notes on my iPad, because the camera would
2:09
be just pointed towards the top of my head. So I will be
2:12
switching to the iPad view soon. Um, nonetheless, I think using
2:17
an iPad and the annotation feature is actually quite useful
2:20
to illustrate some concepts better than just using the
2:23
slides. So after giving you the course overview here, I will
2:28
also then later introduce machine learning and machine
2:32
learning is not a requirement for this class. Some of you I've
2:35
already seen based on the class list have taken statistics 451,
2:39
which I taught last semester. This was the introduction to
2:42
machine learning and statistical pattern classification. So in
2:45
this class, we talked more about traditional methods for machine
2:49
learning. And I was very careful when I designed these two
2:52
courses that there is no overlap. So the other class is
2:56
focused on traditional machine learning, we cover decision
2:59
trees, random forests, other ensemble methods, gradient
3:02
boosting, and so forth. In this class, though, we will be
3:05
entirely focused on deep learning and deep neural
3:08
networks. So there will not be any requirement from the last
3:12
class for this class. So everything right now will be
3:16
relatively new, except of course, some overlaps that are
3:20
concerned with supervised learning, basically that we are
3:23
interested in classifying things. So that will be the only
3:27
overlap. But I don't think there will be a disadvantage if you
3:31
take this class without having taken 451. But yeah, long story
3:36
short, I will give you a brief overview of what machine
3:39
learning is in this class. And then also just outlining how
3:44
supervised machine learning workflow looks like some of the
3:48
necessary jargon and notation, and then also a little bit about
3:52
the practical aspects of this course, because there will also
3:55
be a class project, and we will be using pytorch and doing also
4:00
some coding in this class. So in this way, there will be
4:03
conceptual and practical aspects. And I hope that is a
4:06
good mix yet to prepare you for machine learning projects and
4:12
deep learning projects, and of course, also deep learning in
4:15
both academia and industry. So in that way, let me then
4:18
switch over to my iPad and get started with the course
4:22
overview.

##v2:

0:02
All right, let's now get started then with the contents I
0:04
prepared for this week. I thought I would start with a
0:08
short teaser, what you will be able to do after this course. Of
0:12
course, it's a long journey 1515 weeks in the future. But at
0:17
some point, you will be able to accomplish something really
0:20
cool with deep learning things you will learn in this class. So
0:23
here are a few examples of class projects that students worked on
Class Projects
0:28
in the previous semesters. For example, in this project,
0:31
students converted audio signals into spectrograms, for example,
0:37
spoken text. And then they applied convolutional networks
0:42
to classify different texts and to extract language out of the
0:46
audio clips. So in this case, it was actually not language, I
0:49
just see it was finger snapping and here singing. So a
0:53
distinguishing between different audio inputs. So it was one
0:57
example of a class project from last semester. Another one was
1:01
working with 3d convolutional networks. So this is a 3d
1:05
version of the so called MNIST data set, which you will be
1:08
seeing a lot in this class, or at least in the introductory
1:11
lectures later on, because it's a simple data set to get
1:14
started with neural networks. And yeah, in this project, the
1:19
students worked with frmi or magnetic magnetic resonance
1:24
imaging data. So like brain scans, and so forth. And yeah,
1:28
classifying different types of brain scans. So that was another
1:32
interesting project. Or also, yes, students worked with
Style Transfer
1:36
different types of generative adversarial networks, which will
1:39
also be covered at the end of this class, where you will be
1:43
able to generate new data, or also mix data from different
1:47
data sources. So here, the students are mixed artistic
1:52
or paintings or photographs, artistic inputs with a portrait
1:58
of a photo model. And then the output was basically here shown
2:01
on the right hand side, like a portrait of a person mixed with
2:06
a different styles. So this would be an example of style
2:09
transfer. Um, yeah, why did I pick these three projects? That
2:13
was kind of arbitrarily. It was just something. So I looked at
2:19
the projects from last semester, to be honest, and looked at
2:21
which ones had nice figures. So in that way, it looked nicer on
2:26
slides. But of course, you are free to work on whatever you
2:30
like for your class project. And I will talk more about that
2:33
later. I don't want to overwhelm you with too many things at the
2:36
beginning. Just wanted to show you some examples of things you
2:40
will be able to accomplish at the end of the semester. Yeah,
Research
2:45
also, if you're interested, a little bit about my research, so
2:48
I'm working a lot on machine learning and deep learning. So
2:52
also, yeah, just compiled an overview here of projects I
2:56
worked on. So just to also introduce myself and what I'm
3:00
interested in. So yeah, last year, for example, I worked on
3:04
rank consistent order regression networks, we call that method
3:07
coral, which is for, yeah, you can think of it as classification
3:13
of ordinal inputs. So if you have class labels that are
3:17
ordered, and we want to sort them or predict the right order
3:20
of the labels and also the numeric value associated with
3:24
it, that for that we developed networks here, applied to age
3:28
classification, or we worked on face privacy, we call this
3:32
method privacy net, where we can hide facial attributes, for
3:36
example, age and gender and race and so forth, from the input
3:41
images for protecting one's privacy. Also, yeah,
3:46
collaborated with people from Nvidia was more like a review
3:49
article, we wrote about the latest trends in the realm of
3:54
Python, machine learning and deep learning. In particular, the
3:58
focus on GPU memory. And that's also something we will be
4:01
talking more about later when we talk about the tools that we
4:05
will be using for this class. Yeah, with a student of mine, I
4:09
also wrote another review article here on machine
4:13
learning and AI based approaches for bioactive ligand discovery.
4:17
So yeah, one of my students is working on small ligand
4:21
discovery and synthesis, also using generative models and
4:26
generative deep learning models for in the context of molecule
4:29
molecular synthesis and design. And here, another student of
4:34
mine is working on few shot learning. So few shot learning
4:37
is a branch of deep learning that is concerned with learning
4:42
from small data sets. Most of the time people use meta
4:46
learning or transfer learning, we will be talking more about
4:49
transfer learning later in this course, we won't be covering
4:53
few short learning though, I may ask though, my student maybe to
4:56
give a small guest lecture. If he has time later this semester,
5:01
and John G, he was working also on this paper, he is also our
5:04
TA in the semester. So if you are interested, you can ask
5:08
John G more about different future learning approaches, and
5:11
he would be very excited to chat more about you more with you
5:15
about that, I think. So during office hours, if you have
5:18
questions about few short learning, I think he would be
5:20
excited to talk more about it, because he's always excited to
5:23
talk about it. Yeah, and lastly, I'm also working on some
5:28
traditional machine learning methods. So this was in a
5:31
collaboration, where we used not deep learning, but traditional
5:35
machine learning methods, in this case, nearest neighbor
5:38
methods for yeah, also predictions related to
5:42
computational biology. So here, this was concerned with the
5:46
structure of GPCR, which is a G protein coupled receptor that
5:50
is, yeah, very important protein, protein receptor. It's a
5:57
binding to small molecules in humans. And yeah, most most drug
6:02
targets are actually targeting GPCRs. But here, this was more
6:05
like, yeah, fundamental computational biology research,
6:10
analyzing the structural composition of these proteins. So
6:14
this is just a little bit about me. So you can probably see a
6:18
theme is that I like working on deep learning, and also have
6:22
some interest in computationally computational
6:25
biology applications. So these two are basically my main
6:30
research areas and things I'm really excited about. Okay, but
6:35
now let's talk more about the course. So yeah, for this course,
Course Structure
6:40
I planned lots of topics, so mainly deep learning and
6:43
generative adversary networks, like, like the course title
6:49
suggests, and I structured this course into five parts. So here
6:54
are parts on 123. And on the next slide, I have some more
7:00
parts the remaining two. So first in the introduction, that's
7:05
where we are right now, I wanted to give you a brief overview of
7:08
this course, and also introduce machine learning and deep
7:11
learning. That's what we are going to do this week. Then, I
7:16
want to also briefly briefly talk about the history of deep
7:20
learning. And I think that's interesting, because that helps
7:24
you understanding like where the things and motivations are
7:28
coming from. Because yeah, deep learning, the term deep learning
7:32
is relatively new, it emerged about 10 years ago. But it has a
7:37
long history. Because yeah, deep learning, you can think of it as
7:40
a fancy term for neural networks. And neural networks
7:45
have been around for at least 6070 years. And yeah, some ideas
7:50
that emerged very early on that motivated the development of
7:54
different later ideas later on. And we will be covering a lot of
7:59
things related to neural networks. So in this on this
8:02
lecture, you can think of it as the big picture overview. So we
8:08
will then just briefly cover the history and then later when we
8:12
are introducing different topics in this lecture, we will do this
8:16
step by step and relate that back to the history and also
8:19
motivate why we we learn about them and why they are useful.
8:23
Yeah, and then we will talk about one of the early methods
8:26
of machine learning, a single layer neural network. So the
8:31
perceptron algorithm, it's a very traditional algorithm. It's
8:34
not very commonly used nowadays anymore. But I think this is
8:38
like an easy going introduction to the problem of classification.
8:42
So classifying oops, classifying things, putting things into
8:49
different categories. And yeah, I think that will be a good
8:53
introduction to get started with the topic. And then we will have
8:57
a small part two here, which is concerned with the mathematical
9:04
and computational foundations. So with that, I mean, like
9:07
introducing some mathematical necessities, like linear
9:11
algebra. So in deep learning, linear algebra is usually used
9:15
usually used to express things more compactly. Technically, we
9:20
can, or we could use deep learning without linear algebra,
9:24
but it would be very hard to write it down and also slow to
9:28
implement because when we use deep learning and practice, the
9:32
computing libraries that we use, they use, or they rely on linear
9:37
algebra, computational routines that help us executing certain
9:42
computations more efficiently compared to let's say, a Python
9:45
for loop. So linear algebra is like, in that way, very
9:49
important for deep learning, we won't be covering or needing any
9:53
advanced linear algebra concepts, just simple vector
9:57
dot products and matrix multiplications. That's it
9:59
basically. But I think it's still worthwhile covering this in
10:04
a separate lecture, because laying down the groundwork for
10:08
the later lectures properly makes everything later on a
10:11
little bit easier, I think. Then we will be talking about gradient
10:15
descent. That's a calculus topic. That's gradient descent
10:20
is the main method for parameterizing or training neural
10:24
networks. And then after this is more like a refresher. After
10:29
covering this topic, we will talk about automatic
10:32
differentiation with pytorch. So automatic differentiation is
10:36
calculus on the computer, you can think of it like that. And
10:39
we will be using a tool called pytorch, which is a library for
10:43
linear algebra, automatic differentiation, and then also
10:48
neural network training, or deep learning. And it also allows us
10:52
to implement things on the GPU to make things more efficient. So
10:57
I will also explain then here in lecture seven, how you can use
11:03
cluster and cloud computing resources, it will be a
11:05
relatively short part, though, because yeah, the main the main
11:11
topic is deep learning. Of course, computational aspects
11:15
are necessary. But for this introductory class, you don't
11:19
have to necessarily be an expert programmer and user of computers,
11:24
you should be familiar with certain things on your computer,
11:28
and certain programming aspects. But we are not here in machine
11:32
learning engineering more like giving a conceptual overview. So
11:35
you will get by with some free resources that I will talk about
11:39
in this lecture. But if you're interested, you can of course
11:42
also use more advanced resources, for example, our
11:47
campuses, HTC, and so forth. But it won't be required for this
11:52
class. Yeah, and then after the mathematical and computational
11:56
foundations, we will be talking then finally about neural
11:59
networks. So in this part three, I will lay the groundwork for
12:04
your deep learning. So we will talk what we start with logistic
12:07
regression, which you can think of a single layer neural
12:10
network. So this is basically an extension of this single layer
12:16
neural network that we talked about earlier, that is now
12:21
differentiable. And using the logistic regression as a starter,
12:25
we will add additional hidden layers, making this a deep
12:29
network, which is also called multi layer perceptron. And then
12:33
and then we will learn how we can train such a multi layer
12:36
perceptron using the backpropagation algorithm. Then
12:40
parts here, parts 10 to 12 are more like tricks for training
12:45
deep neural networks, for example, regularization
12:48
techniques to avoid overfitting on your input normalization and
12:53
weight initialization, it's just making training neural networks
12:57
more robust and faster. And then also talking about learning
13:01
rates, and some advanced optimization algorithms. So like
13:06
fancier versions of gradient descent, essentially. And these
13:10
are really kind of necessary to make neural networks work well
13:15
in practice. These topics may not sound super exciting,
13:18
especially like 10 and 11. But they are super useful or
13:21
important even yet to make neural networks work well. And
Course Outline
13:26
then we will get to the interesting parts in this course,
13:29
or I would say the more advanced parts. So here in part four, we
13:34
will then be talking about deep learning for computer vision and
13:38
language modeling. So we will spend a lot of time on
13:42
convolutional networks. So this is one big topic. And then we
13:46
will also talk about recurrent neural networks, they are for
13:49
language modeling. So convolution networks are more
13:52
for image modeling, although you can also use a one dimensional
13:55
convolutional network for text. But yeah, text will be more
13:58
focused on in lecture 15. And these will kind of also lay the
14:05
groundwork for the deep generative models that we will
14:09
be talking about. So in terms of deep generative models, we will
14:14
be talking about auto encoders, so called variational auto
14:18
encoders, then we will talk about generative adversary
14:22
networks, you may already have heard of them as GANs. So just a
14:25
long form of writing GAN, generative adversary network,
14:29
then this is also a very big topic, we will have a two
14:34
lectures on that. So one introduction and then one on some
14:37
more advanced GANs, for example, the Wasserstein GAN, and then
14:42
also how we can evaluate and compare different GANs to each
14:45
other. Because now, in this part, we are focused on
14:51
prediction, oops, prediction. And, and in the second part,
15:02
here, we are focused on generating things. So it's a
15:08
little bit different, it's a little bit trickier to evaluate
15:10
these models. So we will have a lecture on that. And then I also
15:15
plan to cover some aspects about recurrent neural networks for
15:20
generative modeling, for example, generating new text,
15:23
using in a sequence to sequence context. So here in lecture 15,
15:29
I will first try also to focus only on the prediction parts.
15:32
But we will be revisiting this topic also for generating new
15:36
data on text, and then also going into a more advanced
15:40
topic, adding the so called attention mechanism to RNNs, and
15:46
then also explaining self attention in the context of
15:49
transformers, which are underlying the models that you
15:54
have heard about in the media, probably one is called bird or
15:57
GPT two and GPT three. So these are the building blocks of these
16:03
models. So we'll also talk about those. So don't want to make
16:08
this too crowded here. But this part will be essentially for
16:13
images. And these two last parts here will be for text. So we
16:20
will have both generative models for images and for text.

##v3:


0:01
Yeah, regarding the course material and information, we
0:04
will be using canvas in the semester. The reason is really
0:07
that it makes things easier for me and for you, because
0:10
everything will be in one place. So that, yeah, with that, I
0:15
mean, announcements and your grades, and also your Piazza, I
0:20
will say a few more words about that. So yeah, I think having
0:24
everything in one place will make things easier. Yeah, of
0:27
course, we will also be using other technologies like GitHub.
0:30
However, I will then post links to that on canvas. So you'd
0:34
never have to really go out there and search for things by
0:37
yourself on different places. Everything will be here on the
0:42
modules on canvas. So what I'm showing you here is a screenshot
0:47
just of some things you've probably already seen. So here
0:50
was some optional pre course preparation materials that I
0:54
shared during the winter break. For those of you who may have
0:58
not used Python before, but have some programming language
1:01
backgrounds. So yeah, as a requirement for this class, you
1:06
should have taken a programming class, it doesn't have to be
1:09
Python. However, we will be using Python in this course. Of
1:13
course, we don't have to be expert programmers in Python for
1:16
this class, we will only use very basic features in Python,
1:19
but it will be immensely helpful for you. If you learn a little
1:23
bit about how Python works, and I shared some resources for you
1:28
here, it shouldn't take that much effort. It's really only
1:32
the basics. And I think it will make your life in this class
1:35
easier. Also, we won't be using Python right away in the first
1:39
few weeks. I think we will be probably starting in week three
1:43
to use Python. So in that way, there's no stress to do it like
1:46
today. But it would be good maybe in the next couple of days
1:49
if you don't have any Python experience to look over these
1:52
resources. Then I also posted a lot of information about the
1:56
syllabus. A couple of days ago, I don't want to really go over
2:00
everything here. I think it's maybe more efficient if you just
2:04
read through what I've posted there. It's really just the
2:07
topics that I already discussed in a few minutes ago, that we
2:11
are going to cover a little bit about this course, you probably
2:14
already know that because otherwise you wouldn't have
2:16
enrolled. Then yes, some basic comments on where the
2:21
information for this course is located mainly on canvas, some
2:25
other resources like optional textbooks that may be helpful to
2:29
you. And also how we communicate in this course, I will also say
2:32
a little bit more about that in the next couple of slides. And
2:36
then your course logistics, some expectations like how I will
2:40
deliver content and how you are expected to participate. So
2:45
content wise, I will be uploading videos on Tuesdays and
2:49
Thursdays. Why Tuesdays and Thursdays on it was usually
2:53
what I have done and in person when there was a regular
2:56
semester. And also, it's kind of easier for me because when the
3:00
week starts on Monday, I will start recording the videos for
3:03
Tuesday. And then on Tuesday, I will catch up with emails and
3:08
work. And then on Wednesday, I will be recording the back
3:11
lectures for Thursday and things like that. So it's also a good
3:14
rhythm for me. And then there are some other resources and
3:18
useful material that I posted here. Some information about
3:22
grading, I will also talk about this in a few slides. And also
3:26
about the class project and the exam. And then also importantly,
3:29
the rules, rights and responsibilities that you have
3:32
and should know. And then also a little bit about the COVID
3:36
context, also just where you can info find information about
3:41
COVID and how it affects campus. So I'm just linking the campus
3:45
guidelines. You should also maybe take a look at that if you
3:48
are not familiar with that yet. All right. So regarding the
Weekly Content
3:53
weekly content, like I mentioned, I will be uploading
3:56
videos on Tuesdays and Thursdays. Or let's say I will
4:01
upload the Monday night and Wednesday night such that they
4:04
are available on Tuesday mornings and Thursday mornings.
4:07
So that's to the best of my ability. That's my my plan here
4:12
for this semester. So a typical week may then look like this. So
4:18
here is it's not uploaded yet, when I'm recording it. But when
4:22
you are seeing this video, it's probably already uploaded. So
4:25
what I'm showing you here is how a typical week would look like.
4:29
So here's a link to the office hours, we will have, we will be
4:33
having office hours via zoom, the TA and me. So I will have my
4:38
office hours on Tuesdays from six to seven and the TA from seven
4:42
to 8pm, I think. So we both have office hours in the evening. And
4:46
that is because I think it's, it's easier for people who are
4:51
in different time zones. For example, some people I know are
4:55
in China, and then it would be, I think 6pm here would be 9am in
5:00
the morning there or 8am. So I think that's like a more
5:03
reasonable time because last semester, we had office hours
5:06
like more in the afternoon, and then some people had to have
5:10
their alarm clock at 3am in the morning to join the office
5:12
hours, or we always had to find additional time slots. And I
5:17
think having this office hours slot in the evening might be
5:19
more convenient this time. I think 6pm is also maybe
5:22
reasonable for people who are in medicine. So in that way, it's
5:26
like a good, I think, sweet spot. Alright, and then, like I
5:31
said, I will be uploading content on Tuesdays and
5:33
Thursdays. So there will be a page, a canvas page with all
5:37
the videos embedded there. And the same thing for Thursday. And
5:42
I will also post some additional material like extra reading
5:45
material there, or I will link it there. So if you want to have
5:49
some more information beyond, let's say just the videos, I
5:52
will also try to post some interesting papers or additional
5:55
reading material in these pages related to the lecture. And then
6:00
at the end of the week, I'm planning to make every week a
6:03
self assessment quiz. So this quiz will be three to five
6:07
simple multiple choice questions. It's just like, um,
6:10
yeah, so to help you stay on track, there will be a few
6:13
points for this quiz. So of course, you should do the quiz
6:17
because it will be counting towards your final grade. It
6:20
won't be like heavily weighted, it's only a small number of
6:23
points for these quizzes. But it's I think helping you or will
6:26
help you to keep on track because you have to watch these
6:31
materials in order to do the quiz. I mean, you can do it
6:36
without watching the videos. But then I think you you have to
6:39
guess really, because the questions will be related to the
6:42
video content. Of course, the I will post the quiz at the end
6:46
of the week, but it will not be due at the same day, it will be
6:48
due one week later. So if you let's say on don't have
6:53
completed videos by the end of the week, you still can watch
6:57
them on a video on the weekend or the beginning of the next
7:00
week. So we'll have like seven, approximately seven days after
7:04
the videos have been posted to complete the self assessment
7:08
quiz. I think that's like also, yeah, I will think this will
7:12
help you to keep on track and not, let's say delay going
7:18
through the content too much and help you to stay on track in
7:21
this class. Alright, so the grading, I think that's probably
Grading
7:25
some question or something you are curious about. So how I
7:31
decided to do things this semester is that there will be
7:35
30% of the grade will be from problem sets, that's homeworks
7:39
and these self assessment quizzes. So regarding the
7:42
homeworks, I don't know exactly how many homeworks there will
7:45
be, I will be making them every two weeks, approximately, and
7:50
there will be a new homework. These are a little bit longer
7:53
than the quizzes, and they won't be multiple choice, they will be
7:56
involving usually some free form answer or some slight coding. So
8:02
in that way, there will be approximately five homeworks
8:05
this semester, a little bit more, maybe. So five, I would
8:08
say five to seven. And there will be the self assessment
8:12
quiz quiz every week. And then this will be 30% of your grade,
8:17
20% of your grade will be from the midterm exam. I posted the
8:22
date, I think in the syllabus for the midterm exam, I will
8:27
send another announcement about that. I just forgot the date
8:30
right now. So I can't recall it on top of my head. But it was
8:34
more like later, I think, sometime in March, I think, so
8:38
don't worry about it yet. So 20% will be the midterm exam, which
8:43
will be online on canvas. So and then 50% will be the class
8:48
project. So I think this is the most fun part of the class,
8:52
because this is something where you get to be creative. So first
8:57
you get to propose a class project topic that has to be
9:02
related to machine learning or deep, I mean, deep learning, of
9:05
course. So it will be related to deep learning. And you will be
9:09
working in teams with three students in total, so three
9:14
students per team. And we will wait a few days, or let's say,
9:20
maybe a week or two, until I ask you to find team members, because
9:27
there are students in the beginning who are still on the
9:29
waitlist, and some students may change their classes. So we will
9:32
wait a few days or weeks until things have settled. So then we
9:37
will form student teams of consisting of three students
9:41
each. And then with your team, you will be thinking or
9:44
brainstorming deep learning related project, I will post
9:48
data sets that you may consider or data set resources, and
9:53
websites and also project ideas. And I will also post some
9:57
examples from previous semesters so that you can get an idea of
10:01
what roughly is expected. I don't want to do this right now,
10:06
because there are so many things going on right now. But in the
10:09
next couple of days, I will share more information about
10:12
that. So don't worry about it. And it won't be due until I
10:16
would say also like March. So and this proposal, what what's
10:19
the goal of this proposal, this is a really a two page report.
10:24
So again, I will share more information later, but it will
10:26
be a two page report, where you let me know what you are
10:32
interested in working on. And then I can give you some
10:35
feedback to let you know whether this is a good idea or not, or
10:38
maybe also to give you some more tips regarding your projects and
10:42
supply you with resources or additional ideas. And so the
10:47
grading is, it's only 5% of the total grade. So in that way,
10:52
it's more about making sure that you have a good idea for the
10:57
rest of the semester that you can work on it. And yeah, and
11:00
then at the end of the semester, there will be a project
11:03
presentation. That's an oral presentation, and a project
11:07
report. So of course, the semester is virtual, so it will
11:11
be recorded. So you will be recording a video, a short eight
11:16
to 10 minute presentation, and that will be shared with other
11:22
students in this class. So we will be all watching the
11:24
presentations. And there will also be a project report then
11:29
also at the end of the semester. And the project report, this
11:32
will be a eight page written report in the form of it will
11:38
look like a conference paper, I will give you a template for
11:41
that. And this is really where you would write up should be
11:47
style conference paper style, this will be where you will be
11:50
writing up your project more formally in the form of a paper.
11:54
And I really think this will give you some real world
11:56
experience on with working on a deep learning project, how you
12:00
communicate it also in the presentation, and then also how
12:03
you write it up, for example, also later on, if you're
12:06
interested in academic path, where you publish papers, that
12:11
might be a great exercise to if you have not done that already,
12:15
like work on papers, but also in industry, a lot of people in
12:19
deep learning are publishing papers nowadays. So either way,
12:22
I think this is a very useful exercise for you. And it's also
12:24
great for your CV, you can optionally share your project,
12:27
for example, on GitHub, if you like. And then if you apply for
12:31
an internship, you can show that you have worked on a creative
12:34
individual project, I think that's always a good idea. Okay,
12:39
but again, like I said, I will share more about that. One
12:42
little aspect I wanted to say is also there will be a peer review
12:46
stage. That is something I've not done in previous
12:49
semesters. And I thought it might be also a good idea. That
12:52
is something where each student will be reviewing three other
12:57
students, reports and project presentations and also give
13:03
feedback basically. So in that way, I think that might be also
13:07
a cool thing to do like providing feedback on other
13:09
students, presentations and reports. Alright, of course, I
13:14
will also be providing feedback, but this is like for you on
13:17
among each other. So I think that's also nice. Yeah,
Questions & Discussions
13:21
regarding the communication in this course, so how are we, how
13:26
are you going to ask questions? And how are we having
13:29
discussions? Yeah, first of all, we will have the office hours
13:34
via zoom. So that will be a face to face live office hours. And
13:38
in addition to that, we will be using Canvas for the asynchronous
13:43
communication. So Piazza is like online forum, which is in
13:47
Canvas, or only the students in this class have access to it.
13:50
And you can post questions either on showing like your name
13:56
to the other students or also anonymously if you prefer. So
13:59
the name if you post that will be on only visible, let's say to
14:04
me if you post anonymously, but you are of course encouraged to
14:07
also post just generally with showing your name. So if you
14:12
want to find, for example, team members and things like that,
14:14
you can also use Piazza. And this is really like for
14:17
questions about this course about the lecture contents and
14:22
everything related to this course really. And what's nice
14:25
about it is, I think, is that everything will be in one place.
14:30
And on Piazza, I can also see which questions I have answered
14:33
and which I have not answered. And I really prefer this over
14:36
email, because you know, a lot of people are sending me emails
14:39
who are not in this class, like colleagues and paper reviews
14:44
and everything. And sometimes it's more difficult to catch up
14:48
with email every day. So if you have a question, it's easier for
14:52
me just to go to Piazza and see all the questions related to
14:54
this class. And I can, I think, answer them more quickly. And
14:58
there's also less danger that I miss a question compared to
15:01
emails, where emails always like this always too much email, and
15:05
it's always easy to overlook something. So on Piazza, it
15:07
will be more organized. So you can also send me private
15:11
questions on Piazza, there's an option that only I will be able
15:14
to see the question. So if you have some private question, like,
15:18
I don't know, maybe you have a doctor's appointment and some
15:22
issues came up and you can't complete homework for some
15:26
reason. That would be also a private option where you can ask
15:29
me a private question on Piazza. So that's also a good place to
15:36
ask private questions. So where you don't have to worry that
15:38
other people see that. Anyway, so yeah, we will be using then
15:41
Piazza and zoom for the communication this class, I hope
15:46
this will work well, we can adopt if we need additional
15:50
resources. So for example, for the office hours, we will be
15:52
having these links. But if there's a reason, you never can
15:56
attend these office hours, because you have another class
15:59
during these times, we can also find optional additional dates.
Important!
16:05
Yeah, important. One last important thing is, I would
16:09
really hardly strongly recommend that you enable the notifications
16:13
on canvas. I know it can be maybe a little bit annoying. But
16:16
this way, you get a notification via email, if there's some new
16:19
content, because yeah, this way, you don't have to always refresh
16:23
the page, if there's some new content, you will get an
16:25
automated, automatic, automatic message, for example, if
16:30
there's a new deadline, or new content uploaded and things like
16:33
that. So I recommend activating these notifications. So how you
16:37
do that is you go to this little symbol here. And then you go to
16:42
notifications. And then there should be these preferences
16:45
where you can just check these. Alright, so that is all I wanted
16:50
to say about the course. If you have questions, yeah, we will
16:55
have office hours this week. So you can ask me that in person,
16:58
face to face, or you can just post a question on Piazza.
17:02
Honestly, what I also like really about Piazza is if you
17:05
have a general question, and you posted there, then other students
17:08
will see it as well. And maybe other students had the same
17:10
question. So this information will also be shared with other
17:13
students, which can be really useful. So more efficient,
17:17
basically. So instead of having every student asking me the
17:20
question, I, that could be just one student asking the question
17:23
and answering, I can answer it for everyone, basically. Alright,
17:26
so then let me finish this video. And then in the next
17:30
video, I will talk finally more about machine learning.

##v4:

0:00
Yeah, before we jump into deep learning, let me briefly define
0:05
what machine learning is and what it is all about in a few
0:08
minutes. So it all goes back to the traditional programming
0:14
paradigm. So what do I mean by that? It's like, yeah, the
0:18
development of computer software to make our lives easier. So I
0:22
think one of the motivations behind developing software was
0:26
to make common tasks more convenient, for example,
0:31
replacing physical mail, by let's say, email, although it's
0:35
not 100% replaced. But yeah, with that, like change, now
0:39
things are a little bit more convenient compared to writing a
0:43
letter by hand, and then bringing it to the post office,
0:45
and then taking a few days until it's delivered, and so forth.
0:49
Email makes this whole communication aspect more
0:51
convenient. Although I would say maybe email is not so great,
0:55
because everyone included, I think, think that email is maybe
0:59
not making life easier, but harder, because there's no more
1:03
email than physical mail. In any case, so let's now imagine you
1:10
have an email program, and you want to make email more
1:12
convenient, you want to filter out spam, so unwanted email. So
1:18
imagine you want to design a spam filter. So as a programmer,
1:23
you want to design the spam filter. So our program is the
1:28
spam filter. And then we can give this to the computer, who
1:33
then will produce the outputs, which would be the label,
1:39
whether something is spam or not spam, or maybe going one step
1:46
further, just putting it into the right folder, like either
1:50
the inbox or the spam box on our email program. Now, how do we
1:55
design this filter? I mean, as a programmer, this could be a very
1:59
tedious exercise, we would first take a look at examples of
2:04
email. So we would take a look at our inbox, and then look at
2:08
what could be some spam email, we would then compare it to
2:13
non spam email, think about it, and maybe come up with a rule
2:16
that says, for example, if let's say, if email has the word, let's
2:27
say, win money or something like that, in the subject, then
2:38
classify it as spam. And then you can have an else, if
2:44
if something else, and so forth, you can develop these rules,
2:48
hard code them in your program, and then develop a spam folder
2:52
like that. But I think it would be super tedious to do that,
2:55
because you would have to take a look at a lot of messages, and
2:58
do a lot of testing and see if your rule works. And if some
3:03
additional l l if statement could improve it and not. And
3:07
it is like a lot of work like to take a look at this. And this is
3:10
why machine learning is so popular, because it can make
3:15
this life easier for us programmers for developing
3:18
software that can, for example, classify things. So here, in
3:23
contrast, at the bottom, I have machine learning in contrast to
3:28
the traditional programming paradigm. So in machine
3:31
learning, instead of having the programmer look at these inputs,
3:38
and making decisions, we provide the machine learning algorithm
3:42
with inputs and outputs. Again, outputs would be the labels for
3:47
our email. So we have a labeled data set. So here, this would be
3:53
our emails, and the outputs would be whether they are spam or
3:59
not spam. So a human actually would have to label those. So
4:03
you have to have a human to assign these labels to show the
4:07
computer what we want. So it's basically this is what what we
4:10
want the desired desirable outcome. So we have as a human,
4:14
we have to of course, communicate to the computer
4:17
what we want. We have to say, okay, we want spam and non spam
4:21
email labels. So we provide these as examples. And then the
4:25
computer can learn rules to make this classification. So the
4:30
computer is actually developing this program. This is our
4:32
machine learning model. And then the machine learning model can
4:41
actually replace our role as the programmer, developing the
4:46
program manually, we can actually give the program
4:49
directly to the computer to produce new outputs on new data.
4:52
So machine learning is the in a way the automatic learning from
4:57
examples. So there's also a famous quote by Arthur Samuel,
5:01
Samuel, this is a quote that you can find in almost every
5:05
machine learning textbook. So the quote goes like this,
5:08
machine learning is the field of study that gives computers the
5:11
ability to learn without being explicitly programmed. So here,
5:17
that means we are providing examples, and then the algorithm
5:20
learns automatically basic from based on the data instead of
5:24
having humans thinking about these rules. That's machine
5:28
learning in a nutshell. Specifically, this is a subfield
5:31
of machine learning called supervised learning, which I
5:34
will talk about in a future video. So yeah, but you may
5:39
wonder, how is machine learning now related to deep learning and
5:43
for example, artificial intelligence, you probably all
5:46
heard about AI and artificial intelligence. Most of the time
5:50
nowadays, deep learning and AI are used interchangeably.
5:56
However, there is a distinction I wanted to briefly discuss. So
6:00
machine learning, I would say is the biggest field. It's like
6:05
field encompassing deep learning. So deep learning is
6:10
strictly a subfield of machine learning, a subfield that
6:12
focuses on neural networks, deep neural networks, and AI is
6:19
intersecting with both, I would say, if there's one thing about
6:23
this graphic is I made the this one maybe I'm not I mean, not
6:29
big enough. But maybe I made this this part here too big. So
6:33
there is also what I wanted to say here is there are also AI
6:37
methods that don't use machine learning. So let me go through
6:41
these things step by step. So first of all, there are
6:47
there are different types of AI. So usually we say, generally AI
6:53
as artificial intelligence, which is a subfield of computer
6:56
science, solving tasks humans are good at, for example,
7:00
natural language, speech recognition, image recognition,
7:04
and so forth. And then we can subcategorize AI into two smaller
7:12
categories. One is narrow AI, and one is artificial general
7:19
intelligence. So what is narrow AI, narrow AI is a form of AI
7:26
that is focused on solving a particular task. So only one
7:31
task at a time, for example, image classification, or playing
7:34
a game, driving a car, let's say an algorithm for unlocking your
7:38
phone. So this would be a narrow AI, because it can only do
7:42
one task. So it's not like a human, a human can do multiple
7:46
things. I mean, I can go skiing, I can do cooking, I can write
7:50
emails, I can record a lecture and things like that. So I can
7:56
do multiple things, but a narrow AI system can only do one thing
7:59
that it has been developed for. In contrast, artificial general
8:03
intelligence is multipurpose AI, mimicking human intelligence
8:09
across multiple tasks. So if you have seen the movie X Machina,
8:14
the robot in this movie, for example, I would say it would be
8:17
more like a AGI agent where it can do things a human can do. So
8:23
multiple things, not only classifying images, for example,
8:26
so in that way, there's a difference between narrow AI and
8:29
AGI. However, AGI is for most people what they want to
8:33
accomplish is like the far future goal, but we are not very
8:38
close to that one yet. So that's like, people are actually
8:41
arguing whether it's possible at all, whether it will be possible.
8:45
Some people think it's like within 50 years, some people say
8:49
within 1000 years, there's actually a nice book on what was
8:52
the name architects of intelligence where the author I
8:56
think his last name was Ford, I forgot the first name. So the
9:00
author interviewed multiple experts in deep learning, when
9:05
when they would predict AGI will be invented. And there's like a
9:09
huge, huge span of predictions between 20 and 20 years, and
9:17
maybe 10,000 years, or maybe never things like that. So no
9:20
one really has a good idea, even when, or if this will ever be
9:25
invented. Narrow AI is something that we have nowadays in in
9:29
almost every aspect of our lives. And I will also talk more
9:33
about examples of that. So, um, yeah, so why did I do? Why did I
9:40
draw these circles like that? So AI, there was also something
9:44
called good old fashioned AI, it does not always have to involve
9:47
machine learning. For example, when we developed our spam
9:51
filter a few slides back, when I designed these if and else
9:54
rules, as a programmer, I was developing an intelligent
9:58
system, right? If I add enough of these if and else rules, this
10:01
system will be intelligent, and we'll be able to sort my emails
10:05
by spam and not spam. However, for that, I didn't use machine
10:08
learning. So in that way, AI doesn't always have to use
10:12
machine learning. Nowadays, most of the AI systems use machine
10:17
learning, though. And also, even more of them are using deep
10:21
learning, because deep learning is usually very good at natural
10:25
language and computer vision. So and this is also the focus of
10:29
this course. And this course will be focusing on deep
10:31
learning. Regular machine learning that is not deep
10:35
learning could be, for example, generalized linear models, for
10:38
example, linear logistic regression, tree based methods,
10:42
certain methods like random forests, or gradient boosting,
10:48
support vector machines, k nearest neighbors, this is all
10:53
something we covered in machine learning statistics 451
10:58
introduction to machine learning and the fall semester. In this
11:01
semester, we will be specifically focused on deep
11:04
learning, which is deep neural networks, which are very good at
11:08
our computer vision and natural language, which is something
11:11
these methods are not good at. So these methods, only because
11:15
we call them traditional doesn't mean they are bad, they are
11:17
still really, really powerful and useful for tabular data, I
11:22
will explain what I mean by that later. So they're really good at
11:26
on learning from tabular data. And deep learning is more suited
11:31
for learning from raw data, like images and speech and things
11:35
like that. So it's, it's not like one is better than the
11:38
other. The purposes are kind of different. So that's, that's the
11:42
main difference, basically.
11:44
Yeah, so yeah, just one more example of an AI system that
11:48
does not involve machine learning and deep learning. So
11:51
as far as I know, I mean, I was a bit young back then. But as
11:54
far as I know, deep blue, that was like a old chess computer is
11:59
not based on machine learning, it is like using an alpha beta
12:03
search, which is a search algorithm for finding good chess
12:07
moves. And as far as I know, for example, this would be an
12:10
example of a good old fashioned artificial intelligence that is
12:13
not involving machine learning, I may be wrong, but then there
12:17
are definitely examples of AI systems that don't use machine
12:23
learning. So then in general, we can say I is a system that
12:29
employs rules and is kind of intelligent through these rules
12:33
by using these rules. For example, if you think back of
12:35
our spam filter, that we could develop by hand by having a lot
12:39
of if and else statements, this can become intelligent as a
12:44
narrow AI, but it doesn't necessarily have to involve
12:47
machine learning. And yeah, machine learning is about
12:51
algorithms that learn models or representations or rules
12:55
automatically from data and examples, the labeled data. For
12:59
example, if you think back of the slide that I showed you,
13:01
when we showed algorithm examples of labeled email, and
13:06
then the algorithm would develop the program that would be what
13:09
machine learning is about. And then deep learning is also
13:12
machine learning, but it is specifically focused on
13:15
multi layer neural networks. So they are a little bit more and
13:19
more complex than simpler algorithms are not necessarily
13:23
they have usually more parameters. And we will see all
13:26
about that in this course. Yeah, here are some applications of
13:32
machine learning and deep learning in practice. So one, we
13:35
already covered the email spam detection. Another popular
13:39
example of machine learning would be deep learning specific
13:43
would be fingerprint and face detection and matching on the
13:46
phone. So if you have a smartphone, you probably either
13:48
have a fingerprint sensor or camera that detects your face to
13:53
unlock your phone, or web search is also heavily using machine
13:57
and deep learning, for example, Dr. Goh, Bing and Google spots
14:01
predictions, people use it for making predictions. At the post
14:04
office, also machine learning and deep learning are used for
14:08
scanning in the letters, the letters on the letters, and the
14:14
zip codes and then categorize the letters by zip codes like
14:17
image recognition, and handwriting recognition. And the
14:20
same is true for ATMs for reading checks. This was actually
14:24
one of the earliest applications of deep learning or machine
14:29
learning, it was a multi layer neural network, in particular,
14:31
convolution neural network, which we will be covering in
14:34
this course, it wasn't called Lynette. And it goes back to
14:38
the 90s. So it's almost 30 years ago. And that was one of the
14:42
early applications of deep learning. I mean, I say deep
14:45
learning, back then, the term deep learning wasn't invented. So
14:48
back then, people called it machine learning, but it was a
14:50
deep neural network. So here's a fun video. It's a real video
14:56
from the 90s, illustrating how this works. So here's a hand
15:00
written image of a handwritten digit. And then the machine
15:05
learning here, machine learning system here recognizes which
15:08
digit that is, and that can be then used in an ATM, for
15:11
example, or for sorting the zip codes. So of course, we will be
15:15
developing much more sophisticated systems in these
15:19
next couple of weeks. But this is, I think, a nice, nice
15:22
example of classic deep learning. Yeah, other applications
15:28
include, for example, smart assistance, like Apple Siri,
15:32
like the voice assistant, and also Amazon Alexa, and all these
15:35
types of voice assistance nowadays, or using deep
15:39
learning. And then the product recommendations, if you know
15:43
Netflix or Amazon, they always recommend products based on
15:47
machine learning, self driving cars, unfortunately, still not
15:50
here yet. I mean, I'm not sure if it's unfortunate. But yeah,
15:53
that would be another great application, not application,
15:57
but at least example of deep learning. It's actually a bit
16:01
complicated. So there are many things at work, from
16:03
reinforcement learning to supervised learning with
16:06
images. So here's like a little example from Waymo. So that
16:11
would be another area where AI deep learning machine learning
16:15
are used, language translation, sentiment analysis, drug
16:20
design, medical diagnoses, diagnoses, and things like that.
16:25
So I will also at the end of each week, upload a video that I
16:29
will call stuff in the news, where I will highlight some of
16:36
the recent applications or interesting things in the deep
16:40
learning world, where I will show you way more examples. For
16:43
example, I'm just thinking of this because when I mentioned
16:47
medical diagnoses is there was like a system recently a new
16:51
system for detecting COVID from lung x rays. There have been
16:55
lots of these systems lately, but there was a particularly
16:57
good one, for example, last week, in collaboration with
17:01
doctors at NYU. And I will show you more examples of deep
17:04
learning in the real world in these stuff in the news videos.
17:07
But yeah, that is just a quick overview of machine learning.
17:13
Just to lay the groundwork. And then in the next few videos, I
17:17
will say a little bit more about the subcategories of machine
17:20
learning. It also applies, of course, to deep learning,
17:23
because we've learned that deep learning is a subcategory of
17:25
machine learning. And we will also talk more about the
17:27
workflow and some jargon. And then about the tools we'll be
17:31
using in this course. So this is still all lecture one. And then
17:34
I will pause this video here and then record the next one on the
17:40
broad categories of machine learning.

##v5:

0:01
Okay, let's now talk about the three broad categories of
0:05
machine learning. So the three broad categories of machine
0:08
learning are supervised learning, unsupervised
0:11
learning, and reinforcement learning. So what is supervised
0:15
learning? supervised learning is, I would say the most common
0:19
form of machine learning or deep learning. So supervised learning
0:23
is the biggest subcategory. And it involves labeled data. So if
0:29
you recall the spam classification example, that
0:33
would be one example of a supervised problem, where we
0:35
want to predict whether an email is spam or not spam. And the
0:40
labeled data are then examples of spam and non spam email. And
0:45
it also involves direct feedback. So we can, yeah, we
0:49
can say whether our prediction was correct or not, basically.
0:51
So you, you have an example of an email that spam or not spam,
0:55
the model does a prediction. And if you, let's say during
0:58
evaluation, know the correct label, you have direct feedback
1:00
here, during the training. We will talk about this a little
1:05
bit more. So let me just briefly go over the three categories.
1:08
And then I will talk more about supervised learning, and the
1:11
others two. So unsupervised learning is, in contrast to
1:14
supervised learning, not involving any labeled data. So
1:18
here, we don't have labels or targets here, we also then don't
1:21
have feedback. So we assign, for example, a group to give an
1:26
example. For example, in clustering, we have cluster
1:29
memberships, but we don't have any feedback here. So it's more
1:31
really about finding a hidden structure in the data.
1:35
reinforcement learning is the third category of machine
1:38
learning. And here, this is more about learning a decision
1:42
process. So think about the example of the self driving car.
1:47
So the process of driving the car, it's like making multiple
1:51
decisions. It's like the goal here might be to arrive at a
1:55
destination, but to get there, you have to make a lot of
1:57
decisions like stopping at a red street light on turning around
2:02
the corner, and so forth. So here, what we do is we employ
2:05
in a reward system that rewards the agent for making correct
2:10
choices. And it's not like predicting a single outcome or
2:15
something. It's more about learning a series of actions
2:18
like steering the car through a difficult environment. And there
2:23
are some examples where you can actually use supervised
2:25
learning for self driving cars to, for example, recognizing
2:29
the streetlight itself, right, could be involving convolution
2:33
network, for example. But yeah, the process here is more like
2:36
learning a series of actions. We won't be talking about
2:40
reinforcement learning in this class, though, it's kind of out
2:43
of the scope of this class. Nowadays, you can also use deep
2:47
learning for reinforcement learning that is usually known
2:49
as deep Q learning. But yeah, this is really not in the scope
2:54
of this class. So here, we will be focusing more on supervised
2:56
and unsupervised learning. And as you have seen from the
2:59
introductory slides, where I showed you the topics, we already
3:01
have plenty of things to talk about in this class. So yeah, a
Supervised Learning
3:06
little bit more about supervised learning. So supervised
3:10
learning, like I said, is the largest subcategory of machine
3:13
learning, which is focused on label to data. So you already
Regression
3:17
from other statistics classes have seen an example of
3:20
supervised learning, that would be, for example, regression. So
3:24
here is just a sketch of a linear regression model. And
3:28
here, how this works is it's just a example with one
3:33
observational input, or we call that in machine learning feature.
3:38
So our x variable, the explanatory variable, we call
3:41
that the feature. And the target here, the dependent variable
3:45
that would be our y axis, or the data on the y axis here. And
3:50
here, we are fitting a linear model. So we, for example, can
3:56
then predict, if we have a new observation, what its target
3:59
value might be given this model. So these x's here, the training
4:04
data, think of it as the training data. And now think of
4:07
it as, let's say I have a new data point that is, let's say
4:10
here, sorry, if I go up here, so this is my input, I only know
4:15
the x value. So I know this x value to predict the y value, I
4:19
would go up here, and then look up the y value here. So using
4:23
this linear model, I can make predictions for new data points
4:26
for this one here, which is not in my data set, it would be one
4:30
example of a supervised learning problem. Another example of
Classification
4:34
supervised learning is classification. And actually,
4:37
classification is much more common than regression. If you
4:40
look at literature and deep learning. So most systems are
4:42
focused on classification, for example, recognizing objects and
4:47
images like is a cat or a dog or something like that. So we will
4:52
see a lot of examples of classification also in this
4:54
class. Or if you think back of the ATM machine that I showed
4:58
you earlier, where it was recognizing these handwritten
5:00
digits, it was recognizing or classifying these digit digits.
5:04
So whether it's a two or three or four, and so forth. Here's an
5:09
example of a binary classification problem, where we
5:12
only have two possible labels, one possible label is the minus
5:17
sign and one is the plus sign. So the labels here, either the
5:22
minus sign or the plus sign here, my two possible labels is
5:26
just for the sake of simplicity. And here I have two features, x
5:31
one and x two. And the goal is to predict for a new data point,
5:38
whether it's a plus or minus. So if I have, for example, new
5:41
data point that is located here, because it's on the left side of
5:45
the decision boundary. So this is a linear decision boundary
5:49
learned by this machine learning system, it would predict a minus
5:53
sign and everything on the right hand side would be predicted as
5:56
a plus sign, for example. So we will see more examples of that.
6:01
But here, the goal is to learn a decision boundary. So that's,
6:04
that's the goal in classification. And here, this
6:07
is a linear decision boundary. But it can also be a complex
6:10
decision boundary, it could be like something like this. And
6:13
deep learning, or deep neural networks are actually learning
6:16
very complex decision boundaries. Also, in practice,
6:20
when we have real world data, we rarely only have two features,
6:23
we usually have very high dimensional data. So we can't
6:27
easily visualize it. But yeah, that is, it's just like an
6:30
overview of a very simple case of classification, so that you
6:33
know that two different types of supervised learning, regression,
6:38
and classification. And yeah, to make things more interesting,
6:41
there's actually a third type, which is also known as ordinary
Order Regression
6:45
regression, or ordinary classification. That is what I
6:48
have worked a little bit on recently, when I talked about
6:51
this coral, consistent rank logits system, we developed for
6:57
deep learning. So ordinary regression is very similar to
7:02
classification, but there's a rank order. So we have ranks
7:06
that we want to predict, think of it as, for example, as movie
7:09
ratings, like grade is better than good, which is better than
7:12
okay, which is better for than genre fans, which is better than
7:16
bad. So there's a ranking. So these are classes, you can
7:20
actually use a classifier to classify, let's say, a written
7:24
text, or a movie into these classes, whether it's great,
7:29
great, good, okay, movie. But here, you have additional
7:32
information, you have like the ordering information among among
7:35
these labels. So there's a little bit more information
7:38
about that. So it's also called ordinary classification, or
7:42
ordinary regression. So, yeah, and here's another example,
Ranking
7:48
like, what actually two types of sub problems, one is ranking,
7:52
and one is ordinary regression. So ranking is closely related to
7:57
ordinary regression, but it's a little bit different. Because
7:59
here, it's more about predicting the correct order, we don't
8:04
really care so much about the correct label. Because, yeah,
8:09
this is just my personal ranking. So from, yeah, I would
8:14
say favorite to least favorite, because you probably never heard
8:17
of these movies. I don't know. Let me take a simple example
8:21
here. So these are cups in different sizes. And if you
8:25
don't know the size of the cup, if you only have a word to
8:27
describe it like small, medium, large, I forgot they have
8:31
specific names, even like bendy and grandi or something like
8:33
that. But let's say you have these cups, you don't know the
8:37
exact sizes, this would be like ordering problem where you want
8:41
to order them from small to large, or an order regression
8:45
problem, you go a little bit beyond just ranking, you also
8:48
want to predict the correct label. For example, when we
8:53
worked on the coral network, we used an age data set as an
8:57
example, because we had large face image data sets available.
9:02
And deep learning, or we used conversion networks are
9:05
particularly good for image data. So it was a good example
9:07
for demonstrating this auto regression network. So here, the
9:11
task was predicting the age. So the age also has ordering
9:15
information. You might wonder, why don't you use regular
9:19
regression for that, you can think of it also as a non
9:22
stationary problem, or it just like the difference, let's say
9:26
between a six and a 10 year old person is much bigger, let's
9:30
say, between six, and 10 years, it's only four years, the
9:34
difference might be much bigger than the difference of a person,
9:38
let's say between, let's say 70 and 74. It's also only four
9:44
years here, maybe the differences are mostly defined
9:47
by how the skin looks like, like wrinkles and things like that.
9:51
But it's only maybe a slight difference between 70 and 74.
9:54
Here between the age six and 10 person might grow a lot like
10:00
child might be much larger, for example, or the features of the
10:03
face face change more and things like that. So comparing these
10:08
four units to these four units is kind of unfair. And in that
10:12
way, metric regression treats all the values at the same, it
10:17
wouldn't be really a good idea to use metric regression. I
10:20
mean, you can, but I think ordinary regression would be a
10:23
more natural choice here where you don't have defined
10:27
differences that are not on a metric scale, for example. But
10:30
yeah, also, in this class, we won't talk about ordinary
10:33
regression, really, we will be mostly focused on classification
10:37
for supervised learning. So I just wanted to cover this for
10:41
the sake of completeness, because there are three
10:43
categories really like classification, regression, and
10:47
ordinary regression and supervised learning. So in the
Summary
10:49
next video, I will then talk more about unsupervised
10:52
learning and also briefly about reinforcement learning.

##v6:

0:02
Okay, let's now talk about the second subcategory of machine
0:06
learning. And of course, it also implies it's a subcategory of
0:09
deep learning. So this is unsupervised learning, which in
0:12
contrast to supervised learning, does not use any labels or
0:16
targets. So we don't have any feedback here. And it's more
0:19
about finding a hidden structure in the data. So in that sense,
Unsupervised Learning
0:25
we can also think of unsupervised learning as
0:28
representation learning. And this is sometimes also used for
0:31
dimensionality reduction, it doesn't have to be used for
0:34
dimensionality reduction, but it's one application of it. So
0:38
you probably have heard of principal component analysis and
0:42
other statistics classes, or short PCA, which is a linear
0:46
transformation technique that rotates the data and then
0:51
extracts a linear combination of the inputs. So if you
0:56
consider this example here, there are two features of
1:00
feature one and feature two, these are our inputs. And here
1:05
these circles are our data points in this space. And with
1:10
principal component analysis, we find the eigenvectors of this
1:15
data set. So in that way, we use these eigenvectors to rotate the
1:21
data. So we have these two principal components, these are
1:24
essentially eigenvectors. And usually, we sort them by
1:28
decreasing order so that we sort them by the eigenvalues by the
1:32
corresponding eigenvalues. So we usually keep the large eigenvalues
1:37
or the eigenvectors corresponding to the large
1:39
eigenvalues. So in this case, on the eigenvalue corresponding to
1:44
the first principal component is larger than the second one. So
1:48
in a practical application, we may use this first principal
1:52
component to have a compressed representation of our data. But
1:57
yeah, this is a little bit more detail than we need to know. I
2:01
just wanted to show you an example of unsupervised
2:04
learning. If you don't know how PCA works, no worries about
2:08
that. It's just if you know it, this is a nice example of
2:12
unsupervised learning. Another example of unsupervised
Auto Encoders
2:15
learning are auto encoders. And this is something we will be
2:19
talking in part five of this course. So this will be the
2:22
first lecture in part five, generative adversarial general
2:27
generative deep learning. So auto encoders work like this,
2:31
it's actually a very simple concept, you have input data. So
2:35
this is your input data. And then you have the output
2:41
produced by the auto encoder. And the auto encoder consists of
2:45
two parts, an encoder and a decoder. And first, the
2:51
dimensionality of the input is very large. And then through
2:55
hidden layers, there are that's a learned representation that is
3:00
smaller dimensional. So we call that also the latent
3:03
representation or feature embedding. This is, let's say,
3:07
low dimensional. And this is high dimensional. So you can
3:15
think of each pixel in the image as a feature. So if we have,
3:19
let's say 100 times 100 pixels, we have 100,000 features as
3:28
input. So that way, it's a very high dimensional input. And then
3:31
you can maybe make this like 10 dimensional, it really depends
3:36
on the data set. But let's say we make this 10 dimensional,
3:38
this is learned by the encoder, it's a neural network. And then
3:41
we have a decoder, which undoes that it's basically the opposite
3:46
taking the low dimensional input, and making the high
3:50
dimensional, let's say the 100,000 dimensional output. So
3:55
the goal here is reconstructing the input. So why would we be
4:01
interested in that? So why is that a useful exercise? But
4:05
what's the point of this auto encoder, if it's just learning
4:07
how to reconstruct the input. So the goal is basically what the
4:12
interesting part is, this latent representation. So you can think
4:15
of this as a compressed version of your data. So the decoder is
4:22
able to reconstruct the original image from this small dimension,
4:27
it means that this this dimensional here is sufficient to
4:32
encode important information about the data. So it's, you can
4:36
think of it as a compressed version of the data. So in that
4:46
way, it's also dimensionality reduction, there's actually a
4:49
close relationship between an auto encoder and principal
4:53
component analysis, if the auto encoder consists of linear
4:57
activations, but don't worry about this detail, we will be
5:00
talking about auto encoders more in part five, it's just another
5:03
example of unsupervised learning here. And just for reference,
Classification
5:08
because I already had this nice cat picture, again, how
5:12
classification works is the majority of deep learning is
5:16
about classification. So consider we have an input data
5:20
point here, it's this cat image. And during training, we have a
5:24
label that's cat here. And then the network produces probability,
5:29
the probability that this image is a cat. And then we can give
5:32
it a new data, it could be a dog or a cat, and basically
5:35
everything, anything, and then it would produce a probability,
5:39
how likely is it to belong to the class cat, for example. So a
5:44
classifier is classifying the images, what label they have,
5:48
whereas unsupervised learning is really very different. It's not
5:52
about predicting any labels here, it's about learning this
5:55
hidden representation that can be used to reconstruct the
5:58
input. Okay, so this was one example of unsupervised
Clustering
6:04
learning, the dimensionality reduction or representation
6:06
learning. Another example of unsupervised learning is
6:10
clustering, you've probably heard of clustering before, it's
6:13
assigning a group membership to unlabeled examples. So here,
6:18
let's consider a data set where I have again, two features x one
6:21
and x two, I don't have any class labels, I'm just grouping
6:24
them by similarity. And just by looking at it, you can think of
6:27
these points here, because they are closer together that they
6:30
may belong to a cluster, and these belong to a cluster and so
6:33
forth. Here, it's kind of obvious what belongs to a
6:36
cluster. In real life, cluster boundaries are sometimes not so
6:40
clear. It's also usually high dimensionality. So usually
6:44
clustering is about finding group memberships. So yeah, but
6:50
here, the difference again, to classification is that we don't
6:52
know the true labels. So we can also say this could maybe be one
6:57
cluster, and this could be one cluster, there are some measures
7:00
for measuring cluster quality, like intrinsic measures,
7:04
measures, but we don't have like, a real true answer here.
7:08
Also clustering, I'm just mentioning it here, but it also
7:11
want to play a role in this course. So we won't be talking
7:14
about clustering in this class. It's really not the goal of this
7:19
class here. And it's more like a data mining topic, I would say.
7:24
Alright, in the next video, let me briefly talk about
7:26
reinforcement learning.

##v7:

0:01
Alright, reinforcement learning, the third sub category of
0:04
machine learning. And of course, you can also use deep learning
0:08
for reinforcement learning. But also don't worry about it too
0:10
much, because this is another topic that we won't cover in
0:14
this course. It's because yeah, reinforcement learning is
0:17
really a long and big topic by itself. And you can have a
0:21
separate whole course and multiple textbooks on that
0:24
topic. I have a chapter on reinforcement learning for
0:28
beginners in my Python machine learning book, it's like 30 or
0:31
40 pages long, if you're really interested in reinforcement
0:34
learning with deep learning. However, like I said, in this
0:37
class, it won't be a topic. But just for completeness, because
0:41
it's still maybe interesting to briefly talk about it in two
0:44
slides, how reinforcement learning works. So reinforcement
0:49
learning is about learning a series of actions. So here, in
0:53
this case, on this is our drug design problem, where we want to
0:57
design a small molecule. So let's say we have our current
1:01
state. So that's usually a current state in the
1:03
environment. So the current state is that we have this
1:08
benzene ring here, and the agent sees this current state and then
1:13
has to take an action on it. So here, the action would be to add
1:16
this small chemical group to it. So this methyl group to the
1:21
benzene ring, and this will be then updating the environment.
1:25
And that will be updating the new next state. So it will then
1:31
look like that. So we'll have the benzene ring with a methyl
1:34
group attached. So the agent is the part of the reinforcement
1:40
learning program that updates the current state, and it has
1:44
access to the environment. So and it takes one of the possible
1:49
actions. And that will be also a reward for taking this action
1:53
and modifying this environment. So this is like going over
1:57
multiple rounds until you would have, for example, a complete
2:00
small molecule. And in other areas, you can also think of
2:04
designing a chess game with reinforcement learning where
2:07
each move in on the chessboard would be one action taken by the
2:11
agent. And then you take these multiple actions, and there will
2:17
be a delayed reward. In the end, it's about winning or losing
2:20
the game. And then based on that you optimize taking these
2:25
actions. So maybe a more concrete example would be
2:30
StarCraft two. So that's a video game. You probably I'm not sure
2:34
maybe maybe you haven't maybe have played it. I actually played
2:38
it I think back in undergrad long time ago. But yeah, it's a
2:42
game where there are a lot of things going on at the same
2:45
time. It's very complex, lots of things, lots of possible actions
2:50
you can take at any given moment. And recently, a few
2:53
years ago, DeepMind started working on designing reinforcement
2:59
learning for StarCraft. So here, of course, the goal is not to
3:05
design the world best StarCraft player. I mean, it's a sub goal,
3:08
but ultimately, you want to develop reinforcement learning
3:11
systems that can generalize to other things, maybe self
3:15
driving cars, other more important things. But yeah,
3:17
impressively, I think the current state of the art in
3:20
StarCraft two is that they were able to beat most of the world's
3:25
best players, human players. So it was actually pretty
3:27
impressive, given how complicated this game is, so
3:31
many different actions going on and things going on. So in that
3:35
way, yeah, that was actually pretty, pretty impressive. All
3:39
right. So yeah, this was just a short note on reinforcement
3:42
learning. But like I said, we won't be going into too much
3:46
detail in this class about reinforcement learning.

##v8:

0:01
Yeah, if you remember, I mentioned there are three broad
0:03
categories of machine learning. And if you counted with me, we
0:06
already covered those three, they are supervised learning,
0:09
unsupervised learning and reinforcement learning. So yeah,
0:13
why is there another video on the three categories of deep
0:16
learning? So they are actually two special cases of supervised
0:20
learning that I just wanted to briefly cover because they are
0:23
super interesting. So one is called semi supervised learning,
0:27
which is kind of like a mix between supervised and
0:30
unsupervised learning. So in that scenario, we have some
0:34
labels for some training examples, but not labeled for
0:37
others. So semi supervised learning is about using the
0:41
labeled training subsets to label the unlabeled portion of
0:45
the training set for which we don't have labels, and then we
0:47
can use them to make a better decision boundary. So here's a
0:51
sketch that I made, like a very simple example. On the left hand
0:54
side, we have a supervised data set. So this is strictly
0:59
supervised, where we only have two classes, the class one here
1:04
and the class two. So these are our two classes here. And we
1:08
made the right for decision boundary like that. So again,
1:11
this is a two feature problem. And our decision boundary might
1:14
be just like here in the center between the two. Now consider a
1:18
case where we have more data, but the data is unlabeled. So
1:22
consider this unlabeled data, I added it here on the right hand
1:25
side. So these blue dots are the unlabeled data points. And if I
1:30
consider these unlabeled data points, a semi supervised
1:33
learning system may derive a slightly different decision
1:36
boundary. So going from here to here, I have not changed the
1:40
position of the class one and class two examples. However, I
1:44
added these blue dots here. And the machine learning system may
1:48
use them to put the decision boundary more like this
1:51
diagonally. Of course, it assumes or makes the assumption
1:55
that this data point is actually one of the diamonds, the class
1:59
one ones, it doesn't have to be correct. We don't know because
2:01
we don't have labeled information. It's just an
2:04
assumption. But yeah, we can actually still use this data to
2:08
make assumptions. And this can potentially improve the system.
2:13
So in this case, the decision boundary might be slightly
2:16
different. And this might be a slightly better decision
2:18
boundary. Yeah, this is a special case of supervised
2:23
learning. Other case of supervisor of supervised
2:26
learning is self supervised learning. And this is a very
2:29
popular area of research right now in deep learning. So it's
2:34
yeah, it's a very recent development and very hot topic.
2:37
And it's particularly useful also for training large models
2:42
that need a lot of data. And where we don't have access to
2:46
Yeah, these large amounts of data. So it's usually about
2:51
pre training a model on a larger data set, and then you're
2:56
fine tuning it on a smaller data set. So this is sometimes also
2:59
called transfer learning, because we are transferring the
3:03
model from one task to another task. And yeah, here, why is it
3:11
called self supervised learning? It's because we are deriving a
3:15
utilizing label information directly from the data itself,
3:20
rather than having humans annotating it. So let's let me
3:25
think of an example. So you have probably heard of BERT, the
3:29
language model, it's a very large model of billions of
3:32
parameters, it's very hard to train, you need a lot of data
3:34
for that. However, you don't have really millions of
3:38
documents that are labeled with some classification task. So
3:42
think of building a spam classification system, you want
3:47
to build a very good system. But you have a lot of parameters in
3:51
this model. So but you only have, let's say 100,000 labeled
3:55
images labeled emails, which are not enough for the system. So
4:00
what you can do is you can pre train it on all the text on the
4:02
internet. And here, how do you get the labels for that you make
4:06
up some labeling task that is kind of contained in the data
4:11
set itself. So in the case of BERT, this BERT model, what the
4:15
researchers do is the mask, I think it's 15% of the words. So
4:21
they give it the text, some text on the internet, and they remove
4:25
15% of the words, and they let the system predict these words.
4:30
So for that, so you are kind of removing or withholding the
4:33
labels, but you're using the data itself as the label
4:37
information. So you are, you have, let's say a sentence, and
4:41
then you remove, let's say these parts of the sentence, and you
4:45
have the model, predict these parts of the sentence, but you
4:49
you know what the correct labels are. So in that way, you can
4:52
teach the machine. Or another second self supervised task
4:56
within the BERT system is predicting whether a certain
5:00
sentence is contained in the document. For example, if you
5:04
have a document with multiple sentences, you remove one of
5:09
these sentences, or you just take it out, and you make up a
5:13
new sentence, a second sentence, it's not in the same document,
5:16
you just maybe make it up or take it from a different
5:18
document. And then you let the system predict which of the two
5:22
sentences is actually in the real document. So you, you kind
5:26
of make up these classification tasks by yourself, you create
5:29
them from the data without needing a human to label it.
5:33
Because yeah, in that way, you teach the model to understand
5:36
the sentences. However, it still cannot predict spam or non spam,
5:41
it can only predict now missing words or the sentences, but it
5:45
kind of helps the model to deal with language. So after you
5:48
completed the training of the BERT system, with self
5:53
supervision, you can take this pre trained system, and then fit
5:56
it on the smaller spam and non spam data set to have a
6:02
prediction task now that is a little bit different. But yeah,
6:05
during this task, it learned how to understand language, and then
6:07
you can apply it to the classification task to train it
6:10
on that one. So this is called here on this one, on the right
6:14
one, it's called pre training, and then you have the transfer
6:20
learning and then fine tuning on the real data set you care
6:24
about. So this would be an example of self supervised
6:27
learning. Another case of self supervised learning is from the
6:31
image domain from computer vision, where, for example, you
6:35
want to train a classifier to classify cats and dogs, but you
6:39
don't have many cats and dogs in your data set. It's very small
6:41
data set. So you want to use unlabeled images, for example,
6:46
to have it learned. So here, you don't know what's in the image,
6:48
because you don't have the labels for that. But you can
6:51
actually use the image still. So what you can do is you can
6:55
divide the image into smaller images here. And what I've shown
6:59
you as an example is by dividing the images in eight, or actually
7:03
nine parts. And then you take out one part, and you predict
7:10
whether another part is a label on a neighbor or not. And you
7:14
know, the answer for that, because you know, this image and
7:18
you divided it yourself, you can write a Python algorithm for
7:21
that, you know, all the labels here, the 12812345678. And you
7:29
withhold this ninth part. And then you ask basically, which
7:34
so you, you have extracted this part, you presented to the deep
7:39
learning system, or the convolutional network. And then
7:42
you present it with another one of these. So you have seven
7:47
other of these image chunks. So here, I have it next to it. And
7:51
then you have it predict what label is, is it the seven
7:55
position seven, position five, position three, and so forth. So
7:58
you know the answer, because you were the one dividing this
8:01
image was, let's say, a Python algorithm. And you have the
8:04
machine, then, or you teach the machine to predict the right
8:07
position. So why is that useful, if you want to build a cat
8:11
versus doc classifier, this is really like helping the system
8:15
to learn to understand what's in the image, what's an object,
8:20
because it kind of has to understand a little bit about
8:22
cats here, to put them in the right order, because here, you
8:25
have the ear, there's an eye here, a part of an eye, that's
8:29
part of an eye here. So it has to kind of somewhat learn the
8:32
structure of a cat to put these pieces into the right order. And
8:38
you have maybe also other objects there, like dogs and
8:40
cats and other animals. So it kind of learns the structure of
8:43
an animal. And it's like the pre training task again. And then
8:49
after this pre training, you can take your network and fit it
8:52
onto a smaller target data set that is, let's say, concerned
8:55
with animal classification. But again, self service learning,
8:58
it's like a very recent very hot topic, we will maybe briefly
9:02
revisit this in the context of transformers at the very end of
9:07
this course. But yeah, I just wanted to mention it for
9:09
completeness. It's more like an I would say a little bit of an
9:13
advanced topic for this introductory course. So I just
9:16
want to introduce it that it exists, you might find that
9:18
interesting, you can maybe play around with that in your class
9:21
project, that might be something to explore. There are many
9:23
different types of self supervised learning approaches.
9:26
But yeah, that would be another special case of supervised
9:30
learning. So okay, now I covered all the broad categories of
9:35
machine learning. And the next on the remaining three parts of
9:39
lecture one, they will be probably hopefully a little bit
9:41
shorter. I will briefly talk about the supervised learning
9:46
workflow, like going into a little bit more detail of how we
9:50
get train a supervised learning system, the different steps. And
9:54
then I will introduce some of the notation and jargon like
9:59
some mathematical notation, like how we use symbols to denote a
10:05
training set and loss function and things like that. And then I
10:08
will talk a little bit about the tools pytorch that we will be
10:12
using just introducing it. And we will cover that also in more
10:16
detail in a later lecture. But yeah, this is also just the
10:20
introduction. So if there are some details that I introduced
10:25
here, that are maybe too much detail, and it's confusing, don't
10:28
worry about it. I just wanted to give you a brief picture
10:32
overview. And we will cover the important details really much
10:36
more slowly later in this class. Alright, so that's it for now.
10:41
And the next video will be on the supervised learning workflow.

##v9:

0:01
Yeah, hi, and welcome back, everyone. I hope you had a nice
0:04
first lecture day. And remember when I mentioned that snow is
0:08
awesome. If you look outside, there's a whole lot of new snow
0:11
outside. But anyways, so today, I'm going to talk about the
0:15
supervised learning workflow in a little bit more detail. Last
0:19
lecture day, I talked about machine learning, and the three
0:22
categories of machine learning. Now I want to provide some more
0:25
details about the supervised learning workflow. And then I
0:28
will also cover some of the necessary notation and jargon
0:33
regarding machine learning that we will be needing for the
0:36
remainder of this course. So just laying some groundwork, how
0:39
we define a training set and what mathematical symbols we use
0:43
and some terms that we will be using. However, I'm trying to
0:47
keep things a little bit short this time, because yeah, as
0:50
you've seen in the previous lecture day, there are lots of
0:53
topics I want to cover this semester. So I don't want to go
0:56
into too much technical details that are not very interesting
0:59
for each topic. So I try to keep things a bit short. And then
1:03
with that, I hope we will be able to tackle all the projects
1:08
that we are topics that I have in mind for this course. So
1:11
that without wasting too much more time, let me get started
1:15
with supervised learning workflow.
1:18
Alright, now let me talk a little bit more about the
1:20
supervised learning workflow. And yeah, we will be using
1:24
supervised learning a lot in the next couple of weeks. So just to
1:28
briefly outline how supervised learning works. So supervised
1:33
learning is, like you remember from the previous videos, the
1:36
process of regression or classification. So there are
1:40
essentially two steps. One is the training step. So we train
1:45
a machine learning model. And the second step is the
1:48
inference step. But before we get to the inference step, let
1:51
me talk about the training step first. So imagine you have a
1:56
training data set. And your task is in this case, let's say
2:00
classification, you want to classify something, let's maybe
2:05
pick a simple example of classifying different flowers.
2:10
So let's say you have on different flowers. And there
2:18
might be different flower species, maybe some flowers more
2:22
like this, and so forth. And you are interested in classifying
2:27
how or what type of flower it is based on an image. So you
2:30
collected multiple flower images, that's your training
2:34
data set. And you also have an expert consulted an expert to
2:38
provide you with the labels. So it could be for example, let me
2:44
think that's, let's say this is an iris flower, this is a rose
2:48
and yeah, the third one would be let's say a sunflower or
2:52
something like that. So you have these labels, these are your
3:02
labels that you want to predict. And the flowers, the pictures,
3:06
the pictures of the flowers, these are your observations. So
3:13
you're collected, maybe 1000s of those, this is your training
3:16
data set. And in traditional machine learning, what you would
3:20
do is you would extract some features. So usually, traditional
3:25
machine learning algorithms don't work very well on image
3:28
data. So you would extract some features. And here again, you
3:32
would need a domain expert. And having someone someone's opinion
3:38
like what could be a good feature, you can think about it.
3:40
But also, usually, it's good to consult an expert who knows a
3:44
lot about flowers. And it also helps like understanding the
3:48
data set a little bit. So one might think, okay, um, yeah, what
3:51
could be a potential feature, it could be maybe, maybe the color
3:55
of the flower, and maybe the height of the flower. And yeah,
4:00
other aspects on the number of leaves, and so forth. So there
4:09
might be different features, you have to think about what could
4:11
be a good feature. And also, what would be a feature that you
4:14
can obtain from, let's say, the image data easily. So if you
4:19
have that, if you have these features, and also the labels,
4:23
you can then train an algorithm machine learning algorithm to
4:27
make predictions. So after you're training the model, so in
4:32
this step, so we say training, we can also say, fitting the
4:39
model or parameter rising. The model depends on what model we
4:46
are talking about. Some models are nonparametric models. So we
4:51
don't really update weight parameters in the model. So in
4:54
that case, parameter rising would be not a good fit. But
4:57
yeah, these terms, training, fitting and parameter rising are
5:02
kind of synonymous in the context of deep learning. Now,
5:06
let's say we have our model that is our model that was learned
5:12
from the data, or parameterized based on the training data set.
5:15
Then the other goal is to make predictions on new flowers,
5:19
because yeah, the whole goal about developing the model is to
5:23
use it in some prediction tasks. So for example, if let's say you
5:27
have a website, you have to develop the website, where
5:30
people can upload pictures of flowers, and then your pipeline
5:35
can predict what type of flow it is. So you would have new
5:40
flowers, new images, that would be a feature extraction step
5:44
for these flowers. So here, the feature extraction step is
5:48
exactly the same as during training, because your model has
5:52
learned to work with this data that it has seen during
5:56
training. So you have to have the same feature extraction
5:59
steps here, then you have your model. And then you can use it
6:03
to predict new labels. And this is nowadays called inference as
6:09
shown here. So yeah, inference, why inference, it's a little bit
6:13
different from statistical inference, it's just happens to
6:16
be called inference. But yeah, it's really like, you can think
6:19
of it as, as prediction on new data or something like that.
6:25
All right. So this is the typical supervised learning
6:30
workflow, training a model, and then using it. However,
6:35
somewhere in this process, we also want to evaluate how good
6:38
our model is, before we employ it in the real world. So how do
6:42
we evaluate the performance of a model. So this is relatively
6:47
similar to the inference step I've shown you in the previous
6:50
slide. However, we use a test set for that. So the test set.
6:55
Set here, it looks like the training set, but it is usually
7:01
independent from the training set. So if you have a large
7:04
data set, so let's say you have a large data set, what you
7:08
usually do is you shuffle the data set and then randomly
7:12
divided into a large portion for training, let's say, 70%, and a
7:18
smaller portion for testing, let's say 30%. Usually, there's
7:25
a third split. Let me write this down. So this is training, but
7:30
this is also only an approximate number. 30% for testing, you can
7:36
maybe also it depends really on the data set size, we will talk
7:38
more about that. But you can also just make this a little
7:41
bit smaller, let's say 20%. And then make this maybe, I don't
7:47
know, let's say, let's keep it at 70%. And then there could be a
7:51
third data set here, that's 10%. And that is the validation
7:57
set that we use for tuning a model. But yeah, we will talk
8:02
more about that later when we also see our first code
8:05
examples. So for now, consider this test set. And this test set
8:10
here looks very similar to the training set, we have
8:13
observations and labels. And now what we do though is, so we have
8:19
this step here, which is like the inference step. I showed you
8:24
in the previous slide. So what's going on here is the same as I
8:31
have here on the right side, the inference step, the same, same
8:35
step. But yeah, what we do now is we have these known labels. So
8:42
we separate from the test set observations and labels, we keep
8:46
them separately. So we use our labels. Here, we withhold them
8:51
from the model, because there is no training right now. And then
8:54
we use the observations as we treat them as new observations,
8:59
we pretend they are new. So we pretend these are new labels.
9:06
Then we do our feature extraction step, give the data
9:10
to the model. And the model makes the predictions. So we
9:13
have now two sets of labels. One are the known labels, we know
9:17
them because we had them in the test set. They are sometimes
9:20
also called ground truth data. So that is also sometimes they
9:30
are called ground truth data. And we compare these known
9:33
labels to the predicted labels. And then we can count the number
9:37
of times often our model makes a correct prediction. And then we
9:41
can, for example, compute the accuracy if we count the number
9:44
of correct predictions over the number of total data points in
9:51
the test set that gives us the accuracy. And similarly, we can
9:59
compute the error by one minus the accuracy. So it's like the
10:04
basic workflow of a supervised learning model. Yeah, regarding
10:11
the data regarding the flowers. So I also wanted to briefly
10:16
discuss the difference between structured and unstructured data.
10:22
So students who have taken statistics 451, the introduction
10:29
to machine learning. In this class, we mainly worked with
10:33
structured data. So in this class, we won't be working with
10:36
structured data, except for some basic examples. So a structured
10:41
data set is, you can think of it as a tabular data set, or a
10:47
data set that yet it looks like a table, essentially. And this is
10:52
something where you have the data set organized as follows,
10:59
where the columns are your features. And the rows are your
11:07
observations. So let me go back a step. So this is a table you
11:15
may get during this feature extraction step. So this is
11:21
something a human has to do, or you can also automate it in
11:24
certain points. But imagine the original data, you can also
11:28
the original data would look like an image. So the original
11:31
data is the flower. So you can observe it either in the real
11:35
world, or you can take a picture of the flower. And then as a
11:37
human, you can use a ruler and then make the measurements
11:41
about these petal and sepal leaves. So sepal and petal are
11:47
these leaves here. And then you can measure how long they are
11:53
and how wide they are. So here I have a table of the sepal
11:57
length, sepal width, petal length and petal width, either
12:01
yeah, from an image, I mean, from image would be a bit hard
12:03
because it's not three dimensional, but let's say an
12:05
observation in the real world. So this could be then your
12:09
tabular data set here, these would be your four features, we
12:13
have four features here, on the right hand side, this is the
12:17
label that we want to predict included it here in the same
12:21
table. This would be an example of a structured data set. In
12:26
contrast, an unstructured data set would be the raw data, for
12:32
example, this image here. So this would be an unstructured
12:36
data set. So let me write this down unstructured. Sometimes we
12:40
also just call it the raw data. So you can actually extract this
12:47
structured data set from the unstructured data set. But yeah,
12:50
it's not always very simple. Because for example, sometimes
12:53
you can automate it here, it might be hard to automate it,
12:56
you have some have to have some human helping with that, like,
12:59
maybe even taking the floor taking a ruler and making
13:02
measurements on structured data is something where we use
13:08
traditional machine learning and unstructured data is something
13:13
where we can use deep learning. Because deep learning has
13:19
internally a feature extraction step, it's implicitly doing
13:23
feature extraction for us. The downside is, of course, we need
13:27
much more data. For example, here, this iris data set only
13:32
has 150 flower examples. And this is sufficient for regular
13:37
machine learning algorithms for traditional machine learning
13:39
algorithms such as random forests, you can easily get
13:43
something like a 99% accuracy with a random forest on this
13:47
data set. If you want to get 99% performance with deep learning
13:52
on a flower species prediction task, you would at least I would
13:56
say, there are some papers I can maybe link later, but I would
14:00
say at least 10,000 images of these flowers to get, let's say
14:05
within the 90% accuracy. So this is a three class prediction
14:12
problem. So it would be requiring much more data and
14:16
not in every scenario, you have such a large data set. So I'm
14:20
currently also working on a collaboration where we analyze
14:23
videos. So we classify different videos. And yeah, one limitation
14:27
is that we only have 1000 videos. So the videos are
14:30
actually from YouTube. But the problem is the labels, the
14:34
labels is here on what's kind of costly, because you would have
14:37
to have a human looking at these video videos to provide the
14:41
labels. So it's not always possible to find people to watch
14:46
long videos to provide these annotations that would be very
14:49
intensive. So sometimes, you have to make the trade off. Okay,
14:52
um, I can use deep learning, but I need a large data set. So if
14:56
you have a lot of labels available, then it's feasible.
14:59
But sometimes you don't and then using a structured data set is
15:03
maybe not a bad idea. Because it's simpler, in a sense. Okay,
15:08
so here's a nice also summary. I found in this book, it's a nice
15:13
cartoon, illustrating the difference between the
15:16
structured and unstructured workflow, where you have
15:19
traditional machine learning with this deep learning. So here
15:25
on the left hand side, this is the workflow for for deep
15:31
learning, essentially, where you have the data, and then you
15:34
throw it into the network, it's like a black box. And then the
15:39
output is some prediction. So if you get the reference here 42,
15:44
if you know the joke, maybe post in Piazza, it's actually, I'm
15:48
just curious how many people nowadays know what the number
15:54
42 refers to, it's kind of a insider joke. Anyways, so yeah,
15:59
and on the right hand side, this is the traditional workflow
16:04
where you have a human extracting the feature from the
16:08
data. So you have these hand crafted features that you then
16:12
provide to the machine learning system, and then do the
16:15
prediction. So it's essentially highlighting the difference
16:19
between the unstructured and structured workflow, or data
16:29
sets. So the structured data would be this one here in the
16:34
center where you have the hand crafted features. Yeah, just to
16:38
overlay it with the example I've just shown you with the flowers.
16:42
So on the left hand side, for the deep learning context, you
16:46
would just give the model the raw images. And the model will
16:50
figure out what features to use. So it will learn certain feature
16:56
extractors, we will talk more about this when we talk about
16:59
convolutional neural networks later, they would implicitly
17:12
learn how to extract features. And in contrast, the machine
17:17
learning workflow with a hand crafted features here on the
17:20
right hand side, where you have these hand crafted features
17:23
such as you're taking these measurements here. Alright, so
17:27
yeah, that's just a brief overview of the supervised
17:29
learning workflow and how machine learning is different
17:32
from deep learning. Next, I want to introduce some of the
17:36
necessary notation and jargon. And then I will also show you a
17:40
little bit how what type of tools we're using in this class.

##v10:

0:05
Yeah. Yeah, no, let me go over some of the necessary machine
0:12
learning notation and jargon, something that we will be using
0:15
in this class over and over again. And that is also commonly
0:18
used in the machine learning and deep learning communities. So
0:23
yeah, I'm revisiting the term supervised learning. What is
0:25
supervised learning? It's about learning a function that maps
0:29
some input x to some output y, where x are the features, and y
0:35
are the targets. So yeah, like you remember from the previous
0:38
videos, the features, or we also call them observations. They are
0:44
usually vectors, or, for example, the flower dimensions,
0:49
sepal length, sepal width, petal length, and petal width, or
0:54
pixels of an image and so forth. By the way, if I write a vector,
0:58
I would then if I do use handwriting, use this a little
1:02
arrow to denote a vector. And I will try to use, if I don't
1:06
forget, an underscore and a capital letter to refer to a
1:09
matrix. And x, if I don't use any of this would be a scalar
1:14
value. So here, though, I was just writing x as a scalar, but
1:18
features in practice can be also vectors. So anyways, we are
1:22
getting ahead of ourselves here a little bit. So the next term
1:26
here on this slide is structured data, which we discussed also
1:30
in the previous video. So the term structured data usually
1:33
refers to data in a format of tables cannot also think of it
1:38
as tabular data usually comes in the form of databases, like if
1:46
you know SQL databases, for example, or if you think of
1:49
Excel spreadsheets or CSV files, this would be a typical example
1:55
of a structured data set. Then your unstructured data, this is
1:59
usually what we refer to as the raw data, for example, images,
2:04
the pixels and image, audio signals or text sentences like
2:08
documents. And this is usually something that yeah, deep
2:12
learning works with. So and before deep learning, we usually
2:16
needed extensive feature engineering, as I explained
2:19
before, where we extracted features from raw data sources.
2:24
So here on the right hand side, I just wanted to show you
2:26
another example of raw image input versus something that
2:33
requires feature engineering. So for example, here you have a
2:37
portrait of image. And let's say the task is face recognition,
2:42
where you want to match multiple faces. So here, I don't have
2:48
multiple people where we want to compare whether it's the same
2:50
person or not. So we don't have really face recognition matching
2:53
however, what I'm illustrating here is that we can extract
2:58
features from this image. So here, this is a traditional
3:03
method using like facial key point extraction. So we're
3:07
extracting so called face landmarks. And this would be a
3:13
feature engineering step, like simplifying the image, such that
3:18
it only now contains these key points, I think they are on 67
3:21
or so key points. So we reduced the complexity of the data set
3:25
by having a high dimensional data set. So if this is for
3:28
example, 200 by 200 pixel image, we would have 40,000 pixels or
3:37
40,000 features, including background and everything. And
3:40
we here we just simplified it and only have I think it's 67
3:45
features, I could be wrong, you would have to double check. So
3:48
here, this is actually a function I implemented based on
3:54
library called D lib, which implements this face extraction.
3:59
Here, I'm just I implemented a Python wrapper function to make
4:02
it a little bit simpler to use any case. So here, this would be
4:05
an example of manual feature engineering, like reducing the
4:09
complexity of the problem by extracting a smaller number of
4:13
features from this raw input. Okay, so moving on. So here on
4:20
this slide are some more terminology. So a training set,
4:24
we usually refer to it as D. And a training set comes in pairs of
4:29
these observations, the so called training examples, or
4:33
features, and the target labels. And like I said, I will be using
4:39
this arrow notation, if I do handwriting to refer to
4:42
vectors. So and if I don't do handwriting, like in the slides,
4:47
using the computer font, I will make them bold. And yeah, for
4:52
scalars, I won't use bold font, then a training data set
4:58
consists of n training examples. So that's the number of examples
5:02
in the training set. And I will be using the squared bracket
5:07
notation here as a superscript to refer to the training data
5:11
points index. So if I write something like 10, then this
5:17
means that's the 10th training feature, feature vector in the
5:23
training sets, I'm referring to the 10th training example to the
5:26
feature vector of the 10th training example. So then, in
5:31
practice, so usually the data set, the training data set
5:35
data set comes from some data generating distribution,
5:38
something could be a natural physical phenomenon that has
5:42
created our data and so forth. So there exists some unknown
5:46
function that associates our feature vectors with some label.
5:51
And the goal in machine learning is in supervised learning is to
5:55
predict the labels. So how we do that is by approximating this
6:01
unknown function. And yeah, traditionally, this is called
6:04
the hypothesis. Nowadays, I think the hypothesis term is a
6:10
little bit dated. We can just call that model, we don't have
6:14
to use fancy terms like hypothesis can just call that
6:17
the machine learning model. So it's like a more common way to
6:21
refer to it. So you can think of the machine learning model as a
6:24
function that approximates approximates this unknown
6:27
function. So it will, for example, in the classification
6:30
example, return a predicted label, so we can write the
6:35
predicted hit label as y hat, for example, or we can just
6:39
call it target, target t or output, oh, oh, it's maybe a
6:43
little bit tricky, because it almost looks like a zero. But
6:46
yeah, these are all equivalent notations. So in this way, is
6:50
eight, you can think of it as the machine learning model.
6:54
Yeah, and classification again, so we have the model, which is a
6:59
function that maps some m dimensional input vector. So
7:03
this would be our features mapping those to some targets
7:09
here, where the targets in the term in the context of
7:12
classifications are class labels. So we can have up to k
7:16
class labels. So usually k is larger or larger equal to two,
7:22
we have at least two classes. In the case of the iris data set
7:26
that I've shown you earlier, there were actually three
7:29
possible classes on setosa, versicolor, and organica, for
7:37
example. But yeah, of course, really depends on the data set,
7:42
there is no limit to the number of classes you can have. Also,
7:46
yeah, in regression, we have an input vector that is m
7:49
dimensional, and we map that to a continuous to real valued
7:53
number. Yeah, more about the feature vector. So I said before
8:00
the feature vector is m dimensional. So if you think
8:02
back of the iris example, where we had the sepal length, sepal
8:12
width, petal length, and petal width, so we had four features.
8:22
And then if I look at the training index, let's say, focus
8:29
in on the third training example, I would write it down as
8:37
three. And then it's a vector. So it's a third feature vector.
8:43
So in this case, we have a vector of consisting of four
8:47
values. So this is what I'm showing you here as a vector
8:49
representation. So yeah, we have an m dimensional vector, and I
8:53
will use the subscript notation to refer to the feature index.
8:59
So if I write something like three here, this would refer to
9:03
the third, so 123 to the petal length of the third training
9:10
example. Now in Python, we start zero indexing. So if we do
9:15
Python coding, it might be a bit more complicated because we
9:18
should restart indexing at zero in contrast to R. So in, in
9:24
Python notation, this would be actually the fourth training
9:28
example. And the fourth feature like petal width. Yeah, moving
9:34
on. And now here I have a feature vector again, just as on
9:38
the previous slide. However, in practice, we usually have
9:41
multiple feature vectors. So one feature vector per training
9:45
example. So if you think back of the iris data set where we had
9:48
up to 150 training examples, let's use the letter n here over
9:55
the rows to refer to the training data points. And then
10:01
for each one, we had a feature, let's call that feature one,
10:04
feature two, feature three, and feature four. So we have this
10:08
table here. So you can also use, let's say, dot dot dot feature M.
10:16
So then each data point, so each observation is a feature vector.
10:23
So in linear algebra notation, we usually write a vector as a
10:28
column. However, we arrange the vector here as like a row
10:32
vector. So a row vector would be referring to one data point as
10:37
one observation. So we use a transpose on that one to refer
10:43
to this one here as the first data point in our table. It's
10:48
a little bit confusing the way I've written it here. Because
10:51
now I'm using the subscript. This is just because I have the
10:53
transpose here. And then it's a little bit squished. So actually,
11:00
I could have written it as transpose one, for example, it
11:05
would have been clearer, maybe. So maybe ignore this notation
11:09
here on the right hand side, I have the more extended notation
11:13
where I'm referring with a superscript to the data point
11:19
index. So this would be all the first data point here in the
11:23
first row. And then the subscript refers to the feature
11:28
index. So if I pick, for example, this case here, this
11:34
would be what is maybe unfortunate, let me use this one
11:37
here. This is the second feature of the nth data point. So this
11:42
would be if I go right here, this would be this one here. So
11:46
this scalar value. So usually a machine and we use a design
11:50
matrix, I will use bold letters. And if I handwrite this, I will
11:55
try to use an underscore to make sure or to indicate that this is
11:58
a matrix, because with handwriting, it can be unclear
12:02
if I do an x, it's unclear. If I don't, yeah, denote it further,
12:06
whether it's a vector or matrix, and so forth. So for again, for
12:09
vectors, I will use this notation and for matrices, this
12:12
notation. And I may forget, but I will try not to. Okay, yeah,
12:18
just to summarize, this is a structured data set how it would
12:21
look like in machine learning. In the first couple of lectures,
12:25
we will actually be using with structured data before we go
12:28
into working with unstructured data. So in the first couple of
12:33
lectures, just as a warm up using simpler, deep learning
12:36
related methods like single layer neural networks, and then
12:39
multi layer neural networks that are fully connected, they will
12:44
be working with also structured data. And then when we talk
12:47
about convolutional networks and recurrent neural networks, which
12:50
are the real innovations in deep learning, then we will be using
12:54
unstructured data. Alright, so yeah, just to recap, m is the
13:02
feature number. So we have up to m features and n is the number
13:14
of training examples. So I think the reason why I left the
13:21
blank here, I wanted to ask you that as an exercise. So in that
13:25
way, um, I already did the exercise for you. So here, the
13:31
rows thing, it was what I was referring to our training
13:36
examples, where the columns are features. And this is our class
13:47
class label column. Alright, so it was not very exciting. But
13:53
I was just summarizing how we think of a data set in the
13:57
context of machine learning. Now, if we have image data, how
14:04
do we deal with that? How does it fit into our concept of
14:09
representing data? So images are actually unstructured data, as
14:14
I mentioned before, but we can actually convert it into a
14:17
structured data set. And if you think of image like this, this
14:21
is actually a 28 by 28 image, which should be 784 dimensional.
14:30
So we have 784 pixels, pixels are usually in the range between
14:36
zero and 255. However, here, assume I normalized the data,
14:43
we will talk more about why data normalization is useful. I
14:48
normalized it such that the pixel values are in the range
14:51
between zero and one. So we have a pixel like a 700 of these
14:59
384 of these pixels here. So you can actually all can see this
15:05
actually low resolution, one pixel here and one pixel here
15:08
and so forth. So I think you know what I mean by pixel. So
15:11
we can actually use that as input to a traditional machine
15:15
learning method in terms of thinking of this as a structure
15:18
data set by concatenating the rows. So we can make a long
15:22
feature vector out of this image, because I mean, this is a
15:26
matrix, right? So it's like a 28 by 28 matrix, but we can
15:32
convert this into a vector by just concatenating. So take the
15:36
first row, let's say this first row here. And then we have the
15:43
second row. And just add it here to the first row. And then third
15:51
row. Adding it here. So and if I keep doing that, I get a very
15:57
long vector, in fact, a 784 dimensional vector. And that is
16:03
what I'm showing you here in the center. We're probably already
16:07
wondering what these numbers are. And these are the pixel
16:10
values. So the 0.0 refers to a white pixel. So you can see in
16:15
the beginning, here, the image is all white. So you have all
16:19
the white 0.0 is here. And then you have these grayscale and
16:25
black pixels, which are about here. So we kind of converted
16:30
this unstructured data set into a feature vector that we can then
16:34
use with traditional methods. And we will also be doing that
16:38
in the context of deep learning using simpler methods like
16:42
multi layer perceptrons, fully connected neural networks. So we
16:45
will start with a simple approach and then build up to
16:48
it and then later use the unstructured data directly. All
16:52
right. So yeah, like I said before, convolution neural
16:56
networks, which will be a topic later on in this course,
16:59
convolution neural networks, they use the image data
17:03
directly. And usually the format for that is also a matrix or
17:08
more precisely, it's actually a three or four dimensional
17:12
tensor. So here, so there are two, two common representations,
17:18
one is called n ch w. We will talk more about that later when
17:23
the time comes. But maybe if you're curious what it stands
17:26
what it stands for, h stands for the height. W stands for the
17:32
width of an image. So we have here the h times w. So this
17:36
would be a matrix. However, there's usually also a color
17:40
channel. So C stands for color. In this case, we don't have
17:46
color because it's a black and white image. So in this case,
17:49
it's so there's a one to actually I'm showing you here
17:52
the dimensions. So 28 by 28 height times width, and then the
17:58
color channel. And then usually in deep learning, what we do is
18:01
we bundle a bunch of images together as input for the neural
18:05
network. So and we have something called a batch size.
18:08
So here I have 128 images where each image is a 3d tensor. So in
18:15
that way, if I consider all of that, it's a 40 tensor. So in
18:19
that way, we are representing the data as tensors. And this is
18:24
why we need some basic linear algebra for this course while I
18:29
mean, we won't be using fancy things, just simple matrix
18:33
multiplications and dot product. And I will also talk more about
18:36
that later. So right now, I don't want to go into too much
18:39
detail because convolutional networks, that is topic far
18:43
ahead a few weeks ahead. So I don't want to talk too much
18:47
about this year, I have to be honestly, a little bit careful
18:50
with the time because like you noticed, I always try or I try
18:54
to avoid it, but I always end up going on tangents and talking
18:58
about things in too much detail too early, I think. So let me
19:02
move on then. Yeah, here, lastly, machine learning jargon
19:07
part two. So some more terms we will be using, I think this is
19:11
more like useful as a cheat sheet, like something you can
19:14
maybe refer to later, when certain terms are unclear. So
19:19
when we say, for example, training a model, that is the
19:23
same as saying, for example, fitting a model or parameter
19:26
raising a model or learning from data, then the other word
19:30
training example, it's synonymous to saying, for
19:33
example, training record or training instance or training
19:36
sample. However, yeah, for example, when I teach other
19:41
statistics classes, I usually use often as the decisions we
19:46
use the term sample. But I find sample can be a little bit
19:50
ambiguous, especially in the context of deep learning.
19:53
Because if we say training sample, it's not clear really,
19:57
whether we are we are referring to a single training data point
20:01
or multiple training data points. So for example, when I
20:04
was writing my Python machine learning book in 2015, in the
20:07
first edition, I used the term training sample as I remember, I
20:11
mean, it has been six years ago, but I think I used training
20:14
sample throughout. And then sometimes I noticed it was a
20:17
little bit confusing. Do I mean now a single data point? Or do I
20:20
mean the training data set as a training sample? So I later also
20:23
went back and changed everything to saying training example, if I
20:27
refer to a simple or single training example. And then also
20:31
in plural, I would say training examples. I think this is a
20:35
little bit more clear. And this is also something most people in
20:38
machine learning and deep learning nowadays use. So the
20:41
term training example, then yeah, feature feature is also
20:46
synonymous to observation or predictor variable, independent
20:50
variable input attribute covariate. So in other
20:53
statistics classes, we are often using the term, for example,
20:56
predictor, and things like that, or even covariate. So here in
21:00
machine learning and deep learning, we usually use the
21:02
term feature. Then we have the term target, which is synonymous
21:07
to outcome ground truth, output response variable, dependent
21:11
variable, and then a specific context of classification, we
21:14
also say class label or just label. So also, these are all
21:19
the same thing. And then yeah, lastly here, output prediction.
21:23
And this is what the model produces. This is different from
21:26
the target. So the target is, we want to predict the target. So
21:31
this is the ground truth or something that is provided in
21:36
the data set. And the prediction or output is the thing that the
21:41
model returns, and we want to usually match the target. Okay,
21:46
so this is it for jargon. And the next video, I want to
21:49
briefly talk about a little bit more about the tools that we
21:53
will be using in this course.

##v11:

0:01
All right, lastly, to wrap things up, let's briefly talk
0:04
about the practical aspects of this course, the tools that we
0:07
are going to use, as you have already guessed, probably, we
0:11
are going to use Python as our main programming language. So
0:15
here's a nice chart by Jacob and a plus who made it in 2015. It
0:20
is here outlining the different layers of the Python ecosystem,
0:24
the scientific computing ecosystem. So you have your
0:27
Python at the lowest level, that's the basic fundamental
0:31
thing that all these libraries require. And then layer by layer,
0:35
these libraries become more specialized. So you have general
0:40
computing libraries like the IPython interactive computing
0:43
environment, the NumPy linear algebra library, there's
0:47
siphon, which kind of helps inputting or using C code in
0:53
Python if you need to. So that's something we won't be doing in
0:56
this class. But for certain scientific projects, it's also
0:59
useful to make things faster. There's Jupiter, that is
1:04
ecosystem providing Jupiter notebooks, which you have
1:07
probably heard about already. I will say a few things about
1:11
Jupiter later. Yeah, so let me not say it here, I will say it
1:16
later. So then there are other libraries like scipy, which are
1:20
providing additional algorithms on top of NumPy, or the
1:25
visualization library like matplotlib, and pandas, which is
1:28
a data frame library, I want to go over the other ones, because
1:32
we won't be using them in this course. So the only maybe
1:37
notable ones are here, or is scikit learn, which is a machine
1:41
learning library that we have used in statistics for 51 in
1:46
fall semester. And there's also ML extend, which is a library
1:50
that I developed, implementing algorithms that are not
1:53
implemented in scikit learn. So I called it ML extend for
1:56
machine learning extensions, because I was not very creative.
1:59
So yeah, these are libraries that we used in 451. And we
2:04
won't be using those at all in this class. So there's basically
2:08
almost zero overlap between these two classes. And that's
2:11
not really an advantage of taking 451. Because really, we
2:15
will be focusing on deep learning here and not on
2:18
traditional machine learning. So in this class, we will be
2:21
mainly using Python and pytorch pytorch is the library built on
2:27
top of Python, we will of course also be using a little bit of
2:30
NumPy for some basic computing, especially in the next lecture
2:36
to just introduce things slowly. And then in I think in the
2:41
third lecture on perceptrons, and then also we will be using
2:44
matplotlib occasionally to make visualizations. But yeah, the
2:47
focus will be really on pytorch. Regarding Jupiter. So honestly,
2:53
I like Jupiter notebooks a lot, I have been using them a lot for
2:57
data analysis. However, based on my experience, I actually
3:03
recently started to prefer using regular Python scripts when
3:07
working with deep learning. There are many reasons because
3:11
deep learning code can be very verbose sometimes. And sometimes
3:15
it also takes a long time to run. And sometimes I also run
3:18
that on different computers, via the terminal, and things like
3:22
that. And they're just certain aspects where on script files
3:26
are a little bit more convenient to handle. Also, one aspect is
3:30
that there are easier ways to debug your code because there
3:34
are nicer linters and code highlighters in Yeah, in script,
3:39
text editors or visual, sorry, IDs into developer IDs. So I
3:46
will also say a few words about that maybe later. So regarding
3:52
pytorch, why are we going to use pytorch? So personally, my
3:57
history is like I started doing deep learning or working with
4:01
neural networks. In like 2014 1314, there was a library
4:06
called Theano that I've been using extensively. And for my
4:10
first machine learning book, I was also using that for the
4:13
neural network chapter. Then in 2015, a new library called
4:17
TensorFlow was released by Google. And I started using
4:21
TensorFlow like everyone else back in 2015. I really liked
4:24
it. So I've been using that quite a bit in the last couple
4:29
of years. But then in 2017. So this was 2015 2017 pytorch came
4:37
out, which made certain things way more convenient. So
4:41
personally, I felt the library was a little bit more organized.
4:44
It had dynamic graphs, it was a little bit closer to NumPy.
4:48
Nowadays, I mean, both pytorch and TensorFlow have very similar
4:52
features, both have static and dynamic graph support and so
4:56
forth. So there's not that much difference anymore. But in the
4:59
years between, I would say 2017 1819 pytorch was much, much
5:05
nicer than TensorFlow, like for my personal view. Also, the deep
5:10
learning community. Yeah, really like pytorch, because you can
5:16
see based here on this visualization, this is like the
5:19
top machine, deep learning and machine learning conferences,
5:21
you can see that there's a huge growth in pytorch use. So
5:26
the solid lines here are pytorch, the graphs for pytorch
5:30
from 2017 2019, middle of 2019. So the 2020 conference year is
5:37
not included because this article is from 2019. Unfortunately,
5:40
they didn't update this article. But yeah, you can see there's
5:44
like a steep growth for all the conferences, in terms of pytorch
5:50
use, whereas for TensorFlow, it's rather going more like
5:55
downward or not growing as fast. So that way, many, many, many
5:58
people have adopted pytorch recently. And also when you look
6:01
at papers. So if you find a new paper, and you look for code on
6:06
GitHub, you will most often find nowadays that there is pytorch
6:10
code, of course, there's also often TensorFlow code. But yeah,
6:13
pytorch is or has grown a lot. So it's also very popular. Why is
6:20
it important that a library is popular? So yeah, one reason is
6:23
really that if you want to implement more sophisticated
6:26
models, it's really easier to find tutorials or example code
6:32
or the implementation corresponding to a paper and so
6:35
forth. And for this class, really, I still find pytorch is
6:40
a little bit more organized and easier to use than TensorFlow.
6:43
It's more similar to NumPy. And I think you will appreciate that
6:46
because the learning curve is not quite as steep. So yeah,
6:51
just for fun here, I made a short implemented the Leonard
6:56
five that we talked about a short code implementation. Like
7:00
I said, I kind of for deep learning nowadays prefer using
7:05
text editors. The reason really is that, for example, if I make
7:09
a typo here or something like that, it will underline it and
7:12
them way more convenience features. And deep learning
7:16
code can be sometimes long. And I find it easier to develop on
7:20
code in a text editor. Nowadays, I still use Jupyter
7:23
notebooks a lot. I'm just currently even today, I've been
7:27
working with them extensively, working on a paper where we made
7:30
visualizations. And for things like that, for analyzing data,
7:34
it's really, I think really great to use Jupyter notebooks.
7:37
It's just like, if you write long code, like more like,
7:41
coding the networks, I find text editors more convenient.
7:44
Personally, I would recommend, for example, a text editor,
7:46
like Visual Studio code, which is fast, free and works on all
7:51
operating systems like Windows, Linux, and Mac OS. Personally,
7:55
I use a Mac, but this is supported by what it's
7:58
supporting all major operating systems. And it has great
8:01
support for Python and also debugging and things like that.
8:04
So yeah, anyways, here, this is just a brief outline of how the
8:10
Linux work looked like. So if I hit enter, yeah, so this is the
8:15
one doing the image recognition here, the handwritten digit
8:18
recognition. And you can see in time pytorch, it's actually just
8:21
a few lines of code implementing this rather complicated
8:25
convolutional network. So you can see there are lots of things
8:27
going on. But in pytorch, it's just a few lines of code to
8:30
implement this model. Of course, there are a few more lines of
8:33
code to train the model. But actually, it's not that
8:36
complicated. And we will walk through this in more detail
8:40
step by step later in this course. So for right now, you
8:43
don't have to understand how this works. I just wanted to
8:45
show you the code is actually not that complicated. So here, I
8:50
was just running the code. Also, I was running it on a computer
8:53
that had a GPU. So in this case, I was running it for 10 epochs,
9:00
which means 10 iterations over the training set. And the
9:03
training set, I think it has 60,000 images. So you can think
9:07
of it as 10 times 60,000 images training it on that. And it
9:11
only takes, yeah, less than a minute. So it's super fast. And
9:15
even Yeah, then after a minute, you get already almost like
9:18
99% accuracy. So you have just some visualizations. And you can
9:22
see, even like after the second or fourth epoch, it already
9:26
reaches something like almost 99% accuracy, which I think is
9:30
really impressive. So this is on the validation set. Sorry. So
9:33
you can see actually, there's a gap between validation and
9:36
training set, which indicates overfitting. But we will also
9:40
talk more about that later. It's just like a quick demo of how
9:44
deep learning works and looks like. Okay, so let me finish
9:49
this introduction. So if there are still some things that are
9:53
unclear, I mean, this was just an introduction. So just an
9:57
overview, I noticed that I went into too much detail here and
10:00
there. So if there are some details, you don't understand
10:03
yet, don't worry about it too much. I've actually written a
10:05
blog post on this because I was planning to write a little
10:10
textbook based on my lecture slides, which is an ongoing
10:13
project. I'm not sure when and if I ever finished this. But
10:18
anyways, I uploaded the first chapter here as a blog post. So
10:21
you can actually read everything I talked about in written form.
10:25
And also, for those who are just interested in a general overview
10:29
of traditional machine learning, you can find the lecture notes
10:33
for the 451 class. So just if you're interested, you don't
10:38
have to read this, of course. However, what's also maybe
10:41
helpful is chapter one of my Python machine learning book,
10:44
which is, I would say a shorter version of this blog post. It's
10:47
just, it's, of course, written differently. It's a little bit,
10:52
I would say, smaller and shorter. And yeah, not not quite
10:57
the same. It's just like a different perspective, because
10:59
that's something I've written quite some time ago. Okay, so
11:03
with that, let me wrap up this introduction. And in the next
11:07
lecture, we will be looking at the brief history of neural
11:10
networks and deep learning. So I will just mainly outline why
11:14
things are cool and interesting and go over the major
11:17
architectures, because this will give you the big picture
11:20
overview of the topics we are going to cover then throughout
11:24
this whole semester.

##v12:

0:00
Yeah, hi, everyone. I decided to make a short bonus video stuff
0:04
in the news, interesting things related to deep learning. So
0:07
here, I'm just briefly talking about cool things I discovered
0:10
in the news this week related to deep learning. And I think it's
0:14
just fun to talk about the recent developments in deep
0:17
learning just to stay up to date with things. So I'm planning to
0:20
release such a video every week, if I have time. So it's also
0:25
only optional, so you don't have to watch them. So it's something
0:28
just watch it if you're interested in if not, don't
0:31
worry about it. It's just like some fun, additional video
0:34
content for this class. So then let me get started. And let me
0:38
tell you what happened in the world of deep learning this
0:41
week. Yeah, let's start with a cool application of deep
COVID19 Resource Needs Prediction
0:47
learning for COVID-19 resource needs predictions from a series
0:51
of x rays. So this was a project by Facebook AI research in
0:56
collaboration with medical doctors at NYU. And it's always
1:00
cool to involve your domain experts. I think that's super
1:03
important. As I mentioned in the lectures, it's always a good
1:07
idea to consult people who actually have some expertise in
1:11
the data that you're working with, especially if it's an
1:13
important application like a medical application. So in this
1:16
case, the researchers trained three models to predict your
1:21
patient deterioration and to help predict the resource
1:25
requirements like oxygen. So here in the first model, they
1:29
predicted the deterioration of the patient from only one x ray
1:33
image, they did the same thing, the same prediction task now
1:37
form also a series of x rays. And the third model was
1:41
predicting the oxygen supply needed for helping a patient
1:46
that was also based on a single x ray. So of course, it's
1:50
usually helpful to have multiple x rays that can also then boost
1:54
the performance if you have a sequence of x rays and you can
1:59
tackle this as a time series problem. However, these models
2:02
also work if only one single x ray is available. So how they
2:08
approach this modeling task was that they pre trained the deep
2:12
neural network on a large non COVID chest x ray database. So
2:17
they used a general x ray database. Why did they do that?
2:20
That's because they had a larger data set available this way,
2:24
because there are only limited numbers of x rays from COVID
2:28
patients at this point. So here they used self supervised
2:32
learning. Remember from the lecture self supervised learning
2:35
is this new trend where you pre train a model on a so called
2:39
pre text task, and then you find unit to your target data set. So
2:43
here, they did the fine tuning based on a smaller COVID 19 x
2:47
ray data set where they had 27,000 x rays from 5000
2:51
patients. And what was interesting is that, um, yeah,
2:54
these methods, they developed or performed human experts on some
2:59
of the measures. So of course, it's not a good idea probably to
3:02
replace humans. But I think developing these systems can be
3:06
really useful to help humans because yeah, everyone is
3:09
stretched very thin these days, especially to the large amount
3:14
of patients at hospitals right now. So maybe the doctor's task
3:19
can be done more effectively in the combination with deep
3:23
learning, especially for example, if you think of medical
3:26
staff that is maybe a little bit tired, having a deep learning
3:30
system taking also a second look at these images x rays could
3:35
maybe help you avoid making mistakes. So you can find the
3:40
full paper here on archive. And they also uploaded the pre
3:43
trained models on GitHub if someone is interested. Yeah,
Archive
3:48
regarding COVID-19 research. So on archive, which is a pre print
3:53
server, there's a large amount of 1000s of papers or
3:57
manuscripts pre prints uploaded regarding COVID-19. So this is a
4:01
general pre print server for machine learning. We have a lot
4:05
of papers on this server. So I help moderating the machine
4:10
learning categories. And every day, there are about 140 new
4:16
papers about deep learning and machine learning. So it's like a
4:19
huge amount of papers, I think there are no in total, like 14
4:23
million papers across different research domains. In any case,
4:27
you can use the search function to also search for specific
4:33
research. And here, I try to search keyword combination to
4:39
also bring up more COVID-19 related research with deep
4:45
learning. So what I showed you here on the previous slide was
4:48
pretty cool. But of course, it's not the only approach using
4:52
deep learning for COVID prediction from chest x ray. So
4:56
here using these search terms, you can find many more works in
4:59
this area. But yeah, also, you have to take this a little bit
5:02
with a grain of salt, because not all of these papers have
5:05
undergone peer review. So some of the findings may be spurious
5:11
or maybe less rigorous. So always take your archive papers with a
5:15
grain of salt. I will post a link so you can access these
5:19
papers if you're interested in that, for example, for the
5:22
context of your class projects. Yeah, there was another
5:25
interesting research project related to COVID-19 was the
5:29
learning of the language of viral evolution and escape. So
5:33
this was an article where the researchers described the
5:36
training of a bidirectional LSTM. So an LSTM LSTM stands for
5:42
long short term memory. It's a recurrent neural network of
5:51
flavor. And it's a particular, yeah, you can think of it as a
5:55
particular version of RNN. And we will talk also about that
5:58
more later in this course. So here, they trained a
6:01
bidirectional LSTM bidirectional just means that they process a
6:05
sequence from both ends from beginning to end and from the
6:09
end to the beginning. And it's a language model. So here, they
6:12
treat the amino acid sequence corresponding to a virus. They
6:17
treat this as a language model, like text, for example. And they
6:20
also draw some analogies from language modeling. For example,
6:24
they consider the context of being grammatically correct as
6:27
the biologically being correct. Like, is this like a correct
6:31
sequence, a correct amino acid sequence? Is it a plausible one?
6:35
And then also considering its semantic meaning. So here, in
6:39
context of a language, the semantic meaning would be the
6:42
meaning of the sentence. Here, it's whether the other sequence
6:46
causes immune responses or not. And yeah, they got a pretty good
6:50
performance. They have a point 85 AUC AUC stands for area
6:59
another curve,
7:02
which is rather ambiguous, because what curve do we mean
7:06
here, if there's no context, if you see something like a UC in a
7:09
paper, it usually means receiver operating characteristic area
7:13
under the curve. So our OC, that's a measure of false
7:18
positive and true positive rates, if you shift the
7:22
prediction threshold, but that's maybe too much detail at this
7:25
point. So what's important is that the point five is random.
7:30
So point five is a random prediction. And one point Oh, is
7:34
a perfect model. So in this way, they are closer to a really good
7:39
model than to a random or bad predictor. So yeah, that is
7:44
another interesting COVID-19 paper. Moving on to the more
Human AI
7:49
like business side of AI or deep learning. There was also
7:52
something I found really interesting, not that
7:55
interesting, but it was like, quite a headline. So there's
7:58
like a project called human AI, that just got 3.2 million of
8:03
funding to build a personal intelligence platform. So here,
8:08
that sounds very interesting. So what it is about is that they
8:11
are building an individual personal AI that is secured by a
8:14
blockchain to retain and recall information. So you have two
8:18
passwords in here. So you have the AI and blockchain, black
8:21
blockchain. So this is building a knowledge base in a way it
8:26
sounds like it, but based on an individual's information. So you
8:30
can maybe also think of it as a second brain. So they say it's
8:35
made possible through a convergence of neuroscience,
8:38
natural language processing, and blockchain to deliver seamless
8:41
in the moment recall, GPT three is built on the memories of the
8:45
public internet, while Luther, that's their system is built on
8:49
the memories of your private self. So it sounds like, yeah,
8:52
they're attempting to build a second brain or digital copy of
8:57
your brain. So that kind of also reminded me of of this movie
9:01
scene here, or actually TV show scene might be also fun to let
9:06
let me know if you know this, what the name of the TV show is
9:09
as a little side quiz here. Anyways, I'm moving on. So
Twitter Data
9:15
regarding access to data, to make a transition here, there's
9:20
also a cool initiative by Twitter. So Twitter is opening
9:23
up its full tweet archive to academic researchers for free.
9:27
So there have been projects before academic projects where
9:32
people used Twitter data, but as I as far as I know, it was a
9:35
little bit tedious to access the data through the API, because
9:39
there were some limitations. Now, um, yeah, they say they
9:44
want to make this easier and to give more access. So they say,
9:49
for example, they are giving applicants approved applicants,
9:53
the higher monthly tweet volume cap of 10 million tweets per
9:57
month, which is 20 times higher than what it was before. And
10:02
yeah, they also allow more precise filtering to help
10:05
researchers pinpoint tweets and other relevant data to what they
10:09
are studying, basically. So in that way, making research based
10:13
on Twitter a little bit more convenient. So what can you do?
10:16
What? What is Twitter data useful for? Why is why is that
10:20
actually cool? So there are actually quite some projects
10:24
involving social media data that are quite useful, beyond just
10:29
a simple sentiment analysis. So here, I saw another news article
10:33
where they're using artificial intelligence to manage extreme
10:36
weather events. So in this research, they use social media
10:41
contributions, for example, tweets to more usefully manage
10:45
crises. So they developed a noise reduction mechanism to
10:50
filter for valuable information from social media to better
10:54
assess trouble spots where there are, for example, floods or
10:57
snowstorms, and so forth. So yeah, that was another
11:02
interesting application of deep learning, where information can
11:07
be efficiently accessed to help certain areas where there are
11:14
problems. Okay, talking about data sets, large data sets. So
Imagenet
11:20
one data set that is very common in the deep learning community
11:23
very commonly used as a benchmark is the image net data set. I
11:27
think it's already 1616 15 years old, it has been released around
11:33
2005 2006. It's still very popular. It's a very large
11:37
data set about 14 million images. And it's usually used
11:41
for evaluating the classification performance of
11:45
image models like convolutional networks, or now also visual
11:49
transformers. So the problem, though, is that the image data
11:54
set is kind of notorious for mistakes. And there are also
11:58
incomplete labels. So sometimes you have multiple object in an
12:02
object in an image, for example, as shown here, you have a cow
12:07
here, and then a barn. And some, yeah, I don't know, maybe also
12:13
sky in the background. So there are multiple things going on,
12:16
or actually, they call it an ox here. So they are actually not
12:20
it's, it's the fence, I just see it here, it's the fence here. So
12:24
there are multiple objects in this image. And if you train a
12:27
classifier, a regular classifier, usually, it only gives
12:31
you the most confident class label as the prediction. So if
12:36
you have a classifier that predicts barn, it may be wrong
12:39
because the image was just labeled with ox here, cow. And
12:44
in that way, the classifier may be correct, but you are
12:49
counting it as a misclassification. So here in
12:52
this project, the researchers are relabeling image net. So
12:57
they are adding multiple labels to the image here. So they are
13:01
using also machine learning to do that, because it would take a
13:05
lot of people or resources to look at these 14 million images
13:09
and to assign the correct labels. So they make their life
13:12
easier by also using deep learning for that. So it's kind
13:14
of like a chicken egg problem. What comes first the data set or
13:18
the model, and the model can then be used for labeling the
13:21
data set. Here, what they do is they use a different data set,
13:24
they use 1 billion images from Instagram. And they train a
13:28
model called efficient net for for training this model to
13:33
become a machine annotator to annotate the 14 million images
13:37
in image net. They use crop regions for that. So they are
13:41
cropping different regions of the image. So for example, as
13:44
shown here, they are cropping the image into smaller regions
13:48
and then apply a classifier to each of these smaller regions to
13:51
obtain the class label. And then you have this model multi label
13:56
context for each image. That is also something I found actually
13:59
useful and interesting. Yeah, another project from Facebook AI
Facebook AI
14:04
research here, I also thought that might be a cool application
14:08
of machine learning, and deep learning that has some use for
14:13
the real world. So here, so what Facebook did is they used AI to
14:17
improve photo descriptions for people who are blind or visually
14:21
impaired. So they developed a smartphone app that way you can
14:26
take a picture and that app can then describe what can be seen
14:29
in that picture, like an audio message. So the system has been
14:35
around, I think for a couple of years, but they are just
14:38
improved to make it more accurate. So here, they trained
14:40
a res next model on 3.5 billion Instagram photos and the
14:45
corresponding hashtags. And they also are combined with a fast
14:48
RCN object detector to describe different aspects of this image.
14:53
So for example, here in this example, the description is it
14:57
may be an image of one person standing on or at Machu Picchu.
15:03
So going back here, this is kind of similar to these crop regions
15:07
where people have these different crops of the same
15:10
image, and then assign a label here. It's a similar approach
15:14
that you have, for example, person Machu Picchu, and so
15:18
forth. But the addition here is that there's also a text
15:22
describing this or putting this into context.


##v13:

0:00
Yeah, hi, and good morning, everyone. I hope you had a good
0:02
week and worked through all the lecture one material. Yeah, I
0:06
noticed that there were not that many questions, which I hope is
0:09
a good sign. So that means hopefully things were not too
0:11
complicated. And in this second lecture, I want to talk about a
0:15
brief summary of the history of neural networks and deep
0:18
learning. And you may wonder, why are we going to talk about
0:21
the history of deep learning? Why don't we just get started?
0:23
And I think a good justification for that is really that this
0:27
will provide you a nice big picture overview of all the
0:30
different topics in deep learning. So more like from a
0:33
historical perspective, because that's also somewhat how we are
0:36
going to talk about that in more detail, like starting with
0:40
simple things like single layer neural networks, and then because
0:44
they are kind of limited, we add additional hidden layers. So
0:47
they become more powerful at solving certain problems. And
0:51
then we will talk about also some advances like making them
0:55
work better for image data, like convolution neural networks and
0:59
making them work better for text data like sequence data, using
1:03
recurrent neural networks. So in that way, this lecture will
1:07
provide you with a big picture of all the little topics we are
1:09
going to cover in this course. So with that, then let me get
1:13
started.
Lecture Overview
1:15
Yeah, and when we are talking about the history of neural
1:18
networks and deep learning in this lecture, I also want to
1:21
emphasize again, this is the brief history of neural networks
1:25
and deep learning. I don't want to cover every nitty gritty
1:28
detail in this lecture, because otherwise, it would be easily a
1:32
two or three hour lecture or even longer. So in this way, I
1:35
just want to give you a short overview of the most important
1:38
parts that are important for this course. So yeah, I
Outline
1:42
structured this lecture into five parts, starting with the
1:45
simplest topic, artificial neurons, these are simple,
1:49
single layer neural networks. However, they have some
1:52
shortcomings, which are addressed in the multi layer
1:55
neural networks. So in the second part, we will talk about
1:59
why multi layer neural networks were invented and why they are
2:02
useful. And then how we go from multi layer neural networks to
2:07
deep learning, because multi layer networks have been around
2:09
since maybe at least 50 years. So deep learning is a more
2:13
recent term. So how did it evolve? How did multi layer
2:17
neural networks involve evolve into deep learning? Okay, and
2:20
then we will talk a little bit about deep learning hardware and
2:24
software developments, like recent tools that have been
2:29
developed to make computers that say better head deep learning
2:33
and also help humans to implement the more and more
2:37
complicated deep learning models. And then I will also
2:40
briefly outline the current research trends. Well, I would
2:44
say more like things that just emerged in the last few years,
2:48
one to one to three years that have become more popular in the
2:52
recent conference proceedings and so forth.

##v14:

0:00
Yeah, just to clarify how the mathematical model of a neuron
0:04
relates to these first logic functions is just a quick
0:08
overview. So you have drawn three tables and and or and not
0:13
table representing these different types of first or
0:16
logic functions. So how this works is you can think of x one
0:21
and x two as the inputs and as y as the output. So if both the
0:31
inputs are zero, the output is zero. If one of the two is zero,
0:36
then the output is still zero. And you have to have both inputs
0:40
equal to one to have an output of one. That's usually how an
0:43
end function works. For the or function, it's sufficient for
0:49
one of the inputs to be one to output a one. And the not
0:53
function is it's the inverse basic. So if the input is zero,
0:57
then the output is one. And if the input is one, the output is
1:01
zero. So here we are talking about binary values. So the
1:05
possible values are only zeros and ones here, like, like a bit
1:08
function, for example, like representing one bit, one bit
1:12
of information. So here, this relates. So this would be the
1:17
mathematical one way, a mathematical way to implement an
1:21
end function with analogies to this biological neuron. So we
1:25
have these inputs x one and x two, and then the output. So we
1:31
will revisit this in way more detail in the next lecture when
1:35
we talk about the perceptual models. So I mean, not in that
1:39
much more detail, but we will actually implement this also in
1:42
code in a way that it automatically learns weights to
1:45
make classifications here, it's just showing that it's actually
1:49
indeed possible to use this idea of the biological neuron to
1:53
implement such a function. And this would work by having these
1:57
inputs here. And then you integrate these inputs by
2:01
summing over them. So you would have here, sum over these
2:07
inputs. And then there's a threshold. So we can think of
2:12
the threshold as something you have to reach in order to fire
2:16
or not in order to relay a signal or not. So in that way,
2:20
it's basically you can think of it as a piecewise linear
2:23
function. So where it returns one, if the inputs, let's say x
2:29
one plus x two are greater than the threshold, let's say greater
2:33
equal to and zero. Otherwise, this would be our neuron here.
2:41
So there are also some weights. Notice that I set them to one
2:46
here. So then they're actually not doing anything. So usually
2:50
you would compute a weighted sum of the inputs. But we are not
2:55
worrying about it right here right now. So one would
2:59
basically say that the weights have no function here. So we can
3:02
actually ignore them here. So otherwise, instead of x one plus
3:06
x two, it would be the weighted input, it would be w one times
3:10
times x one plus w two times x two. But since the weights were
3:15
one, they are not doing anything. So in this case, we
3:18
can also ignore them. Later, we will actually talk about ways we
3:22
can actually learn these weights like parameterize the model.
3:27
Yeah, and then I don't want to spend too much time on this. But
3:30
if you like, you can then just plug in different values like
3:33
zero and zero, one and zero, zero and one and one one and see
3:38
what the weighted sum is, or the sum x one plus x two, and see
3:42
whether it's bigger or smaller than the threshold. And then you
3:45
can real or will realize that this will be implementing on an
3:52
end function. And similarly, you can implement an R function by
3:56
changing the threshold to point five. And you can also implement
4:00
a not function by for example, changing the threshold to minus
4:04
point four, nine, and having the weight of minus one. So you
4:10
would basically compute it like this. So you would have the
4:15
function as a return of one, if minus x one is greater than t
4:27
greater than equal on zero, if minus x one is smaller than t.
4:32
So this would be the not function. So this is already too
4:36
much detail, maybe, but this would be an example of how the
4:39
mathematical neuron model could represent and or and not
4:42
functions. Moving on. So in the previous slide, I talked about
Classification
4:50
the model, but we there was no way we could determine the
4:53
threshold automatically. So we would have to hand code the
4:55
threshold for specific functions. But now let's say you
4:58
are given a data set, and you want to learn a classifier. So
5:01
you would have to maybe try out a lot of these weights and
5:05
thresholds to find a good way to classify data. So one idea was
5:09
done by Frank Rosenblatt to develop a learning algorithm. If
5:12
I go back one slide, a learning algorithm that can find optimal
5:15
weights and thresholds automatically from the data to
5:18
make a good classification. So if we want to classify data, so
5:21
for example, if you want to classify spam and not spam
5:24
email, you could use, for example, a system that can learn
5:28
from data to find a good decision threshold. So this was
5:31
by Frank Rosenblatt, and only a few Lacey, one decade later,
5:36
approximately one decade after the McCulloch and pits neuron.
5:42
Also, I should mention there are multiple perceptron algorithms.
5:46
However, in practice, usually we say the perceptron algorithm. So
5:49
although there are multiple ones, so there's one popular
5:52
perceptron algorithm, and we will talk about this perceptron
5:55
algorithm in the next lecture in more detail, and also
5:58
implemented in code. So but yeah, here's just a quick
6:03
overview of how this works, and how it looks like. So yeah,
6:07
similar to the previous slide, we have multiple inputs. There
6:11
are also these weights, and they get combined. So this is a
6:16
weighted sum here at this point. So it's a people call it a net
6:20
input function. And then there's an activation function. This is
6:24
basically our threshold that I introduced in the previous
6:27
slide. And then it will produce an output. So zero or one, we
6:32
will again talk about this in way more detail. So it's just a
6:35
quick overview. And here would be Yeah, if you're interested,
6:38
this would be how it actually looked like in practice, because
6:41
back then, um, yeah, computers were quite different. So it's
6:44
actually a physical machine, and people had to plug in wires to
6:50
make it work and rearrange wires and stuff like that. So yeah,
6:53
we've come a long way with computations. Alright, and then
Adaline
6:58
also, after the perceptron, we are still talking about single
7:02
layer neural networks. After the perceptron, there was the so
7:07
called edeline, which stands for adaptive linear neuron, by
7:13
Widrow and Hoff in 1960, it's only three years later. And what
7:18
is different between the perceptron and the edeline. So
7:22
this one is now differentiable neuron model. So that changes a
7:27
little bit how we learn on the weights. So it's a little more
7:31
convenient to learn the weights, because now we can use calculus
7:34
to learn the weights, we will see next lecture, how this
7:37
learning algorithm works. And then in a future lecture, we
7:40
will also talk of course, about gradient descent, like using
7:43
calculus to learn the weights. So here's just our quick last
7:48
overview of this for this video. So this is the perceptron I've
7:52
shown you. And now the edeline is actually very similar. So it
7:55
is shown here at the bottom. And here, the only or the main
8:00
difference is that there is no linear activation function. And
8:05
so in the perceptron, you do a classification, then you get an
8:09
output here. And then based on the error, you compute the error
8:14
by comparing this output to the true label. So you have a true
8:18
label. And you, you compare the two. And based on this, you can
8:23
see whether you make an error or not. If you make an error, you
8:27
go back and update these weights. So for the edeline, the
8:32
difference is, you have this update before you have this
8:36
threshold function before you compute the actual output. And
8:39
I have a question here, it says, does this figure below remind
8:43
you of something you know, from other statistics classes? And by
8:46
that, I mean, if you only take a look, let me use a different
8:51
color, let me use the yellow color here. So if you only look
8:54
at this part here, if you don't look at the threshold function,
8:59
if you only look at this part, does this one? Yeah, remind you
9:03
of something. So maybe that would be a good question for
9:06
Piazza. If you know, something from a statistics class,
9:11
probably from a very introductory statistics class,
9:14
that reminds you of this structure. Yeah, maybe post and
9:17
Piazza, and we can discuss this further. Alright, so lastly, why,
Why Deep Learning
9:24
why do we have deep learning nowadays? Why didn't we stop now
9:27
with perceptrons and edeline? Because apparently, we have no
9:31
classifiers that can be easily parameterized. Well, the problem
9:35
with these is that they can only learn very simple decision
9:39
boundaries. So you can only learn so called binary decision
9:43
boundaries. So a binary decision boundary is a decision boundary
9:48
that splits a data set into two halves. So if we have a
9:51
classification problem, let me sketch this here up here. So if
9:56
we have a classification problem with two features x one, and x
10:00
two, and one class is let's say these circles here. And the
10:05
other class are these plus signs here. And I want to classify
10:10
them. So while we can train a binary classifier, and it might
10:14
learn a decision boundary that looks like this year, and
10:17
everything left will be classified as a plus. And
10:21
everything to the right will be classified as a circle. So this
10:24
is a binary decision boundary. But now if we have an, for
10:28
example, x or problem, so x or is an exclusive or, and it might
10:34
look like this. So here, I have two classes here, I have minus
10:40
minuses and pluses. So there are these minuses and pluses. But
10:44
look at how they are arranged, they are kind of like a range
10:47
like, like an x here, right, you can see that. So a binary
10:51
classifier would not be able to solve this problem, because a
10:54
binary decision boundary, you can draw it maybe like this. But
10:58
then, if we draw it like this, we make a lot of mistakes,
11:01
right, it gets these minuses right to the left, and
11:04
everything to the right, let's say is a plus, but then it gets
11:06
these here wrong. So that's a problem. Another way we can
11:10
draw this decision boundary might be like this, let's say
11:13
like this. But again, we make mistakes here. So there's no way
11:17
if you try it out in practice, if you try different
11:19
combinations, there's no way we can classify these points here
11:23
correctly, using a binary classifier. And there was
11:27
actually a book called perceptrons. I would have brought
11:32
this to class if we had an important person class and pass
11:34
it around. It's actually a very nice book. I have a used copy of
11:38
it. It's from 1969. And it was written by Minsky and Puppert.
11:43
And this was actually very negative. It's a nice book, of
11:47
course, like, the way it's written is nice, but the message
11:50
is like very negative towards perceptrons. It's basically
11:53
saying, perceptrons, and for example, the airline could not
11:57
solve these X or problems. So they are very limited. And they
12:00
are probably not the goal in AI. So we still need to develop
12:06
better methods. So this was really like dismissing perceptrons
12:09
and airlines at not useful, it's not useful in practice, because
12:13
they couldn't solve very useful problems, because they're
12:15
limited to these binary binary decision boundary, and started
12:18
this so called AI winter where people kind of lost interest in
12:22
neural network research. However, here things are
12:26
actually not that bleak, because there are ways we can actually
12:31
develop new networks that can solve the X or problem. And I
12:35
will talk about this in the next video.
Artificial Neurons
12:39
Alright, let's start with the artificial neuron. So the single
12:43
layer neural network, yet all goes back to McCulloch and
12:47
pits, the neuron model they developed around 1943, which is
12:52
the mathematical formulation of a biological neuron that could
12:56
solve and or, and not problems. So these are first order logic
13:02
problems, or functions. And you have maybe heard about them in
13:08
introductory computer science classes, on first order logic,
13:13
or in mathematical classes, so the fundamental and or, and not
13:18
building blocks. So a biological neuron, you don't really have to
13:22
know about that, because deep learning and neural networks
13:26
were inspired by how the human brain works. But yeah, to be
13:29
honest, they work quite differently from each other. So
13:33
you can also think of it as, let's say, a submarine and a
13:37
fish. So humans were inspired how a fish can dive underwater,
13:42
or go underwater. And so they developed on submarines, which
13:45
can do the same thing. However, a submarine works very
13:48
differently from a fish overall. I mean, there are some
13:50
analogies. However, of course, the submarine is very different
13:53
from a fish or think about a bird and an airplane. So both
13:58
can fly, bird flaps its wings to fly airplane doesn't. So but
14:04
there are still some analogies. So airplanes are inspired by
14:08
birds, but they're not necessarily the same. And this
14:11
also applies, of course, to neurons and models of neurons.
14:16
But yeah, the goal of building an airplane is to build
14:20
something useful. And if you make it more like a bird, it
14:24
doesn't necessarily makes it more useful. And the same is
14:27
then also true for neural networks, we can maybe make them
14:29
more similar to a neuron brain, give them some properties that
14:32
human brains have, but it doesn't imply that they would be
14:35
better at solving certain problems, they might, but they
14:38
may not be. And also, to be honest, the real challenge is no
14:42
one really knows exactly how the human brain works. So we can't
14:45
really replicate it yet. But yeah, let me not get distracted.
14:49
And let's get back to the topic here. So just briefly about the
14:52
biological neuron. So the biological neuron looks as
14:58
follows. So this is, of course, a sketch, I actually made this
15:01
in PowerPoint a few years ago, which is why it doesn't look
15:05
very nice. And I can tell you, it's a lot of work to make a
15:08
drawing like that in PowerPoint. But yeah, the takeaway is that
15:13
there are some input signals here that are received by the
15:16
neuron. So you have these ten rights where input signals are
15:20
received. There's a cell nucleus, where some integration
15:25
of the information happens, some processing of the information.
15:28
And then this information is trans, transferred to the so
15:32
called axon terminal. So the signal comes in here, there's
15:37
some computation happening, and then it goes to the axon
15:42
terminal. So actually, it would jump, it's an electrical signal
15:45
here. But this detail doesn't really matter. What's important
15:49
is that this results in an output signal. And in a human
15:55
brain, for example, or in other types of brains of animals, the
16:00
neurons are connected to other neurons. So they are usually
16:03
like, there would be another neuron sitting right here
16:06
receiving these signals as input. So these output signals
16:11
would be the input signals of another neuron, and so forth.
16:15
But then this would be more like a multi layer neural network
16:18
here, we are just thinking about a single neuron. And of course,
16:23
also, there are many types of neurons in our brain. So there's
16:26
not only one type, here, we are just thinking of a very simple
16:30
version, where we have input signals, and one, let's say,
16:34
output signal. So we can think of whether the neuron is
16:38
activated or not, whether it fires or not. And with that
16:41
concept, we can implement a so called and or or not first order
16:46
logic.

##v15:

0:01
Alright, let's now talk about training neural networks with
0:04
multiple layers. So here on the right hand side, I'm showing you
0:08
so called multi layer
0:13
perceptron,
0:16
which is sometimes also called or it's a feet forward
0:21
neural network. And it is also a fully
0:31
connected neural network. So there are two properties here
0:34
describing that the data data flow is like a forward only one
0:40
direction. And then it's also fully connected. That means that
0:43
each unit here is fully connected to another unit. And
0:47
also notice the word perceptron, although this type of network is
0:51
not that closely related to the perceptron, because there's
0:54
another thing going on here, it's not shown in this figure.
0:57
But we have nonlinear activation functions. And what that means,
1:01
we will cover this in way more detail in a future lecture. So
1:05
no need to memorize that here.
1:08
But yeah, so what this architecture allows us to do is
1:12
now to solve the X or problem. So the reasons why this can
1:16
solve the X or problem, even though there's only one output
1:19
node here, is that it has multiple layers, and also that
1:22
it has nonlinear activation functions. So these two aspects
1:26
make it able to solve the X or problem. So here, I have
1:30
generated some toy data, and I applied a real multi layer
1:33
perceptron for this data. And I trained to multi layer
1:37
perceptrons with a slightly different numbers of hidden
1:39
units. And you can see, in both ways, the neural network came
1:44
up with solutions for this X or problem. So on the left hand
1:47
side, it learned solving the X or problem by just having these
1:51
two parallel binary boundaries. Um, I found this very
1:55
interesting, to be honest. So yeah, it looks very organized
1:58
and very efficient. Another way the network could solve the X or
2:02
problem was here was shown here on the right hand side. So yeah,
2:05
just change the number of hidden units a little bit. And you can
2:07
see the solution is quite different. And of course, there
2:10
are infinitely many solutions to this problem using a multi layer
2:15
neural network. So we will again talk about this in way more
2:19
detail later on. But if you're interested also later in this
2:22
course, if you're interested in drawing neural network,
2:26
architecture, figures, for example, for your report or
2:29
proposal, and so forth, here is actually a very nice tool by
2:34
Alex, the nail, I think, actually, I don't know if this
2:39
is the last name, or if it's related to AI or something. So I
2:45
think the first name of this person is Alex, the last name, I
2:48
don't know. But this is a very nice tool that lets you quickly
2:50
draw simple drawings of neural networks. They also have
2:56
drawings for the Linux style and Alex night, Alex net style
2:59
networks, which are convolutional neural networks,
3:02
which will be covered also later in this course. Yeah,
3:07
moving on. So a little bit more about the multi layer neural
3:11
networks. So they have now the solution to our x or problem
3:15
with the hidden layers and the nonlinear activation functions.
3:18
However, there was a new problem when this network architecture
3:21
was proposed. And the problem was that it was hard to train. So
3:25
initially, there was no training algorithm for that. So one
3:29
solution that was proposed at some point was back
3:33
propagation. So it has been proposed several independent
3:36
times. So there's actually an article by Juergen Schmidt
3:39
Huber, who wrote about who invented it first. So there are
3:44
different resources or literature cited here, which
3:47
you may find interesting. So it's a blog post listing all the
3:51
different ways or inventors of back propagation or things
3:54
related to back propagation. The paper that made it really
3:57
popular, though, and that showed that it actually works for
4:00
training, multi layer perceptrons was by Rumelhart and
4:05
Hinton in 1986. So this was an independent formulation. So they
4:10
formulated it independently. So by that, I mean, they were not
4:14
aware of the previous literature. So and this was
4:18
also the paper then, that made made this really popular where
4:22
because they really showed that this actually works in practice.
4:26
And also, later, it was shown that neural nets, such as the
4:30
multi layer perceptron here with one hidden layer, if it's
4:32
arbitrarily large, is able to approximate arbitrary function.
4:36
So it can approximate any arbitrary function with certain
4:40
precision if the hidden layer has a relatively very large
4:46
size. But of course, that the ability to approximate arbitrary
4:52
function doesn't mean it's easy to do that. So it's still hard
4:55
to train a network in certain cases. So there are other
4:58
architectures, we will learn about them later, which are
5:01
suited for or better suited for certain types of problems. But
5:04
again, this was like a big breakthrough, because now there
5:07
is this algorithm for training multi layer neural networks very
5:12
efficiently. And yeah, spoiler. So this algorithm is also still
5:17
used in common architectures. It's still our most efficient and
5:22
most popular algorithm for training neural networks. So it
5:26
has stood the test of time so far. Yeah, and here's a little
5:31
fun fact about the backpropagation algorithm by
5:34
Rumelhart and Hinton. So I read this in an interview book,
5:38
where Joe Fenton talked about how they came up with it. So he
5:42
said in late 1985, I actually had a deal with Dave Rumelhart
5:46
that I would write a short paper about backpropagation, which was
5:49
his idea. And he would write a short paper about autoencoders,
5:53
which was my idea. It was always better to have someone who
5:56
didn't come up with the idea, write the paper, because he
5:59
could say more clearly what was important. So I wrote a short
6:03
paper about backpropagation, which was the nature paper that
6:06
came out in 1986. But Dave still hasn't written the short paper
6:09
about autoencoders. I'm still waiting. So this was from a book,
6:14
The Talking Nets. It's a little bit old, but it's still
6:17
interesting. If you're interested, it's like an
6:19
interview book, like outlining the oral history of neural
6:23
networks, via interviews with people who worked on neural
6:27
networks in the last century. And then there was also the other
6:32
interesting book, Art Architects of Intelligence. It's more
6:35
recent from, I think it's from 2018, which I read last year. It
6:40
was also very entertaining. It's like a lot of interviews also
6:43
with Joe Fenton and many other people who are famous deep
6:47
learning researchers. So it was another enjoyable read. So if
6:50
you're interested for pleasure reading these are, this is
6:53
actually a particular fun book, because also, they ask everyone
6:57
to give a prediction when AI can be invented. And there's no
7:00
clear consensus. So some people say the artificial general
7:04
intelligence that I talked about last lecture will never be
7:06
invented something it's like 100 years old, and so forth. So it
7:10
was actually an interesting read. I kind of like that. Okay.
7:15
Yeah, backpropagation is not the only algorithm for
7:18
parameterizing neural networks, such as the multilayer
7:22
perceptron. So there are other types of algorithms. So here,
7:25
this is from a paper by Lily crap, Santoro, Maris, Ackerman,
7:30
and Hinton, where they discussed backpropagation and the brain,
7:34
basically discussing how similar learning algorithm in a human
7:39
brain could be to backpropagation. Of course, we
7:43
don't know the answer yet. We know that the brain is probably
7:47
not using the backpropagation that we are using in for
7:51
training neural networks. However, it may use something
7:53
that is somewhat similar to backpropagation. But yeah, I
7:57
want to go into a discussion about neuroscience and how
8:00
similar it is to how the human brain works. But yeah, what I
8:04
found interesting is here, this brief overview of the different
8:07
types of learning algorithms that we could use for training
8:12
and neural network. So for example, there would be heavy
8:14
and learning. So say you are interested in this, in this note
8:20
here, updating this connection here, heavy and learning does
8:23
not involve feedback. So with feedback here is meant that if
8:27
you do a prediction, and then you look at the error, you
8:29
usually update the network such that the error is minimized. But
8:34
if there's no feedback, um, yeah, it's not really minimizing
8:37
the error, what happens in heavy learning is that the connection
8:40
is strengthened, the more often it is used for making a
8:43
prediction. So it's not necessarily on improving the
8:47
error, you can think of it, maybe if you are playing, let's
8:51
say, if you're playing tennis, and you make a wrong move, but
8:54
no one teaches you that it is wrong, and you make the move
8:58
more often and more often and more often. So if you
9:00
repeatedly, repeatedly make the wrong move in tennis, and no
9:04
one teaches you that this is wrong, it will be harder to
9:07
unlearn it later. And it doesn't mean you become better at
9:09
tennis, if you do a wrong move that is not hitting the ball
9:13
over the over the net, for example. So another type of
9:17
learning is perturbation learning. So you make a
9:20
perturbation, like you put up a weight and see if it's better or
9:23
not, if it's better, then you keep the weight. Otherwise, you
9:26
discard it. It's also not very efficient. This is actually very
9:30
slow. Yeah, backpropagation is actually very efficient. And
9:34
it's also very good for minimizing the error. So there's
9:39
another type of learning algorithm where it's similar to
9:43
backpropagation. But in instead of doing backpropagation, back
9:46
propagating the errors, it's involving a second network. But
9:51
according to the paper, also, they admit that backpropagation
9:53
is sufficient, the most efficient algorithm for
9:56
minimizing the error, although it may not be what the human
9:59
brain uses. But in practice, when we develop computers and
10:04
predictive algorithms, we care about, yeah, low error, good
10:08
predictions, and so forth. So that's why we are still using
10:11
backpropagation, because we haven't found anything yet that
10:15
works better than backpropagation. But this was
10:17
just a short overview. In this course, of course, when we talk
10:21
about new networks, we will be focused on backpropagation. He
10:25
was a nice figure I just saw this weekend from a paper
10:29
discussing relational inductive biases and other types of
10:33
biases. So I like this figure because it kind of outlines the
10:38
different types of neural network architectures that are
10:41
commonly used. So we have our multilayer neural network or
10:46
multilayer
10:48
perceptron that I briefly talked about in this video. And here we
10:52
assume that the data columns are independent. So this would be a
10:57
network that you can use with a tabular data set that we
11:00
discussed in the previous week. So for example, when you think
11:05
back of your iris data set, where you have iris flowers, up
11:09
to 150 iris flowers, and then you have the sepal length, sepal
11:13
width, petal length, and petal width, and then a class table.
11:18
So this would be something as an input to the multilayer
11:22
perceptron. And it doesn't really matter in what order
11:26
these columns are. I mean, once you train the network, of
11:29
course, then the order matters, because it was trained on this
11:32
table. But before training, it doesn't matter whether, let's
11:36
say on the sepal length is here, it could be you can have
11:39
actually the petal width here, and the sepal length here,
11:44
there's, there's no difference, you could learn the same
11:46
network if the columns are in a different order. So there is no
11:51
assumption about dependence of these features. In contrast, so
11:56
called convolutional networks, I will introduce them in the next
11:59
video. convolutional neural, let me abbreviate it nets, they
12:05
have one assumption that is locality, there's another
12:08
assumption, equivalence, feature equivalence, but focusing on the
12:12
locality. Now, it's basically assuming there's some structure
12:15
that's usually used for image analysis, because you can think
12:18
of it as neighboring pixels are being related to each other, for
12:22
example. So if you if you have an image of a person, so let's
12:27
say two eyes, nose interface. So these pixels are clearly related
12:32
because they all include the eye, right? So shuffling these
12:36
pixels, putting one pixel up here, for example, doesn't
12:39
really make sense. So in that way, there's some locality
12:42
assumption. So here, in terms of relational inductive basis, you
12:45
can think of the assumption you make of the data when when you
12:50
use a certain architecture, or there is something called
12:53
a recurrent neural network. And this one assumes, for example, if
13:01
these are actually a little bit maybe unfortunate, not sure why
13:05
these arrows are pointing down. Maybe we will clear if they
13:08
would be pointing up as the inputs. In any case, so this
13:13
would be our assumption where you assume the inputs are
13:17
sequentially related. So there's an order relationship, a
13:21
relationship, a sequential relationship. So recurrent neural
13:25
networks are thus useful for text where you have words in a
13:28
certain order, it wouldn't make sense to shuffle words in a
13:31
sentence, because then a sentence wouldn't make sense
13:33
anymore. In the same way, it doesn't make sense to shuffle
13:36
pixel in an image, because then you lose the relationship
13:40
between the images, multi layer perceptron doesn't have such an
13:44
assumption. So in that way, it is very powerful, you can learn
13:50
a lot of things we I mean, I just briefly mentioned that it
13:52
can be regarded as a universal function approximator. However,
13:56
of course, it's also more challenging if you don't have
14:00
any prior assumptions. So in that way, leveraging these
14:04
prior assumptions, that's such as locality or sequentiality can
14:09
actually make the learning easier. And that is also one of
14:12
the key ideas behind deep learning. I will in the next
14:15
video talk about deep learning, how deep learning evolved from
14:19
simple multi layer networks. Okay, lastly, there's the last
14:24
architecture here, it's called specified. But of course, this
14:27
is not a particular neural network architecture. This is
14:30
here referring to the fact that someone hand codes things how
14:34
things are related. And this is something that I don't think is
14:39
easily be implemented. So you would have to hand code this,
14:42
which is very tedious. So something like that is currently
14:45
not used in practice in deep learning. So usually we use
14:48
recurrent neural networks, and commercial networks for images
14:52
and text. And for tabular data, we can use multi layer
14:57
perceptrons. Okay, so the next lecture, I will briefly talk
15:00
about deep learning the origin of the of the name and some
15:05
developments on how deep learning evolved from multi
15:09
layer networks.

##v16:

0:01
Yeah, now moving on from the multilayer networks, like the
0:04
multilayer perceptrons to deep learning. So we're going to talk
0:07
about the origins of deep learning in this video. So
0:11
coincidentally, I just submitted a paper today with collaborators
0:14
where we used multilayer perceptrons. And we were
0:18
debating whether we should call it deep learning or whether we
0:21
should avoid the word. The reason is deep learning is a
0:25
relatively new word like that was invented, I would say like
0:28
1015 years ago. But multilayer perceptrons have been around for
0:33
at least like 3040 years, right, like I talked about in the
0:36
previous video. So is this really deep learning? So yeah,
0:40
that is kind of debatable. So technically, when the term deep
0:45
learning first occurred, when it was first used, what people
0:49
refer to was the representation learning with advanced
0:53
architectures with many layers. So having multiple layers is not
0:58
really what makes the difference between a multilayer perceptron
1:02
and deep learning. It's more like the representation learning
1:05
capabilities. That is usually, yeah, what deep learning is all
1:11
about. So nowadays, though, if you read papers, newer papers
1:15
where people use multilayer perceptrons, they call them
1:19
deep learning, too. So I think nowadays, it's okay to also call
1:22
it deep learning to make it maybe less confusing for people
1:24
because everything nowadays that is a neural network is also
1:27
automatically deep learning. But let's dive a little bit more into
1:31
the representation learning aspects that I just mentioned. So
Convolutional Neural Networks
1:35
that goes back to, yeah, also the approximately 1990s. So
1:40
also, in that way, it's a thing that was discovered or invented
1:45
before deep learning was a thing, the word deep learning,
1:47
and it is convolutional neural networks. So this is kind of on
1:52
top of, yeah, the multilayer perceptrons, it's like, you can
1:55
think of it as a specialized version where you have locality.
1:59
So here, it's about making training more efficient, and
2:04
also extracting local features, which then better capture feature
2:08
dependency. So recall, in multilayer perceptrons, we had
2:13
like the feature independence, so it would work with tabular
2:16
data. Now with this convolutional network, we can
2:19
leverage some prior knowledge of this relational inductive
2:25
bias. So it's specific specifically for image
2:28
recognition for image data. So how multilayer perceptron works
2:34
is you have these independent features, and the convolution
2:37
network captures dependency. On the right hand side, I'm showing
2:40
you this original linnet architecture from Yanli Kuhn and
2:46
coworkers that was applied to hand written zip code
2:50
recognition. And we will have a dedicated lecture just to
2:55
convolutional networks later. But here just a brief overview is
2:59
that it consists of two parts. So there's one part that is the
3:04
convolutional part. So here you have convolution layers, they
3:12
have a trick or concept called weight sharing. And there's also
3:17
pooling involved. And that makes the training more efficient, we
3:20
will discuss this in more detail later. But you can think of it
3:23
roughly as the feature learning layers where these layers are
3:32
able to extract abstract features from the data. And
3:36
these features are then passed on to fully connected set of
3:44
layers. So these are fully connected layers. And these are
3:48
essentially a multilayer perceptron. And you can think of
3:56
it as a classifier here. So if you think of it as a task, let
4:02
me also use the red here. So here we have this part, the
4:07
lower part here for feature learning. This upper part is
4:10
for classifying the features that have been extracted by these
4:16
earlier layers. So this is making the hand crafting of the
4:21
features obsolete. Now the network learns the features and
4:25
it learns it in a way such that it is optimal for the classifier
4:29
because everything here is connected. So it's learning
4:32
together, which is one advantage that makes that makes new
4:36
networks for image data specifically very efficient. So
4:41
this is, again, this is from the 1990s. Back then, the term deep
4:44
learning didn't exist. But I would say nowadays, convolutional
4:47
neural networks are really like the most popular form of deep
4:51
learning, because there are, I mean, many, many advances that
4:55
followed this earlier architectures, and made deep
4:59
learning what it is nowadays, of course, there's also a separate
5:02
branch of recurrent neural networks that is also very
5:05
popular in deep learning. So recurrent neural networks also
Recurrent Neural Networks
5:08
are, I would say an advanced version of the multi layer
5:10
perceptron. So here, what's new is that there is a recurrence.
5:15
So and so you can think of this as a multi layer perceptron, but
5:19
a multi layer perceptron is a feed forward network. Now you
5:23
have this recurrence. So you're revisiting earlier things. So
5:28
again, this will be covered in way more detail in a dedicated
5:31
lecture later on in this course. But the key idea is basically
5:34
that we have a modified version of backpropagation, which is
5:38
called backpropagation through time, because there's a time
5:41
component component. And this is especially useful for sequence
5:47
data, where there's a sequential dependency in the data among
5:51
across the features. So but the problem with that is now when we
5:57
train neural networks with many layers, especially for recurrence
6:00
over long sequence, there's this problem of vanishing and
6:03
exploding gradients. So that is like a big challenge. However,
6:08
it was also I mean, there are many potential solutions to
6:11
that. One of them that is one of the ones that is still commonly
6:15
used as LSTMs that stands for long, shorter memory. So also
6:19
this one was like overcome. And this is also one popular form of
6:23
deep learning, like using these neural networks. But again, this
6:26
is something that has been around for a long time, actually,
6:29
I don't know exactly when recurrent neural networks were
6:31
invented. First, it was like also in the 1980s, sometime
6:35
after backpropagation was invented, because yeah, this is
6:38
an advancement of backpropagation. It was someone
6:41
sometime in the 1980s. Yeah, just to summarize what
About the term "Deep Learning"
6:46
originally the term deep learning meant, he has a nice
6:50
section or sentence from the deep learning review by Lacoon,
6:55
Benjo, and Hinton. So Hinton was the person working on the back
6:59
propagation algorithm, Lacoon was the one who came up with the
7:04
convolution neural network. And Benjo is doing a lot of work
7:07
also across deep learning, mainly also focusing on the
7:10
recurrent neural networks, but also basically everything. So in
7:14
this review, the sentence goes like, like this representation
7:19
learning is a set of methods that allows machine to be fed
7:23
with raw data, and to automatically discover the
7:25
representations needed for detection or classification. Deep
7:29
learning methods are representation learning methods
7:32
with multiple levels of representation can also say
7:35
abstraction. Yeah, and so here, the focus is really like the
7:41
implicit feature extraction that deep learning does. That is
7:45
something that traditional machine learning is not capable
7:47
of, like we talked about last week, where we have the
7:50
handcrafted features versus the automatic feature extraction. So
7:54
here, the focus is really on on the automatic part. But
7:58
nowadays, really, deep learning means the same as using neural
8:04
networks. So deep learning nowadays, it's really the same
8:09
as using neural networks, maybe we should be a little bit more
8:17
specific and say, multi layer. Yeah, but going from these
Neural Networks and Deep Learning -- A Timeline
8:25
architectures, I showed you that were invented in the 90s, towards
8:29
the modern era of deep learning research, there was unfortunately
8:32
in between another AI winter in the late 1990s and early 2000s.
8:37
And I think that was probably due to the popularity of support
8:41
vector machines and random forests. Because back then,
8:43
yeah, neural networks were capable, but they were very
8:47
expensive to train. So you needed like, enormous computer
8:50
hardware to train them efficiently. And even then, you
8:53
had to wait a long time to train them. So they were not easy to
8:55
train compared to, let's say, support vector machines and
8:58
random forests. Of course, support vector machines come
9:01
with their own set of problems like the really inefficiency of
9:04
RBF kernel machines on high dimensional data. Also, random
9:08
forests require a lot of trees. So but still compared to deep
9:13
neural networks, these were easier to train and worked quite
9:17
well. So yeah, but then at some point, people figured out how to
9:22
use GPUs to make the training of neural networks more efficient.
9:26
And that is really what helped me I'm making neural networks
9:29
really popular and feasible. So when I looked at literature,
9:34
what I could find, it goes already back to 2004. So on GPU
9:37
implementations of neural networks have been around for
9:40
quite some time. But really, when it became popular was in
9:43
2012, where Kroshevsky, suits giver and Hinton worked on
9:48
image net classification. So very common benchmark data set
9:52
like millions of images, where they used deep neural networks
9:56
trained on GPUs to outperform traditional computer vision
9:59
approaches. So a few more words about that in the next couple of
10:03
nights. So here's a table from my 2017 book, I actually updated
10:11
this last year. So I don't know why I have the old one here,
10:15
maybe I should swap it. But again, so the bottom line here
10:19
is more that the difference between traditional CPU, for
10:25
example, here, an Intel CPU, and an Nvidia graphics card, or in
10:30
general, a graphics card, maybe think of it as the difference
10:32
between a CPU and GPU. And GPUs are particularly good at linear
10:38
algebra operations like vector and matrix operations. So even
10:42
though GPUs have a smaller clock frequency, one advantage is
10:46
really like the parallel course, each column is slower than a
10:50
CPU core, of course, but you have more of them. And that
10:53
helps you parallelizing computation. So parallel
10:58
computing of dot products and matrix multiplications is really
11:06
what what makes GPUs very useful for deep learning. So you really
11:10
get a higher way higher memory bandwidth also. So the GPU
11:14
memory, GPUs come with their own memory, which is closer to
11:18
where things are computed. So it's also faster. In that way, if
11:21
you have the data on the GPU, however, you have to get the
11:24
data to the GPU, which is sometimes a little bit slower.
11:26
So there are some tricks also to make this efficient in terms of
11:31
data loading. But this is something we will talk about
11:34
when we actually use pytorch for deep learning, I will also show
11:38
you how you can use GPUs. For this class, you won't need a
11:41
GPU, I will later on talk about some free online resources where
11:46
you can get one GPU for free, which can help with some
11:50
homeworks and also the project. But yeah, you don't need to buy
11:52
your own GPU or something like that. So yeah, and moving on.
11:56
Yeah, so really, the you can see the number of floating point
12:00
calculation of float is, you can think of it as a decimal number
12:04
in the computer, you can see it has a way higher number of
12:07
floating point calculations. And it's also cheaper, at least
12:10
compared to this high end Intel CPU. But of course, there are
12:15
also things with GPUs that make certain things inconvenient
12:20
because they have their own memory, which is not very large.
12:23
I mean, there are nowadays more expensive cards that have larger
12:26
memory. But usually in deep learning, GPU memory is a
12:29
bottleneck, at least for me. But again, that is a topic for
12:32
another day. Yes. So here's another fun quote from the
When did Deep Learning Become Really Popular?
12:35
architects of intelligence, like an interview with Joe Fintan. So
12:40
it is about when
12:44
Yeah, so regarding the question, when did deep learning become
12:47
when did deep learning become really popular. So here again,
12:51
as a fun quote from one excerpt from interview from the book,
12:55
architects of intelligence. And yeah, this refers to the 2012
12:59
image net competition. So there was a famous computer vision
13:03
competition on a data set called
13:07
image net. And it was essentially about a benchmark and
13:12
people submitted computer vision methods and papers. And it was
13:17
about having the best system each year, who could do the best
13:21
classification on this image data set. It's like a image
13:24
data set consisting of up to 14 million images of they used only
13:28
a subset of at that time, as far as I remember. But yeah, it was
13:32
millions of images. And back then, really, the conferences
13:36
were dominated by traditional computer vision approaches like
13:40
manual feature engineering, and so forth. No deep learning,
13:43
really. And here in this interview, and I want to read
13:47
everything here, maybe you can pause the video and read through
13:50
it if you are curious. But it is essentially about that deep
13:53
learning methods were usually rejected. So here's like
13:57
something I underlined, the referees thought that it was the
14:00
ray wave, sorry, the referees thought it was the wrong way to
14:03
do things, referring to the neural network architectures
14:06
here. So people really didn't like deep neural networks back
14:10
then. I mean, people who were using traditional computer
14:13
vision systems, however, in the network that was submitted that
14:18
year in 2012, the Alex net, which was by Alex Kroshevsky,
14:23
so it's cable and Joff Hinton was really outperforming
14:27
traditional computer vision methods by a large margin. So
14:30
they achieved a 15.4% error in 2012 on top five classification,
14:36
I will in the next slide explain what top five accuracy or error
14:40
means. So forget about top five for now. So they achieved a
14:44
15.4% classification error. And the second best method only
14:49
achieved 26.2% error. So their method was about twice as good
14:55
as any traditional computer vision system. And by the way,
14:58
as a side note, nowadays, you can even get down to 3% error on
15:01
image net. So even like since 2012, things improved quite a
15:06
lot. But yeah, so just briefly here, the last thing, so people
15:12
were really surprised about how well deep learning worked. And
15:16
then also, like he says, within two years, they all switched. So
15:19
for things like object classification, nobody would
15:22
dream of trying to do it without using a new network now. So this
15:26
was really like 2012 was really like the breakthrough moment for
15:30
deep learning, because it performed really well on image
15:33
classification. Yeah, and he has also just a quick overview of
Evolution of Benchmark Datasets for Computer Vision
15:38
the benchmark data sets. Nowadays, there are other even
15:41
bigger data sets, but these are still common data sets when you
15:44
develop convolutional networks or object classification
15:48
methods. So there's the traditional MNIST data set from
15:52
1998. 60,000 examples, 10 classes, and very low resolution
15:57
images. So these are the handwritten digits. So this is
16:00
still a great data set for debugging your network. It's
16:04
like when you want to try a network, get the code written
16:08
and see whether it works, because it's really fast to
16:11
train a network on that. In practice, if you write a
16:13
conference paper, testing your method on MNIST may not be
16:17
enough anymore. But yeah, it's still a good way to start more,
16:21
I would say advanced data set is cipher 10 and cipher 100. So
16:26
there are 60,000 examples of either 10 classes, which is for
16:30
cipher 10 or 100 classes in cipher 100. Again, very low
16:34
resolution 32 by 32. Now that we have color images, so we have
16:39
three color channels. And yeah, we have different objects here
16:42
to classify this usually only one object in each image. A more
16:47
challenging data set is the image net data set, which
16:50
consists of 14 million images. So they have full resolution.
16:55
And what is a little bit more challenging about that, too, is
16:58
that there can be multiple objects in an image I talked
17:02
about in the stuff in the news section where people were
17:06
relabeling image net. But yeah, so what can happen is that there
17:10
could be multiple objects sometimes. So it can be kind of
17:14
ambiguous. So usually what people do is they measure the
17:17
top five accuracy or error. So for example, when you have a
17:25
prediction, you check whether it's so whether your top five
17:31
labels are matching with the image label because the network
17:34
is trained to return a probability or confidence score
17:39
for each possible class. And then you look at the top five
17:43
most confident labels. And you look whether one of the five
17:47
labels matches with the label in the image. For example, a it's
17:51
a bit small, I can't really read this here. Um, yeah, let me see.
17:58
But let me pick an example. So here, for example, we have
18:02
actually also two things we have a cherry and a dog. So it's
18:06
also you can see this is like a challenging example where your
18:09
network may predict a dog. But since the data point here is
18:13
labeled with cherry, it would actually count as an error,
18:16
which is kind of unfortunate. So you would look whether your
18:20
prediction is kind of within a top five. Or here in this case,
18:25
your algorithm may predict car or grill, like the grill of a
18:29
car, both would be correct, right. So in that way, you look
18:32
is whether a grill is under your top five, for example. So in
18:36
that way, it's a little bit harder to evaluate on image net
18:40
compared to cipher 10. I think in cipher 10, it's a little bit
18:43
more obvious, not, not more than more obvious. But here you have
18:47
classes where it's at least a little bit less ambiguous.
18:52
Alright, but yeah, moving on, I don't want to make this brief
18:55
overview lecture like too long, because we will dive into these
18:59
little concepts in way more detail later throughout this
19:02
course. So like, like the last thing here, of course, there
19:05
have been many advances since 2012. So okay, this is 2010.
19:10
But for example, advances that are making deep neural networks
19:14
work way better. So common ones are popular ones are relu units,
19:19
rectified linear units, which are activation functions, very
19:23
simple, but very effective batch normalization, dropout,
19:28
generative adversarial networks. And these are all covered in
19:30
this course, and many more. So there have been a lot of advances
19:34
also in the last decade. And these are already like six, seven
19:37
years old. And so there are way more of these and they are all
19:43
contributing together to make deep learning work better. So in
19:48
the next video, I want to briefly just very briefly talk
19:51
a little bit about hardware and software landscape, what has
19:53
changed in the few last few years, and then briefly going
19:58
over some current research trends, and then really
20:01
wrapping up these series of videos here for lecture two, and
20:05
then that we can go into our more detailed lesson on
20:10
perceptrons.

##v17:

0:02
Yeah, as promised, I will keep this video short, I want to
0:04
briefly just outline a little bit about the deep learning
0:07
hardware and software landscape. So yeah, regarding
0:12
hardware for deep learning, what has happened in this area, there's
0:15
a lot of research going on in this area, but essentially, most
0:19
of it is still, or most of deep learning is still done using
0:23
GPUs. So Nvidia is advancing the GPUs every year, there's a new
0:28
model every year, actually, a set of models. So most people
0:31
still use GPUs for deep learning. However, especially if
0:35
you work at Google, there are also no cloud TPUs. TPU stands
0:39
for tensor processing unit, it's kind of like a specialized
0:43
version of GPUs that are better at certain tasks. I think I'm
0:48
not an expert in this. I actually never use TPUs because
0:51
I have my own computers and TPUs, I think restricted to
0:55
Google Cloud servers, although as a user, you can rent those.
1:00
But I think each TPU, it's technically cheaper than a GPU,
1:04
but not as powerful, the power comes from the fact that you can
1:08
combine a lot of them together. Anyways, ARM is also working on
1:12
machine learning processors. Also, the new MacBook, I think
1:16
has an ARM processor in it, which is kind of very
1:19
competitive compared to GPUs, but it's more for prediction
1:24
compared to training. So right now, still GPUs are the status
1:28
quo, most people are using GPUs. But again, other companies are
1:32
also developing custom chips, focused on deep learning, just
1:36
to make deep learning more efficient. Because if you think
1:39
about it, GPUs are really like, inspired or come from the gaming
1:43
industry. So they were not developed with deep learning
1:47
originally in mind. However, they are very good at deep
1:49
learning. And nowadays, Nvidia also develops chips that are
1:53
especially only for deep learning, not for gaming. Yeah,
1:57
and also, there's a new company called graph core, I just saw
2:00
that in a recent article, there's also no
2:04
IPU, which is an intelligence processing unit, which is
2:07
especially useful for graph neural networks. So you have
2:11
CPUs, which are very good at computing, simple computation
2:15
with scalar values, like single values, GPUs are very good at
2:18
working with vectors. And these IPUs are very good at working
2:22
with graphs. It's also a new thing recently. So regarding the
2:27
software landscape, I don't want to talk about it too much. But I
2:32
thought it might be interested. Interesting, because you may
2:35
also as a student learning now, pytorch wonder what the other
2:40
libraries are, and for example, how it relates to pytorch. So
2:45
here's a nice summary from the deep learning with pytorch book
2:48
about the history. So yeah, I remember back then I was using
2:51
Theano that was like before 2015. So in the first edition of
2:55
my Python machine learning book, I still used Theano. And then
2:58
approximately in 2015, TensorFlow came out by Google.
3:02
And yeah, also, lots of things have happened since then. So
3:06
back then, lasagna and Keras were high level wrappers around
3:09
Theano. So high level wrappers means making things more
3:13
convenient, because both TensorFlow and Theano were very,
3:19
I would say low level languages, they were not very easy to
3:21
use. And like, you could do a lot of things, they were very
3:24
powerful, but you needed to write a lot of code. So they
3:26
provided lasagna and Keras, they provided more easy access. But
3:32
then you also Keras extended its capabilities and also was made
3:38
compatible with TensorFlow and CNTK. CNTK was a deep learning
3:42
library by Microsoft, I'm not sure if it's still around, I
3:45
think it also stopped the development. Then there were
3:48
other special purpose libraries like cafe, chainer, dinette,
3:52
dinette, I think was a dynamic graphs, chainer was also dynamic
3:55
graphs, cafe was especially good for deployment, like mobile
3:59
devices, and things like that. I think it was based on C++, MX
4:04
net, and so forth. So there were many, many other libraries.
4:09
Yeah, but so what happened then in the next couple of years, a
4:12
lot of people were switching to TensorFlow. So Theano stopped
4:15
actually the development. So Theano was a university based
4:20
library on TensorFlow extended. So they consumed Keras. So
4:26
Keras became a part of TensorFlow, I think the Keras
4:28
developer started working for Google, then they hired him and
4:32
they were more tightly integrating tens of Keras and
4:36
TensorFlow. So then in TensorFlow version two, Keras
4:42
became the default API for TensorFlow. And they also added
4:46
eager mode, which is similar to pytorch. Yeah, dynamic graph. So
4:52
pytorch got the dynamic graph idea, kind of like from a
4:56
chainer, that's another library here. And then TensorFlow also
5:01
added it later on because it was really popular with the users of
5:04
pytorch. And then in TensorFlow two, nowadays, there's also an
5:08
eager mode. I heard some people or many people at Google don't
5:13
really like working with TensorFlow anymore, because
5:15
it's a little bit clunky. So there's also a new library
5:17
called Jax, which was developed at Google. So that's
5:20
independently developed from TensorFlow. And it's kind of
5:24
like NumPy that can be run on the GPU, also has autograd and
5:29
JIT capabilities. It's a relatively new library, it looks
5:33
interesting. And I think you can do cool things with it. But I
5:36
think it's, it's not where pytorch is right now with all
5:40
the features for deep learning. It's more like a lower level
5:43
library. There are other libraries on top of it. I
5:45
forgot the name, I think it's called flex, which is like a
5:49
wrapper around Jax more for deep learning. But again, on pytorch
5:53
is really, I think nowadays, the most mature library that is also
5:58
nice and easy to use. So most researchers like we saw last
6:02
week, really use type pytorch, because it's easy to use. And I
6:04
really recommend that as a beginner, especially, but also,
6:08
it's just like something everyone uses nowadays. So there's
6:11
nothing wrong with that. So pytorch, the history of pytorch
6:14
is that they compute consumed cafe to cafe to us again, an
6:19
independent project focused on mobile development and server
6:23
deployment, because pytorch was more like a research library.
6:26
Now it's both so it's good for production on mobile devices and
6:30
stuff, but also still for research. It was made way more
6:34
efficient over the years, got on an X support, which is standard
6:39
for exporting neural networks into a common format. So you can
6:43
actually export pytorch models and import them in other
6:46
libraries, other deep learning libraries and stuff like that.
6:49
And they actually added also graph mode. So in that way, pytorch
6:54
became more similar to TensorFlow by adding this graph
6:57
mode and TensorFlow became more similar to pytorch by adding the
6:59
IGA mode. So they are both very, very similar nowadays. Anyways,
7:04
that's just a short history of how software developed over the
7:09
years. In the next last video of lecture two, I want to briefly
7:13
highlight some of the current research areas and trends. And
7:16
then in the next lecture, we will get to perceptrons.

##v18:

0:00
Yeah, I want to end this brief history on deep learning with a
0:03
short video on the current research trends, things that
0:07
became very popular in the last couple of years. So one thing
0:11
that became very popular in the last couple of years was self
0:14
supervised learning. So last lecture, I explained how
0:17
self supervised learning works in a nutshell. So essentially,
0:21
it's about leveraging unlabeled data where you create some
0:25
artificial labels that you can then use for supervised
0:28
learning. But this is really for data sets where you don't have
0:31
labels for your target tasks. So you would come up with tasks
0:34
like, yes, separating an image into individual parts, and then
0:38
predicting the neighboring parts of an image. So if you have the
0:42
face of the cat, and then an ear here, and you show the network
0:46
only the face, the network should predict the prediction
0:50
of the year, whether it's here, the upper left corner, upper
0:52
right corner, and so forth. And by that, you teach the network
0:55
to understand better the object structure of the cat, what a cat
1:01
looks like. Another thing I saw recently, or last year, a lot
1:07
was contrastive learning. So this is a form of self
1:10
supervised learning where you generate two versions of an
1:14
image. So let's say you have an image of a house. That's maybe
1:19
not a nice house. But you know what I mean? So it's a house
1:22
like this. So you feed it to the network here. And then let's say
1:26
you have the same house that is maybe squeezed, or let's say,
1:30
rotate it upside down, this house upside down, and you feed
1:34
it to this image, to this network. So it's the same
1:37
network, but you feed the image one time in the original
1:41
position and one in some augmented version. And then the
1:44
network has to predict whether it's still the same object or
1:48
not. And so that you train the network to recognize that this
1:52
upside down house is indeed the same object. But then if you
1:56
let's say give it something different, let's say you give it
2:01
a cat image here or something like that, you give the cat
2:06
image to the network, then it should predict that this is
2:09
indeed different from the house. So you train the network to also
2:12
better recognize objects. But here notice you don't have class
2:17
labels or something, you just create the labels yourself by
2:22
augmenting this. So if you augment this by rotating it,
2:24
you know, it's still
2:27
the same house. So in that way, you created this label for free
2:31
without having a human to label this data, because you can do
2:34
this all algorithmically. Of course, this is not the target
2:38
task, you're probably interested in something else. But this is
2:40
usually useful for pre training a network before you can find
2:44
unit to your target data set, it usually helps you're making a
2:47
network better. But this is something that is beyond the
2:50
scope of this course, it's more like an advanced topic, or
2:54
something that is more recent, we won't be using it in this
2:57
course, it's like an optional topic. But if you're interested,
3:00
there was a very beginner friendly article by Jeremy
3:05
Howard, which you can find here, where you can learn a bit more
3:08
about self supposed learning, you can of course experiment
3:10
with it in your class project, if you like. Another recent
Graph neural networks
3:15
research trend is the focus on graph neural networks for graph
3:18
structured data. So traditionally, deploying was
3:22
focused on text data and image data. And nowadays, also people
3:27
work with graph neural networks, if you have graph structured
3:31
data, for example, personally, I work with molecules also, like
3:36
structures of small molecules. And you can also think of them
3:39
as graphs where you have the atoms connected by the covalent
3:44
bonds, you can think of it as a graph neural network. And yeah,
3:48
but I, this is a big topic. And also, this would be a little bit
3:52
out of the scope of this course. But I found a nice introduction
3:55
to graph neural networks here. If you're interested, there are
3:59
so many papers, I don't want to pick a particular one. But I
4:01
think this is an interesting, beginner friendly introduction
4:05
to the topic. So it's all kind of related to message passing
4:09
also. So that would be another interesting thing. Also, a
Large scale language models
4:13
recent trend is the work on large scale language models. So
4:19
it started like in 2018, where people trained models with 94
4:24
million parameters. And then they scaled up, you probably
4:27
heard about GPT two was I think, in 2019. Now there's GPT three
4:32
with 175 billion parameters. So language models become bigger
4:37
and bigger and bigger. Of course, there are also some
4:39
research approaches that focus on keeping things small, like
4:44
distill bird, it's like a small version of bird. So in that way,
4:48
people also make smaller versions of existing models. But
4:54
the trend is somehow going towards these bigger models. Of
4:57
course, this is something that is really out of reach for most
5:00
academic researchers, this is something you would do at a big
5:03
company. I think I forgot the exact numbers. But I think this
5:07
model just training it back then cost like $500,000 or some
5:11
crazy amount. So it's something you can only do if you if you
5:16
work in a very big company. So anyway, so he has also
5:22
interesting or nice blog post summarizing the research
5:25
highlights of 2020, focusing mostly on the natural language
5:29
processing. This is where I also found this image, which I think
5:31
is based on some other website. But this is also if you're
5:36
interested in these large scale language models, it would be an
5:39
interesting read for you. We will be covering actually some
5:44
of these models at the end of this course, when we talk about
5:48
transformer models, because they are all based on the transformer
5:51
architecture. Yeah, and another trend also recently read this
Transforms in Vision
5:57
paper here was transformers and vision where people now also
6:02
adopt these transformer architectures to computer
6:05
vision. So however, this is also really large scale. So here, for
6:11
example, they say even like an image net, like 40 million
6:16
images is not enough to train a vision transformer. So it's,
6:20
it's really something that is mostly out of reach for academic
6:24
research. And also these transform models, they may work
6:27
very well on very, very, very large data sets like 500 million
6:31
images or something. However, for most applications,
6:34
convolutional networks will still outperform them. There was also
6:37
recently just a new architecture of convolution networks. So
6:39
they conversion networks are still status quo, it's still
6:43
what you would use in practice for computer vision. So it's
6:46
nothing like it's very experimental. It's nothing that
6:48
is very close to being competitive with convolution
6:51
networks on common images. But I just thought it was interesting
6:55
and worth mentioning where things are going. Alright, so in
Next Lecture
6:59
the next lecture, we will talk about the perceptron algorithm
7:03
in more detail. And we will have some code examples. In the
7:06
lecture last week, I mentioned the code examples may come
7:09
later. But I think it's maybe really useful to introduce it
7:12
rather than sooner rather sooner than later. So I have an
Homework
7:15
ungraded homework exercise for you, you don't have to submit
7:19
anything, it's just for yourself. So just to prepare
7:22
yourself a little bit. So I already posted this in on
7:26
canvas. But yeah, please really take a look at this as
7:32
preparation for the other following lectures. It's like an
7:35
introduction to NumPy, Python and NumPy. So of course, there
7:40
won't be any questions in homework or exam on NumPy,
7:44
really specifically, but it really will help you to
7:46
understand how pytorch works, and how we implement code,
7:51
because it's really like the linear algebra foundation here.
7:55
So yeah, if you have questions also about that, please let me
7:57
know. So it's just like a brief review of NumPy. If you are
8:01
already familiar with NumPy, you can also skip that. But yeah, I
8:04
would just recommend taking a look at it and see whether it
8:08
makes sense to you. If it's all new stuff, you may want to read
8:12
through it more carefully. Alright, then let me know if you
8:15
have any questions. And then the next lecture on Thursday will be
8:19
on the perceptron.

##v19:


Search in video
0:00
Yeah, good morning, everyone. I hope you had a good week so far.
0:04
And I have good news. So today, we are going to talk about the
0:08
perceptron. So a first implementation of artificial
0:12
neuron. And the good news is that this time, there will also
0:15
be some hands on aspects. So I'm going to show you some simple
0:19
code, how we can implement the perceptron and NumPy, and
0:23
pytorch. So based on that, I'm going just a little bit over
0:28
some items I wanted to briefly discuss. I will also send you
0:33
specific announcements about that on canvas. So to explain a
0:36
little bit more and to add also the concrete deadlines. But
0:39
there are a few things now. So yeah, on Wednesday was the last
0:44
official day where you could change classes. So I think most
0:48
people who are in this class right now are also likely going
0:52
to be in this class until the end of the semester. So that
0:55
means we can slowly get started with forming the project groups
0:59
for your class project. So I will ask our TA to set up on
1:05
spreadsheet where you can then enter your preferences for group
1:08
members. So I'm thinking that it would be best if you find
1:13
someone else in this class you you may want to work with. And
1:16
then you can add your preferences in this spreadsheet.
1:20
If you don't know anyone in this class, if you can't find a team
1:23
member, we will randomly assign you to a group. So in that way,
1:27
don't worry if you don't find anyone. And also if you if you
1:30
don't have any preference, you don't have to do anything in the
1:33
end on the TA will then assign groups if you can't find
1:36
someone for example, regarding the group itself. So it would be
1:42
great then once you know with whom you want to work, let's say
1:44
starting next week to think a little bit about what you want
1:47
to work on for your class project, I will prepare like an
1:50
overview of the kind of expectations and also compile
1:54
some examples for the project from other classes like previous
1:59
semesters. So to have an idea so you have an idea what what the
2:03
scope is approximately. And then I will also put together a data
2:08
sheet with resources where you can find interesting data sets.
2:12
So over the winter break, I've compiled a long list of
2:15
different data set repositories where you can find interesting
2:19
data sets that may spark your creativity. So if you don't have
2:23
any good idea, you may just want to browse through some of the
2:26
data set repositories. And maybe you find something that you
2:29
find particularly interesting. So also, yeah, homework one. So I
2:34
will set up a homework for about this lecture for practicing
2:39
some Python coding. So my idea is for this lecture to make a
2:43
homework where you take some of the code that I will be
2:46
presenting in this class. So I will only present it briefly.
2:50
And then in the homework, you will take this code, which is a
2:54
NumPy, and then translate it into just regular Python code
2:58
without the use of any NumPy. And by that, I think by this
3:02
reverse engineering going from NumPy to Python, you get to play
3:06
around a little bit with NumPy and then get a better feeling
3:09
for how it works. I may also think about just not even using
3:13
NumPy, but doing that with pytorch. But more details about
3:16
that after this lecture, I have to think a little bit also about
3:19
this, how to do it exactly. But you will see in this lecture
3:22
that NumPy and pytorch are very, very similar. So I think it
3:26
might be even make sense to just go from pytorch to Python. But I
3:32
have to think a little bit about that based on the difficulty
3:34
level. But again, don't worry about it right now, I will open
3:38
up a new canvas announcement and discuss also the details,
3:42
depending on how I decide. And then yeah, also wanted to remind
3:46
you, you can use Piazza if you have questions. So ideally, also
3:50
other students can participate in Piazza. So if you have a
3:53
question, and someone knows the answer, it would be great if you
3:55
can help with the answer, because that's also more
3:58
interactive than and more fun if more multiple people
4:01
participate. However, yeah, one short reminder is, please don't
4:05
use Piazza to post any solutions to the homework. So for
4:09
homework, everyone should work on the homework by themselves. So
4:13
please don't post any solutions on Piazza. But if you have
4:17
general questions about the homework, or there are things
4:19
that are unclear, you're very welcome to use Piazza and
4:22
discuss this. Alright, so with that, just what you will learn
4:27
after this lecture. So in this lecture, you will be able to
4:30
implement implement your first neural network. So it will be a
4:34
small single layer neural network perceptron. And you can
4:37
then use that to make predictions like classification,
4:40
like simple binary classification. It's not very
4:43
exciting by itself. Because of course, we will be using more
4:47
complicated networks that aren't to make predictions. But I
4:50
think this is like a great start to get familiar with
4:52
classification setting and also yet to see some code examples.
4:57
So with that, yeah, then let me get started with the lecture.

##v20:

0:00
Yeah, here's a lecture overview of all the topics we are going
0:04
to cover today. So first, in this video, we will start with
0:08
the brains and neuron models, just like a big picture
0:12
overview. And then in the next video, we will talk about the
0:15
perceptron learning rule, which is related to the Rosenblatt
0:19
perceptron, which we briefly talked about in the last
0:22
lecture. And then I will have a short interlude on
0:26
vectorization in Python. That is just like a quick note of how
0:29
we can make computational code in Python run more efficiently.
0:34
So that is usually by replacing for loops with vector dot
0:38
products, because that's something we're going to need in
0:41
the next video when we talk about implementing a perceptron
0:45
in Python using NumPy and pytorch. Then optionally, I
0:50
have a video of planning to make a video on the perceptron
0:54
convergence theorem. So I have to see how long these videos
0:58
take, whether we have time for that. Because, to be honest,
1:01
this is not like a super important topic. So and I don't
1:04
want to talk about it for too long, and then not having enough
1:08
time for other topics in this class, which I think are more
1:11
relevant and more important. Here, the perceptron convergence
1:15
theorem, that's a mathematical proof, it may be useful for some
1:19
of you in other contexts. But to be honest, it's not really that
1:23
useful for deep learning in the grand scheme. So if we cover it
1:27
or not, it doesn't really matter for the rest of this course. So
1:30
in this way, we have to really see how much time we have. And
1:33
then lastly, I want to give a brief intuition into the
1:37
geometric aspects of the perceptron, but one thing at a
1:41
time. So let's start with brains and neural models. So yeah, like
1:46
you recall from the history on deep learning, things were
1:50
inspired by biological brains and how neurons work. So here's
1:55
a picture of a neuron and then zooming in, sorry, of a brain
1:58
and then zooming in a little bit. These are some neurons in
2:02
the brain. I think this is actually from a mouse brain I
2:04
took from Wikipedia. And here's zoomed in version of a particular
2:09
neuron. Here, I think you can nicely see that neurons are
2:12
connected to each other. Here in this neuron, this is a
2:15
specific type of neuron. It's a pyramidal hippocampal neuron. So
2:19
it's a neuron in the hippocampus, the pyramid
2:23
unit neuron. And there are many different types of neurons in
2:26
the brain. So this is only one type of neuron. Yeah, and also
2:32
the big question is usually, do our brains use deep learning at
2:36
all? So in the human brain, is there some deep learning
2:39
algorithm running? Actually, I don't think we can answer that
2:42
with full certainty, because people don't know yet how human
2:47
brains work exactly. There are still many things that are not
2:51
clear yet, and many things that are still mysteries. However, I
2:55
think we can confidently say, though, that it's probably not
3:01
true. Because, yep, the brain is very complicated. And deep
3:06
learning, it performs well, and certain tasks like object
3:11
detection, and so forth. But to be honest, the human brain and
3:15
the capabilities of neural network are still very
3:19
different. So because we don't have artificial general
3:22
intelligence, I think that it's like an indicator that maybe,
3:27
maybe deep learning works differently. However, recall,
3:30
there was also this paper by Joe Fenton, where they looked at the
3:34
different learning algorithms, we briefly discussed that last
3:37
lecture, where they were the authors, it was not by Joe
3:41
Fenton, he was, I think, the last author on that. Think
3:44
Lily crap was the first author and doesn't, but doesn't really
3:46
matter. So the, um, the gist was that the brain may use type of
3:54
algorithm that is somewhat related to backpropagation. But
3:57
even that was not fully clear. So that still remains to be
4:01
seen. But to be honest, also, it doesn't really matter that much
4:05
whether the human brain does deep learning or not. Because
4:09
deep learning, the things we have are actually pretty
4:11
efficient for certain things that we are some people care
4:15
about, for example, object detection for object detection,
4:19
classifying objects in the image, deep learning performs
4:22
reasonably well. And it's kind of like, similar to the analogy
4:26
of the airplane, and how birds work. So someone was inspired by
4:33
your whole birds fly or here in this case, geese, and build the
4:37
first airplanes. However, it wasn't that important to exactly
4:41
mimic the bird, right? I mean, airplanes don't flap their
4:45
wings. And I think also, if you would design airplanes that have
4:48
flapping wings, it wouldn't be more efficient than, let's say,
4:53
airplane with flapping wings. So in that way, it's not always
4:56
important to make something like exactly the same. Sometimes it's
5:00
just useful to take something as an inspiration, and then you can
5:05
develop things on top of it, but they don't have to be exactly
5:08
the same to be useful. But yeah, just out of interest, I looked
5:12
up on Wikipedia, the number of neurons because one might argue,
5:17
maybe neural networks are not as good as the human brain in terms
5:20
of doing certain tasks, because the number of neurons is maybe
5:24
different. When I look up the number here, it says 16 billion,
5:29
340 million neurons in the human brain. So here, in this case, we
5:35
have 16 billion, if I look at the killer whale, it has 43
5:39
billion. So I would say human brain, or humans are more
5:43
intelligent than whales. Also, we can't answer that with 100%
5:49
certainty, but that's my assumption here. So it can't be
5:51
just the number of neurons that make something more intelligent.
5:55
Also, if you think back of the large scale language models that
6:02
I introduced in the history of deep learning lecture, I think
6:06
the big ones, they are GPT three and stuff, you have to double
6:09
check, but I think they had like 170 180 billion nodes in that
6:15
were parameters. So in that way, these models are actually even
6:19
larger than the human brain in terms of the parameters, if you
6:22
think of a parameter as like a neuron. So in that way, these
6:28
language models are even more powerful in terms of the
6:32
computation than the human brain or at least more, more
6:35
parameters. And these models don't really perform as well as
6:40
the human brain does. One thing they perform well, it is like
6:43
memorizing information. So these large scale languages, language
6:48
models, ingest lots of data from the internet, like lots of
6:51
documents and can kind of memorize them pretty well. And I
6:55
think humans are not that good at memorizing things. But on the
6:58
other hand, humans are better at understanding, which is
7:01
something then these models lack. So it can't be just the
7:04
number of parameters, there must be something different. But what
7:07
it is, that has to be yet has yet to be discovered. Yeah, so
7:12
in this lecture, we are actually talking not about neural
7:15
networks, we're talking about a single layer neural network or
7:19
a ballad. Yeah, and also in this lecture, we're not going to talk
7:23
about multi layer networks and networks with many, many, many
7:27
parameters, we are going to start simple talking about a
7:31
neural model. So model of the biological neuron, like a
7:34
computational model of the biological neuron. So just to
7:38
recap what a biological neuron is a neuron is a nerve cell. So
7:42
here's a circuit one neuron where you have the cell core or
7:47
nucleus, there are the dendrites where other neurons connected to
7:51
and there's the exon, the exon is where the signal gets
7:55
transmitted. So usually, signal arrives at the dendrites, then
7:59
it gets integrated or processed at the nucleus, and then it gets
8:03
transmitted. If the neuron is activated to these endings, nerve
8:11
endings, and they are basically connecting to dendrites of other
8:16
neurons. So yeah, so called connections that are connecting
8:20
to neurons and whether this neuron provides a signal or not
8:26
to the next neuron really depends on what happens in the
8:29
processing core here, which is something we will talk about.
8:34
Yeah, the earliest neural model, the earliest mathematical neural
8:38
model was the McCulloch pits model that we discussed in the
8:42
history of deep learning. So just to briefly recap, so here's
8:46
approximately how it would look like. So you have the inputs
8:52
here. So the x's are your inputs, let me close more clearly
8:56
here. These are your inputs. And then you have certain weights
9:04
here. So these are my weight parameters. And then this is our
9:08
nucleus, that's where the signals get integrated. So it's
9:11
a weighted sum. So you can also write it as, let's say in this
9:16
case, if we have x m m inputs, then you can write it as
9:27
follows where you have each input multiplied with each
9:32
weight. So this is the weighted input. And in deep learning, we
9:36
usually call that the the pre activation, we use usually the
9:41
mathematical letter z, we also call it sometimes the net input.
9:47
So that's more like a traditional term. So and this
9:51
value here is then passed onto a threshold function. And when the
9:57
signal here reaches a certain threshold, then a corresponding
10:03
signal gets transmitted. So the binary signal binary means a zero
10:07
or one in this context. So zero is transmitted, if the value of
10:13
the weighted sum is below the threshold, and the one is
10:16
transmitted, if the one is above the threshold, but we will see
10:20
that in more detail when we talk about the perceptron learning
10:23
rule and the perceptron model. So here's an example of an
10:29
integrate that you can implement with this mechanics and pit
10:33
neuron. This is just a recap also from the last lecture. So
10:36
if you set these weights to one, then our weighted sum is just x
10:41
one plus x two. And if the sum is bigger than 1.5, then it
10:48
returns a one. In this case, because one plus one is two,
10:53
right? So one plus one is two, which is greater than the
10:57
threshold. So you return a one. And otherwise you return a zero
11:01
because if only one of the two is one, then you won't reach the
11:05
threshold of 1.5. And then the output is zero. And this would
11:10
this would be an end gate. Similarly, you can also
11:13
implement an or gate. So here, the threshold is smaller. So the
11:17
weights are still one. So you're computing x one plus x two, and
11:21
compare that value to the threshold. If both are one, in
11:26
this case, the value is two and two is bigger than point five.
11:30
So you return a one, if one of the two is one, then also your
11:36
value is larger than the threshold, right? Because one
11:38
plus zero is one, it's greater than point five. So you also
11:42
return a one in both cases, only if both are zero, then you
11:47
return a zero because zero plus zero is zero. So this is how you
11:52
could use this concept of the McCulloch pits model, for
11:55
example, to implement different first order logic functions. Yeah,
12:00
you can also implement a not gate. So I don't want to go into
12:03
too much detail here. But yeah, you can walk through this maybe
12:08
by yourself. And then another one as a take home exercise. Can
12:13
you implement a logical x or function in using this McCulloch
12:18
spit neuron? So here's the table of x or function. Can you find
12:25
weights here? And can you find a threshold such that this simple
12:30
model here can implement the x or gate as an ungraded homework
12:36
exercise? You can maybe post on Piazza in a few days to see
12:40
whether this is possible or not. Alright, so this was just a
12:45
brief introduction. Let's now talk about the perceptron model
12:48
and the perceptron learning rules.

##v21:

0:10
Alright, let's now finally talk about training single layer neural networks, and in particular, the perceptron
0:17
learning rule. So that goes back to the Rosenblatt perceptron that we briefly mentioned in the history of deep learning
0:24
lecture. So the perceptron is kind of like a model. But yeah,
0:29
thinking about it, the model was already proposed by McCulloch's and Pitts, the mathematical model of a neuron in the human
0:36
brain. So at least it was inspired by this biological neuron. And the perceptron to be more, I would say specific, it's
0:44
a learning rule for the computational mathematical representation of the neural model. So this is now offering
0:50
us something that can help us find the weights automatically to make classifications, for example. So previously, we have
0:58
seen that how we can manually implement end and or functions
1:03
using specific weights of one and a certain threshold. Now with the perceptron, we can find automatic weights for different
1:12
types of problems like classification problems in general. So here's a picture of how that looked like back then.
1:18
So back then, the perceptron was actually a hardware device where people Frank Rosenblatt had to plug in and plug out certain
1:26
cables to reach certain decisions and stuff like that. So but yeah, we are not in a museum here. So we don't have to
1:32
go over how that works. So yeah, moving on. So I also should
1:38
highlight just for correctness, there are multiple perceptron algorithms. And I don't know how many, but there are several
1:46
variants. Here we are talking about, let's call it the perceptron. So basic version of the perceptron, which is now the
1:54
commonly known variant. So when we talk about the perceptron, in
2:00
theory, it's a perceptron, one of the classic Rosenblatt perceptrons. But yeah, there are multiple ones, we don't have to
2:07
worry about it here. We just take the classic one that is commonly known and just refer to it as perceptron for short. So
2:15
yeah, now we have a computational model of a biological neuron here. So for reference, on the left hand
2:20
side, what is shown is the biological neuron. And on the right hand side, would be the computational or mathematical
2:28
representation of that. So the one based on McCulloch and Pitt's idea, and that is also then the model that we are going
2:35
to use in the perceptron. So the perceptron learning rule would be then learning the parameters of this model. So how does this
2:42
model work? So what we have here are the inputs x one to x m. And
2:47
you can think of it as a feature vector. For example, if you think back of the iris data set, so in the iris data set, we had a
2:56
tabular data set where we had petal length, let's do it correctly, sepal length, sepal width, beta length, and beta
3:04
width, the four features. And then we had the number of training examples of 1234, and so forth. And in this case, we
3:13
had m features where m equals four. So here is x one x two x
3:22
m, you can really think of it as a feature vector, for example, a feature vector corresponding to the first training example.
3:28
And then each feature value gets multiplied by a weight. So you can see, each x here goes together with the weight. So
3:37
they are multiplied to compute the so called net input, the weighted sum. So this is weighted sum, which you compute
3:47
SWI times x i. And this is then what we usually use, or we
3:53
usually use the letter z for representing that to have it more compactly. And then so this is an input here. And then we
4:02
pass it to a threshold function. And a threshold function is returning a class label. So the class labels either zero or one,
4:10
depending on the value of z. So if z is smaller than the threshold, then we return the class label zero. And if z is
4:19
greater than a threshold, we return class label one. To be
4:24
more precise, if z is smaller or equal to the threshold, but if we use floating point operations, like real value
4:32
numbers in a computer, then the chance that something is equal is very small, because it could be also equally greater or equal
4:39
to so in that case, we could remove it here. So it's, I'm trying to say is whether we use zero smaller than and greater
4:46
equal to or smaller equal to and greater doesn't really matter. Either either way would work, because the chance that we have
4:53
an equal is kind of very small anyways. So in our output, this
4:59
is the either the zero or the one that is our class label. And now we can, yeah, then talk about a learning rule for this
5:05
perceptron that can then be used to determine a good threshold and a good, good values for w, so that we can solve different
5:14
classification problems, for example, classifying flowers in an iris data set. However, one shortcoming here is that this is
5:21
only for binary labels, so zero and one. And in iris, we have three flower classes. So if we would want to use the standard
5:30
perceptron for iris, we would have to simplify the data set to only two flower classes, but we are getting ahead of ourselves
5:36
here. So also here at the bottom, I just see another equation included. So this is also abbreviating the threshold.
5:44
So the threshold based on the threshold function based on the threshold theta, if it receives basically the weighted input, so
5:52
this is the net input. It returns the predicted class
5:58
label y hat. So y hat, the output is the predicted class
6:06
label. I will show you how that looks like for a concrete data set later on. Yeah, here to recap some of the terminology
6:18
that I already introduced in the previous slide, I made an overview slide because some of these symbols and words or terms
6:26
will be used later on in this course, when we talk also about logistic regression and multi layer neural nets. So we have
6:35
the net input, which is just another word for the weighted inputs. And we usually use the symbol or letter z for denoting
6:41
that on the activations, these are values from activation function. So an activation function takes the net input as
6:49
input. And we use the letter a and the activation function is a
6:55
sigma, which takes in z. So this is something that we will be using over and over in this course. And then the output of a
7:04
model, that is when we apply the threshold to these activations of the last layer of a neural network. And we can, for example,
7:12
use y hat to denote the predicted label or the output. And F is the threshold function which takes an A. So the flow
7:21
would be, you can think of it as first computing. So if we go
7:26
from z, so we have z is the weighted net input. So this is
7:32
computed based on x and w. And then we use sigma and activation
7:38
function to compute these activations. And then we have F
7:44
to compute the label outputs. So this will become also more clear
7:50
clear later, because right now, we have a special case in the perceptron, where our activation function is the same as a
7:58
threshold function. So the perceptron doesn't really have an activation function, they are here in that case, synonymous.
8:04
And in linear regression, there's another special case. So some of you are probably already familiar with linear
8:10
regression. So in linear regression, the activation is equal to the net input, and it's also equal to the output. So in
8:16
that way, um, yeah, these are two special cases, and it will become more clear. So I can maybe quickly draw this. So if
8:24
we have a linear regression model, recall what we had in the
8:29
history of deep learning lecture, and also on the Piazza discussion, the relationship or the figure that I shown of the
8:36
adder line, and then also how that related to the linear regression. So if we have then the model here, and a linear
8:43
regression, we would have a linear activation or just the weighted sum, and then the output is just a weighted sum.
8:53
It's our continuous value in a regular neuron, we have usually the steps, we have the weighted sum. So this is our net input.
9:02
And then we have activation function. And then we have a
9:09
threshold function. And then this produces our output. output. However, in the perceptron, so in the
9:17
perceptron, these are the same, the sigma and the threshold function, they are one function. And in the linear regression
9:28
model, so in the regression model, we don't have these. So the net input is basically our y hat. So there are these special
9:36
cases. But let's not worry about it too much, because we will be
9:43
talking about linear regression and logistic regression later on in more detail. So you will see how these concepts of activation
9:50
functions and thresholds relate to these. So let's focus in now
9:56
on the perceptron and only worry about the net input and the threshold, where in the bottom here, you can, again, see the
10:04
summary where we have first weighted inputs as the net input, and then we apply the threshold to return either the
10:10
zero or one, depending on the threshold value on theta. So I
10:18
want to make one little change to that formula to make things a little bit more convenient. So I just told you that we return
10:27
zero, if z is smaller or equal to theta threshold, and it's the
10:32
output is one, if z is greater than theta, it's a little bit inconvenient to write it like this. For I mean, it's not that
10:41
inconvenient, but for the sake of training the perceptron, it would be more inconvenient. So we will make things a little bit
10:48
more convenient by rearranging the terms. So we are just now
10:53
applying the mathematical operation minus theta on both sides. So we are bringing theta here onto the left side. And
11:01
then what we get is we return zero, if z is smaller, if z
11:07
minus theta is smaller equal to zero, and we return one, if z minus theta is greater than zero. So in this way, this is
11:15
our, I would say more convenient notation here. And if you think
11:21
about it like that, you can think of the negative threshold. So this part here, you can think of it as a as a
11:29
bias. So this is like a common term in deep learning, or also
11:35
in machine learning, a bias unit, it's a little bit weird to use the term bias, because it's a little bit overloaded,
11:40
there are other types of bias. For example, there's an inductive bias, like this relational inductive bias that we
11:46
talked about, there's also a fairness bias, and now we have this bias, mathematical bias unit here. There's also a
11:55
statistical bias, if you think of decomposing a loss function into a bias and variance term. So it's a bit unfortunate. But
12:02
in the context of deep learning, if you read the term bias unit,
12:08
that would be in this case, this, this theta, we can treat it as a parameter will become more clear in a few moments.
12:17
Yes, in this representation, we are now using the bias as a parameter, when we compute z. So we set the minus theta to be
12:28
B is short for bias unit. So it's easy to memorize B for
12:33
bias unit. So we set B equals to this minus theta. And then we compute the Z, the net input is shown here. So just to recap,
12:44
what we had before was multiplying the W's and the
12:51
X's. So this is from index one to M. And this was our Z. Now,
13:00
when we compute the Z, let's call it. Let's make that right to denote this on UC. This includes now our bias unit. So
13:08
net input is now including the bias unit, if we want to update the figure to reflect that I've drawn here, this B, this B goes
13:17
now also into the net input. So the net input is really this computation here. And yeah, it's also the same as shown here. And
13:25
now what we can do is we can also write then the activation
13:31
function or here the threshold function. So I should have actually used F, but the perceptron is the special case
13:38
where the threshold function is equal to the activation function. So I can use either sigma or F doesn't matter here to be
13:45
consistent. And so now we can have the zero here on the right hand side instead of having the minus theta. So this will make
13:54
more sense from a learning perspective. So in this way, it's easier to parameterize the network, if we don't have to
14:00
learn the threshold here on the right hand side is just easier to write in code. Because then we have a threshold function
14:06
that just simply checks whether some something is greater or smaller than zero. But of course, you can also implement
14:12
it. Like shown on the previous slide with a minus theta, it doesn't really matter. But this is also the common notation. And
14:20
this will be something that you will also encounter when we talk about multilayer perceptrons, convolutional networks,
14:27
recurrent networks. And when we use existing code implementations, for example, in pytorch, this is really like the
14:33
common way also, if you look at recent deep learning papers. So this is like the like I said, the common notation that you
14:39
will find in most modern texts, like maybe not textbooks, because textbooks are usually a few years behind with the
14:45
trends. But if you look at a modern deep learning literature, you will find that people use this extra this notation with a
14:52
additional bias unit here. Yeah, however, it's slightly inconvenient for mathematical notation compared to a slightly
15:00
different notation again. So on the right on the next slide, I will show you how we can modify this even a little bit
15:07
differently to have the bias as part of the other inputs. So
15:13
here, what I've done now is I'm setting B equals to weight, I
15:19
call that W zero. And this is again, or minus theta or minus or negative threshold. Now I'm including this bias as a weight.
15:29
So first, let's maybe start with the figure. If you look at the figure here on the left hand side, what I've now what I've
15:36
done now is I have removed this B here, I've removed that B here, compared to the previous slide, and now have the value
15:45
one, this is really like a value, an integer or float number of value one. And then now I have the W zero as weight.
15:51
So this is essentially our bias, but I'm writing it as a W, because then we can write this notation more compactly. So
15:58
instead of writing it on the previous slide with index over one to M, like this, with a W with a B, or you can also write
16:13
it as this, instead of this, I can change this to zero, and
16:18
then I can get rid of it as slightly more compactly. It's not that interesting to do it like this. But as one advantage
16:25
of doing it as the advantage is that we can now use a dot product, just x transpose W. If we wouldn't have the modified
16:35
version here, what we would have to do is we would have to write it as x transpose W plus B, which is just slightly more work.
16:47
It's not that much more work. But yeah, mathematicians are sometimes efficient or lazy. I would say not lazy, definitely
16:54
not lazy, but efficient. So the notation here shown would kind of help us to make things a little bit simpler. So why am I
17:03
telling you this? So this is something this notation here on this slide is something you will find in some or most textbooks,
17:10
actually, whereas this is I would say the more modern one. I mean, for things like this, it might be overkill to use this
17:17
separate bias. So this looks simpler. But when we talk about multi layer networks, actually, this becomes more convenient.
17:25
And this is also what most framework use. And the reason why this is more convenient is because I'm going I don't want
17:32
to switch too much because it probably gets confusing when you watch this video, and I'm going left and right and left and right. But one more thing about this slide is, if you want to
17:41
use this notation, you have to modify the inputs here, right. So if you think of the iris example, you have x one, x two,
17:49
x three, x four as your feature vector for one training example. So this would be your, let's say, first training
17:57
example. Now, if you have this as input, and you want to use
18:04
this notation, what you might have to do, what you would have to do is to have, you have to have one here. So you have to
18:09
modify this list. So in practice, usually you have fixed
18:16
size array, and then you would have to make a new array. That's how it would work in a computer, you would have to make a new
18:23
array that is a little bit bigger. And then you have to move all the values you have to let me use different colors,
18:29
maybe you have to make an x one, x two, let's start with one, put
18:35
the one here, and then the x one, x two, x three, x four. So
18:40
you have to make a new array to make the one fit into this array. And making a new array can be expensive, of course, it's an
18:46
additional computation, it's just much simpler. If we just add this B to it, if we compute it as x transpose w plus B,
18:56
this is computation actually simpler than adding a new value to an array, because then we have to make a copy of the array
19:03
move all the values over. And this is something it's a computational consideration, essentially. Yeah, I'm not
19:12
exactly sure what I wanted to show on this slide. I think I just wanted to emphasize again, that we can now use dot product.
19:19
Alright, so this is our general framework. And now we are going to take a look at the perceptron learning rule. So how it
19:27
actually learns the weights to classify classes. So assume we have a binary classification task. So here we have two
19:34
classes, these blue dots and the yellow or orange squares. And
19:42
the perceptron finds the decision boundary to classify these two classes. If the classes are separable, by that,
19:50
I mean, if there is a linear decision boundary, I should have maybe set linearly separable, that means there has to exist a
20:00
decision boundary that can separate these classes perfectly, then the perceptron is guaranteed to find it. So
20:07
here, just looking at it, you may guess that decision one, you could potentially look like that, and then it will perfectly
20:14
classify these two classes. So this is a problem with only two
20:19
features for simplicity. Because if I have more than two features, it would be very challenging to draw it in a slide. So in this
20:26
case, we only focus on the simple example. And I actually made an animated GIF here, I will play it in a second. And
20:32
then you can see how the network or the perceptron goes about the task of finding this decision boundary. So starting at a
20:40
random place, it will basically update the rule in each iteration. So there will be an iteration counter moving up by
20:47
and it will try to adjust decision boundaries to make them better, basically. So let's take a look.
21:00
Actually, I forgot how many iterations they are, there might be 20 or 30. So you can see it's still making mistakes. And the
21:06
circle that is shown here, that is indicating which data point it currently looks at. So you can see it's on this black
21:14
circle, it's moving around, because we have shuffled the data set. And then it will look at one training example at a
21:21
time. And if it finds that there's a misclassification, then it will move the decision boundary. So if it right now,
21:28
you can see it always finds classes that are already on the right, correct side of the decision boundary. So there are no updates are necessary, but it has to find are on the ones
21:37
where it makes mistakes like these here, if it touches these updated. So if it touches these, see, then it will update. So
21:45
yeah, it's back to one. So it was a little bit faster. Let me move on though. So yeah, what you can see here in the lower
21:51
left corner is the results. Yeah, it was 49 iterations. So
21:56
here's the final decision boundary, how it looks like. And you can see it, um, yeah, it classifies those two classes,
22:04
say, class, zero and class one perfectly. Now, though, it's
22:12
gone only guaranteed to converge if a solution exists. So if there is no solution to that, for example, if I have a blue
22:20
dot that is here, there would be no decision boundary, where you can classify this data set perfectly. And what will happen
22:28
is, if the perceptron encounters this point, it will move the decision boundary more to this side. So it may even move the
22:36
decision boundary, let's say to here, but then all the other points are wrong. So it's moving it back here. But then again,
22:41
this blue point is wrong, and it's going back to the right hand side. So it's always like flipping back and forth. So if
22:47
the data set is not perfectly separable, then it will never stop to converge. Later in this course, we will of course learn
22:54
about algorithms where this is not the case, where it will always converge to at least some solution, it will at least stop
23:00
updating. Because I mean, this is a big issue. If you have a real world data set, classes are rarely separable by linear
23:07
decision boundary, there's usually always a case where you can't separate things perfectly. And it would be very annoying if
23:14
your algorithm makes these big jumps back and forth. So the Adeline algorithm, for example, it will converge even if classes
23:22
are not linearly separable. And we will learn about this and not to distant future. But for now, let's stick with the perceptron
23:29
learning algorithm, just outlining how it learns. So there are three scenarios. It's the one scenario is if is if we
23:36
make a correct prediction. By that, I mean, if the predicted label y hat is equal to the target label. So for that, we
23:46
can also have two scenarios of the if y hat is one, and y is
23:54
one, or if the predicted label is zero, sorry, someone jumped
24:00
here, the predicted label is zero. And the actual label is
24:06
also zero, then we are correct. And then we don't have to do anything. So if both the prediction of the output are
24:13
equal to the target, I think this word is extra. Okay, and
24:20
there are no two scenarios and be where things have to be updated. It's if we are incorrect. So one scenario is
24:28
where y hat is zero, and y is equal to one. So in this case,
24:35
what we do is we add the input vector to the weight vector. So we update it like that. So that means, let me draw this maybe as
24:43
an example. So if we have data points here, data points here,
24:50
or let me spread them a little bit. Oh, that's easier to draw the decision boundary. So let's say, blue is class zero, and
25:00
yellow is class one. In this scenario here, what we have is we have the prediction is zero, although the true label is one.
25:07
So for example, for a decision boundary like that, and we encounter this data point, what we have to do then is we have
25:13
to move things over here. It's by adding the input vector to the weight vector. Why is that I will show you exactly why that
25:23
is later when I go over the geometric intuition, and it will become clear why we have to add the input vector to the weight
25:29
vector rather than subtracting it. The other scenario is if the output is one, and the target is zero, and then we subtract the
25:37
input vector from the weight vector. So there are two update rules here going on. They are both very similar, we can write
25:43
this mathematically very compactly, as shown here. So here, assume we have a data set D, this is our training data
25:56
set. So we have n data points here from one to n. So x our
26:03
feature vectors, and y our class labels. Yeah, so this is our
26:10
data set. And now here, that's the perceptron learning algorithm. So how does it work? First, we initialize the weights
26:18
or the weight vector to zeros, if we have m weight vectors, that would be a vector of zeros. And we are assuming the
26:26
notation where the weight includes the bias, so we don't have to write the bias separately, we could do that, but
26:33
it would be a little bit more work here. So it would be a little bit more verbose. So there's a little bit more compact here. So then we have a follow up here. So for every
26:43
training epoch, what is an epoch epoch means pass over
26:50
the entire training set. So if I have a training set, like shown
26:58
here, then an epoch would be processing every data point in
27:05
this data set. So for example, I consider the first data point, I do my computation, then I consider the second one, and so
27:11
forth until I reach the last one. And then this is one epoch when I when I reached this last data point, and I have
27:20
completed one epoch. And then I may go back to the beginning and
27:26
do another sweep over the data set, that would be then the second epoch and so forth. So epoch really means pass or
27:34
iteration over the data set. So then this is our auto loop. So for every training epoch is our auto loop, and then the inner
27:42
loop is for every data point in the data set, we perform steps A, B, and C. So if we have multiple epochs, that means we
27:51
can do this multiple times. So we would just go back to the beginning of the training set and do it all over again. So but
27:57
the interesting part happens now for every data point. So note here, the perceptron processes, one data point, or training,
28:08
let's say, one training example at a time. So for every training
28:20
example, compute the prediction, this is our prediction. And it's
28:27
computed by computing the weighted sum, this is our net input. So this is input z. And this is our predicted label. And
28:38
then we compute the error. So the error is computed by the
28:44
true label minus the predicted label. Why is that? So if this
28:49
is one and this is y hat is zero, for example, then so let's first let's assume the simple case where we make no error. So
28:57
if we have zero and zero, then the error is zero. And then if
29:03
you look at the row C here, we have the weight update. So C is
29:10
the weight update, then the weight update or the new weight is the old weight plus the error times the input vector. But if
29:20
the error is zero, if the prediction is correct here, zero minus 00, then we can cancel this term and there is no weight
29:27
update. So let me clear this a little bit here. If both are
29:33
one, then the error is also zero. And then we can also cancel this term. So we can see the weight update only happens
29:41
if we have an error if we make a prediction error. And then now
29:46
let's consider the case where we have a one and a zero here. So then the error would be one here, so we would have an error
29:58
of one into then we would be adding the weight vector. So if
30:04
we have the case for the predicted label as a zero, and
30:09
the case for the true label, a one, this is when we are adding, adding something, right? So we are adding the feature vector
30:17
here. So this is exactly like the case that we have here where y hat is zero, and y is one, this is the same case here.
30:28
Now, let me, I can't delete if I switched slides. Okay, so then
30:33
let me write it like this, with a different color. So if we have the last scenario, zero, and one, then our arrow is minus
30:41
one. And in this case, if this is minus one, we are subtracting,
30:47
right? So w minus x one, so we are subtracting the feature x i,
30:54
we are subtracting the feature vector, which is equal to this,
30:59
sorry, to this case here, where we are subtracting the input vector. So here, this is really just a mathematical summary of
31:08
the slide I've shown you before. Alright, so I think if this is confusing, maybe look at that more slowly. And then in the
31:18
next video, I will show you vectorization in Python. And
31:24
after that, I will also show you how to implement perceptron in Python using NumPy and pytorch, which will I think, make this
31:32
video more clear. So what we just have discussed, if this is still complicated, I would look at it a little bit more slowly,
31:39
like step by step. And then maybe don't worry about it too much, because we will implement it in code. And after that, I
31:46
think it will be really clear.

##v22:

0:02
Yeah, in this video, I want to talk a little bit about making
0:04
scientific computing a little bit more efficient using a
0:07
concept called vectorization in Python. So why am I talking
0:11
about this right now? So the reason is because in the next
0:14
video, I want to show you an implementation of the
0:16
perception in Python using NumPy and pytorch. And I will make use
0:21
of this concept of vectorization in the next video. So here, I
0:24
just want to give you some background information on that.
Why use Python
0:27
So now in general, running computations is a big part of
0:30
deep learning. So deep learning is a very applied field. Most of
0:33
the things we do require here large amounts, large amounts of
0:37
computing and computations. So in that way, I'm getting doing
0:41
things efficiently is kind of important. Some of you may
0:43
wonder why do we use Python then because Python is not known for
0:47
being a fast language. I mean, the truth is, usually, Python is
0:52
not really a big bottleneck in deep learning, because we use
0:56
efficient libraries like NumPy for CPU computations and pytorch,
1:01
for example, for GPU computations, which implement
1:05
algorithms very efficiently in underlying c++ routines and
1:09
CUDA routines. And so if you would take out Python out of the
1:14
equation, and just look at these implementations that say in c
1:18
plus plus, and everything, Python would only slow things
1:22
down by 10%, approximately. So that is what is estimated by the
1:26
pytorch developers. So whether you use pytorch, Python or not
1:29
for writing code, it does not really slow things down because
1:33
Python is only like a glue around these lower level
1:37
libraries. So it's basically just a wrapper around things. So
1:41
it's not that slow actually to use pytorch in Python compared
1:46
to let's say, other languages. However, that only applies if we
1:52
use Python, I would say smartly, because there are certain things
1:56
that are not very fast in Python. So let's let's talk
Computing the net input
2:00
about vectorization. And now, so maybe stop the video at this
2:04
point, and take a look at what is shown here, and then try to
2:07
answer the question, what are we computing here? So yeah, what we
2:13
are computing here is the net input, the weighted sum from
2:18
the perceptron. So here, I'm just defining the variables. So
2:25
I'm using this notation where we have the bias implicitly as a
2:31
weight. So instead of bias, I could also have written W zero
2:36
would have been maybe a little bit more clear. But I think you
2:38
know what's going on here. So what we have is the inputs x
2:43
zero, x one and x two. So I'm just using some arbitrary values
2:48
here. Same for the weights. So in the bias, so these are the
2:52
parameters that we want to learn. Usually, here, it's just
2:54
about computing the net input, not no learning involved. So I'm
2:59
assigning them to a Python list here. So these are no Python
3:04
lists. And then here in the bottom, this is how we compute
3:07
the net input. So z is our net input. So what's going on here,
3:10
we initialize z to zero. And then in a for loop, we iterate
3:15
over the indices on the indices i to length of x or m. So from i
3:24
to m, where length of x is equal to m, the number of features.
3:28
And for each iteration, we update z. So this is how we
3:32
compute the weighted synthesis equivalent to this one that we
3:39
we computed before. And yeah, there's not that much more to
3:43
say about that. This is just that using a for loop to
3:46
compute the net input. Slightly modified version of that would
List comprehension
3:52
be using a list comprehension. And I'm just seeing actually,
3:55
this is even a little bit better than a list comprehension in
3:58
that way in that context, because we don't have to
4:01
construct the list. So you could actually put square brackets
4:04
around this, it's not necessary. If you don't use
4:06
spare brackets in Python, it will be a generator expression
4:10
with a spare brackets, it will be a list comprehension. Either
4:13
way, both are slightly better versions of that for loop. Or
4:18
that's at least what the typical Python developer would tell you.
4:22
So personally, I'm actually planning maybe to use fewer
4:27
list comprehensions in the future. You may find them still
4:31
used in my code for this class, because yeah, I'm historically
4:35
I've been using this comprehension a lot, a lot of
4:38
Python developer do that. But to be honest, sometimes, I think,
4:43
especially if there's a lot of things going on, this
4:46
comprehension can make things maybe a little bit less readable,
4:49
because I think this is a little bit longer. But I think it's
4:55
somewhat easier to read than this one here. Because here,
4:58
it's everything on one line, you have something like the
5:01
multiplication for x i and w i and then in the zip. So here zip
5:07
is iterating over two lists at the same time. So in that way, I
5:11
mean, it's the same thing. It's just a little bit more compact. I
5:14
would say compact is nice if you care about the number of lines
5:18
of code, sometimes a little bit harder to read. So but anyway,
5:22
so you should be familiar with both ways of writing things,
5:25
because they are very, very common in the Python ecosystem.
5:27
So now there's another way. I recall the dot product that we
Numpy
5:33
talked about x, the vector x dot w. So that would be another way
5:41
of computing our net input. That is what I'm showing you here at
5:44
the bottom. So I'm actually using NumPy now. So I'm using
5:49
NumPy arrays, I'm converting the lists to NumPy arrays. NumPy
5:52
arrays have efficiency benefits compared to regular lists,
5:56
because in regular lists, everything is a pointer to some
6:00
random location in memory. So if every time you want to look
6:04
something up, the Python has to find or go to the location in
6:08
memory. And these are like random locations in NumPy array,
6:14
everything is so it's basically a fixed size array. So you can't
6:17
make the array bigger compared to a Python list. But in that
6:20
way, everything has a fixed size, you only need to store the
6:25
first location of that array in memory. And then pi or the
6:30
computer can use, for example, the CPU caches like the l one
6:35
and l two cache to do certain computations more efficiently by
6:39
pulling out numbers from the memory more efficiently. So
6:41
NumPy arrays for computing much faster than Python lists. And
6:46
also you have linear algebra operations already implemented
6:50
for it like the dot product, for example. So here, I'm computing
6:55
the dot product between so x transpose w. So that's how we
7:01
compute the dot product, you can actually also write x, back dot
7:06
t, I've been writing transpose to just be explicit. So you know
7:11
what this is doing. So if I do this, dot w, back should be the
7:20
same. I am actually doing it here, too. Okay. Oh, yeah. Also
7:28
one, one thing is here, that in this case, our NumPy array only
7:34
has one dimension. So you don't actually have to do the
7:36
transpose. I hope you have worked through the NumPy
7:40
tutorial that I've given you. So then this should be I think
7:44
more clear. And for the rest of the course, we will also
7:47
also assuming that you have some familiarity with NumPy, pytorch
7:52
will be very similar to NumPy as you will see shortly. Okay, so
7:56
you can just confirm these are the same computations or mean
8:00
different computations, but the same results. Now, here are all
Computations
8:05
the three options for computing the net input listed. So my
8:10
question to you now is, for large vectors, which one is the
8:17
fastest? So have a guess how fast these implementations are.
8:21
And then on the next slide, I will show you the results. And
8:24
you're also very welcome to try this on your computer, for
8:27
example. So the results are as follows, I was using the time
Results
8:32
it magic function in ipython, because I find it a personally
8:35
very convenient. So here, with minus r, you set the number of
8:39
repetitions. And I think, honestly, I think I'm, yeah,
8:47
this is, I was just wondering, RS repetitions, I was correct,
8:51
because I'm just seeing it here. And this is the number of loops.
8:54
So it's running the computation 10 times as one experiment. And
9:01
then it's repeating this experiment 100 times and
9:03
averages over those. So you can see it computes the mean and
9:06
standard deviation of that, because sometimes, depending on
9:09
what your CPU is currently running in the background, it
9:11
may be faster or slower. So in this way, you get some better,
9:15
more stable estimate by averaging over multiple
9:18
experiments, or repetitions. So the first case, the for loop
9:23
here runs in like 40 milliseconds, approximately.
9:28
The list comprehension or generator, in that case, is a
9:31
little bit faster, it's 30 milliseconds. So it's 10
9:34
milliseconds faster, it's quite a bit. I mean, it's like, I
9:38
would say almost 20% or something. But what's what's
9:41
really interesting is the vectorized implementation. Now
9:45
instead of having, let's say 40 milliseconds, you're almost down
9:48
to 40 microseconds, where micro is 1000 times faster than
9:54
milli, right? So in that way, there's a huge improvement by
9:57
just using NumPy code here. So this vectorized implementation.
10:01
And this is why in deep learning, we want to avoid to
10:05
use for loops. So wherever you can, if you ever see a for loop
10:08
in your code, try to eliminate that by using dot products or
10:13
matrix multiplications in NumPy and pytorch. Yeah, regarding
Parallel Computing
10:21
the reason why they are more efficient. So I haven't really
10:25
this figure just inspired me to talk about this. We haven't
10:29
really talked about why it is more efficient, if I go back a
10:32
little bit. So if you look at the for loop here, what is
10:35
going on here is that things are computed in a sequential order,
10:39
right? So the for loop is doing one thing at a time, it's doing
10:43
this computation computation for the first index, and then it
10:46
goes back and does it for the second index, and so forth. So
10:49
it's doing this sequentially one thing at a time. However, for a
10:53
dot product, for example, you can think and compute things in
10:56
parallel, right? So if you have two vectors, so let's say one,
11:04
two, three, and 123. So what you would do is you what you would
11:11
do is in the dot product, you would compute one times one plus
11:15
two times two times plus three times three. So you would
11:19
compute product, this one plus the product, this one, and plus
11:28
the product of this pair. So I would write it out as one, one
11:33
times one plus two times two plus three times three. So of
11:43
course, you have to have the results of that when you want to
11:48
add that up, basically, but each pair can be computed in parallel,
11:52
right? So you can already carry out this multiplication and this
11:56
multiplication and this multiplication. At the same time,
11:58
you don't have to wait until one is finished. So you can compute
12:03
things in parallel. So the computer can actually compute
12:06
this. Oops.
12:09
Let me use a different color can compute this multiplication, this
12:19
multiplication and this motivation all at the same time
12:23
and then sum up the results. And in this way, we can leverage
12:26
parallel computing, there's something called SIMD. It's a
12:30
similar operation, but on the same data. So that is one
GPU vs Neural Network
12:40
advantage why GPUs are kind of especially good at this because
12:45
GPUs have a lot of cores. So you can actually carry out large
12:48
vector dot products or large matrix multiplication very
12:53
efficiently. So in a matrix multiplication, you have multiple
12:56
dot products at the same time. So you can parallelize the dot
12:59
product computations. And yeah, going back to the question I
13:05
raised earlier, why the human brain is, for example, so much
13:09
more powerful than a neural network. One reason could also
13:13
be that it's just a yeah, also the number of connections. So
13:16
the brain may not have that many parameters as like these big
13:19
language models, but it has a lot of connections. Although
13:22
it's also not really true for language models anymore, because
13:25
the transformers also have these attention layers, which have an
13:28
attention over all the inputs and stuff like that. But let's
13:32
let's consider here a GPU for reference. The GPU has a lot of
13:36
transistors, it has 2.1 billion transistors, which is actually
13:40
more than the sorry, that is actually 21 billion 21 billion
13:48
transistors, this particular one from 2017. Whereas the brain has
13:53
16 billion neurons. So GPU is actually more transistors than a
14:00
brain has neurons. So one idea why the brain is also so much
14:05
more powerful than a GPU, for example, is that there are just
14:09
so many more connections per neuron compared to a transistor.
14:12
So transistor only has approximately 10 connections on
14:15
average. And the human brain has about 10 to 100,000 connections
14:23
per neuron. So in totally have, what is it like 10,000 billion
14:28
connections in the human brain? Alright, so, but going on moving
14:32
on. So this was like a short interlude into the
14:34
vectorization. I explained, I think, things more in detail in
14:38
this NumPy resource in the series of videos I shared with
14:42
you. So if you want to know more detail, so but here, that was
14:45
just like the minimum, what we need for the next section for
14:49
implementing a perceptron in Python using NumPy and
14:52
PyTorch.

##v23:

0:00
Yeah, so in this video, I'm going to show you how we can
0:02
implement a perceptron in Python using NumPy and pytorch. So I
0:07
will be using Jupyter notebooks, because I think for simpler
0:11
code examples, it's actually quite nice to use Jupyter
0:14
notebooks, because I can execute one thing at a time, and it will
0:17
make things easier to explain. However, later on in this
0:21
course, we have to I think move to Python script files, because
0:25
when the deep learning models become larger and larger, managing
0:30
them and Jupyter notebooks can be a little bit, I would say
0:32
tedious and also dangerous. Because it's easy to lose the
0:37
overview and debugging is a little harder if you have the
0:39
separate cells and stuff like that. And then the danger is
0:42
that you might execute things out of order. And yeah, also, you
0:47
want to import certain aspects from different files, you don't
0:50
want to have everything in one notebook, because then it
0:52
becomes really confusing and manageable. But we will get to
0:56
these parts later in this course. So yeah, so back to
1:01
this topic of the perceptron implementation in NumPy and pytorch
1:05
on all the code files are actually on GitHub. So if you go
1:09
here to this link, or I will also link them on canvas so that
1:13
you can just click on them if you are interested to play around
1:16
with them. The homework will be based actually on the NumPy one
1:20
where I will ask you to implement this in plain Python,
1:24
just to make sure you understand what's going on. And by
1:30
converting NumPy code to Python, I think you will work with the
1:34
code step by step and get a better understanding of these
1:37
individual things. And I think also you're going from NumPy to
1:41
Python is easier than from Python to NumPy if you are
1:44
relatively new to NumPy. So in that way, let me now walk
1:49
through the NumPy notebook. The pytorch notebook is actually
1:52
very, very similar, which is one of the cool things about
1:54
pytorch, because it is very similar to NumPy. Except there
1:58
are some extra features that we will be using later on. And I
2:01
will have a lecture on pytorch where I will explain you these
2:04
differences. So for right now, it doesn't make such a big
2:08
difference whether we use the NumPy or pytorch notebook. I
2:11
will also show you a step by step comparison after I
2:15
explained the NumPy notebook. So you will see what's actually
2:18
different between the two. Alright, but let's do one thing
2:22
at a time. So here, I will make this a little bigger. I hope
2:26
it's easier to see them. It's almost too big. Alright, so yeah,
2:35
so I'm starting here, let me clear, maybe the outputs, and
2:39
then I will execute them one at a time. So I'm importing some
2:43
libraries for those who have not used notebooks, this one here,
2:48
this command is for showing plots in the notebook. It's
2:51
technically not necessary anymore. Always sometimes, on
2:55
some computers, plots will not be shown in a notebook, if you
2:59
don't include that line, and it doesn't hurt to include that
3:01
line. So I always do this. Here, I'm just loading the data set.
3:06
So there's nothing really interesting happening here. But
3:09
I will step through this step by step. So the data set is like
3:13
some toy data that I generated, I will show you how that looks
3:17
like shortly. So here, I have two feature columns, I didn't
3:20
include any column header. But this is the first feature. This
3:23
is the second feature value. And this is the class table here. So
3:27
there are zeros and ones. And you can see the data set is not
3:30
shuffled. And actually, it's helpful for learning if the
3:33
data set is shuffled, it will make the learning a little bit
3:36
faster in the perceptron. Yeah, alright. So here, I'm loading
3:43
the data set into NumPy can also use pandas. But I thought it
3:47
might be overkill, because it's a relatively simple data set.
3:50
And then I'm assigning the features to x, which is a
3:56
matrix, then, and y, which is the class table. I can maybe
4:02
show you just how they look like. So this is x, it's a matrix.
4:07
And y is class level array. So here, it's shuffled because I
4:12
actually executed this whole bunch of code. So you then can
4:15
already guess what's going on here. So here, I'm loading the
4:20
data, and then just printing some summary information, it's
4:23
always, I think a good idea to do that to get an idea. So we
4:26
have 50 labels from class zero and 50 labels from class one, we
4:31
have thus 100 data points in total, and two feature columns,
4:37
and also 100 labels. So, for example, here, we can see, okay,
4:40
these and these match numbers match. So and that's what we
4:43
expect. It's just some sanity checks here and some making sure
4:46
that everything looks okay. Then here, I'm shuffling the data set
4:51
so that they are not all in order, they are shuffled. And
4:56
how I'm doing that is I have to shuffle x and y together, right?
5:01
So otherwise, on everything will be mixed up, then the features
5:06
won't correspond to the class labels anymore. So how am I
5:08
doing that is I'm creating a shuffle index. So I can just
5:11
show you creating this shuffle index here. And how it looks
5:20
like this is just the numbers from zero to 99. So the 100
5:26
indices, and then I'm actually shuffling these indices. So here,
5:31
I'm generating random number generator, and then I am
5:34
shuffling these indices here. So you can look at these after
5:41
shuffling. So after I execute that, you will see that oops,
5:54
that's too much. But you will see they are no random order.
5:58
And then I'm using that to select the data points from x
6:01
and y. So then x and y will be shuffled based on the shuffle
6:06
index here. So that's how we shuffle. And then I will use the
6:11
first 70 data points for training. And the last 30. So
6:18
we have 100 data points to 70 to 100. The last 30 data points
6:22
will be for our test set. Later on, we will be seeing or using
6:26
more convenient ways to load data in pytorch. So there are
6:30
some loading utilities here, I'm just doing it step by step. So
6:33
you get a feeling of what's basically going on. And then I'm
6:39
normalizing the data. So this is sometimes also called
6:42
standardization. So here, I'm standardizing the data such that
6:47
after standardization, it will have mean zero and unit
6:50
variance. So I'm subtracting the mean and divide by the standard
6:54
deviation. So here, I'm computing the mean and
6:56
standard deviation of my sample. And then I'm subtracting the
7:03
mean and divide by the standard deviation. And then both will be
7:09
having mean zero and subdivision one, so unit variance, so you
7:13
can actually check that.
7:16
Oops. It's not quite true, because we have to look at the
7:26
training. Okay, very close to zero. So this is 70 digits after
7:34
zero. So 0.000 or something up to two. So very, very small.
7:38
It's almost identical to zero, essentially. And then for the
7:43
standard deviation, it should be around one. Yep. So the data is
7:48
standardized. Well, why am I doing that? It kind of speeds
7:51
up training a little bit. It's like stabilizing the training
7:54
for the perceptron. It's not that necessarily necessary. But
7:58
it is a good practice to do that for other types of optimization
8:03
algorithms later on when we talk about stochastic gradient
8:06
descent. So this is something standardization that is usually
8:09
recommended. The only types of machine learning models where
8:12
this is really not that necessary is like for tree
8:15
based models. That is something we covered in or that was the
8:19
end discussed in statistics 451. When we talked about decision
8:22
tree algorithms, these don't require standardization. But all
8:26
other machine learning deep learning models, I know, they
8:28
can usually benefit from that, like, especially stochastic
8:31
gradient descent will just learn faster, which is something we
8:35
will be doing later. So it's just a good practice. Alright,
8:39
let's take a look at the data. So here, this is our training
8:43
set, how it looks like. So you can see it's around centered at
8:45
zero. We have two classes, class zero, these circle here, and
8:51
then the square for class one. So feature one and feature two,
8:55
that's our training set. And so there should be 70 examples, and
8:59
then the remaining 30 examples in our test set. So what we
9:02
want to do is we want to train our model on the training set
9:06
and then evaluate it on the test set. So let's implement our
9:10
perceptron model then. So yes, the perceptron code, you can see
9:15
it's relatively short, I'm implementing it using a
9:19
forward and backward method. Why I'm doing that is because that
9:24
is also how things are done in pytorch. And it will make things
9:28
more familiar later on if I start using this habit. Alright,
9:33
but let's start at the top. So I'm implementing it as a
9:36
class here. And yeah, you should be I think familiar with Python
9:40
classes. So here, what I'm doing is I'm running the constructor.
9:48
So this is a special class method, a constructor, I'm
9:51
giving it the number of features, because that's what I
9:54
need to know the number of weights. And I'm using here, the
9:58
implementation where the weights and the bias are separate,
10:01
because that is more convenient. So I don't have to modify the
10:05
feature vector. So what I'm doing here, if I go back to my
10:09
lecture slides, I'm using this, this notation here where we have
10:15
the bias separately. So I'm initializing the weight vector,
10:19
and the bias units, the bias unit is just a single value,
10:23
that's just one number. And the weights, the weight vector, it
10:27
depends on the number of features, right? So I make this
10:29
a column vector, sorry, a row vector. So this is then this
10:38
equal to m, the number of features. All right. So here,
10:43
I'm just setting up my weights and bias and setting them to
10:46
zero. Later on, for certain algorithms for stochastic
10:50
rendition, it's better to initialize them to small random
10:53
numbers here for the perceptron, it's not necessary. But for
10:56
neural networks, it will be necessary later on, we will see
10:59
that in the forward method, I'm computing the net inputs,
11:05
actually here in linear. And then I'm predicting the
11:08
prediction, computing the predictions, that's my
11:10
threshold. So this is the net input. I'm calling it linear,
11:15
because later on, we will also see linear layers in pytorch,
11:20
they are called linear, and they are basically computing net
11:27
input. So this is you can see the dot product between the
11:33
input vector and the weights. So that is computing this part
11:38
here. And then I'm adding the bias here. I can actually make
11:43
this bigger. Alright, um, then here we have our threshold
11:50
function, this threshold function is just using NumPy
11:52
where so how this works is it's saying if linear, so if the net
11:56
input is greater than zero, then output one, otherwise output
12:01
zero. So it's our forward method. And here is our
12:07
backward method. So the backward method, why am I calling it
12:10
like that? It is for computing the arrows. So usually, yeah,
12:15
when we have deeper neural networks, we will use something
12:18
called back propagation, where we look at the outputs. And then
12:21
based on the outputs, we adjust the inputs. So in that way, we
12:25
run the forward method to produce the predictions. And
12:29
then we compute the arrows and then update. So it will become
12:33
more clear when we have a deeper network where there's really
12:36
like a back propagation going on. So these are our two
12:41
methods. So backward is computing the arrows, which is
12:46
the difference between the true class labels and the predictions.
12:49
And forward is used to get the predictions in the first place.
12:55
Let me see here. So this is
12:59
what we just implemented. So we implemented here the prediction
13:03
that's going on here, prediction is equal to step A. And then
13:08
step B is the backward pass with which gives us the arrows. And
13:14
now we have to put everything together. So I implemented train
13:19
method here. So for so this train method is basically the
13:24
whole, the whole thing here. So for epoch in the number of
13:29
epochs, so this is for every training epoch. And then for
13:34
every training example, this is here, this part, we perform the
13:41
four paths path, backward path, and update. Alright, so since
13:49
backward is already doing all forward, we just call backward
13:52
here. There's some ugly reshape here going on. And that is
13:56
because we are making the vector dimensions match. Otherwise, you
14:00
will get some arrows. So here, I'm just making the dimensions
14:04
met, you can maybe let's take a look. So here, this will be one
14:13
row and m columns. So it will be I think this is called a row
14:19
vector I said earlier, the other one was a row vector. But yeah,
14:21
I'm always confusing the words, row vector and column vector.
14:25
Because here, this is just one, one row and multiple columns.
14:29
But this is because there are multiple columns, but still
14:32
called row vector, because it looks like a row. Anyway, so
14:35
here, we have this row vector here. And this has to have the
14:39
same dimension as why it's in this way. I'm just making this
14:44
the same dimension. So you can compute everything nicely.
14:51
Otherwise, you will find there will be a dimension mismatch. So
14:54
there's just a reshaping going on here. And then here, we
15:01
perform the update. So again, I'm doing the reshape
15:05
afterwards, so that we get the original dimensions back,
15:08
because because the weights here, they also have the same.
15:14
So see, we are matching the original dimension. So we're
15:18
just reshaping so we can add to it. Otherwise, there will also
15:21
be a dimension mismatch if this is just a single number, or if
15:24
it's a one times m vector instead of m times one vector.
15:28
So yeah, this is annoying to do this reshaping, technically would
15:31
also I think not be necessary if I remove the dimension from
15:34
everywhere. But here, that's more explicit actually doesn't
15:38
hurt. Just like you have to be aware of that. And then also we
15:44
update the bias. So the bias, it's just updating it by the
15:49
arrows. The reason is, think about it, if we would have one
15:54
here, if I have a one here, so this would be one times the bias
16:02
unit instead of so the input would be the one, right. So
16:09
instead of saying errors times the feature, we would have be we
16:13
would have error times one, right. So error times one. And
16:18
we can cancel the ones instead of writing it like this. Since
16:22
we have the bias separate, I can just cancel this, we don't have
16:25
to include that. Yeah, the next evaluating it. So evaluating
16:31
the performance here, I'm just doing the forward pass. And then
16:35
compute the accuracy. The accuracy is computed by checking
16:39
how many of the predictions match the true label, and then divide
16:43
by the data set size. So it will be giving me a number between
16:47
zero and one. Alright, so this is my perceptron. And then here,
16:54
I'm training it. So yeah, initializing it, and then
16:58
training it for five epochs. And then I will print the model
17:01
parameters afterwards. It's pretty fast. So we get the
17:07
weights, the weight vector 1.27 1.346. And then the bias is
17:12
minus one in this case. And now we can evaluate it, compute the
17:16
accuracy. So the test set accuracy is 93%. It's not quite
17:20
100%. On the training set, it should actually have 100%,
17:27
right? Because it's linearly separable, this data set, and
17:32
it should converge if it's linearly separable. Let's do
17:39
that. Yeah, that's 100%. Everything is classified
18:01
correctly tested is not as good because we may overfit. So let's
18:06
take a look at the decision boundaries. So here is some
18:10
complicated code to compute the decision boundaries. It's
18:13
actually not complicated is what I did is I rearrange things
18:16
here, right? So what we have is if you think about it, the
18:22
decision boundary is greater or equal to zero. So everything
18:26
hinges upon zero. So if we have our computation, it's x zero
18:32
times w zero, right? Plus this on it and put x one times your
18:40
one with me. Yeah, that's correct. Let me just wanted to
18:48
bring that a little bit more closer together. It's easier to
18:50
see and then plus the bias, right? So this hinges upon zero.
18:54
And now let's see on nets. So what we're interested in is what
18:59
we're doing here is we are taking one fixed number. So
19:04
let's say we're taking for feature zero, the minimum value
19:08
of minus two. So we are going to the left hand side here. And
19:11
then we want to find so this is
19:15
for x zero x. So x zero is the x axis and x one is the y axis.
19:21
So we take minus two this data point here. Or actually here, we
19:25
only know minus two, and we want to find the corresponding x one
19:29
value. So this is this is x zero. So it's at minus two. So
19:35
what is the corresponding x one value? So we have to rearrange
19:39
this solving for x one, right? So what we do is we move this
19:45
stuff, and this to the left hand to the right hand side. So we
19:48
have x one times w one equals two minus x zero times zero
20:02
minus b, right? So I'm just subtracting this and this. So
20:07
it's now on the right hand side. And then I want to know x one,
20:10
right? So I divide by w one. So when I divide this,
20:13
and so this is basically essentially what I've written
20:21
here. So I get the x one value, I'm calling it min. The reason
20:25
is because it's the left hand side, then I'm doing the same
20:27
thing for the right hand side. So I'm doing it for the right
20:31
hand side. I'm again setting x zero to some value, I'm setting
20:35
it to two here. And then I'm finding the corresponding y axis
20:39
value, which is this x one max here. So I'm doing the same
20:43
thing, just rearranging. Now I'm using a max value. And then I'm
20:46
connecting these lines. And that's how I get this. I've done
20:50
this here for the left hand side for the training set and right
20:53
hand side for the test set. So yeah, one is the training set,
21:00
and one is the test set.
21:01
So this should be the maybe easier to write like this. The
21:16
decision boundary doesn't change actually, because it's the same
21:19
for the training and test set. Just the data set is different
21:22
because the decision boundary only depends on w, right? So we
21:27
are providing these are fixed values, we are providing them.
21:29
And the decision boundary only depends on these parameters on
21:32
the model parameters. So the decision boundary does not
21:35
change here. So this is for the training set. And this is for
21:39
the test set here on the right hand side. And you can see in
21:42
the training set case, it perfectly classifies these
21:44
examples. And on the right hand side, this is the test that you
21:49
can see, it's maybe fitting some of the data too closely. I mean,
21:53
there's no other way, actually. But it happens that here in this
21:56
case, it doesn't perform well. Actually, yeah, there's a
22:01
different way. If you would fit the boundary like this, oops,
22:04
like this, more, more straight, then you may get these right,
22:09
but it just happens so that these data points are not in the
22:13
training set. So the model doesn't know that it should
22:15
shift the boundary more to the right here. So in this way, the
22:19
model does actually a good job and on the training set, but on
22:22
the test set, it's it's not so good. So in that way, it's
22:25
actually this term is called overfitting because it fits the
22:28
training data a little bit too closely, and doesn't generalize
22:31
so well to the test set. Okay, so this is how the NumPy code
22:37
works. In the homework, you will be playing around with this a
22:40
little bit more and then re implemented in just regular
22:43
Python, just removing some of the dot products, replacing
22:45
them by for loops and so forth. Um, yeah, the pytorch code, I
22:51
don't need to talk about this, I think, because it's the same
22:55
same. So this is exactly the same. This is exactly the same.
22:59
This is exactly the same. There are some differences here. But
23:03
yeah, this is exactly the same this this except that I'm now
23:07
using torch tensor instead of NumPy arrays. But yeah, I
23:12
prepared an overview here to show you the main differences.
23:17
So in class, we will be talking about this in more detail when I
23:20
talk about pytorch thing next week or in two weeks, depending
23:26
on how far we get next week. So here I highlighted the
23:30
differences, though it's also in the slides from the slides. So
23:33
on the left hand side, this is the pytorch implementation. On
23:36
the right hand side is the pytorch. So NumPy and pytorch.
23:39
And you can see there are not that many differences. So the
23:45
way the weights and biases are implemented here, we are using
23:49
NumPy zeros here, we are using torch zeros, we had a bit more
23:52
specific here, instead of saying NumPy float, we say torch float
23:56
32, it's a 32 bit, I have this device here, cause on the way I
24:01
implemented things that would also run on the GPU, if there's
24:05
a GPU available, if no GPU is available, it will use the CPU.
24:08
So there's this device here, which is provided here,
24:11
optionally. It's not necessary, though. And what's a little bit
24:17
more, it's a little bit different. So here, I mean,
24:20
there are multiple ways you can write that you can also use a
24:22
plus function, to be honest, I just happened to use torch dot
24:25
add, but I could have also used a plus. So what I mean is I
24:29
could have, I don't know why I actually did it so complicated.
24:32
I could have just had a plus here and remove this torch at
24:37
should still work.
24:38
Um, yeah, and then the mm is matrix multiplication. And so
24:49
in NumPy, we usually write dot in torch, we write a pytorch,
24:54
we write mm for matrix multiplication. But in pytorch,
24:59
the dot function can also do matrix multiplication. So in
25:02
the way, it is kind of like the same thing, it's just looks a
25:05
little bit different. The where function and pytorch is a bit
25:07
more, I would say involved, not that much more involved, but it
25:11
has to have placeholders, such having a one and zero, it needs
25:15
to have a tensor here. So I'm creating this as placeholder
25:19
here and providing them. But it's the same concept. And then
25:22
what's a little bit different here is the last part. So instead
25:26
of numpy dot sum, it's torture sum. Here, I'm converting it to
25:31
a float. Because otherwise, it will be an integer. And then
25:35
an integer divided by some value will give an integer, what we
25:41
want to have a float, because it's a fraction between zero and
25:44
one. So if you don't do that, you will get back an integer.
25:47
And that's not correct, because the value of accuracy is very
25:51
between zero and one, which is why I'm casting this to float.
25:55
But again, the pytorch code will be covered in class in more
25:59
detail later. So um, yeah, that is what I wanted to say about
26:06
the code, you get to play around with that a little more in the
26:09
homework. Then here, for the optional convergence theorem, I
26:15
wanted to make a video about that. But I realize I talked a
26:19
lot about the code right now. So I honestly want to wrap up this
26:22
lecture, the next day will be probably short, so that in the
26:25
next week, we can start a fresh topic. So then we can talk a
26:29
little bit about the linear algebra background for deep
26:31
learning, some notation, a little bit about calculus, and
26:35
then get started with pytorch next week. So in that way, I
26:41
think this is not really necessary. So this is some
26:43
optional mathematical proof, I will leave it in the slides,
26:47
because I spent a lot of time making this. But yeah, you can
26:52
read through that, but it won't. So if you don't know about that,
26:55
you won't miss anything, because it's not relevant for deep
26:59
learning. It's just showing that the perceptron will not converge
27:04
if the data is not linearly separable. And you can try that
27:08
out in practice. So you can, for example, if you go to the
27:12
animation here, this is the animation that I showed you in
27:16
class, it's just as a Jupyter Notebook. And you can change
27:20
the data such that one of the blue points is here. So you can
27:24
change the class table of one of these points, or you can change
27:26
the class of one of these points. And then you can run
27:28
this, and you will see it will never converge. So here, this
27:31
one will converge eventually at iteration 49. But if you change
27:35
one data point, such that it cannot separate the data
27:40
correctly, it will go on forever, essentially. And this
27:44
is what the proof is about. So you can mathematically show
27:49
that there's a lower bound and upper bound for the size of the
27:52
weights. And based on that, you can basically conclude that it
28:01
will converge on if the classes are linearly separable. So I
28:05
won't go into too much detail about that, when it will
28:08
converge. So this is showing that it is, it will converge if
28:10
it's linearly separable. But only if it's a linear
28:14
separable. And yeah, in the last video, let me talk about the
28:17
geometric intuition about the decision boundary. So again,
28:22
don't worry about the convergence theorem, all you
28:24
have to know is that the code will run forever if the data is
28:29
not linear, simple, and otherwise, it's guaranteed to
28:32
find the solution. So it's guaranteed to find this boundary
28:35
if it exists. That's what the proof is about. Alright, so next
28:38
video, the geometric intuition.

##v24:

0:00
Yeah, as the last video for this week, I want to briefly talk
0:03
about the geometric intuition behind the perceptron. So this
0:07
is, I think, particularly interesting, because the
0:09
perceptron rule is so simple. And yeah, here, we will briefly
0:13
go over why it actually works at all. So if you recall, this is
0:18
the perceptron learning algorithm. The slide is just
0:21
copied from an earlier video. So it's just for recapping what's
0:25
going on. So if the prediction is correct, nothing happens. So
0:30
we don't need to update the decision boundary. However, if
0:33
it's incorrect, there are two scenarios, scenario A and a
0:36
scenario B. So scenario A is if the output, the prediction is
0:41
zero class able zero, while the target is class label one. And
0:46
scenario B is if the prediction is one, and the class label, the
0:51
actual one is zero. So in both cases, we make a mistake. And
0:55
then we have to update the perceptron. So in the first
0:57
case, in this case, how we update the decision boundary is
1:02
by adding the input vector, so the feature vector to the weight
1:07
vector. So why do we have to add the input vector to the weight
1:11
vector? And why does it help at all? So in this video, I want to
1:14
briefly go over the intuition behind that. So here also, yeah,
1:18
in code, just again, the outline of the learning algorithm, if
1:21
it's more clear this way, so we initialize the weights with all
1:25
zeros, or we can also use all small random numbers doesn't
1:28
really matter. And then for every training epoch, we iterate
1:32
over the training examples. And then we compute the prediction.
1:36
And then you update if we make a mistake. So here we compute the
1:39
arrow and then update. So that is the basic concept behind the
1:44
perceptron that we talked about before. Now, regarding the
1:49
geometric intuition. So imagine you have these two classes here
1:52
on class zero and class one. And here that's the black line here
1:57
is the decision boundary. So the weight vector turns out to be
2:02
perpendicular to the decision boundary. Can you think of the
2:07
reason why the weight vector would be perpendicular to the
2:12
decision boundary? So perpendicular here means 90
2:14
degree angle, why is there a 19 degree angle between the weight
2:18
vector and the decision boundary, maybe pause the video
2:20
for a few minutes and think about it a little bit, maybe you
2:25
get the idea, if not, don't worry, it's a little bit, I
2:28
would say, it's not immediately obvious.
2:34
Alright, so the intuition behind it is why the decision boundary
2:38
in the weight vector of this 90 degree angle is because if you
2:42
think of our threshold, if we compute or look at the dot
2:46
product, let's ignore the bias for now, if we just look at the
2:50
dot product of the weights and the feature vector, we make a
2:53
decision at zero, so whether it's greater or smaller than
2:58
zero. So if it's smaller equal to zero, the net input, so this
3:02
is the net input. If it's smaller equal to zero, we
3:09
predict or return class able one, if it's greater than zero,
3:12
we return one, so everything kind of hinges upon the zero
3:16
here. And if we write the dot product a little bit differently
3:21
as the length, magnitudes of the two vectors, and then the angle
3:26
between them, the cosine of the angle, then we have the
3:29
following equation, you probably have seen that from linear
3:31
algebra classes. So in order, so in order not to have this dot
3:38
product zero, like if we want to have it zero, um, yeah, what we
3:41
would have is to have at least one of these two terms zero, but
3:46
this is not the case, right? Because the vector is not zero,
3:49
unless it's all values are zero. But um, yeah, so in this case,
3:56
that would be one scenario where we might have a case of zero.
3:59
Another case is where the decision boundary, sorry, the
4:06
angle here between the weight vector and the decision boundary,
4:09
when this term here becomes zero, and when is this term
4:13
zero, the term is zero, if we have a 90 degree angle here
4:17
between the two, right, because the cosine of 90 degree is zero.
4:22
So by setting this part here, this part to zero, we get a
4:26
weight vector that actually has some length. And that has an
4:31
angle between the decision boundary and the weight vector
4:33
of 90 degree.
4:34
Yes, so what else does that mean? So if we think about the 90
4:43
degrees a little bit more, so what we can deduce then is that
4:48
there will be an angle smaller than 90 degree on this side
4:54
here of the decision boundary. So by that, I mean, if you have a
4:58
training example, or a data point that is somewhere, you
5:02
know, on the right side of the decision boundary, let's say it
5:04
can be here. So if we have a feature vector that is here can
5:08
also be here doesn't really matter. So anywhere where we
5:13
have a decision.
5:22
Yes, so what else does this mean? So let's focus in a little
5:25
bit more on the 90 degrees here that we just talked about. So
5:29
now every input vector on this side here on the right hand side
5:33
will have an angle with a weight vector that is smaller than 90
5:36
degrees. So again, in blue, this is the weight vector here. And
5:43
now if I take a training example, and put it anywhere on
5:46
the right side of the decision boundary, for example, here, so
5:49
if we look at this one, it has this angle that is smaller than
5:53
90 degree. If we put it here, same thing is true. Or if we put
5:57
it here, outside, maybe it doesn't really matter. Also, we
6:00
have always this 90 degree angle. And also you note that it
6:04
doesn't really matter how large the weight vector is. So if we
6:08
scale the late weight vector by a factor of 100 or 1000, it
6:12
doesn't matter, it will be still than the angle because whether
6:16
this is longer or not doesn't really matter. The same is true
6:19
for the training examples, if they are super large, if let's
6:22
say one training example is somewhere here, still the 90
6:26
degree angle, or smaller, sorry, smaller than 90 degree angle. So
6:30
the magnitudes of the weights and features doesn't really
6:33
matter whether we scale them or not. However, the updating the
6:37
learning can be a little bit faster if they are scaled, which
6:42
is why I had the standardization in the code example. But yeah,
6:47
so there's one takeaway that the angle is smaller than 90 degree
6:50
on this side. And on the left side here, it would be of
6:53
course, greater than 90 degree, if we have a value here, that
6:58
would be greater than 90 degree. So everything, again, hinges
7:01
upon the 90 degrees here. Now, why is that again, interesting?
7:10
So let's now focus on the actual prediction case before I just
7:14
laid out where all the data set on the weight vectors are
7:18
oriented. Now, let's take a look at prediction case. So we have a
7:22
correct side and a wrong side. So let's assume we have an input
7:27
vector with class label one. And like I've shown you before a
7:33
weight vector for the correct prediction must be somewhere
7:37
such that the angle is smaller than 90 degrees to make a
7:40
correct prediction. Let me go back to just show you again what
7:43
I mean. So notice here, we have all the ones on this side. And
7:48
this is our weight vector here. So to make a correct prediction
7:52
that is predicting a new training example like this one
7:56
as class one, it has to be smaller than 90 degree, it has
7:59
to be in within the circle here, right. So that's what we are
8:02
looking at now. So we have here on this correct side. So if you
8:06
think of this as the decision boundary between the wrong and
8:09
the correct side, we have to have an angle between the input
8:12
vector and the weight vector that is smaller than 90 degrees.
8:15
So if we are within the 90 degrees, then we make a correct
8:19
prediction, because the product then will be positive greater
8:23
than zero, because um, yeah, because this term will be
8:28
greater than zero. Yeah, now let's take a look at what
8:33
happens if we make a wrong prediction. So here in red, I
8:37
have now a weight vector that is not ideal. So that is a weight
8:41
vector, where, when we make a prediction, where we make a
8:46
wrong prediction, because the angle is not smaller than 90
8:50
degrees, it's in fact, larger than 90 degrees now. So if it's
8:54
between a value between larger than 90, up to 270, we will make
9:02
a wrong prediction, because now the value of the cosine of that
9:06
angle larger than 90 and smaller than 270 would be negative. So
9:11
we would be smaller than zero. So we would make class zero
9:14
prediction, which is what happens here. So we have an
9:18
angle that is greater than 90 degrees. And then we would
9:22
predict the wrong label, we would predict
9:27
class level zero, although our input vector here, we assume
9:32
that it still has class level one. How do we make this
9:36
correct? And how can we correct this prediction that is by
9:39
moving the weight vector to the side of closer to the side of
9:45
the training example, so that the angle is smaller than 90
9:48
degree. So how do we do that? So in the perceptron algorithm, how
9:52
we do that is we add the feature vector. So the input vector, we
9:55
add it to the weight vector. So here, the dash line here, that
10:00
is the input vector. So here, that's the same input vector,
10:09
I'm just taking the input vector and adding it to my weight
10:12
vector. So maybe doing it step by step. So what we have is we
10:17
have our input vector, and we have our wrong weight vector.
10:22
What I'm going to do now is I'm taking this input vector, and
10:26
I'm adding it to the weight vector, like this, and then my
10:31
new weight vector will be like this, right. So then we will
10:35
have this smaller than 90 degree angle, which is shown here. So
10:39
by adding the weight vector, we can make the decision boundary
10:43
correct for this case. So this is if I go back here, this is
10:47
exactly what happens in scenario A. So we predict on the output
10:52
is zero, although the target is one. So this is when we go back
10:57
here, that is what we have, we have a label of one. And then we
11:00
predict zero, because we are on the right, wrong side here. But
11:04
we what we do is then we add the input vector to the weight
11:07
vector, which is what I've shown you in the previous slide. And
11:09
by that, we can correct the decision boundary. And yeah, if
11:13
you want, or like, you can also play through the same scenario,
11:17
if prediction and the targets are flipped. So the same concept
11:21
applies there too. Yeah, to summarize, the perceptron has
11:28
many shortcomings. So there are many problems with a perceptron,
11:32
which is why it's not commonly used anymore in practice, some
11:36
people still may use it in certain applications where
11:38
computational performance matters, because one advantage of
11:42
the perceptron is it's very simple to implement and very
11:44
fast. However, nowadays, many problems that we have in the
11:49
real world cannot be solved by this perceptron, which is why we
11:52
have fancy and deep learning methods. So let me go over the
11:56
shortcomings of the perceptron. So first of all, it's a linear
12:00
classifier. So you cannot have nonlinear decision boundaries.
12:03
If you think back of the x or problem, it cannot solve the x
12:06
or problem. Or if I, for example, just have another
12:10
simple problem where we have two classes like, like this, for
12:15
example, class zero and class, one like this around it. So if
12:21
we have these concentric circles, the perceptron cannot
12:24
classify these very well, because it can only do a linear
12:27
decision boundary like this or like this. And that is not
12:30
helpful. What we need is we have, we need a nonlinear decision
12:33
boundary like this, for example. So that is one shortcoming.
12:38
Another shortcoming is that it is a binary classifier. So it
12:42
can only classify two classes. But yeah, of course, there are
12:46
also extensions where you can use multiple perceptrons.
12:49
There's a method called one versus rest, or one versus all
12:53
or one versus one. So actually two methods that I can just
12:57
write them down one versus rest. Sometimes it's also called one
13:03
versus all, where you can just use multiple perceptrons, or
13:08
multiple binary classifiers. And one is called one versus one to
13:13
have multi class classification. Yeah, but it is like one single
13:19
perceptron cannot do multi class classification, because it's
13:21
just returning either a zero and one. Another shortcoming is it
13:26
does not converge if classes are not linearly separable. So what
13:30
does that mean? So that is exactly the problem related to
13:36
the convergence theorem that we have not covered. But in the
13:40
convergence theorem, it says it only converges if the classes
13:43
are linearly separable. So let me draw that out also. So if we
13:47
have a case, again, like let's say this, it will find a
13:54
decision boundary like this. However, if I have a data point
13:58
over here, then there is no decision boundary such that I
14:01
can classify everything correctly. So it will learn,
14:04
let's say this decision boundary, but then it
14:07
encounters this data point. So if we keep iterating, and then
14:11
it thinks, okay, I have to move the decision boundary further to
14:14
the right, like here, but then it gets these examples wrong. So
14:18
it then it thinks, okay, I have to move it back to the left. So
14:21
it will keep on moving the decision boundary back and
14:25
forth, and it will never really stop updating. So in that case,
14:30
that is also a problem if you want to have the final model.
14:33
Okay, that's fluctuating. It's like the longer you run the
14:37
algorithm, the more solutions you will get. So it will never
14:41
really finish updating. Yeah, and then also, another thing is
14:48
there are multiple solutions possible, if the classes are
14:52
separable. So now let's assume you have a problem that is, let
14:56
me do this a little prettier. Let's say no, you have a problem
14:59
where you can linearly separate these classes, let's say, like
15:05
this. So one possible decision boundary is like this. Another
15:10
one is like this one is like this. So there are multiple
15:13
solutions. And it depends on Yeah, where you start with your
15:16
weights, which one is the best one, or which one is picked by
15:18
the perceptron before it stops updating. And yeah, this is
15:22
also kind of annoying, or can be annoying, there are multiple
15:25
solutions. So that I would say there's a best one, the best one
15:29
might be the one that is just in the center. Rather than
15:33
something that fits, let's say, the data very closely to the
15:36
left or very closely to the right, because one might argue
15:39
that putting the decision boundary in the center helps
15:43
with reducing overfitting, for example. But yeah, that is also
15:47
something the perceptron is not capable of. And in your later
15:51
lectures, the methods that we will be using, they are a bit
15:53
better with that. Alright, so that is just the other
15:56
conclusions on regarding the perceptron. So like, one last
16:01
thing, like a little fun fact. So yeah, back in the day, the
16:06
perceptron was used, or people try to use it to detect tanks in
16:11
photographs. So here on the left hand side would be a tank. And
16:16
here, there would be no tank. And they used the perceptron on
16:20
images to classify whether there's a tank in the photograph
16:23
or not. However, like we just said, the perceptron is very
16:27
limited. So why would that work at all? People found that it
16:30
worked. But there was like a little gotcha, a little mistake
16:34
or conceptual mistake. So because people didn't first
16:39
think about it very well. So what happened was that all the
16:42
forest pictures were darker than the pictures with the tanks. And
16:46
the perceptron simply recognized that darker photographs means no
16:52
tank and brighter photographs means tank. Of course, it had no
16:55
idea whether there was actually a tank or not. So if you would
16:58
have a dark photograph with a tank, it would, of course, get
17:01
that wrong. Yeah. And this was like a little fun fact about the
17:04
perceptron. I got that from this interview with Marvin Minsky,
17:08
who was one of the authors of this perceptron book I mentioned
17:11
where they kind of said bad things about the perceptron that
17:14
it was limited. So here's like a little excerpt from this
17:18
interview. So basically, it was looking for a scene at a scene
17:27
of a forest with which there were camouflage tanks in one
17:30
picture and no camouflage tanks in the other picture. And the
17:34
perceptron after a little training made 100% correct
17:36
distinctions between these two different sets of photographs.
17:40
Then they were embarrassed a few hours later to discover that the
17:43
two roles of film had been developed differently. And so
17:46
these pictures were just a little darker than all of the
17:49
pictures. And the perceptron was just measuring the total amount
17:52
of light in the scene. So it was just counting the pixel values,
17:57
the pixel brightnesses. But it was very clever of the perceptron
18:00
to find some way of making this distinction. Yeah, I think I
18:02
would admit that it was actually kind of exploiting the fact
18:06
that photographs were brighter and darker. But of course, it
18:08
had nothing to do with whether there was a tank in the picture
18:11
or not. It was just how they developed the film. Alright,
18:14
with that, I want to end this lecture, which was a little bit
18:16
long, I will, in the future, try to keep that shorter. But I
18:19
didn't want to split this topic over two weeks. So in the next
18:23
week, we will cover some basic linear algebra. I mean, just
18:27
some ground rules that we will be using. And then hopefully
18:30
also slowly get into implementing more
18:33
sophisticated methods in pytorch.

##v25:

0:01
Yeah, hi, everyone. I can't believe we already completed the
0:05
second week of the semester. But in the meantime, there have been
0:08
a lot of interesting things happening in the deep learning
0:11
and artificial intelligence world. So here, I'm back with
0:14
stuff in the news number two, some of the interesting things
0:17
that happened this week. So we will be mainly seeing things
0:21
from my perspective, things I've been reading about. But I also
0:23
had to trim down the list. Yeah, quite a bit because there are
0:27
always lots of interesting research papers and news
0:30
articles coming out. So but with that, let me not waste too much
0:34
time on the introduction and get started with the stuff in the
0:37
news.
0:39
Yeah, one of the things that piqued my interest this week was
0:42
this article entitled, semi researchers explore crazy idea
0:46
of automating AI paper reviews. So paper reviews, that's a very,
0:51
I would say sensitive topic in the deep learning and machine
0:54
learning community right now. Because yeah, these are top
0:57
conferences where people submit papers like ICML and Europe's
1:03
there are usually around I don't know, five to 10,000, let's say
1:06
10,000 submissions every year nowadays. And it's pretty
1:10
challenging to find or to maintain good quality reviews.
1:13
I'm also a reviewer for both of these conferences and get about
1:17
like three to five papers to review. Also, the timeline is
1:20
very short. And yet, if you have 10,000 submissions, you have to
1:24
find also 10,000 reviewers, every one of those reviewing
1:29
three papers or more. And it's really hard to keep up with
1:32
these numbers. So I think that was what motivated these people
1:36
to work on this idea. I would say I'm not honestly convinced
1:40
this is a good thing to work on or even try to automate paper
1:44
reviews with AI. Maybe it's good for checking general formats
1:49
like beyond the conventional quality checks, like whether the
1:56
paper has, or has the right page limit or right template and
2:00
things like that. Maybe AI can be used for some quality checks.
2:04
I'm a little bit skeptical whether it can be used to really
2:08
make or should make decisions on the quality or regarding the
2:13
quality of a paper. Nonetheless, I think this is an interesting
2:16
project from a language perspective, like assessing how
2:20
far deep learning has come in terms of understanding human
2:24
language and contents of more comprehensive texts. And also
2:29
what I found as a general interesting takeaway, these most
2:34
frequently mentioned qualities of a good review. So these are
2:37
things to assess whether a review a peer review is good or
2:42
not. And this is actually something I'm thinking about
2:44
adopting as a rubric for our class projects. Because like I
2:48
mentioned before, there will be a peer review for our class
2:51
projects at the end of the semester. And I will of course
2:54
share more details later on during the semester. But this
2:57
might be a good rubric for me also to assess whether the peer
3:01
reviews you write about the reports of other students might
3:04
be good peer reviews. So something like decisiveness,
3:08
comprehensiveness, justification, accuracy, and
3:11
kindness. Kindness is also very important because yeah, reviews
3:15
can sometimes be grumpy. And I think that's usually not very,
3:18
not very nice and not very fair to write grumpy reviews.
3:23
Alright, so yeah, this model they proposed is based on Bert
3:27
who went Bart Bart is a denoising autoencoder. It's
3:32
related to Bert. And this is like for pre training sequence
3:35
to sequence models, we will talk more about sequence to sequence
3:39
models. Yeah, and part five of this course at the end of the
3:42
semester. So sequence to sequence means that the input
3:46
to the model is a sequence and the output is also a sequence
3:49
instead of just a single prediction. So instead of just
3:52
predicting a single class table, you are outputting also a
3:55
sequence, for example, text, a simple example also of sequence
4:01
to sequence models would be for example, language translation
4:04
where you translate from one language to the other. So here
4:08
they involve, of course, human annotation. So they annotate the
4:11
paper with these statistics, I think, on some stands for
4:15
summary, or actually posted here, summary, or MOT is for
4:19
motivation, as you be as for substance. So they tag, humans
4:24
tag the article with these different aspects, then they
4:27
train a tagger that can do the same thing. Then there's some
4:32
process post processing going on, and then a human has to
4:36
evaluate the results. So if you're interested in this
4:39
project, or want to read more, there's the paper here on
4:42
archive. And they also posted, yeah, the code on GitHub. So if
4:46
you want to play around with us, if you're curious. All right,
4:49
moving on, you've probably never wondered what a night made of
4:53
spaghetti would look like. So this is not new news. It's a
4:57
little bit older, it's like a month old or something. That's
4:59
like a machine learning project called Dal E. It's like I think
5:04
a mashup of wall E and the artist Dali. So in that way,
5:09
here, what the researchers did is they trained another language
5:13
model, GPT three, 12 billion parameter model. And in this
5:18
Dal E model here, which is based on GPT three, or the concepts of
5:22
GPT three, what the researchers do is they train a model on
5:27
images and descriptions of images. And then, so these are
5:32
the inputs. So you can think of it as image net, for example.
5:35
And then you can query the model and it gives you outputs and the
5:39
outputs outputs are mashups from the text input. So for example,
5:44
you can type in spaghetti night or night made of spaghetti, you
5:49
can type that in and the model will produce new images that
5:53
have both concepts in common, for example, night and
5:57
spaghetti. And here are some some of the results of nights
6:02
made out of spaghetti. So these are images that don't exist.
6:05
This is something the model synthesized. Unfortunately,
6:10
yeah, the paper is not available and the code is also not
6:13
available. But there is a blog article if you want to read more
6:16
about this project, I thought it might be also fun project,
6:19
especially if you're interested in generative models. Yeah, and
6:25
while the Dalai paper and code are currently not available yet,
6:29
one part of Dalai is available, this so called clip model or
6:33
approach. So clip stands for contrast of language image
6:37
pre training. So this is something that Dalai uses under
6:41
the hood. It's also based on GPT three, I think. So and what
6:47
clip does it's you can think of it as Yeah, and almost like an
6:51
image classifier in that sense, but it is doing something clever.
6:55
So clip is based on zero shot transfer. So here, zero shot
7:00
means classifying something where you don't have any training
7:04
example for. So as I mentioned earlier, I'm also working a lot
7:08
in the area of few short learning with my student
7:12
genre. And in a few short learning, we have this setting
7:16
on like, n shot k way, few short learning. So the n in n shot few
7:26
short learning stands for the number of examples per class in
7:30
case the number of classes. So for example, if you have, let's
7:34
say a five, short 10, way few short learning problem, that
7:41
means you have 10 different classes, but only five examples
7:45
per class are very small problem. And it's very
7:49
challenging to develop deep learning systems that can work
7:52
with such small data sets. So zero shot is even more extreme.
7:56
It really means you have zero examples. So in this case, the
8:00
model should predict something even though it may have never
8:03
seen this class before. So how would you approach this? So for
8:06
that, the researchers use natural language supervision,
8:12
and multimodal learning. So multimodal learning stands for
8:16
our means using different data sources. So here they use image
8:21
data and text data. So that's where the natural language
8:24
supervision part comes in. So in particular, they are predicting
8:27
novel image classes based on word embeddings. So when they
8:32
train the data set, they are the model, they use both
8:36
descriptions of an image, and the image itself. And then if
8:40
they see a new class, they can use the word embeddings or the
8:43
descriptions to predict the class. So here's an example of
8:48
that. So this is from the paper, or the blog post, I think that
8:54
I linked here. So what they do is here, they compare them up
8:58
model with a regular residual net 101. That is something we
9:02
will also talk about later in class, that's a convolution
9:05
network trained on, I think it's yet they are trained on
9:10
image net. And I should say, um, none, none of this clip thing is
9:18
fine tuned to these data sets. So it's trained on a different
9:21
data set, and then applied to data sets, it has not been
9:24
fine tuned to. So this rest net here was trained on image net,
9:28
and it reaches 76.2% accuracy prediction accuracy, this clip
9:33
model, which was trained on a different data set, also
9:36
reaches 76.2% accuracy on this data set. But what's more
9:40
impressive is it also achieves good performance on different
9:45
types of image nets that were not contained in this training
9:49
set. So in that way, this clip model, um, yeah, generalizes
9:54
better to other types of data sets by this concept of this
9:58
contrast of language image pre training. So that is also, I
10:02
think an interesting idea or approach. And you can also have
10:06
to find more about this in the paper here. And the code is also
10:09
available here. And this I think can be potentially really
10:12
useful if for example, you get developed, for example, let's
10:16
say a self driving car, and you have a large data set, and you
10:19
want to look for specific videos or clips or different images,
10:24
like, I want to have an image of let's say a pedestrian crossing
10:28
a busy intersection. So in this way, you can have maybe this
10:31
model, finding your query very efficiently in a large data set.
10:37
And why is that interesting? Because yeah, you can imagine
10:40
you don't have to train the model on all possible queries.
10:43
If you have these word embeddings, you can search for
10:46
something that is similar to your input word embedding, and
10:50
it pulls out the corresponding image. So in that way, I think
10:54
this is actually a very interesting approach. Yeah, and
11:00
here's a big picture overview of how the method works. It has
11:04
been some time since lecture one, where I think I briefly
11:07
mentioned it, but contrastive pre training, that's a form of
11:12
self supervised
11:18
learning. And here in this particular case, what they do is
11:22
they train a model on text descriptions and images. So in
11:28
the example I gave earlier about self supervised learning, the
11:32
researchers used an image and then a transformed version of
11:36
this image and the model had to predict whether it's the same
11:39
image or not compared to an image that is different. So like
11:43
being able to distinguish different images from each other
11:47
and modified versions of the same image. And here in this
11:52
case, it's kind of a similar concept. But here it's based on
11:57
text data and image data. So they train this text encoder on
12:00
the test text description, and the image decoder on the image
12:04
description. So they produce then a so called embedding. And
12:08
then based on the text and the image embedding, the model
12:12
learns like the relationship. So it should be basically, let's
12:17
say for the I think that's what it means for the diagonal, if
12:20
you have an image from a certain class from this class and a
12:23
description that matches this class, it should give a high
12:27
relationship score or something like that. So you would train
12:30
the model basically to associate the right description with the
12:33
right image, then you can if you have a data set of descriptions
12:37
and images, you can shuffle them. And it should give you a low
12:39
score if you have a description that does not match your image
12:43
and so forth. So let's say you pre trained your model, then you
12:46
can create a data set classifier from text labels. So here what
12:50
they do is they embed the class label in a text description, for
12:54
example, here, a photo of a plane car, dog, bird, and so
12:59
forth. And then you produce these text embeddings. And now
13:05
imagine you have a new image that you want to classify, you
13:08
don't know the class label, that is what you want to find out. So
13:11
in this zero shot prediction, this means this class label
13:14
doesn't have to be necessarily the training set. So you don't
13:19
have to have an example of that if you have the right
13:23
embeddings. So in that way, what they have here is they have this
13:28
image, they go and give it to the image encoder. And then you
13:32
have an embedding and then you would pull out the text
13:36
description embedding that has the highest scores in this case,
13:40
a photo of a dog, for example. So in this case, you from the
13:44
text encoding and the image, you would then pull out the class
13:47
from that one. Yeah, that is on a high level, how this clip
13:51
method works. I mentioned the model GPT multiple times on GPT
13:56
two and GPT three. Unfortunately, GPT three is not
14:00
available yet. So this is a model by open AI for GPT two, I'm
14:05
actually not sure whether it's already available. I haven't
14:08
followed it very closely. However, there's I also saw now
14:12
an initiative to train an open source version of that model. So
14:17
here they say on our primary goal is to replicate GPT three
14:21
sized model, or models and open source it to the public for free.
14:27
So they train the models on the data set called the pile, which
14:32
is 825 gigabyte model, including like YouTube descriptions on
14:37
papers from PubMed and so forth. And it is like a 200 parameter
14:41
model. It's very big. So yeah, it's a big initiative, because
14:45
these models for us, normal people are really out of reach,
14:49
you really need a big company to be able to train such a model.
14:53
And I remember when the first bird or GPT models came out, I
14:58
think it was estimated like, the cost was estimated to be like
15:02
around $100,000 just to train the model. And I think for this
15:05
GPT three, which is magnitudes bigger, it's probably in the
15:09
realm of almost a million dollars to just train the model.
15:12
So that's, it's actually good, then that someone maybe does
15:16
that, you know, in a way that is then also available and free for
15:22
the public. Alright, so moving on, I also saw it's not
15:26
directly related to deep learning. But I also saw this
15:28
news article today. So it's about the popularity of
15:33
programming languages and tools. So this is by O'Reilly, and they
15:38
are based their analysis based on queries on their website and
15:42
books and things like that, like mostly search terms on the
15:45
website, and what people look for. So yeah, unsurprisingly,
15:51
Python is of course, the first place also, it already get or
15:55
it's growing again. So it's still not stagnating. So people
16:00
use more and more Python, which I think is, yeah, it's good to
16:04
know. So you know where things are headed. What I also found
16:09
interesting is Scala. So Scala, I thought personally, that might
16:13
be the next hot thing when I was in grad school, when I was in
16:15
grad school, everyone started talking about Scala at some
16:19
point, which is language kind of related to JavaScript, or I
16:23
think it, it runs in the JVM, the JavaScript virtual machine.
16:27
Personally, I have to say I never really used it. And now
16:30
seeing that has this big decline, I'm also glad that I
16:33
didn't waste my time learning a new programming language,
16:36
because that's also always a trade off. It's like the trade
16:39
of between doing research, getting things done and doing
16:44
things like learning new languages. So that is like a
16:46
trade off, you want to always be up to date with current
16:50
technology and what people are doing, because that's how you
16:53
keep up to date and can produce cutting edge work. But then
16:57
also, you don't want to waste your time by pursuing things
16:59
that are maybe not worthwhile. So for now, it seems like Python
17:03
is still a good choice for machine learning and deep
17:07
learning. Alright, so another interesting project I saw was
17:11
this approach or method by Facebook AI research where they
17:16
are teaching AI to manipulate objects using visual demos. So
17:20
it's currently very challenging still to train robots, there's a
17:25
field called reinforcement learning, as you recall from
17:28
the introductory lectures. So in this way, robots learn by
17:32
trial and error. So you train a robot to do something by having
17:36
it fail a lot of times. And there's another approach to
17:41
reinforcement learning called inverse reinforcement learning,
17:44
which is like learning based on a demonstration. However,
17:48
traditionally, it was kind of also not very easy, because you
17:51
had to have a virtual environment for that, where you
17:54
can simulate this behavior that you want your agent to mimic. So
17:59
here, a Facebook AI research proposed a model based inverse
18:03
reinforcement learning approach using visual demonstrations on a
18:08
physical robot. So that means the robot can learn by looking
18:13
at something on a video series of images, instead of having
18:17
this virtual environment, for example, a video game context, a
18:21
3d world, you can show the robot images of a task that a human
18:25
performs. For example, here, a human is grabbing a bottle and
18:30
moving a bottle around. If you show the reinforcement learning
18:34
agent the video, it can to some extent learn to perform this
18:39
behavior as well. So there's a video I can't unfortunately play
18:42
it in the slides. But if you're interested, yeah, you can find
18:45
out more here under this blog post address. And there's also
18:50
the code available on GitHub. Yeah, lastly, the last topic for
18:56
today is about t sny t distributed stochastic neighbor
19:00
embedding. And this is a very popular technique in deep
19:03
learning to visualize high dimensional data sets. So here I
19:08
have an image of MNIST. So MNIST, as you know, is a high
19:13
dimensional data set, right. So for MNIST, for these handwritten
19:16
digits, you have 28 times 28 pixels, which is on 784
19:22
dimensions. So you have a very high dimensional data set. And
19:25
you can really easily visualize that in a scatterplot, for
19:29
example. So you can use t sny though, to reduce the dimension
19:34
ID of this data set into down to two dimensions. And yeah, the
19:38
interesting aspect about t sny is that it preserves the
19:42
relationship between the high dimensional space between the
19:46
objects in a high dimensional space, and in the new lower
19:49
dimensional space. So here is the result of a t sny
19:55
dimensionality reduction into two dimensions, let's say you
19:58
have two features now x one and x two. And you can see that the
20:04
t sny algorithm takes these high dimensional 784 dimensional
20:09
MNIST embeddings, and puts them into this 2d space, such that
20:14
the relationship between the numbers is still preserved, you
20:17
can see all the zeros here cluster together, or the seventh
20:21
cluster together, or the force force cluster together, and so
20:27
forth. So you can see it kind of preserves the relationship or
20:31
the relative meaning of these numbers by when when it is
20:37
when it is projecting those into a higher dimensions, lower
20:40
dimensional space. And you can also think of it as principal
20:44
component analysis. But principal component analysis is
20:48
a two, it's a linear transformation. So PCA is a
20:54
linear transformation. And this method here, the t sny method is
21:00
not just a linear transformation, it's a little bit
21:02
more involved than that. I actually taught t sny in statistics
21:07
479. I have actually some slides I can upload. I had a full
21:12
lecture on that I don't want to go into too much detail here.
21:14
But it's a very cool method. It's really useful. But one kind
21:20
of downside of that is that you have to tune the hyper parameters
21:25
in order to make it perform well. And usually you don't know
21:28
because you don't know the labels, always, you don't know
21:33
what a good setting is. So there was a paper I saw this week,
21:38
it's about initialization is critical for preserving the
21:41
global structure in both t sny and UMAP. So here, the
21:45
researchers say that it's really important that you choose the
21:48
right parameters when you use t sny, the right hyper parameters.
21:53
And one of those is the random start, like how you start t
21:57
sny, the initialization. And here, they found that t sny
22:02
will perform much, much better if you use actually piece PCA as
22:07
an initial initialization, you basically initialize t sny with
22:11
PCA result. So in that way, they found that, for example, when
22:17
they compared t sny with PCA initialization, and the random
22:21
initialization that t sny performed much, much better on
22:25
and across everything here, almost everything. Um, I think
22:29
the way they measure that, and if I recall correctly, is they
22:33
measure the correlation between the distances and the original
22:38
space and the reduced space. So if I go back, they would
22:42
compute the distance between two images in the high dimensional
22:46
space. And then they would compute it in the low
22:50
dimensional space in the two dimensional space, and then
22:53
check the correlation for these different approaches. And they
22:55
found basically that using t sny with PCA really preserves the
23:01
distance between objects in the low dimensional space. Yeah,
23:06
here, as you can see from the title, there's another method
23:09
called you map. This is also a very good method. And it's
23:13
recently even become more popular than t sny, because
23:17
sometimes it's even better at preserving this structure. So
23:21
yeah, with that, this is t sny, I think you may probably want to
23:25
use it at some point in your class projects. It's really
23:27
useful for visualizing high dimensional data sets. But in
23:32
practice, it's not really only used for visualizing data sets.
23:36
It's usually also used for understanding what a deep neural
23:39
network does. For example, you would apply that to an embedding
23:44
of a neural network to really understand what information is
23:46
contained in the network. So if you have a big convolution
23:49
network, so you usually have layers that become smaller in
23:54
size, the deeper the network becomes, and then researchers,
23:56
for example, would take the later embeddings and then apply
23:59
t sny to see how well it separates on different classes
24:03
in the slower embedding and so forth. Yeah, just like a last
24:09
thing here about t sny. So inside could learn on the
24:12
random. Sorry, the initialization scheme is a
24:15
random initialization. And yeah, here you if you want to use
24:19
t sny in practice, according to this research paper, you want to
24:22
change that to PCA. So instead of using the default random, you
24:26
would want to use PCA because it performs better according to
24:30
this paper on the previous slide. And also there is a
24:33
discussion right now on the psychic learn issue tracker
24:36
where it's proposed to change this default behavior, so that
24:40
it will also use PCA by default. And then also there are some
24:45
other tips. So if you want to use t sny, I would recommend you
24:47
to check out this issue here where there's a more in depth
24:51
Yeah, discussion. And with that, I think it's already a long
24:55
video. So enough news for this week. I will see you on Tuesday
24:59
with the next lecture.

##v26:

0:01
Yeah, hi, everyone. I hope last week's lecture on perceptrons
0:04
was a nice, easygoing introduction into the overall
0:08
concept of supervised learning. So but yeah, of course, we want
0:11
to solve more complex problems, especially in deep learning here
0:14
in this class. So in this lecture, I'm gonna tell you a
0:18
little bit more about the linear algebra conventions for deep
0:21
learning. Because yeah, deep learning kind of heavily relies
0:24
on basic concepts of linear algebra for making the notation
0:28
a little bit more convenient, but then also to implement
0:31
things in code more efficiently. But yeah, no worries, these will
0:34
be relatively simple, straightforward applications of
0:38
linear algebra. So here, I just want to lay the groundwork so
0:41
that we can then later talk about how we represent multi
0:46
layer neural networks that can solve more complex problems such
0:49
as the X or problem and many other things like image
0:53
classification. So yeah, in this lecture, I want to briefly talk
0:57
about the use of tensors in deep learning, then how we work with
1:02
pytorch in terms of using or working with tensors. So this
1:07
will be then the concept of multi dimensional arrays. And
1:10
then I will talk a little bit about vectors, matrices, and
1:14
then the concept of broadcasting. So this third
1:17
section will be particularly about the broadcasting, which
1:19
makes the work with vectors, matrices and tensors more
1:23
convenient. Then lastly, I will end this lecture with some
1:27
notational conventions for neural networks. So there's some
1:31
little I would say on discrepancy between textbook
1:35
notations where we have linear transformations and textbooks as
1:38
the weight vector times the inputs and then in computational
1:43
tools like pytorch, it's usually the other way around to make
1:46
things a little more convenient from a computational
1:48
perspective. So here, I just want to give you an overview. So
1:52
then things will become easier later on in this lecture when we
1:55
talk about certain concepts like convolution networks and
1:59
recurrent networks where these things heavily rely on high
2:04
dimensional tensors. So but with that, yeah, let me then get
2:08
started with the first video of this week.

##v27:

0:02
Yeah, let's start by defining the term tensor and how it is
0:06
used in the context of deep learning. So yeah, tensor, a
0:11
tensor is a generalization of the concept of a vector matrix
0:16
and scalar and so forth. So for example, here's a scalar, a
0:21
scalar is also you can think of it as a rank zero tensor. And an
0:26
example of a scalar would be for example, a real number. So it
0:30
could be also an integer, for example. So but yeah, in the
0:33
context of deep learning, we will usually work with real
0:36
numbers most of the time, except maybe for the class labels where
0:40
we have integers. So here, for example, that would be a scalar
0:45
a single value like 1.23. And a vector would be a rank one
0:52
tensor. So you can see, we're adding a dimension to it vector
0:56
as a rank one tensor, and the matrix would be then a rank two
0:59
tensor. So a vector is a vector is like you can think of it as a
1:06
data container with n values in it. So that is usually
1:12
something you would find in a linear algebra book. However, in
1:17
our context here in machine learning and deep learning
1:20
concepts, contexts, we usually think of vectors as n times one
1:25
dimensional. So it's still written the same way as you
1:30
would find it in a linear algebra book if this if you
1:32
would write it like follows, we have n elements, one, two, two
1:37
n. However, we will assume there's another dimension there.
1:42
It's just one. So there's one other dimension with no values
1:47
in there. So it's essentially a very you can think of it as a
1:50
very slim matrix, a matrix with only one column. And that is
1:54
because you have for certain computations for convenience.
1:59
Yeah, and usually by default, I will denote the vector as a
2:03
column vector. However, when I write a transpose, we will also
2:08
sometimes use row vectors. So it's basically just a vector
2:12
transposed, which is now a one times n dimensional vector. So
2:16
yeah, regarding the matrix, he has an m times n dimensional
2:20
matrix. So m is the number of rows. And n is here the number
2:29
of columns. So that is just a general layout. So if n was one,
2:36
then we would have just this first column here. And you can
2:40
then ignore this one, this would be then a column vector, like
2:44
shown on the left hand side here. This is just yet to lay
2:48
the groundwork into the notation, but a vector in the
2:51
matrix, and the scalar are and how that relates to the concept
2:55
of a tensor. Now, in the context of deep learning and machine
3:01
learning, we usually use for the data, so called design matrices,
3:06
that's a common convention, we use the letter x, then we
3:11
usually refer to a design matrix, which is an n times m
3:17
dimensional matrix. So on the previous slide, what I was
3:20
writing on the previous slide was m times n dimensional, this
3:25
is just something you would find a linear algebra textbook, the
3:28
letters here m and n don't matter really. But there is a
3:31
convention in machine learning and deep learning that most of
3:34
the people use n for the data set size in terms of the number
3:46
of training examples. And m is the number of features. So this
3:57
is why I'm writing it as n times m. But it's also not super
4:01
important. It's just just a convention. And then like I
4:05
already talked about in the very first lecture, we will be using
4:10
the subscript for the features. So that's the feature index. And
4:19
here, the superscript, that would be the training data point
4:25
index or training example index, say call it training example
4:32
index. So if we have n training examples, then we would have the
4:37
indices one to up to n. And here, we would have up to m
4:41
features. For example, in the iris data set, we would have 150
4:48
training examples or data points and four features. So this would
4:53
be m and this would be n. Yes, on the previous slide, we have
4:59
seen rank zero tensors and called them scalars. And we had
5:06
for rank one tensors, the word vector and for rank two tensors,
5:12
we had the word matrix. Now for rank three tensor, how should we
5:18
call it? Unfortunately, there is no special word for that. So
5:22
usually, if we call or refer to a rank three tensor, we use the
5:26
word 3d tensor, or sometimes or often even just tensor in without
5:33
the 3d here in front of it. So yeah, um, what is a 3d tensor,
5:38
then a 3d tensor, you can think of it as a stack of matrices. So
5:43
if each of the box here represents a matrix, a rank two
5:50
tensor, then a 3d tensor would be in the context of deep
5:54
learning. Like you can think of that like a stack of matrices,
5:58
so multiple of these matrices stacked on top of each other.
6:02
For example, here, this would be a stack of p matrices, and each
6:06
of the matrices here is m times n dimensional. So here we have m
6:12
times n dimensional matrices, and we have p of such matrices
6:16
here. And note here, the m and n, they are really arbitrary,
6:20
they don't refer to the features and training examples. These are
6:24
just some arbitrary letters, I was just using m and p, because
6:27
they are commonly used. But here, don't don't think of them
6:31
as training examples of features, they're just generic
6:33
terms here, or letters. So in practice, where we encounter
6:38
these 3d tensors in deep learning is, for example, when we
6:42
work with image data. So you can think of a single image here,
6:46
like this cat as a 3d tensor, where we have, for example,
6:54
three color channels, the color channels are for red, g for
6:58
green, and B for blue. And each of these color channels
7:02
consists of pixel values, for examples, could be a 100 times
7:07
100 matrix containing the pixel values for each of the color
7:11
channels. And combined, they are basically a 3d tensor. And that
7:16
would be a case where we encounter a 3d tensor when we
7:19
work with image data in deep learning. However, it doesn't
7:24
stop there with 3d tensors. And practice actually work with 4d
7:29
tensors in deep learning, because we have a training set
7:31
consisting of multiple of such 3d images. So you can think of
7:36
the 4d tensor here, if I go back as a stack of multiple of these
7:42
3d tensors, basically, so stacking multiple of these. So
7:45
here, on the right hand side is just an example of the cipher 10
7:49
data set. So each each of these is an RGB on 3d tensor. Yeah,
7:58
and then also regarding the dimensionality. Usually, in
8:02
deep learning, we have the dimensionality of these four
8:06
tensors as n, c, h, w, where n is the number of training
8:14
examples. Then c is the number of color channels, for example,
8:25
three in the case of RGB. So this is the color channels. And
8:31
then h is the height of the image. And w is the width. So in
8:41
that way, on these last three dimensions here, they are
8:46
basically our features m. So in this case, we have c times h
8:50
types w features, and n is still on our training examples. So if
8:55
we don't use deep learning, we would reshape that we would
8:59
reshape that into a matrix design matrix, which is n times
9:04
m dimensional, where m is really c times h times w. Alright, so
9:12
but we are we are not working with color images yet. That
9:15
would be something when we encounter convolution networks,
9:18
where we talk about this. But I also plan to, yeah, to use a
9:22
simpler model with color images, where we explore then also this
9:27
this reshaping. So but don't worry about it yet. Also, yeah,
9:33
one more thing I wanted to say about tensors, you probably
9:36
heard about the tool, TensorFlow. So TensorFlow has
9:42
the name tensor in it. And here, in the context of these tools,
9:46
like TensorFlow, or NumPy and pytorch, the tensors really
9:51
refer to the concept of a multi dimensional array. So multi
9:56
dimensional array, you can think of it as a data structure or a
10:00
computational data structure for storing or representing a
10:05
tensor. So in mathematics, we say tensor, but in practice,
10:11
when we do coding, these are essentially multi dimensional
10:14
arrays. And it just happens in TensorFlow, these multi
10:20
dimensional arrays are called tensor. In NumPy, they are
10:23
called nd array, where nd array stands for n dimensional array,
10:30
like multi dimensional n dimensional. And in pytorch,
10:33
they are also called tensor, but they're essentially all the same
10:37
thing. So here's just an example. So here I'm creating
10:41
importing torch creating a tensor. And this tensor is two
10:46
by three matrix. So two rows, three loops, three columns. So
10:51
this is really two by three matrix. And then here, what I'm
10:55
doing is I'm using t dot shape. And notice in NumPy, there's
11:00
also a t dot shape, you probably know that. And this gives you
11:03
the dimensions of the multi dimensional array or tensor. So
11:08
you can see here two and three, this is on the dimensionality,
11:12
or in fact, it's the numbers of numbers of values in each
11:16
dimension. So this would be a two dimensional array, because
11:20
there are two dimensions, there's a row and a column
11:22
dimension. So this would be the first and the second dimension.
11:32
So the number of indices and shape would be the number of
11:35
dimensions. And also, conveniently, you can also call
11:39
ndm, which stands for the number of dimensions, and it will also
11:43
return to two. So ndm is essentially the same as calling
11:48
length, sorry, link in Python, link on t dot shape. So it's
11:55
just a shortcut for doing that. So yeah, just wanted to briefly
11:58
highlight 10 source in the context of pytorch tensor flow
12:03
are the same as multi dimensional arrays in NumPy is
12:06
really the same concept. Yeah, and here's also just a nice
12:10
summary from the deep learning with pytorch book, where all the
12:14
terms are here at one glance, scalar vector matrix tensor. So
12:19
in this case, a 3d tensor, and here are higher dimensional
12:22
tensor. So n dimensional tensor, if yeah, so in this case, you
12:27
actually don't know how many dimensions could be arbitrary.
12:30
So it's also just making fun of it that this is something we
12:33
can't visualize in our head anymore. Because, yeah, as
12:36
humans, we can only really think of three dimensions with a
12:39
fourth dimension, that becomes all some gobbledygook here.
12:43
Here. And yeah, this is just a short summary here of what we
12:47
just discussed in the previous slides. And in the next video,
12:52
I want to briefly talk about more about tensors and pytorch.
12:56
So if this was just a little bit short, um, yeah, I will talk
13:00
more about this in the next video.

##v28:

0:00
So in this video, I want to briefly talk about broadcasting,
0:03
which is a concept that makes working with vector and matrix
0:07
computations more convenient on a computer compared to, for
0:10
example, pen and paper or the traditional way of doing linear
0:13
algebra. All right, so yeah, let's start with vectors. So if
0:19
you look at this notation here, w transpose x plus b equals z.
0:24
So you recall how this is called like to check yourself, there's
0:28
a certain word for that result. Maybe pause the video, think
0:33
about it briefly. Yeah, so the result is net input. So we
0:38
learned in the perceptual nature that we usually call that the
0:41
net input. So I mean, I'm just providing this as a simple
0:45
example here. So we're x and w would be two vectors here. So we
0:51
would do w transpose dot x plus b. And this would be the proper
0:58
linear algebra way of computing the net input. So in linear
1:02
algebra, the supported operations for a vector
1:06
addition, you can also think of subtraction if we add a vector
1:12
with negative values, and then the inner products like the dot
1:15
product would be one of them, and scalar multiplication. So we
1:19
can multiply a vector by a scalar. So these are the only
1:24
proper I would say, yeah, basic vector operations that you would
1:28
find in a traditional linear algebra textbook. Now in
1:33
practice, though, if you work on a computer, there are a few more
1:36
possibilities that can make our life easier. They wouldn't be I
1:40
would say valid linear algebra operations in the traditional
1:44
sense. So let's say if you write a paper for a linear algebra
1:48
journal or something, they would maybe complain about this. If
1:52
you would do this on pen and paper, but on a computer, it's
1:54
possible, for example, to add a scalar value to a vector. So
2:00
also, you can, let's start at the top. So let's say we have
2:04
two vectors, a and b here implemented as pytorch tensors,
2:08
a one dimensional pytorch tensors. So what we can do in
2:11
pytorch is we can multiply these two tensors. So that is
2:15
something in traditional linear algebra, which would be not
2:18
valid, but here it is, which is nice. And then the other one is
2:22
you're adding a scalar to a vector. So what will happen is
2:25
it will add the value one to each individual element in the
2:30
vector, which is also convenient, you have to be a
2:32
little bit careful about that. Sometimes it's easy to make or
2:37
to compute something that you don't intend. So it can also
2:42
make mistakes a little bit easier. But in many, many cases,
2:46
this makes life easier. So you don't have to, for example, in
2:50
traditional algebra sense, linear algebra sense, what you
2:53
would have to do is you would have to create a vector of ones
2:55
and edit, for example, you would have them 123
3:01
plus 111. Right? So that would be the linear algebra way. But
3:06
here, you don't have to create this explicitly, it will
3:09
implicitly implicitly add this one, which is kind of nice. So
3:13
that would be one convenience function. This is also related
3:17
to the concept of broadcasting, which I will explain further in
3:21
the next couple of slides. Yeah, now in the next couple of
3:26
slides, we will be talking about some concepts around matrices
3:31
that are different from the linear algebra traditional
3:34
sense, and linear algebra on the computer. So if you think back
3:39
of the perceptron algorithm, this is typically considered an
3:44
online algorithm. Online means it processes one training data
3:48
point at a time. So if you think back, you do, you look at one
3:52
training data point, and then you update or not, and then you
3:54
look at the next data point, and then you update or not. However,
3:58
if you have trained your perceptron model, you can
4:01
actually do the prediction on the test examples, all at once,
4:05
you don't have to do one data point at a time. This is because
4:09
we don't train it anymore there. So we can really just feed it a
4:12
gigantic mat matrix of n training examples, and then do
4:18
all the computations at once. This will make it more efficient
4:21
because now we can do a matrix multiplication inside the
4:24
perceptron instead of processing each feature vector. So instead
4:28
of providing the first feature vector doing the computation,
4:31
the net net input, and then doing the second one, and so
4:34
forth, we can now give it this gigantic matrix. So we can avoid
4:39
having a for loop for prediction. Yeah, that is
4:44
essentially what I have written here. And the reason why it's
4:47
more efficient is that the computer can leverage lower
4:50
level routines to compute certain things in parallel. So
4:55
there are two opportunities for parallelism. One is multiplying
5:01
the elements to compute the dot product. So if you have, let's
5:05
say a weight vector here. So let me, there's no space really,
5:10
but let's say we have my weight vector here. And then if we
5:15
multiply this weight vector with the first feature vector, so
5:19
there's a multiplication between the first element, multiplication
5:23
between second element, and so forth until the last element and
5:28
these multiplications can be done all in parallel, and then
5:31
summed up, that would be one way for parallelizing that the
5:35
second way would be parallelizing the dot
5:39
products. So while you compute the product here, I'm showing
5:44
you in pink, you can have a second process running that
5:47
already computes the product between the second row and this
5:50
vector, and then one in parallel that already computes this and
5:55
this. And then lastly, this and this. So if you have four
5:59
processors, for example, you could compute all these four
6:02
dot products in parallel at the same time, you don't have to
6:05
wait until one finishes, right. So in that way, you can make the
6:10
computation more efficient. So you have a little question for
6:13
CS majors, who are maybe familiar with the notation big
6:17
O. So what would be the big O complexity of matrix
6:21
multiplication, if you assume that we have two n times n
6:25
matrices, there's just like a optional question, just seeing
6:29
if you if you know this, you can post this on Piazza, we can have
6:32
a little discussion. But of course, also non CS majors are
6:35
invited to participate in this discussion. But I'm just curious
6:38
if you are familiar with these things. All right. Yeah, like I
6:43
mentioned, there are these two opportunities for parallelism.
6:46
Here's a more concrete example, computing the net input and net
6:50
input. Now, instead of having a single feature vector, we have
6:54
now this matrix, the design matrix, which is n times m
7:00
matrix, n is the number of data points, m is the number of
7:03
features. And w is m dimensional vector, right. So the output of
7:13
this would be n times one, right. So the output of
7:19
multiplying x and w would be n times one dimensional vector.
7:27
And this is also why we actually have this extra dimension for
7:34
the vectors because you can't really in linear algebra in the
7:38
traditional sense, you can't really compute or multiply to a
7:42
matrix multiplication between a matrix and a vector, you can
7:45
only do a dot product between two vectors and a matrix
7:48
multiplication between two matrices. So in this way, for
7:52
correctness, this vector w is actually a matrix m times one
7:57
matrix so that we can do the matrix multiplication between
8:01
the matrix and the feature vector. It's a little bit weird.
8:04
It's just like, I'm just mentioning it here in terms of if
8:08
you stumble upon it, if you have learned linear algebra in the
8:11
traditional sense, and you think maybe that doesn't make sense in
8:14
computer. Yeah, in the computer computing context, we are a
8:17
little bit more forgiving about these little things. So yeah,
8:22
alright. Yeah, here's an example of computing the net input on
8:26
the whole slide. And this is then z, z would be a vector. So
8:31
we would be adding the B to every dot product. So each of
8:35
those is a dot product, plus the bias unit, and that gives us the
8:39
net input. So the net input is also a vector for the training
8:44
example. So we have n data points. For example, I said
8:49
training examples, but it would be more like the test data
8:52
points in the context of the perceptron. In other algorithms
8:56
that we will be talking about in the next few lectures, we can
8:59
also do that with training examples in the perceptron
9:01
example. This would be technically the test examples,
9:05
because, yeah, like I said, in the previous slide, the
9:08
perceptron is an online algorithm, it can only process
9:10
one data point at a time. Alright, moving on. So here's
9:16
example of that in pytorch. So both NumPy and pytorch are not
9:22
very picky about traditional linear algebra notations. So I
9:27
said before, this has to be this is an sorry, n times n matrix,
9:34
and W is an n times one vector. But pytorch is not very picky
9:43
about that. So we can actually also omit this dimension. So
9:46
here, I'm showing you a matrix, two by three matrix. That's just
9:53
a shortcut for making a matrix of value 01234 and five. So it's
9:59
a two by three matrix. And now I have a weight vector, just a one
10:04
dimensional vector 123. And I can actually multiply x with W
10:10
will give me a eight times 26 vector with a values eight and
10:15
26. So this would be also vector with only one dimension and two
10:20
elements. However, so instead of having this vector, I can add
10:27
I can add another dimension to this vector with this view
10:30
function. This is similar to NumPy reshape, which I explained
10:34
in the tutorials that I provided to you if this is unfamiliar,
10:39
maybe refer to the NumPy tutorials again, where I
10:41
explained the reshape and where the minus one comes from. But
10:44
also, if this is confusing, please ask on Piazza, I'm really
10:48
happy to explain that again. Alright, so now, the W here is
10:53
now a vector. So this is a column vector would be 123 with
10:59
another dimension. So this is a matrix of m times one matrix now
11:07
like we had before here. And we can also do that. Now, this is
11:12
not necessary. But you can see now, the output is also m times
11:19
one, sorry, this is actually n times one dimensional matching
11:25
the number of rows here, this is n times one dimensional,
11:29
whereas this one here is only n dimensional. So we have, sorry,
11:43
there's n elements with only one dimension. Yeah, it's a little
11:47
bit confusing when we call or talk about dimensions, if we
11:50
talk about a vector, say n dimensional vector, it means it
11:52
has the number of elements. If we say n dimensional array, it
11:56
means the number of dimensions or axes. So here, this is only
12:02
one axis with n values, and this is an n times one matrix. So
12:06
this is a vector in the traditional sense. And this is,
12:10
um, you can think of it as a column vector or n times one
12:25
matrix. But yeah, this is just nitpicking what I'm doing here.
12:29
I'm just showing you that both ways are possible in pytorch.
12:33
Yeah, and if you like nitpicking or hair splitting, so there was
12:37
actually one little mistake from a traditional linear algebra
12:41
perspective in the previous slide. So here, just asking
12:45
whether you can spot the mistake. So there's something
12:49
here that is not possible in traditional linear algebra. So
12:54
yeah, what's not possible here is that we are adding a scalar
12:58
to a vector, right? So in a one, let me go back. So here, I'm
13:03
actually adding it explicitly as a value. But in a traditional
13:08
linear algebra sense, you can't add a scalar to a vector that is
13:12
not valid. So in a traditional linear algebra sense, you would
13:15
have write it like this. But to be honest, the context of deep
13:18
learning, no one does that it's way too much work. And yeah, we
13:21
deep learning researchers are lazy. I just wanted to go over
13:25
these things. Because some of you might complain what type of
13:28
math am I using here? Because this is not making sense. I've
13:32
learned that differently. So I just wanted to illustrate that
13:35
in deep learning, we have our own rules in a way. Alright. So
13:41
yeah, lastly, the topic I promised for this video is
13:44
broadcasting. So yeah, in broadcasting, what we do is we
13:49
are we can add the one to the vector, like I just mentioned
13:53
before, not only that, it's also possible yet to add a vector to
13:58
a matrix, for example. So let's say we have a matrix here. So
14:02
here, I'm creating this matrix as a two by three matrix, values
14:07
456789. And now I have a tensor here 123, the same as above. And
14:14
I can now add this tensor to the matrix. And you can see, it's
14:20
adding these values, 123 to each of the rows. So it's adding
14:26
four, so the 123 to the upper row here. And it's adding also
14:32
the 123 to the lower row here. So the results are shown as
14:36
follows. So that is another thing that we can do in
14:40
computing. So and this is called broadcasting. So under the hood,
14:47
pytorch, and the same thing is also true for NumPy, they will
14:50
create another dimension implicitly. So you can't see
14:54
this dimension, but it will just do it internally, because it's
14:56
kind of guessing of what you want to do. So in this case,
14:59
under the hood, basically, it's extending this one to a tensor.
15:05
So then you can add these two tensors together, which will
15:08
give you two, three, and four, this is something that happens
15:11
under the hood. And this is called broadcasting, like
15:14
adding this implicit dimension. And the same thing happens here,
15:18
where we have the matrix that we add to the vector or the vector
15:22
to the matrix. So there will be also this implicit dimension
15:25
where the values are duplicated. And then this also works. So
15:30
yeah, this is the concept of broadcasting. And all I've
15:33
shown you in this video was hopefully not too confusing.
15:36
It's somewhat showing you that the rules and computing are a
15:40
little bit more relaxed and more geared towards convenience
15:44
compared to pen and paper linear algebra. Alright, so then in the
15:49
next video, I will go over some of the notational conventions
15:52
from neural networks, and then briefly about cover some concepts
15:57
related to fully connected layers and pytorch and some more
16:00
convention. So these videos in general, this, yeah, not this
16:05
week, today, a little bit drier than usual. But I think this is
16:08
just some foundation that we will need when we talk about
16:12
multilayer networks soon.

##v29:

0:00
So in this video, I want to briefly talk about broadcasting,
0:03
which is a concept that makes working with vector and matrix
0:07
computations more convenient on a computer compared to, for
0:10
example, pen and paper or the traditional way of doing linear
0:13
algebra. All right, so yeah, let's start with vectors. So if
0:19
you look at this notation here, w transpose x plus b equals z.
0:24
So you recall how this is called like to check yourself, there's
0:28
a certain word for that result. Maybe pause the video, think
0:33
about it briefly. Yeah, so the result is net input. So we
0:38
learned in the perceptual nature that we usually call that the
0:41
net input. So I mean, I'm just providing this as a simple
0:45
example here. So we're x and w would be two vectors here. So we
0:51
would do w transpose dot x plus b. And this would be the proper
0:58
linear algebra way of computing the net input. So in linear
1:02
algebra, the supported operations for a vector
1:06
addition, you can also think of subtraction if we add a vector
1:12
with negative values, and then the inner products like the dot
1:15
product would be one of them, and scalar multiplication. So we
1:19
can multiply a vector by a scalar. So these are the only
1:24
proper I would say, yeah, basic vector operations that you would
1:28
find in a traditional linear algebra textbook. Now in
1:33
practice, though, if you work on a computer, there are a few more
1:36
possibilities that can make our life easier. They wouldn't be I
1:40
would say valid linear algebra operations in the traditional
1:44
sense. So let's say if you write a paper for a linear algebra
1:48
journal or something, they would maybe complain about this. If
1:52
you would do this on pen and paper, but on a computer, it's
1:54
possible, for example, to add a scalar value to a vector. So
2:00
also, you can, let's start at the top. So let's say we have
2:04
two vectors, a and b here implemented as pytorch tensors,
2:08
a one dimensional pytorch tensors. So what we can do in
2:11
pytorch is we can multiply these two tensors. So that is
2:15
something in traditional linear algebra, which would be not
2:18
valid, but here it is, which is nice. And then the other one is
2:22
you're adding a scalar to a vector. So what will happen is
2:25
it will add the value one to each individual element in the
2:30
vector, which is also convenient, you have to be a
2:32
little bit careful about that. Sometimes it's easy to make or
2:37
to compute something that you don't intend. So it can also
2:42
make mistakes a little bit easier. But in many, many cases,
2:46
this makes life easier. So you don't have to, for example, in
2:50
traditional algebra sense, linear algebra sense, what you
2:53
would have to do is you would have to create a vector of ones
2:55
and edit, for example, you would have them 123
3:01
plus 111. Right? So that would be the linear algebra way. But
3:06
here, you don't have to create this explicitly, it will
3:09
implicitly implicitly add this one, which is kind of nice. So
3:13
that would be one convenience function. This is also related
3:17
to the concept of broadcasting, which I will explain further in
3:21
the next couple of slides. Yeah, now in the next couple of
3:26
slides, we will be talking about some concepts around matrices
3:31
that are different from the linear algebra traditional
3:34
sense, and linear algebra on the computer. So if you think back
3:39
of the perceptron algorithm, this is typically considered an
3:44
online algorithm. Online means it processes one training data
3:48
point at a time. So if you think back, you do, you look at one
3:52
training data point, and then you update or not, and then you
3:54
look at the next data point, and then you update or not. However,
3:58
if you have trained your perceptron model, you can
4:01
actually do the prediction on the test examples, all at once,
4:05
you don't have to do one data point at a time. This is because
4:09
we don't train it anymore there. So we can really just feed it a
4:12
gigantic mat matrix of n training examples, and then do
4:18
all the computations at once. This will make it more efficient
4:21
because now we can do a matrix multiplication inside the
4:24
perceptron instead of processing each feature vector. So instead
4:28
of providing the first feature vector doing the computation,
4:31
the net net input, and then doing the second one, and so
4:34
forth, we can now give it this gigantic matrix. So we can avoid
4:39
having a for loop for prediction. Yeah, that is
4:44
essentially what I have written here. And the reason why it's
4:47
more efficient is that the computer can leverage lower
4:50
level routines to compute certain things in parallel. So
4:55
there are two opportunities for parallelism. One is multiplying
5:01
the elements to compute the dot product. So if you have, let's
5:05
say a weight vector here. So let me, there's no space really,
5:10
but let's say we have my weight vector here. And then if we
5:15
multiply this weight vector with the first feature vector, so
5:19
there's a multiplication between the first element, multiplication
5:23
between second element, and so forth until the last element and
5:28
these multiplications can be done all in parallel, and then
5:31
summed up, that would be one way for parallelizing that the
5:35
second way would be parallelizing the dot
5:39
products. So while you compute the product here, I'm showing
5:44
you in pink, you can have a second process running that
5:47
already computes the product between the second row and this
5:50
vector, and then one in parallel that already computes this and
5:55
this. And then lastly, this and this. So if you have four
5:59
processors, for example, you could compute all these four
6:02
dot products in parallel at the same time, you don't have to
6:05
wait until one finishes, right. So in that way, you can make the
6:10
computation more efficient. So you have a little question for
6:13
CS majors, who are maybe familiar with the notation big
6:17
O. So what would be the big O complexity of matrix
6:21
multiplication, if you assume that we have two n times n
6:25
matrices, there's just like a optional question, just seeing
6:29
if you if you know this, you can post this on Piazza, we can have
6:32
a little discussion. But of course, also non CS majors are
6:35
invited to participate in this discussion. But I'm just curious
6:38
if you are familiar with these things. All right. Yeah, like I
6:43
mentioned, there are these two opportunities for parallelism.
6:46
Here's a more concrete example, computing the net input and net
6:50
input. Now, instead of having a single feature vector, we have
6:54
now this matrix, the design matrix, which is n times m
7:00
matrix, n is the number of data points, m is the number of
7:03
features. And w is m dimensional vector, right. So the output of
7:13
this would be n times one, right. So the output of
7:19
multiplying x and w would be n times one dimensional vector.
7:27
And this is also why we actually have this extra dimension for
7:34
the vectors because you can't really in linear algebra in the
7:38
traditional sense, you can't really compute or multiply to a
7:42
matrix multiplication between a matrix and a vector, you can
7:45
only do a dot product between two vectors and a matrix
7:48
multiplication between two matrices. So in this way, for
7:52
correctness, this vector w is actually a matrix m times one
7:57
matrix so that we can do the matrix multiplication between
8:01
the matrix and the feature vector. It's a little bit weird.
8:04
It's just like, I'm just mentioning it here in terms of if
8:08
you stumble upon it, if you have learned linear algebra in the
8:11
traditional sense, and you think maybe that doesn't make sense in
8:14
computer. Yeah, in the computer computing context, we are a
8:17
little bit more forgiving about these little things. So yeah,
8:22
alright. Yeah, here's an example of computing the net input on
8:26
the whole slide. And this is then z, z would be a vector. So
8:31
we would be adding the B to every dot product. So each of
8:35
those is a dot product, plus the bias unit, and that gives us the
8:39
net input. So the net input is also a vector for the training
8:44
example. So we have n data points. For example, I said
8:49
training examples, but it would be more like the test data
8:52
points in the context of the perceptron. In other algorithms
8:56
that we will be talking about in the next few lectures, we can
8:59
also do that with training examples in the perceptron
9:01
example. This would be technically the test examples,
9:05
because, yeah, like I said, in the previous slide, the
9:08
perceptron is an online algorithm, it can only process
9:10
one data point at a time. Alright, moving on. So here's
9:16
example of that in pytorch. So both NumPy and pytorch are not
9:22
very picky about traditional linear algebra notations. So I
9:27
said before, this has to be this is an sorry, n times n matrix,
9:34
and W is an n times one vector. But pytorch is not very picky
9:43
about that. So we can actually also omit this dimension. So
9:46
here, I'm showing you a matrix, two by three matrix. That's just
9:53
a shortcut for making a matrix of value 01234 and five. So it's
9:59
a two by three matrix. And now I have a weight vector, just a one
10:04
dimensional vector 123. And I can actually multiply x with W
10:10
will give me a eight times 26 vector with a values eight and
10:15
26. So this would be also vector with only one dimension and two
10:20
elements. However, so instead of having this vector, I can add
10:27
I can add another dimension to this vector with this view
10:30
function. This is similar to NumPy reshape, which I explained
10:34
in the tutorials that I provided to you if this is unfamiliar,
10:39
maybe refer to the NumPy tutorials again, where I
10:41
explained the reshape and where the minus one comes from. But
10:44
also, if this is confusing, please ask on Piazza, I'm really
10:48
happy to explain that again. Alright, so now, the W here is
10:53
now a vector. So this is a column vector would be 123 with
10:59
another dimension. So this is a matrix of m times one matrix now
11:07
like we had before here. And we can also do that. Now, this is
11:12
not necessary. But you can see now, the output is also m times
11:19
one, sorry, this is actually n times one dimensional matching
11:25
the number of rows here, this is n times one dimensional,
11:29
whereas this one here is only n dimensional. So we have, sorry,
11:43
there's n elements with only one dimension. Yeah, it's a little
11:47
bit confusing when we call or talk about dimensions, if we
11:50
talk about a vector, say n dimensional vector, it means it
11:52
has the number of elements. If we say n dimensional array, it
11:56
means the number of dimensions or axes. So here, this is only
12:02
one axis with n values, and this is an n times one matrix. So
12:06
this is a vector in the traditional sense. And this is,
12:10
um, you can think of it as a column vector or n times one
12:25
matrix. But yeah, this is just nitpicking what I'm doing here.
12:29
I'm just showing you that both ways are possible in pytorch.
12:33
Yeah, and if you like nitpicking or hair splitting, so there was
12:37
actually one little mistake from a traditional linear algebra
12:41
perspective in the previous slide. So here, just asking
12:45
whether you can spot the mistake. So there's something
12:49
here that is not possible in traditional linear algebra. So
12:54
yeah, what's not possible here is that we are adding a scalar
12:58
to a vector, right? So in a one, let me go back. So here, I'm
13:03
actually adding it explicitly as a value. But in a traditional
13:08
linear algebra sense, you can't add a scalar to a vector that is
13:12
not valid. So in a traditional linear algebra sense, you would
13:15
have write it like this. But to be honest, the context of deep
13:18
learning, no one does that it's way too much work. And yeah, we
13:21
deep learning researchers are lazy. I just wanted to go over
13:25
these things. Because some of you might complain what type of
13:28
math am I using here? Because this is not making sense. I've
13:32
learned that differently. So I just wanted to illustrate that
13:35
in deep learning, we have our own rules in a way. Alright. So
13:41
yeah, lastly, the topic I promised for this video is
13:44
broadcasting. So yeah, in broadcasting, what we do is we
13:49
are we can add the one to the vector, like I just mentioned
13:53
before, not only that, it's also possible yet to add a vector to
13:58
a matrix, for example. So let's say we have a matrix here. So
14:02
here, I'm creating this matrix as a two by three matrix, values
14:07
456789. And now I have a tensor here 123, the same as above. And
14:14
I can now add this tensor to the matrix. And you can see, it's
14:20
adding these values, 123 to each of the rows. So it's adding
14:26
four, so the 123 to the upper row here. And it's adding also
14:32
the 123 to the lower row here. So the results are shown as
14:36
follows. So that is another thing that we can do in
14:40
computing. So and this is called broadcasting. So under the hood,
14:47
pytorch, and the same thing is also true for NumPy, they will
14:50
create another dimension implicitly. So you can't see
14:54
this dimension, but it will just do it internally, because it's
14:56
kind of guessing of what you want to do. So in this case,
14:59
under the hood, basically, it's extending this one to a tensor.
15:05
So then you can add these two tensors together, which will
15:08
give you two, three, and four, this is something that happens
15:11
under the hood. And this is called broadcasting, like
15:14
adding this implicit dimension. And the same thing happens here,
15:18
where we have the matrix that we add to the vector or the vector
15:22
to the matrix. So there will be also this implicit dimension
15:25
where the values are duplicated. And then this also works. So
15:30
yeah, this is the concept of broadcasting. And all I've
15:33
shown you in this video was hopefully not too confusing.
15:36
It's somewhat showing you that the rules and computing are a
15:40
little bit more relaxed and more geared towards convenience
15:44
compared to pen and paper linear algebra. Alright, so then in the
15:49
next video, I will go over some of the notational conventions
15:52
from neural networks, and then briefly about cover some concepts
15:57
related to fully connected layers and pytorch and some more
16:00
convention. So these videos in general, this, yeah, not this
16:05
week, today, a little bit drier than usual. But I think this is
16:08
just some foundation that we will need when we talk about
16:12
multilayer networks soon.

##v30:

0:00
Yeah, in this video, I want to briefly go over the notational
0:03
conventions regarding linear algebra and deep learning. So
0:08
this is something we have seen before from the perceptron
0:11
lecture. So at the top, there is a perceptron. And now imagine we
0:15
do inference. So inference in the context of deep learning means
0:20
basically predicting the label of input feature vector. So in
0:26
the perceptron, assume we have one training example as input or
0:30
let's say, test, test data point or test example as input. So how
0:36
we would do that is as follows, we would have x transpose w
0:40
plus b, the bias unit, and then get the net input. And then we
0:44
give it to the activation function, which was the
0:48
threshold function, and then we get our prediction. So here,
0:51
this part is doing this linear algebra computation, x
0:56
transpose dot w plus b. So now this is for one data point, we
1:02
can actually also extend that to multiple data points. So if we
1:06
want to do that for multiple data points, like n training
1:09
examples, or n test examples, we can use a design matrix for
1:15
representing the data and n times m dimensional design
1:18
matrix. So n is the number of examples. And we would write it
1:29
as follows. So here, x is n times m, w is m times one, b is
1:38
just a scalar as a one. And then the output should be n times m
1:45
dot m times one, it should be n times one. Yeah, n times one,
1:51
that should be our output. So in this way, we have a vector. So
1:54
each value in the vector is the net input for the corresponding
1:58
test example. So that is just how we can process more data
2:01
points at the same time with still a single operation here.
2:05
Now, in deep learning, we usually have these neural
2:09
networks with hidden layer representations. So we will
2:14
learn about that a little bit later in this course, actually,
2:17
like I think next week already. So we have, let's say one data
2:21
point is input here, that's a feature vector, m features. And
2:26
then we will have a number of outputs. So let's say h is the
2:35
number of hidden units in a hidden layer. And then we have
2:40
also multiple hidden layers. So we can have another hidden
2:43
layer and another one and so forth. So in this way, what I
2:46
want to highlight here is that whereas in the perceptron, we
2:49
have a single output here, here, we can have multiple outputs. So
2:56
how can we do with such a scenario using linear algebra?
3:00
So what we can do is we can now have a weight matrix. So before
3:06
I talked about the design matrix for the inputs, now, there's one
3:10
input vector, one data point, but multiple outputs. So in this
3:18
way, we can use a matrix here. So this matrix would be h times
3:24
m dimensional. So let's write that down. h times m, so h rows
3:34
and m features, whereas the features are corresponding to
3:38
the m here, so the m matches here. So what we do is we put
3:43
the w in front, the x second. So this would be if I write this
3:49
down, h times m dot m times one, and b should be then also the
3:58
same dimension as h. Because there's one bias unit for each
4:04
computation here. So the output should be h times m dot m times
4:08
one, h times one, h times one dimensional output vector. So
4:14
it's also what I've written down here, I just see. So yeah, so in
4:17
this case, this is how we can deal with multiple outputs. And
4:21
we will learn how this works. Also, yeah, shortly later on
4:25
next week. Okay, let's now put both concepts together. So we
4:30
have multiple training examples and multiple outputs. So we have
4:44
now a matrix for the weights and a design matrix for the inputs.
4:48
So let's write it like this. So w has the dimensionality h times
4:55
m like on the previous slide. And x has the dimensionality n
5:01
times m, it's a design matrix, right. But now if you want to
5:04
multiply those two, you notice that they are not compatible,
5:07
right, the inner dimensions don't match. So that's why we
5:11
have the transpose here. So get me write it like this. So this
5:17
has a dimensionality on m times n now. So those dimensions match
5:25
m is h times one dimensional. So if I multiply those, so these
5:33
match the inner ones, so we have n. So this one is h times n plus
5:40
h times one. So the resulting resulting matrix, if we look at
5:46
this one, the dimensionality of that one should be h times n.
5:54
However, it is usually nice for each layer to resemble the input
6:00
dimensions of the previous layer, right. So the original
6:04
input, you can think of x as the original input was n times m. So
6:11
it would be nice if we have for this one as input to the next
6:15
layer, the same dimensionality, like the same ordering, I mean,
6:19
not exactly the same dimensionality, but the input, the
6:22
first dimension, the inputs, the number of inputs should be the
6:25
same, we are carrying over the same number of training
6:27
examples. So what we would want is for a for the outputs, to
6:33
have dimensionality, n times something so n times h, where h
6:39
is the hidden dimension. So in order to achieve that, this is
6:43
why we have the transpose. So with this transpose, we have
6:46
then n times h dimension. So it's usually nice, what I mean
6:50
is, it's nice to have the training examples as the rows
6:54
always. Now, if you think of this, what's going on here, you
6:59
can think of it as a linear transformation that is happening
7:03
to x. So instead of the original m features, we now have h
7:09
features, and h could be larger or smaller than m. So there are
7:14
in deep learning, both some networks make, make it larger
7:18
and some make it smaller. So there's a linear transformation.
7:22
Like I said, but it's not necessary, completely true. So
7:25
if this is a nonlinear function, then it's not a linear
7:28
transformation, it's a linear transformation that goes through
7:31
a nonlinear activation function. But we will talk about this
7:34
activation function on next lecture. So but yeah, this is
7:39
just like the overall notation. Also in textbooks, you may
7:44
notice that there is no transpose. So I have a short
7:47
note here about that. And the reason is in textbooks and
7:50
older textbooks, especially, they have not the n times n, n
7:56
times m design matrix, they have an m times n design matrix. So
8:00
they have the columns as rows switched, which is a little bit
8:04
confusing. I just want to note that in case you stumble upon
8:08
it. So usually modern deep learning has n times m
8:13
dimensional inputs. Sometimes it makes things more inconvenient
8:18
from a linear algebra perspective, because you notice
8:21
here, we have these transpose. If you have it the other way
8:23
around, you don't need the transposes. But yeah, there's
8:26
always a trade off. Alright, so um, why also this w x
8:32
notation, why not x w, actually, in the next video, I will show
8:36
you that in pytorch, it's the other way around. Traditionally,
8:40
though, this is convenient, because it's there's some
8:44
intuition behind it in terms of linear algebra, if you think of
8:48
traditional methods, how you write things in linear algebra,
8:52
it's that you have a transformation matrix that you
8:54
apply to a vector. So the vector would be here your feature
8:57
vector. And this makes it sometimes for some people easier
9:03
to think about linear algebra in a geometry context. So here,
9:08
this is just an identity matrix. So nothing is going to happen.
9:13
So technically, these diagonals, I think I have a slide on that
9:18
these diagonals are for scaling. But this diagonal is for scaling
9:24
values in the vector. And the other diagonal is for
9:30
translation. So moving things. And it's like easy to see. So
9:37
why the eigen sorry by the identity matrix is not doing
9:40
anything, because the scaling is here one and one. So scaling
9:43
something by one doesn't change it. And translation by zero
9:47
doesn't change anything either. So in this way, the original
9:52
inputs are preserved. So also, if you think of it as a dot
9:55
product, we remove the notation here, if you think of it as a
10:00
dot product. So one times zero, with this one, it's basically
10:06
one times x one, plus zero times x two, which is x one, right?
10:11
And here, zero times x one is zero plus one times x two is x
10:17
two. So nothing is going on here. Or he actually has the
10:21
slide on that he has like a summary of what I just meant. So
10:26
you can also write it as follows. So whereas if you so
10:33
you can decompose this into two separate operations vector
10:39
addition with this scalar here. And then you can think of this
10:43
first one as scaling the x coordinate. And then you can
10:48
think of this one as scaling the y coordinate. So like I said
10:55
before, these are for scaling. And then the other ones are
10:59
moving the vectors. So these are for moving the vectors. Yeah,
11:04
here, I just have an example of the scaling. So for example, if
11:08
you have a matrix that has a three here, it would scale
11:11
three. So sorry, scale the x axis by three. So it's kind of
11:15
stretching it here. And so forth, he is scaling or
11:20
stretching the y axis by a factor of two. And this one here
11:25
at the bottom is doing both stretching and scaling. And you
11:29
can maybe as an optional homework, think about the
11:31
translation. But in the context of deep learning, I think it
11:35
might be helpful sometimes to think of it as a series of
11:38
transformations. But yeah, also, one of the reasons why we use
11:41
linear algebra is more like for making notations more
11:45
compact, and we'll show you in the next video how this is
11:48
achieved in pytorch.

##v31:

0:03
Yeah, in this last video of this lecture, I want to give you a
0:06
brief teaser of pytorch convenience functions, the
0:10
linear or fully connected layer, but also like to just wrap up
0:14
the conventions regarding linear algebra. So yeah, what do I mean
0:19
by fully connected or linear layer? So if we have a
0:23
multi layer network, like shown here, so this part here would be
0:29
a linear transformation, if we don't consider the activation
0:32
function. And you can also think of this as a fully connected
0:36
layer. So this is sometimes called fully connected layer. Or
0:46
sometimes people also call that a dense layer. In pytorch, it's
0:51
called a linear layer because it's a linear transformation. So
0:54
you can also think of it as a linear layer. And in the context
0:59
of Keras and TensorFlow, people call it a dense layer. So all
1:06
these things are equivalent. So another dense layer or fully
1:09
connected layer would be from here to here. So neural network
1:14
really is a concatenation of multiple of these fully
1:18
connected layers, which are then interspersed with these non
1:23
linear activation functions, for example. So you can do this many,
1:27
many times. But also, multi layer networks are topic for a
1:31
different time for a different lecture next week, just
1:34
outlying already how that relates to linear algebra here.
1:38
So how we then implement a fully connected layer in pytorch is
1:42
very simple. There's actually a function called torch and dot
1:46
linear. So let's start with the data set here. So let's assume
1:50
I'm just creating some random data. But let's assume this is
1:53
some valid training data. So this is an design matrix with
2:01
dimensionality, what do I have here 10 times five, 10 times
2:08
five input matrix. And then when we initialize this linear layer,
2:13
we give it a number of features. And the number, so that's the
2:17
input features and the number of output features. So here, we
2:21
have five features, like that's our design matrix, the n times
2:25
m matrix. And let's say we want three output features, the
2:30
output features, if I go back one slide, are these here, what
2:34
I highlighted. Well, here, you can think of it as these here,
2:39
the net inputs. So that's basically the number of outputs.
2:44
And they are computed via this linear transformation. Alright,
2:49
so then each of these linear layers, when you initialize it
2:54
here, has attached as an attribute, a weight matrix, and
2:59
a bias vector. So the weight matrix, you can see it here is
3:08
h times m, or in this case, three times five dimensional,
3:14
right? So you have three rows and five columns, so three by
3:18
five dimensional, so you can see that this five here matches with
3:23
this five. So that's the number of input features. And the bias
3:28
unit is equal to the number of output features. So in this
3:31
case, it's a vector with three values. So because each output
3:36
has a bias unit attached to it. So here, we would have five
3:40
inputs in the next slide example, if I would modify it
3:44
here, and three outputs. Alright, so and notice here,
3:50
these are also small random values, we will talk about it
3:54
later why it's useful to have random values here instead of
3:57
all zeros. Now, here, I'm printing the dimensions for the
4:05
input, the weight, the bias. So it's 10 by five, three by five,
4:10
and three. Now I'm applying this fully connected layer. So I'm
4:16
applying it to this x, which is 10 times five, and the w, which
4:22
is three times five, and the output, so there's also plus b,
4:27
this is a matrix multiplication plus b, which is three
4:31
dimensional. And the output is what is it 10 times three
4:36
dimensional, a is a 10 times three dimensional matrix. So how
4:42
does that work? So what is going on here? So you can already
4:46
probably see, there must be some transpose here for the w, right?
4:51
So that the five goes in front, the and the three goes here. And
4:56
then maybe it's compatible with this x, but is it really what's
4:58
going on? So yeah, that's what's going on. So yeah, I have a
5:01
summary of that. So I also have to stare for it or have to stare
5:07
at it for a few seconds. Let me see what I've written down here.
5:17
So yeah, based on pytorch, we have another convention here.
5:20
Recall in the last video, I mentioned the convention where
5:24
the W the transformation matrix or weight matrix is in front of
5:28
x in pytorch is it's after x. And I think this makes sense,
5:35
not from a geometry perspective, but from a data flow
5:37
perspective, because in this way, we have to use fewer
5:41
transposes. And also, it's kind of symbolizing the way the data
5:46
flows through the network. So we start with x, and then we
5:49
multiply it by a weight matrix w, and then we get a so we have x
5:53
dot w resulting in a and stuff like that. So it's more like
5:59
this linear, linear flow here. Actually, I'm writing always a
6:04
but it's the net input. So depends on whether we apply the
6:08
activation function or not. Actually, I have it here. No
6:11
worries. All right. So if we have an input with one training
6:16
example, like this x here, this vector, then we can use the
6:21
notation where x is in front, if we transpose w, then the
6:25
dimensions will match, right. So here, in this case, it's a one
6:30
times m dimensional vector where w is an m times h dimensional
6:36
vector. So the result w will be just one value, the result will
6:41
be then one times h dimensional vector. And if we have n inputs,
6:50
then we can also keep x in front, we can also transpose w,
6:55
then in this case, what will happen is that we have an n
6:59
times m dimensional one here, here, the same m times h
7:03
dimensional one. And here, we will have an n times h
7:06
dimensional one. So this way, what is nice about this
7:09
convention is we can keep the same operations here, whether
7:14
this is multiple or only one data point. So this is actually
7:19
quite convenient from a computational perspective. So if
7:22
we have code, we don't have to change much around. And if you
7:26
don't believe me that this is the way pytorch does it here is
7:29
the source code, if you want to look at it. So this is like the
7:32
common convention in pytorch, how the linear transformation
7:36
happens. So yeah, just to conclude, I mean, multiple
7:41
different ways we can compute this linear transformation,
7:44
what's really important is thinking about it, like, always
7:49
think about how the dot products are computed when writing and
7:52
implementing matrix multiplication. So because yes,
7:55
sometimes it's easy to make mistakes. So things may compute
8:00
because dimensions match, but it's not computing what you
8:03
wanted it to compute. So it's always important to write down
8:06
what the dimensions are, and what you're computing and what
8:09
you expect the output is. Because yeah, also, theoretical
8:16
intuition and convention, like having the W in front as the
8:19
transformation matrix does not always match up with practical
8:22
convenience, like when we write things in code. So here, I've
8:28
written down some rules that you might find useful when you're
8:32
reading textbooks, and things are not the same as, let's say,
8:35
in code. So you can easily translate between those concepts.
8:40
For example, if you have two matrices, A and B, multiplying
8:44
those is the same as B transpose, A transpose, and then
8:48
taking the outer transpose here. So that's the same thing. And
8:51
also here, these are the same. So I was just writing down some
8:55
rules here that help you maybe navigating switches between code
8:59
and textbooks. I think you probably won't read many
9:02
textbooks, because there are not many deep learning textbooks
9:06
really yet, but maybe in the future sometime. But also in
9:08
papers, people use all kinds of different conventions. So I
9:12
think this is like a handy thing to keep in mind. And yeah, also
9:17
just to summarize traditional versus pytorch conventions. So
9:23
yeah, there are multiple ways we can compute this linear
9:26
transformation. Like I mentioned, we can have this weight
9:29
matrix upfront. So this would result in in h times one
9:35
dimensional vector, when x is a feature vector, m times one
9:40
dimensional, this is the same using the rule as I showed you
9:43
in the previous slide as writing it like this same thing. So it
9:47
gives us a way for the same input gives us the same output.
9:52
Another way we can write that that is how pytorch does that is
9:56
putting the x in front. But yeah, we are transposing w here.
10:00
This gives or this assumes a different input, though. This
10:04
assumes the one times m dimensional input. And yeah,
10:08
this is actually my preferred representation, because this is
10:12
kind of easy when we go back and forth between one or multiple
10:18
training examples, because now here at the bottom would be the
10:21
cases where we have n training examples. So if we want to use
10:25
it the traditional way, we have to use two transposes, which is
10:28
more work. So this is the usual case in deep learning, we have
10:32
usually many inputs and many outputs. So we only have to use
10:36
one transpose, it's shorter. And this is also the way pytorch
10:40
implements it. So this is also the pytorch convention. So just
10:46
to sum it up for this lecture. So yes, a little ungraded
10:52
homework experiment, you may can, if you have extra time,
10:57
revisit the perceptron numpy code. And without even running
11:02
the code, just thinking about it, can you tell if the
11:05
perceptron could predict the class labels? If we feed it an
11:10
array, actually, underlining it in an unfortunate way, without
11:14
running the code, can you tell if the perceptron could predict
11:17
the class labels, if we feed an array of multiple training
11:20
examples at once. So if we have a design matrix of dimensionality
11:29
in times m for testing, would it be able to run after training?
11:36
So if yes, why? If not, what change to the code have we have
11:41
to make? So you can think of this, and then you can actually
11:45
run the code right with the design matrix as input for
11:48
prediction and see whether your intuition was correct. And also
11:52
feel free to open a discussion on Piazza about that. So yeah,
11:56
run and verify your intuition. And then how about the train
12:00
methods? Can we also have some parallelism through matrix
12:05
multiplications in the train method having multiple training
12:07
examples? So does it make sense? Without, let's say,
12:11
fundamentally changing the perceptron learning rule, would
12:13
that make sense? So it's also another thing to think about.
12:18
Alright, so next lecture, then we will talk about more like a
12:24
deep learning topic that is not like fundamental linear algebra,
12:28
we will talk about a better learning algorithm for new
12:31
networks. So we learned about the perceptron rule next last
12:34
week. But this is actually not a very good learning rule. And we
12:38
will develop a better learning rule next lecture.

##v32:

0:00
Yeah, hi, everyone. So we had a little excursion last time
0:03
talking about linear algebra. Today, there will be another
0:06
little excursion talking about some concepts in calculus,
0:10
because they will be useful for your fitting neurons with
0:13
gradient descent. So today, the lecture will be on gradient
0:16
descent. And I will have some optional sections on some
0:20
calculus on topics as a little refresher. But yeah, because I
0:24
think there's a lot of stuff to cover today, I will keep the
0:27
introduction short and just dive in. Yeah, so the goal here in
Goals
0:32
this lecture is to improve upon the perceptron that we covered
0:36
last week. So in this lecture, we are going to talk about or
0:39
learn about a neural network model for which the training
0:43
always converges. So even if the data is not linearly separable,
0:47
here's an overview of the big picture goals. So our goals
0:51
overall. So like I just said, in this lecture, we are focusing on
0:54
a learning rule that is more robust than the perceptron, so
0:57
that it always converges even if the data is not linearly
1:00
separable. But yeah, that is not the end goal of this course, of
1:05
course, we want to learn about more sophisticated models
1:07
compared to single layer neural networks. So what we really care
1:11
about is also how we can make or create more complex classifiers
1:18
that can solve more complicated problems than just binary or
1:21
linearly separable problems. Because if I have something like
1:26
that, where I have two classes, I mean, this is relatively
1:31
trivial, right? So the perceptron again, had the shortcoming if a
1:34
data point is over there, there is no linear decision boundary
1:37
such that there is no mistake. So that way, it would never
1:41
converge. But even let's say, if we have a learning rule that
1:43
converges like this, this is a relatively trivial problem. And
1:47
in practice, we are interested in more complicated problems. So
1:50
we need to also find a way to combine multiple neurons.
1:54
Because these combinations of multiple neurons or deep neural
1:57
networks can help us to learn such more complicated decision
2:01
boundaries. And then with that, we can solve Yeah, also
2:04
complicated, real world problems. There are many like
2:07
objective detection, and let's say on classifying arbitrary
2:12
things. So in that way, that is something we will then start
2:16
tackling in the next lecture. So first, here, we lay the
2:18
groundwork, talking about the learning rule, and then we will
2:21
apply the same learning rule to the combination of neurons. And
2:24
also, we will then learn how we can extend this to multiple
2:28
categories, it will also be next lecture next week. So we will
2:33
learn also how we can classify problems where we have more than
2:37
two classes, which is also important, of course, right? If
2:40
you think about, let's say you build an application for a bird
2:44
watcher to classify birds outside. So there are more than
2:47
just two bird species, right? So in that way, we'll also learn
2:49
about methods that can handle multiple classes. And then yeah,
2:53
more towards the end of the course, we will then also learn
2:56
how to do fancier things, not just classification, but also
2:58
like things like generating new images and new text and things
3:02
like that. But yeah, on all these types of things are based
3:07
on the same learning algorithm, and extensions of this learning
3:11
algorithm. It's not like a fundamentally different though.
3:13
And in this core, in this lecture here, we will learn the
3:17
core principle of this learning algorithm that we will be using
3:20
for the rest of the semester. So and yeah, also, the good news is
Good News
3:26
after this lecture here, there won't be any new mathematical
3:29
concepts. So in this lecture, I will talk a little bit about
3:32
calculus. But that is about it when it comes to the mathematics
3:36
of this course. Of course, there will be mathematical concepts or
3:39
applications of the concepts we discussed like the linear
3:42
algebra stuff and calculus stuff in this lecture, but there won't
3:45
be any new fancier concepts. So after this lecture, you can
3:49
relax, there won't be any new mathematical complicated things
3:52
going on. So everything also in deep learning will be extensions
3:57
and applications of these basic concepts in linear algebra and
4:01
calculus that we are covering now. So yeah, just to give you
Lecture Overview
4:05
the big picture overview of things I have in mind for this
4:09
lecture. So first, we are going to talk about the different
4:14
learning modes. There's something called online batch
4:17
and mini batch learning. It is a general concept that applies to
4:20
all types of single layer neural networks and multi layer neural
4:24
networks, convolution networks, and everything basically in deep
4:27
learning. And yeah, after just this big overview here, we will
4:34
talk about the relationship between the perception and
4:37
linear regression. And then we will learn about an iterative
4:42
training algorithm for linear regression, you probably know
4:45
the closed form solution for linear regression, these are the
4:49
matrix matrix formulations and such the short content, a dense
4:54
formula for solving for the weights and the bias unit
4:57
directly. Here, we will talk about an iterative learning
5:00
algorithm, because it helps us understand how we can train our
5:04
neural networks, it's kind of very closely related. Yeah, I
5:08
will have a little calculus refresher. This will be
5:12
optional. So you notice that there are seven sections this
5:16
time, maybe a little bit long. So this is also really just
5:20
optional. It's, I thought it might be good for some of those
5:23
who have taken calculus a long time ago, or maybe not quite
5:28
sure about calculus anymore. So in a way, it's like a little
5:31
refresher. But if you are very familiar with calculus, you
5:33
don't have to watch these videos. So in that way, it will
5:36
be a shorter lecture. It's also something, these optional things
5:40
that I probably wouldn't have covered in the in person class,
5:43
because yeah, this is more like a prerequisite. So in this way,
5:47
I wouldn't want to make the lecture in person too long. But
5:50
if you like, you can watch them, but you're not required to. So
5:53
it's, it's just some background information, some optional
5:57
stuff. Yeah, and after that, we will be talking then about
6:02
gradient descent, that is the learning algorithm that I
6:06
briefly outlined in the previous video. And then we will be
6:10
training a linear neuron at a line. And I will also show you
6:13
then a code example in pytorch of how we can train such a
6:17
linear neuron using the concept of gradient descent. Alright, so
6:21
then let's get started with the first video on online batch and
6:25
mini batch modes in the next video.


##v33:

0:00
Yes, so in this video, I want to talk about the different ways we
0:04
can train a neural network. So there's the online mode, the
0:08
batch mode, and the mini batch mode. And they refer essentially
0:12
to how we utilize our data when we train a neural network model.
0:16
So basically how in which water we read the data regarding the
0:20
training epochs, and also how we update our model. So these are
0:25
general concepts that apply to any type of neural network. So
0:30
just to briefly recap our perceptron model here. So here
0:35
on the left hand side, it is just like, again, a sketch of our
0:37
perceptron, where we compute the net inputs, and then we update
0:41
the weights. So here, I mainly want to highlight what's going
0:47
on again under the hood. So if we have a data set, let's call
0:51
that data set D with n labels, and sorry, with n training
0:58
examples, but also n labels where each training example has
1:02
a feature vector x and class label y. So when we start
1:09
training on this data set, what we do is we initialize the
1:12
parameters of the perceptron. So for example, we can set the
1:16
weights to all zeros, and we can set the bias unit also to a
1:21
zero. So this is nothing new. This is just like a recap. And
1:25
then for every training epoch, remember, a training epoch is
1:31
one cycle over the training set, as I explained, I think it was
1:38
last week on training set. But if you have questions, always
1:42
please feel free to feel free to ask on Piazza, I'm always happy
1:46
to repeat these concepts, because they are quite
1:49
important. So please don't hesitate if you have any
1:51
question about what a training epoch is to ask because that's
1:54
kind of important to make sure everyone knows what we are
1:57
talking about here. So, so for every training epoch, there
2:01
could be multiple ones, we can have an arbitrary number of
2:05
training epochs. In practice, it really depends on the data
2:08
set in deep learning later on, it's not uncommon to train
2:11
something for 100 or 1000 epochs, even, even, it really
2:16
depends on how difficult the problem is. And so for every
2:20
training epoch, this is our for loop, then we go through each
2:24
training example one at a time. So that two for loops, one is
2:27
over the number of training epochs. And one is over the
2:31
data points in each round. Maybe just to draw this again. So if
2:39
this is my in pink, if this is my data set a D, I have these
2:44
different data points here. And this inner for loop here, let me
2:50
use a different color, maybe green. So this for loop here,
2:53
what it is really doing is it's just going from one training
2:56
point to the next one. So one at a time. That's what's going on
3:01
here. And the outer one, the training epoch one, once we
3:05
completed going through the data set, we start at the beginning
3:10
again, and go through the data set again. So that's really
3:13
what's going on here. So for each data point in the
3:16
perceptron, what we're doing is we are computing the
3:19
prediction. So my head is our prediction via the net input.
3:23
And then we have this threshold function or activation function,
3:26
which in this case is the threshold function. Then we
3:30
computed the error. And then based on that we update, so we
3:33
update here, the weight vector. And we also update the bias
3:38
vector. So that two updates, notice that the updates happen
3:44
after each training data point. So again, if I have here in
3:49
green, if I go to the first example, based on that, I
3:53
compute y hat, compute the arrow, and then update w, the
4:02
weight vector and the bias unit. If I have done that, I will go
4:07
to the second training example and do the same thing again. So
4:11
I update after each data point. So and this is called the online
4:21
mode. That is a little bit confusing. It's just I think a
4:24
historical thing that it was called online mode. Notice also
4:28
in textbooks, there is usually a dash between the on and the
4:33
line. This is like old machine learning textbooks. So I think
4:36
that's probably actually related to the World Wide Web, I'm not
4:40
quite sure. But I can imagine it is like when the internet was
4:42
new, you collected one data point at a time. And the
4:45
advantage is really, if you have a model with online mode
4:49
training, you can update after each data point. So if you have
4:53
a model on a web application for each new customer, you can
4:57
update the model, you don't have to collect multiple customers,
5:00
for example, to make an update. So you really after each data
5:03
point, you can make an update if you want to. Um, yeah, so this
5:08
is just a summary of what I had on the previous slide without
5:11
any mathematical symbols, just basically for each training
5:16
epoch, we iterate through the data points, compute the output,
5:19
calculate the error and update the weights and the bias. So
5:24
this is the general concept that applies to any kind of kind of
5:29
new network, not only the perceptron, we have seen that in
5:32
the context of the perceptron, but this is something you can
5:35
use also, as we will see later for linear regression, logistic
5:39
regression, multi layer perceptrons, convolutional
5:42
networks, and so forth. Um, and there are then some variants of
5:48
that one is called the batch node mode. And one is the mini
5:51
batch mode, which are essentially modifications of
5:54
that. And they have also certain advantages, which we will go
5:58
over in the next couple of slides. So this is one way you
6:03
can utilize your data. But there are two other ways one is called
6:07
the batch mode. And the other one is called the mini batch
6:10
mode. Just a little spoiler here. In deep learning, actually,
6:14
the mini batch mode is the most common one. And I will also
6:17
mention briefly then later why that is. So the batch mode,
6:23
let's take a look at the batch mode now next to the online
6:26
mode. So the difference here really is that we collect how we
6:33
would update the model before we actually update it after each
6:36
data point. So we still use the same number of data points in a
6:40
batch mode. But instead of updating after each data point,
6:44
we collect some information first, and then we do the
6:48
update. So the update is only really after each epoch. So
6:52
again, let's take a look at the online mode on the left hand
6:55
side. So for each training epoch, we go over the data
6:58
points. And then you can see here inside each of each data
7:02
point, we update on the right hand side, I have the batch
7:04
mode, it's a little bit different, we still have a for
7:08
loop over the training epochs. However, the difference now is
7:12
that we let's say initialize this placeholder here, it's a I
7:17
call it delta delta for change. So this is some placeholder
7:21
here, which I have for the weights and for the bias, that's
7:24
on, let's call that the placeholder. This is also a
7:29
placeholder. And then, like on the left hand side here, I'm
7:35
iterating through the data points. Also, the same thing
7:38
here, I'm computing the output or the prediction, same thing as
7:42
on in the online mode. Also, I calculate the error, same thing
7:47
here. So that's all the same. However, the difference really
7:51
is here, in this step. So you can see here, I'm updating the
7:57
weight and the bias directly here, I'm only updating my
8:01
placeholders. So I'm just accumulating some error terms or
8:06
some information. And I keep Yeah, I keep accumulating that
8:13
until I iterate it over every data point in the data set. And
8:17
then, based on that, after I finished iterating through the
8:22
current data set here, then I update the weight vector and the
8:25
bias here. So you can see, I'm now using my placeholder here
8:30
and here to update these parameters, I just see there's a
8:35
missing letter that should be a B up front here. So I'm
8:38
updating both the weight and the bias using the placeholders
8:43
which have some accumulated information here. So what is the
8:47
advantage of doing, let's say online and batch mode on. So
8:52
online mode is an update, one update at a time. So it can be a
8:56
little bit noisier. The batch mode is a little bit more, I
9:01
would say robust. So you collect statistics or information from
9:04
the whole data set before you do one update. The disadvantage is
9:08
it's a slower mode of updating because you do only one update
9:13
for each training epoch. And on the left hand side, you do
9:17
multiple updates each epoch. So on the left hand side, you can
9:21
think of it as maybe as a faster learning because there are more
9:23
updates. On the right hand side. They have fewer updates. Each
9:29
update takes longer because you have to cycle through the whole
9:32
data set before you make an update. But the update will be
9:34
more accurate. I will also show you some visualizations of that
9:39
how that works really in in the context of let's say linear
9:42
regression or real on your real case scenario. There's no I
9:48
would say, I would say neither of the two are very common in
9:52
deep learning though. And I will also tell you why later on it
9:56
will become obvious, I guess. In practice, there's something
10:00
called mini batch mode, which is the most common one. I have one
10:04
more note here about the online mode I just see. Yeah, I
10:09
highlighted it here in practice, we usually also shuffle the
10:11
data set to prior to each epoch to prevent cycles. So sometimes
10:17
it can happen that, for example, in the perceptron case or some
10:20
other case that the algorithm gets stuck flipping back and
10:23
forth. So empirically, it's actually better to shuffle the
10:27
data set prior to each epoch. You can also think of it if you
10:31
have, for example, the iris data set. If you just load it, the
10:37
classes will be sorted by class labels. So you have 50 examples
10:41
from class zero, or 50 examples from class one, and then plus
10:45
two. And that is also not ideal, because let's say, this is my
10:49
iris data set, all these are class level zero, and then you
10:53
have class label one, and then class label two. So if you don't
10:57
shuffle, the problem is the algorithm will only update based
11:01
on on the zeros, maybe the zeros are easy. So there's not
11:06
nothing happening. And then it sees a completely new class. And
11:09
then it only focuses on getting these right. But then maybe it's
11:14
getting some other ones wrong again. And it's usually better
11:17
to have more, a better shuffling a little bit more diversity that
11:22
you have zeros, ones and twos like intermixed with each other.
11:26
And also, you have to prevent flipping back and forth, it's
11:29
just good to shuffle it shuffle doesn't cost much. So in that
11:32
way, it's not a bad thing to do anyways.
11:36
Oh, yeah, I should say, the online mode is sometimes also
11:39
called
11:43
stochastic mode, or in the context of gradient descent,
11:47
which we will cover later in this course, it is also called
11:50
stochastic gradient descent. There's another online mode.
11:55
Let's call that online mode version two, that is also quite
11:59
common or used to be quite common. So here, the difference
12:02
is really that you don't iterate over the epochs, you just say
12:06
for a given number of iterations, you do the updates.
12:12
So for a given number of iterations, you say pick at
12:15
random some data point from the data set. And then you proceed
12:19
with computing the prediction, the error and the update. So
12:22
here, really, the difference is you don't iterate over the
12:25
epochs. The difference also then here is on the left hand side,
12:29
you guarantee that each data point is used exactly once in
12:33
each round. Whereas on the right hand side, a data point can be
12:37
used multiple times in the same number of iterations. So for
12:43
example, if you have a data set of size n, and you have n
12:46
iterations, it can be that some data points are used multiple
12:50
times, whereas certain other data points are not used at all.
12:55
On the right hand side, this is usually what people call the
12:57
true stochastic mode. And that is something you'll find
13:00
sometimes in statistics papers, because it's easier with that
13:04
one to to derive certain proofs, like theoretical proofs, it's
13:08
mathematically a little bit easier to handle than the left
13:11
one. But in practice, so in practice, this is usually used
13:18
more often because you get better results with that one,
13:20
because you guarantee that each data point is used in the data
13:23
set. And each data point is used the same number of times, it's
13:26
kind of more making better use of the data set in that way.
13:30
Also, yeah, this is also not truly stochastic, I would say,
13:33
because, you know, for it to be a truly stochastic, you would be
13:37
sampling from the distribution here, we still have a fixed
13:41
size training set. But this is just nitpicking, actually. Now
13:45
let's get to the most common mode of learning. So this is the
13:49
mini batch mode, which is a mix between the online mode and the
13:53
batch mode. So similar to the previous two modes, what we do
13:56
is we initialize our parameters that we want to update the
14:00
weights and the bias. And then we also iterate over the
14:03
training epochs. But now what's new is we also iterate over mini
14:10
batches. So what is a mini batch, a mini batch is a chunk
14:15
of the data set. So if this is my training set, you can think
14:23
of a mini batch as a smaller chunk of the training set. So
14:29
this would be a mini batch. One, mini batch 234. So what is the
14:40
size of mini batch? Usually, it really depends on usually common
14:44
ones you will find in deep learning or something like 3264
14:50
128 256, sometimes also 512. It really depends on also the
14:57
problem. It's like a hyper parameter, something you have to
15:00
try out and see what works. So there are some papers suggesting
15:04
smaller batch sizes can accelerate learning because it's
15:08
noisier and the noise can help making updates a little bit
15:11
faster. So you have more iterations, larger batch size
15:15
use or make better use of the GPU. But yeah, it's really, it's
15:21
really something that depends on practice. And we will also talk
15:24
more about that when we talk about a technique later on
15:27
called batch normalization. In any case, um, so this mini batch
15:32
here, it's then essentially used like batch gradient descent, so
15:37
everything down here, this is similar to the batch mode,
15:47
except that you perform the batch mode on this smaller chunk
15:51
node. So before the batch mode was done on this whole training
15:56
set, now the batch mode is done on one chunk at a time. So you
16:02
again initialize these placeholders. And then for each
16:05
data point in the mini batch, you compute the prediction
16:08
calculate the error, update the placeholder and then Yeah, then
16:13
you update the weight and bias unit here. So this way, it would
16:18
be similar to the batch mode, except that you use one smaller
16:21
mini batch at a time. And this is usually the most common mode
16:26
in deep learning. So as a question for you, do you have any
16:29
ideas why that is? Yeah, maybe pause the video for a second and
16:34
think about it and see if you have some ideas before I read
16:37
out loud my notes on the right hand side. So yeah, I've written
16:40
down three of the reasons why I think that mini batch is much
16:45
more useful than let's say the online model and the batch mode
16:47
in deep learning. So one would be that when you're choosing
16:51
such a subset, such a mini batch, instead of just one
16:57
example at a time, we can take advantage of the vectorization
17:01
that we talked about in the previous lecture. So in the
17:04
previous lecture, we had seen that we can compute things
17:07
efficiently. So when we had, for example, a training matrix
17:12
containing multiple entry entries, multiplied by the weight
17:18
vector. So if we had that we could process multiple training
17:21
examples at a time, which is then faster than in a for loop
17:25
executing this multiplication with a vector here. So instead
17:30
of using a vector times this weight matrix and doing this
17:33
multiple times with a for loop is of course slower than doing
17:38
it one time with this matrix multiplication here. So using
17:42
this vectorization makes everything or makes the
17:47
processing or iterating over an epoch faster in the mini batch
17:52
mode compared to the online mode. I'm also having fewer
17:57
updates than in an online mode, like including more examples in
18:01
each update makes things a little bit more robust, so it
18:05
reduces the noise a little bit. On the other hand, yeah, we
18:10
could, if these two arguments, if you consider these, then we
18:13
can say, okay, why don't we use the full batch mode, the
18:17
regular batch mode then, right, because that would be even
18:20
faster. And it would be even more robust, because updates are
18:24
less noisy. So in practice, actually, um, first, the data
18:28
would be too large, a common data set. So this one on a deep
18:32
learning data set wouldn't be feasible, we can't just have
18:35
millions or 1000s, even of data points here, because then we
18:38
would have, say, if we have 10,000, if we have a 10,000 data
18:42
point training, so we have a matrix that is 10,000 times,
18:47
let's say, maybe also 10,000 for the features in deep learning.
18:51
So x would be a 10,000 times 10,000 times matrix. And w would
19:00
be then also 10,000 times something matrix. And that would
19:04
probably blow up the computer memory. And even if that would
19:08
work, actually, the noise is quite good for learning in deep
19:13
learning, we will see that later, it helps the algorithm to
19:16
escape so called local minima. So in this way, actually, the
19:21
mini batch mode also that little bit of noise is good. So in the
19:25
online mode, there's maybe too much noise, like from one
19:27
training point at a time. But having a little bit of noise,
19:30
like having these small batches actually helps. Yeah, and also,
19:35
compared to the full batch mode, like I said, here, point three,
19:39
we have more updates in the mini batch mode, if for each
19:42
iteration over the epoch. So in the batch mode, we only have
19:49
this iteration of the epochs and then only update once. So we
19:54
apply this only once after each epoch. In the mini batch mode,
19:59
we do that multiple times, depending on how many mini
20:02
batches we have in each epoch. So in that way, we have more
20:06
updates than in the batch mode, which can also help with
20:08
learning things faster. Alright, so in the next video, I will
20:15
briefly go over the relation between the perceptron and
20:17
linear regression. So if things were a little bit, I would say,
20:22
yeah, a little bit weird out of context, this is something that
20:27
we will be using for the rest of this course. So we will be using
20:31
mostly the mini batch mode later on when we train neural
20:34
networks. So here was just explaining the different ways we
20:37
can process a data set. And this will become relevant when we
20:40
start to talk about stochastic gradient descent. So with this
20:43
lecture, it's like usually a chicken egg problem, there are
20:46
many things or concepts, one depends on the other. And we
20:50
have to start somewhere. So now I outlined different ways we can
20:55
process the data. And then we will see in stochastic gradient
20:58
descent and gradient descent how this actually applies to the
21:02
actual updates.

##v34:

0:00
So yeah, in this video, I want to briefly talk about how the
0:04
perceptron and linear regression are related to each other. So
0:08
you can think of linear regression as a single layer
0:10
neural network. And I think since you all hopefully know
0:13
linear regression, this will make things a little bit easier
0:16
when we talk about gradient descent. And also from there,
0:19
it's very easy to go to the edeline. So to the adaptive
0:22
linear neuron. So in this video, I want to just briefly outline
0:25
this relationship before we talk more about that in the following
0:29
videos. So here's again, a sketch of the perceptron
0:35
algorithm, where we have multiple things going on. First,
0:38
we compute the net input based on the features of the data set,
0:43
and the weights. And then there's also the bias unit. So
0:46
we have the net input that we compute. And then we send this
0:51
general model, we have an activation function here. And in
0:54
the case of the perceptron, this was the so called threshold
0:57
function where we had, if you think of it as a threshold, we
1:01
had like this threshold function, if the net input z is
1:07
greater than zero here, then it returns a one and otherwise it
1:12
returns a zero. So if z is greater than zero, then return a
1:15
one, otherwise a zero, that was our activation or threshold
1:19
function. In the case of linear regression, we don't have such a
1:24
prediction, we only return a continuous value. So we don't
1:28
have a threshold for zero and one. And you can think of it
1:32
then as this activation function here in the perceptron or
1:36
threshold function being the identity function. So not doing
1:40
anything, an identity function is just a pass through, it's
1:43
just returning the inputs of the input is x to this function, it
1:48
will also return x. So in this case, in linear regression, the
1:52
same concept applies as in the perceptron here. So the same
1:55
computation of the net input, which was just multiplying the
2:03
weights with the features and then adding the bias unit. So
2:07
that is our net input. And yeah, this is also how the prediction
2:14
and linear regression is created. So yeah, in that way,
2:19
you can think of linear regression as a linear neuron, a
2:23
single layer neural network. And in earlier statistics classes,
2:28
I'm pretty sure you covered this. So you probably fit a
2:32
linear regression model, like this, like shown below using
2:35
these so called normal equations, which are an
2:38
analytical solution to the minimization problem in least
2:42
squares linear regression. So when you wanted to minimize the
2:45
square square error, you could compute or you could find a
2:50
model that minimizes the square error by using these so called
2:55
normal equations. So you have if this is your design matrix x
3:00
transpose x inverted, so inverse here, times x transpose y, if
3:07
you do that. And if you include an additional vector of ones,
3:12
assuming that the bias unit is included in w. So if I go back
3:17
one slide, remember, in the perceptron lecture, we had this
3:19
alternative formulation, where we didn't have a separate bias
3:24
unit, we have one here. And then we had the weight zero. If you
3:29
assume this, if you add this one to the inputs, then the bias
3:35
unit will be included in this w. So with this set of this
3:40
of this equation here, you can actually solve for the
3:43
parameters for linear regression in an optimal way. But yeah,
3:47
this is not what we will be doing in this class. In this
3:50
class, we will be talking about a different type of algorithm
3:53
that can also find these parameters. Yeah, to just
3:59
summarize what I said in the previous slides. So these normal
4:03
equations here are really the recommended approach for least
4:08
squares linear regression. This is something I would use on a
4:11
data set. There might be one little caveat, if you have a
4:14
very large data set, then this matrix on inverse here could
4:18
become problematic for computer memory. But yeah, honestly, I
4:22
think most data sets are in on most data sets, it would be
4:24
fine. So this is what I would be using for linear regression
4:27
practice. However, I am going to introduce or we are going to
4:32
learn about a different way for learning these parameters
4:35
iteratively. And the reason why we do that is because that's
4:39
what we are doing in deep learning, or for deep neural
4:42
networks, where we have large data sets, many connections,
4:46
that is many neurons, and also non convex loss functions. So
4:50
for deep neural networks, there is no closed form solution or
4:54
analytical solution. So that way, we have to be a little bit
4:57
creative and use this iterative way. And I think really,
5:00
because you're already familiar with linear regression from
5:03
other statistics classes, that using linear regression to
5:07
introduce this algorithm will make things a little bit
5:09
easier. So I will introduce the iterative algorithm in the next
5:14
video. And then we will talk about some calculus concepts and
5:17
then see how it works in practice.

##v35:

0:01
Yeah, so in this video, I want to now talk about this
0:04
iterative training algorithm that I mentioned in the previous
0:08
video. So we will be talking about training and linear
0:10
regression using an iterative algorithm. This is also the
0:14
first part, we will come back to that later on, when we talk
0:18
about gradient descent, so yeah, just want to give the general
0:21
outline. So one way we can use an iterative algorithm to fit
0:25
least squares linear regression models is by using brute force.
0:29
So this would be what I call or think of as a very naive way to
0:33
fit a linear regression model, or any type of neural network.
0:37
So what we can do is we can start by initializing parameters
0:40
to all zeros. So the weights and the bias, or small random
0:45
numbers, and then we have a for loop here for k rounds. So let
0:49
me use a different color for that. So for k rounds, we can
0:52
then choose another random set of weights. And then we look at
0:59
the predictions of the linear regression model. And now, if
1:02
the model performs better, we keep those weights. And then
1:07
we go back here. So this is like iteration k times, every time we
1:12
find better ways we keep those. If the weights are worse, so if
1:18
the model with the weights performs worse, we actually
1:21
discard them. So we only keep the weights if they're actually
1:23
better than before. And yeah, if you do that many, many, many
1:26
times, this approach is actually guaranteed to find the optimal
1:29
solution, right? Because yeah, you do this many, many, many
1:32
times. And if the model can only improve, eventually, just by
1:35
luck, you will find a great set of weights, the optimal weights.
1:39
But as you can think, or as you can imagine, this would be a
1:43
very, very inefficient and terribly slow way of fitting a
1:46
linear regression model. So I would not recommend doing this
1:49
in practice, although in practice, it works, it's it's
1:52
not a good way to fit a linear regression model.
1:54
Yeah, so luckily, there is a better way for fitting a linear
1:58
regression model iteratively. So what we can do is we can analyze
2:01
what effect of change a parameter has on the predictive
2:05
performance of the model. So we can take a look at the squared
2:08
error loss and see when we change the weight and the bias
2:11
in a certain way, how it affects these errors. And then we can
2:16
make a small change. So we can change the weight and bias a
2:19
little bit in the direction that improves the performance. So if
2:23
we understand the relationship between the weight and the loss,
2:26
we can change the weight such that the loss goes down. So we
2:29
have a smaller error. And we can then do this several times in
2:34
small steps until the loss is not further decreasing. So one
2:38
by one, we will change the weight such that loss decreases.
2:43
It turns out that this is actually the online mode that we
2:46
talked about. Yeah, just written a little bit differently. So on
2:51
the left hand side, we have again the online mode mode for
2:54
the perceptron learning rule. So where we iterate over the
2:59
training epochs, and then for every training example, we
3:04
compute the other prediction, compute the error, and then do
3:07
the update here. So for linear regression, there's an algorithm
3:12
called stochastic gradient descent. So stochastic gradient
3:16
descent is the analog of the perceptron learning rule for
3:21
convex loss functions here, we can also use it for non convex
3:24
loss functions for neural networks, that will be
3:26
something we will cover in the next lecture. So here we will
3:30
focus on the linear regression model. And then at the end of
3:33
this lecture also at on the adaptive linear neuron. So what
3:38
is similar and what is different? So again, so we have
3:43
the same weight initialization here, let me use a different
3:46
color for things that are the same. So weight initialization
3:50
is the same, we also iterate over the training epochs. Then
3:54
we also iterate over the training examples in a data
3:57
set. We also compute the predictions the same way.
4:01
Because yeah, like I mentioned in the previous video, the
4:04
perceptron and the linear regression model, they both
4:06
compute the net input here. Except here, we have the
4:09
threshold function and the perceptron. And let me use right
4:13
here, that would be the threshold function, the case of
4:16
the perceptron. And here, this would be an identity function.
4:26
This is the threshold. And yeah, inside here, this is the net
4:32
input. This is oops. I don't know what it is with curly
4:40
brackets, but I can't draw curly brackets. Okay, so Z, the net
4:45
inputs on they are computed exactly the same way. This
4:49
function is an identity function, in the case of linear
4:51
regression and threshold function, the case of the
4:54
perceptron. Now, for the perceptron, we compute this this
5:00
error here by just subtracting the predicted value from the
5:05
actual class table. In linear regression, we have continuous
5:09
value, but it's very similar. So also here, we have a
5:13
subtraction for the weights, we multiply this by x by the input
5:18
feature vector. And for the bias unit, we don't. So if you're
5:23
wondering what these symbols here mean, so this labla symbol,
5:27
this stands for the gradient. So here, we are computing the
5:32
gradient of the loss of the gradient of the loss l was
5:36
curly l l here with respect to the weights here. So this is the
5:42
gradient of let me spell this out gradient of the loss
5:50
function with respect to the whoops weights. And then here at
6:03
the bottom, this is the same also also the gradient of the
6:07
loss with respect to the bias unit here, or derivative. So
6:14
yeah, so you can see, this is closely related to what's going
6:19
on in the perceptron. And in step C, now we do the update. So
6:25
the update is a little bit different here. So on the left
6:33
hand side here, we have the current weight. And then we
6:37
multiply the error with the feature vector. We don't do this
6:43
on the right hand side, we have done something like multiplying
6:46
with a feature vector up here. But here, now what we do is we, we
6:49
add another term here. And this term, eta is a scalar, it's a,
6:56
we are scaling something. And this is the so called learning
7:00
rate. So let's call that the learning. Right, it's just a
7:07
scaling term. And in the parentheses here, this is the
7:12
negative gradient. So I also wrote it down here. So we have
7:16
the negative gradient, we now update the parameters by the
7:20
negative gradient. So it's kind of similar to what's going on
7:24
in the perceptron, except that the way we get this gradient is
7:29
based on calculus. And in the next couple of minutes, I will
7:33
give you a brief calculus refresher to explain where this
7:35
comes from. So here, we are really computing the negative
7:39
gradient of the squared error loss with respect to weight and
7:43
the bias. And on the in the perceptron case, this is, it
7:46
looks very similar, it's a little bit different, because
7:48
it's not depending on calculus, here, we have the threshold
7:51
function. And depending on how fresh your calculus skills are,
7:56
you know that for non smooth functions, like threshold
8:00
functions, we can't compute derivatives. So in that way,
8:04
it's somewhat related, and very similar, but there's a little
8:09
little detail. Okay, so yeah, one more slide, I just see I
8:15
have here. So on the left hand side, we are I showed you
8:20
vectorized implementation of this linear regression online
8:24
mode. So where we had vectors, so x here is a vector, for
8:28
example. And the gradient is a vector, but we can also kind of
8:34
unroll this using a for loop. So this way, we don't need
8:38
gradients, we can just talk about partial derivatives. So in
8:44
order to simplify this as a for loop, we would just look at one
8:49
feature at a time or one weight at a time. So if we have a data
8:54
set, where our dimensionality of the inputs is m, so we have m
8:59
features, what we can do is then for each weight, so the number
9:04
of weights is equal to the features, right? Because if I
9:07
have my inputs, x one, x two, x three, then here, they go into
9:14
my net input function, and each input is associated with a
9:19
weight, right? So I'm not drawing the bias here. But yeah,
9:24
each input is associated with a weight. So we have m weights,
9:29
and I can for each weight separately compute the partial
9:32
derivative of the loss with respect to that weight. So it's
9:36
the analog of this one here, not using any linear algebra now
9:40
just using partial derivatives instead of gradients. And then I
9:44
can do also the update the same way. So here, this is just a
9:47
for loop version. I think, yeah, this is maybe conceptually a
9:51
bit easier, because partial derivatives are maybe easier to
9:54
think about as compared to gradients. I mean, it's the same
9:57
thing. But instead of talking about gradients, we could also
10:00
talk about partial derivatives. However, like I explained in the
10:05
previous lecture, vectorized implementations are faster,
10:09
which is why we usually use gradients and vector based
10:13
implementations. So the learning rule from the previous slide now
10:19
is called stochastic gradient descent. I was showing you this
10:23
learning rule, but I didn't show you where this learning rule
10:25
came from. So where how did I derive this learning rule? So in
10:30
order to understand that, yeah, there's some little calculus
10:34
required. I think most of you already took calculus classes,
10:38
because that was a prerequisite for this class. If you are a
10:42
little bit rusty, I have two bonus videos, I will be
10:45
recording after this video. So you can maybe refresh your
10:49
calculus skills, but it's not necessary. So you can also jump
10:53
ahead to this video where I will explain where the learning rule
10:58
comes from. And if you like, you can watch these two videos where
11:02
I go over some of the calculus concepts.

##v36:

0:00
Yes, in the next two videos, I want to give you a brief
0:03
calculus refresher if you need it. So that's optional, you
0:06
don't have to watch the next two videos. If you are very familiar
0:09
with calculus, it will be, I think, too trivial for you. But
0:13
if you don't, if you
0:17
yeah, so in the next two videos, I want to give you a brief
0:19
calculus refresher, talking about derivatives and gradients.
0:24
And like I said, these videos are optional. So if you are very
0:26
familiar with calculus, then I think this might be too easy for
0:29
you. But for those who are here, you want to refresh their
0:33
calculus. This is like a brief summary of the main parts that
0:37
we will need for the gradient descent algorithm.
0:41
Yeah, so here's an overview of what a derivative is. So a
0:44
derivative of a function, you can think of it as the rate of
0:47
change of that function, or the so called slope. So you have a
0:51
very simple example, a function f, which is equal to 2x. So if
0:57
we have an input, let's pick an arbitrary number here on the x
1:01
axis. So if I have the number three here, so the input is
1:06
three, then the output would be two times x or two times a in
1:11
this case, two times three, that would be six. So the output
1:15
would be six. Now let's pick a second point. Let's get move on
1:20
the x axis by delta a units. So then we arrive at this point
1:26
here. So if I look at these values, let's move by four
1:30
points, and we arrived by at seven here, and then the output
1:33
corresponding to that would be two times that which would be
1:37
14. So yeah, there is between these two points, there is a
1:42
change here going on, the change is from six to 14. So this is
1:50
by eight units. And the change on the x axis is from three to
1:58
seven, it's only four units. So we can then compute the rate of
2:02
change or the slope by having this eight divided by four is
2:08
equal to two. So the slope of this function of two x is two.
2:12
So more formally, here's the equation how we can compute the
2:16
slope. So we pick the function on the right hand side. So this
2:22
is the input on the right hand side here. And then this is the
2:26
input here on the left hand side, let me use a different
2:29
color. And of course, then the output here, this is
2:35
corresponding to this one. And the output of this one is
2:38
corresponding to this one. So we are plugging in the difference
2:42
of the height. So the 14, you write this down. Let's do it in
2:47
black 14 minus six. And then divided by and we have a and
2:55
then this second value, delta a minus B, which would be in our
3:00
case, three plus four minus three. So how can I Yeah, so
3:12
actually, I can simplify that. So we have a, and then we have
3:16
this second value, delta a minus a. So maybe it's simpler to see
3:22
it like this. So these two belong together, it's a and f
3:27
of a. And these two are these belong together because it's for
3:31
this point here, a plus delta a, which we plug in here, but we
3:36
can actually simplify that right because we have a minus a so we
3:40
can actually cancel that. And then we have this simpler form
3:44
here, which is essentially then 14 minus six divided by four,
3:53
which is eight divided by four. So this is like more the formal
3:57
way of how we compute the slope. And in this case, the slope of
4:01
this function is two, it tells us by if we change the function
4:05
by one unit, so the input of the function, if you change it by
4:08
one unit, the output changes by two units, because the other
4:12
slope is two. So it gives us an idea of how fast the function
4:16
grows here, with respect to the inputs. Yeah, so on the previous
4:22
slide, I showed you a very, very big leap on the x axis, usually
4:26
when we think of function derivatives, we think of a very
4:29
small change in the input. So we think about what what happens if
4:34
delta x, so the change on the input scale goes to zero is like
4:38
infinitely small. So here on the right hand side, this is again,
4:43
the slope from the previous slide, where I just use the
4:46
letter x now instead of a. And here, these are two different
4:50
ways of denoting that we are computing a derivative. So if we
4:56
have a function f of x, then f prime of x would be the
5:01
derivative of that function. So when I recall from my calculus
5:05
classes long time ago, I think this was called Lagrange
5:11
notation. Whereas this one is the Leibniz notation, you don't
5:20
have to memorize these names. But yeah, they're just two
5:22
different ways of denoting the same thing. The Leibniz notation
5:26
will be a little bit more useful later in the context of deep
5:29
learning when we call talk about your partial derivatives of
5:34
functions, and also your gradients. In any case, let's
5:38
take a look at an example deriving a function or computing
5:42
the derivative more formally. So let's consider again, our
5:45
function to x here. So we are now starting with a simple, just
5:51
a formal notation from above. Now let's plug in, let's plug
5:55
in this function. So if we have x and delta x, the output would
6:02
be what would be the output on should be two x, so two times x
6:07
plus delta x, right. So this one, and here, here, see, I
6:13
just expanded it already. So I'm just expanding this to two x plus
6:20
two delta x. So that's what I have here. And then this one is
6:25
here to x, right? That's where this one comes from. So what
6:29
I've done here is really just plugging in the function into
6:33
the equation here. Now I can see, I have a two x here and a
6:38
two x here. And then I mean, this is minus two x actually, so
6:42
I can cancel those. So this one, and this one cancels. So what I
6:47
have is two delta x divided by delta x. So this can also be
6:52
canceled. And then what remains is the two and that is how we
6:57
derive or compute the derivative of this function. Yeah, let's
7:03
do this again, using a slightly more complicated function. Let's
7:06
take a look at x squared. So how can we derive x squared using
7:11
the same concept as before? So exactly the same notation, now
7:15
plugging in x squared itself to x. So what we get here is for
7:20
the first part is for f of x plus delta x. This is if we
7:27
consider x squared, this would be then x plus delta x squared.
7:33
Then if I expand this, this would be two x, sorry, x
7:39
squared plus two x delta x plus delta x squared. So this is what
7:48
I've written down here. So if I have no this form, I can
7:54
simplify because yeah, if we pay attention, there's again, x
7:58
squared minus x squared, so we can cancel those. So what
8:02
remains is two x delta x plus delta x squared. So now what we
8:10
do is looking at this, we can also further simplify it, right.
8:17
So we can divide actually by delta x. So if I divide by delta
8:23
x, this one goes away, this one goes away, and this one goes
8:28
away. So what, what stays is two x plus delta x. And also
8:34
considering that we are interested in a very small
8:37
chains of x. So when delta x goes to zero, so you can think
8:43
of it as zero. So this kind of also goes away. So the
8:46
derivative is basically two x. So deriving x squared, the
8:51
derivative would be two x.
8:54
Yeah, so conceptually, what we were doing in the previous
8:57
slide, when we computed the derivative of x squared, is we
9:01
approximated the slope by a secant between two points. So
9:07
just to draw out what that how that looks like. So if we
9:10
consider this function, f of x, x squared, so we have this
9:15
parabola here. So now let's consider a concrete point here.
9:21
Let's consider this one here. And the slope of this of the
9:24
function at this point would be this tangent line here, this
9:27
red line, how we approximate it is it is is by taking two
9:33
points. So we took the original point, and then we added delta
9:39
x to it, right plus delta x, x plus delta x. So we added delta
9:46
x to x, let's say this is delta x. So we are here on the right
9:53
hand side. Now we have the second point. So this is f of x
9:57
plus delta x. And then there's this secant line, the line. Yeah,
10:05
between these two points, and we use that line to approximate
10:09
the tangent. And you can see if yeah, the difference is
10:12
relatively large between the two points, right? Between if
10:17
basically, if delta x is very large, then you can see this is
10:19
not a very good approximation. This is why we usually take a
10:24
look at when the tax goes to zero at the limit. So in this
10:30
case, what we would have is we would maybe have a smaller
10:33
distance here, it's still big, but otherwise, I wouldn't be
10:36
able to draw it. And you can see if I now connect this point in
10:39
this point, this is a better approximation of the red line.
10:42
And if I go and make this smaller and smaller, the better
10:46
I will approximate this tangent line here. So this is basically
10:50
conceptually how Yeah, this
10:55
symbolic derivative computation works when we consider this
10:59
small rate of change here. Yeah, here made a cheat sheet for you
11:04
with the most common derivatives, the most useful
11:07
ones to memorize. I don't want to go over all over all of
11:11
these. But yeah, they are in the slides for your convenience. So
11:14
if you need that as a cheat sheet that's in the slides, then
11:18
I hear more derivative rules. So the main ones, the sum rule, the
11:23
difference rule, product rule quotient rule, reciprocal rule,
11:28
these are actually you don't have to memorize these, you can
11:31
actually derive them from the product rule. For example, if
11:34
you consider the quotient rule, you can actually rewrite that as
11:40
um, f of x times g x is one, and then yeah, work with this one.
11:48
So you don't need to memorize the quotient or reciprocal rule,
11:52
you can actually work with a product rule. Um, yeah, so then
11:59
the chain rule, that is actually the most important one. So for
12:02
deep learning, I mean, all of them are important, but the
12:05
chain rule is the main one that kind of drives deep learning. So
12:09
you will see later when we talk about gradient descent, it is
12:13
essentially just an application of the chain rule when we
12:16
compute the derivative of the loss function with respect to
12:19
the weights. Yeah, so here is a visual explanation of this,
12:26
the composition of a nested function using the chain rule.
12:30
So using colors here, it's maybe easier to see. So let's assume
12:34
we have a function, capital F of x that consists of two nested
12:40
functions, f and g here. So what how we compute this is we first
12:47
compute the inner part, and then we compute the outer part. So
12:51
this is just the regular function. So this is visualized
12:54
here in this graph. So we have a computation graph here. So this
12:58
is more like a computation graph view, where we first pass x into
13:03
g, then we get some output. And this output of the inner part
13:08
then goes into the outer part f. And then this gives us the
13:13
result z. So when we then compute the derivative of this
13:17
function, we Yeah, we use the chain rule. And the chain rule
13:21
is two things, what it's two parts, the auto derivative times
13:27
the inner derivative. So we can think of it as the altar, the
13:34
derivative. And here the derivative that we compute here.
13:44
And visually, also, what happens is we can do this separately. So
13:51
we can compute here, in this case, the inner derivative. So
13:56
we pass x to g computer derivative of that. And here,
14:01
that's the auto derivative. So here we are deriving f. And then
14:05
once we have these two results, we can multiply them together.
14:08
And that is the derivative of the whole function. Yeah, one of
14:14
the nice things of pytorch is that it will build such
14:18
computation graphs automatically if we define variables and do
14:21
some computation with those. So pytorch will literally keep a
14:25
computation graph in the background, then. And there are
14:28
utilities then for computing derivatives automatically. So
14:32
pytorch can commute these derivatives automatically with
14:36
using a package inside call, which is called auto grad, so
14:39
automatic gradient computation, we will see that in the next
14:43
week. So usually, it's not required that we derive things
14:47
by hand when we work in pytorch. There are automatic ways of
14:51
doing that. But of course, it's useful to know how derivatives
14:55
and gradients work, because we have to have I think it's a good
14:59
idea to have an understanding of how these types of things work
15:02
before you use packages that can do them automatically. Yeah, and
15:09
here, I just wanted to show you in text, when we write down
15:13
derivatives, we will mostly be using the Leibniz notation. So
15:17
instead of writing this nested thing here, we will use the
15:20
Leibniz notation, which I find personally, a little bit easier
15:23
to read, especially when we have more complicated function with a
15:26
lot of nesting going on. Yeah, so here's just an example
15:32
applying the chain rule in practice on nested function. So
15:37
here we have the nested function log of square root of x. So
15:44
first, it's easy just to take them into two parts. So the
15:49
outer derivative times the inner derivative here. So and then we
15:59
can derive them separately. So now let's just focus on the
16:04
outer one first. So the derivative of the outer function
16:07
is the derivative of log g is one over g. And g, it's just a
16:13
placeholder for square root of x. So the derivative of the
16:17
outer function here is one over square root of x. And then for
16:23
the inner one, so we have the derivative of square root of x,
16:27
I'm just rewriting it here for convenience. And then we can use
16:29
the power rule here, bring the one half up front, and then
16:35
minus one in the exponent, so it's minus one half. And that is
16:40
just rewritten as one over two square root x. So this is the
16:45
inner derivative. And then we just combine them because the
16:48
chain rule is really just sorry, the inner times the outer. So
16:54
here, I'm just putting these two parts together. So the overall
16:57
derivative is one over two x here. Yeah, we can also use the
17:02
chain rule for arbitrarily long function composition. So
17:06
consider this function f of x here, which consists of five
17:10
nested functions 12345. So yeah, we can also expand this using
17:15
the chain rule when we compute the derivative. So if we
17:18
compute the derivative of the function of the auto function f
17:22
here, if we also the derivative of the whole thing here, we can
17:26
decompose that into smaller parts, and then compute all of
17:31
them separately using the chain rule and multiply them to
17:34
compute the derivative basically.

##v37:

0:01
Alright, let's now talk about gradients, the derivative of
0:04
multiple. Alright, let's now talk about gradients, the
0:10
derivatives of multivariable functions. So here, we are now
0:15
interested in functions that have multiple inputs. So note
0:18
though, that the term multivariable and multivariate
0:22
are sometimes used interchangeably. So multivariate
0:25
is usually a more common term. But here, we really mean
0:28
multivariable, because multivariate can mean multiple
0:31
outputs. Here, we are currently only focusing on a case where we
0:34
have multiple inputs and a single output. So for example, if
0:38
you consider linear regression, you can have multiple inputs
0:42
like the features of your data set. So if you have multiple a
0:45
train example with multiple features, or think of the iris
0:48
data set, where you have a simple length, simple width,
0:51
pita length, and pita width, there would be multiple inputs.
0:54
But the output, there would be only one output, for example,
0:57
a continuous value like for regression or class label for
1:01
the prediction. So yeah, in this case, we are focusing now on the
1:06
multivariable functions. So consider a function where we
1:10
have multiple inputs, if we only had one input, we would usually
1:14
write the derivative as follows with a smaller letter D here.
1:21
Now, since we have multiple variables, we have actually a
1:26
vector as the derivative. This is also the so called gradient,
1:30
we use this upside down triangle, the nabla here. So
1:35
this is, I think it's spelled like this nabla. So here, we
1:41
have multiple things going on now in this vector. So each row
1:45
is a partial derivative. So what is a partial derivative? It's
1:49
essentially like the full derivative. However, it's for a
1:54
function where we have multiple input arguments. And if we
1:57
compute the partial derivative of f, with respect to x, what we
2:03
do is we set y and z here, or if we have multiple ones, we set
2:09
all of the all of these as constants, so we treat them as
2:13
regular numbers, not as variables, while we compute this
2:17
one. And then once we have computed this partial
2:19
derivative, we then focus on the second entry, the partial
2:23
derivative of f with respect to y, while considering x and z as
2:30
constants and so forth. So we compute each derivative one at a
2:34
time, the rules are the same as for the full derivative. So
2:38
really, the big difference here is only that we treat the other
2:41
variables as constants. But yeah, that is essentially a very
2:44
similar concept. So here's an example to illustrate that. So
2:49
consider this function here x squared y plus y, so that two
2:53
inputs x and y for this function here. So when we then compute
3:00
the gradient of this function, we have two partial derivatives,
3:04
the partial derivative of x with respect to the partial derivative
3:09
of f with respect to x, and the partial derivative of f with
3:13
respect to y. So we can compute them separately, we don't have
3:17
to intermix them, we can do one at a time. So let's start with
3:21
the partial derivative, use the same color, maybe partial
3:25
derivative of f with respect to x. So what we do is we can, we
3:32
treat y as a constant, so you can think of it as a regular
3:38
number. So it's essentially like computing x times one plus one,
3:44
something like that. So and if you think of the power rule, what
3:49
happens is the two goes up front and then minus one, so it will
3:53
be just two x. And this one will stay right. So if this was a two
4:03
or something, this would stay. So here also the y stays, so we
4:08
have two x, y, and then plus the derivative of a constant is zero.
4:13
So plus zero, so the derivative would be two x, y for this one.
4:18
So using the power rule and the constant rule. Now, we have
4:22
computed this partial derivative to x, y. Now we can compute the
4:27
partial derivative for the second entry for the partial
4:33
derivative for f with respect to y. So that's what I have down
4:38
here. Notice, instead of x, we are focusing now on y. So x here,
4:45
x is no constant. And if this, this basically then stays, right,
4:54
so we have then just to x squared as the constant. So it's
5:01
like, if you consider a case where we have something like two
5:05
x, and we compute f of x, we compute the derivative of df with
5:11
respect to x. So this would be two, right. So in the same way,
5:16
if this is a constant, the y goes away, it just stays. And the
5:21
one is also constant, sorry, the y here is the variable. So the
5:30
derivative of just the variable is one, right. So then the
5:34
derivative of the whole part would be x squared plus one.
5:40
Alright, so we have both and then we just arrange them in the
5:43
vector here. And this is our gradient. Okay, now let's
5:48
consider the case where we have a composite function like the
5:52
following one, notice that we have two inputs. So we have g
5:57
and h, two inputs here, but they both rely on the same input
6:04
argument here. So there's an inner x that is shared by both
6:10
functions here. So remember from the regular chain rule that I
6:14
explained in the last video, if we have a function nesting like
6:18
this one, and we want to compute the derivative, we can do this
6:22
by computing the derivative of the outer part times the
6:28
derivative of the inner part. Now for the two inputs, we have
6:35
the following case, they depend, they have a dependency that
6:38
depend both on x. So it's a little bit trickier. So we
6:42
actually combine them because we have this dependency here. So we
6:47
still use the chain rule here, but we combine the results. So
6:51
if we want to compute the derivative of this function,
6:54
with respect to x, the inner argument, so note that we are
6:59
not computing, we are not computing partial derivative of
7:04
g of f with respect to g and for example, h separately as the
7:13
gradient, because both really depend on x, I mean, we do this,
7:19
we do this, and this is part of it, but it's not the end result
7:22
compared to the previous slide where we had a gradient where we
7:25
had different input arguments. So here, like I just said, we
7:32
have these partial terms with respect to g. So let me use
7:36
different colors. For this part, this is one part and this is the
7:44
other part. However, both share the same x. So the derivative of
7:49
this function with respect to x, the one argument. So in fact,
7:53
we have one argument in a way here, we combine them here with
8:00
where's my yellow with this plus symbol here. So let me clear
8:05
this is maybe more clear like that. We still use the chain
8:08
rule, let's maybe focus on on this part. For this part, we
8:13
still use the chain rule like here. So we have an inner and
8:16
an outer part. So the outer part is a partial derivative f with
8:20
respect to g. Here, we use the partial symbol because there's
8:24
g and h. However, there's only one input argument to g. So here
8:30
we use a little D. If you don't do this, like consistently like
8:34
that, I think no one would blame you if we just use partial
8:37
symbols, that would be fine, too. But yeah, this would be the
8:39
proper way. So this would be the derivative for this part. And
8:45
then for the second part, we have a partial derivative of f
8:50
with respect to h. So and then the inner part. So let me do
8:56
this one more time. So this is one part, this is the other
9:01
part. And here we have the chain rule for each of them, the outer
9:05
one, and the inner one. Here, we also have the outer one, and the
9:11
inner one. Alright, let's take a look at an example to apply
9:17
this in practice. Yeah, consider the following function where we
9:22
have two input functions g and h. So this is just for
9:27
reference what I had on the previous slide. And the function
9:30
is g squared h plus h, where g is also a function that takes
9:36
this input x, where this is 3x. So the function g is 3x. And
9:42
then h also is a function taking input x. And so this function is
9:46
x squared. Alright, so I'm doing it one at a time. So let's
9:51
focus on this part first, which is here. So here, this is the
9:56
partial derivative of x with respect to g. So if we take a
10:02
look at this, and differentiate it with respect to g, use the
10:08
power rule. So this goes front and goes away. And this is a
10:12
constant because it's a partial derivative, h is a constant. So
10:16
this also goes away. So what the result is, is 2gh. So now, let's
10:23
take a look at the inner part. So the inner part of g, so let
10:29
me use this color. So g is 3x. So we are looking at this one
10:33
now. So the derivative of 3x is just three, right? So if we
10:39
derive g with respect to its only input, so there's only one
10:43
input, then we don't have to treat anything as a constant,
10:46
because there is nothing else except x. And the derivative of
10:49
that is three. Now, let's take a look. So we solved basically
10:53
this in this part. Now, let's take a look at the other part
10:57
here, the partial derivative of f with respect to h, the other
11:01
argument. So if we treat, so if we compute partial derivative of
11:08
f with respect to h, then we treat everything that is not h
11:12
as a constant. So this is a constant. So in this way, if g
11:18
squared is a constant, then the derivative of this part with
11:22
respect to h would be g squared, right? So we have g squared. And
11:29
this is then one right, the derivative of a variable is just
11:33
one. All right, so g squared plus one, I have it somewhere
11:38
here. Right. So here we have it. And then the last part, the
11:44
derivative of h with its with respect to its input x, so which
11:49
color do we have left here, this one, maybe. So let's compute
11:54
this terminal on the derivative of h with respect to x. And h is
12:01
x squared. So the derivative should be two x using the power
12:05
rule. So that's two x. And now we just bring everything
12:08
together. So we have the first part in the second part. So I
12:13
don't have any colors left that I haven't used yet. So let me
12:17
just just use black for this left part here. We bring those
12:23
together. So this is basically this part. And then for the
12:29
right part, here, we bring those those together. And this is this
12:39
part. And then if we just simplify this, so if you take a
12:43
look at this, and you expand these terms, it simplifies as
12:46
follows. So this would be how we use the multi variable chain
12:51
rule. Yeah, I don't want to go overboard. But we can also go
12:57
one step further and write this more compactly using vector
13:00
notation. So again, the same function here, f with two inputs
13:05
to input functions g and h, which in turn take both x as
13:10
input. So if we compute the derivative, this is what we have
13:13
written down before. And we can also write this more compactly
13:16
using vector notation, writing it as gradient of f with respect
13:22
to its inputs, and then times the derivative of a vector v. So
13:27
the vector v, we define it as a vector containing those two
13:30
inputs here. And then the derivative would be the derivative
13:36
of this vector would be containing both the derivative of
13:40
g with respect to x, and the derivative of d with respect of
13:45
h with respect to x. So this is more like a compact form of
13:48
writing down these partial terms. So basically, this term,
13:52
and this term, sorry, not the partial terms, but the inner
13:55
terms. So these are the inner, in other words, and now then
14:04
putting it together. So where this comes from, I mean, if you
14:08
then consider the gradient of the function with respect to its
14:10
inputs, and so that's the gradient we discussed. So the
14:15
partial terms, and then here the inner terms. And if you look at
14:20
it now, so if you use or compute the dot product, right, so in
14:25
order to compute the dot product, what we have is, use
14:30
this color, this times this plus this times this, right. So this
14:37
is how we usually compute the product. So it expands to this
14:41
one. So it's just like a little convenience thing to write
14:45
things more compactly. Yeah, there's one more concept to
14:50
cover the Jacobian matrix. So consider now a case where f is a
14:54
vector. So you have a vector f where f is a function, and there
15:00
could be multiple inputs. So let's consider the expanded form
15:04
here. So this vector, so there's f1, f2, f3, fm, different
15:08
functions, each of them has the inputs x1, x2, x3, xm. So this
15:12
could be, for example, a case for perceptron, where you have
15:19
net input function, and it takes multiple features as input. So
15:23
the Jacobian of this vector here is written down here. So the
15:29
Jacobian is a matrix where all the combinations are
15:33
considered. So the partial derivative of f1 with respect to
15:36
x1, the partial derivative of f1 with x2, with respect to x2, the
15:41
partial derivative of x, f2, with respect to x1, and so
15:45
forth. Yeah, so you can see all the different combinations here.
15:49
Alright, I see I have highlighted one thing just to
15:54
highlight this is the gradient of function one, for example,
15:57
with respect to its inputs, if you recall the gradient that we
16:00
discussed earlier, so that each each row of these of this
16:04
Jacobi matrix would be basically a gradient of a function or
16:07
function gradient. Yeah, okay. So second order derivatives. So
16:13
let's talk about second order derivatives. No, I'm just
16:16
kidding. So we won't be talking about second order derivatives
16:18
because we won't be needing it for this class. Actually, second
16:23
order derivatives can be useful. Some people have done some
16:26
research working with them in deep learning. But so far, it
16:29
has not been very fruitful. I mean, the results, I mean, there
16:33
are proof of concepts that it conceptually works, but it is
16:35
very slow. And there's not really any advantage over using
16:39
first order methods. So despite some research efforts, especially
16:44
as far as I know, no one is really seriously using second
16:48
order gradient methods. Yet, I mean, at least while I'm at the
16:54
point when I'm recording this, maybe in the future, there will
16:57
be a method that is vastly superior compared to our
17:01
current methods. But so far, it has not been done very
17:05
prominently or very, I wouldn't say successfully, because the
17:09
research in itself was successful, but it's not very
17:13
practical, I would say. Alright, so with that, let's not worry
17:16
about second order methods, then. Let's go back to the more
17:20
exciting parts to the machine learning and deep learning
17:23
parts. So the next two videos, I will be wrapping up on this
17:27
lecture on gradient descent and then training a single layer
17:30
of neural network.

##v38:

0:01
Yeah, no equipped with the knowledge of what a function
0:04
derivative is. Let us use the idea from calculus to train a
0:08
linear regression model using a method that is called or related
0:12
to
0:16
Yeah, no equipped with the knowledge of what a function
0:18
derivative or gradient is. Let's now take a look at training a
0:22
linear regression model using these concepts.
0:25
But yeah, no equipped with the knowledge of what a function
0:30
derivative and gradient is. Let's not train a linear
0:33
regression model. So this technique in the context of
0:37
linear regression is
0:41
yeah, no equipped with the knowledge of what a function
0:43
derivative and gradient is. Let's not train a linear
0:47
regression model. So for this, we will be using a technique
0:50
called gradient descent, which is related to computing
0:53
function derivatives and gradients. So consider the
0:58
linear regression model here again, where the activation
1:00
function is just the identity function. So this is just like a
1:06
regular linear regression model. And we have one output here. So
1:10
this is our prediction. And for yeah, fitting or finding these
1:15
weights, we want to minimize the loss or the prediction error of
1:19
linear regression. For this, we formulate a convex loss
1:23
function. In the case of least squares, a linear regression,
1:27
that's the sum squared error, we can also consider the mean
1:31
squared error doesn't matter. So either one would work. So for
1:35
this squared error loss, what we have is we have the prediction
1:39
minus the actual value that we want to predict. So we consider
1:43
the difference between the two squared. So why the squared? I
1:47
mean, this way, your outliers will be more heavily penalized.
1:50
And also, it doesn't matter whether one or the others on the
1:55
left or on the right hand side, side, in any case, so if we
1:58
would plot this now, so by the way, I should say, this is over
2:02
the training examples. So if we have a data set with n training
2:06
examples, this would go from first to the last training
2:10
example. So the loss on the training data set. So now, um,
2:15
yeah, I plotted the loss here on the at the bottom, as a function
2:19
of one of the weights. So you notice there are usually sorry,
2:24
usually multiple weights. Here, we are looking only at one of
2:28
the weights, because it's simpler to look at, but you can
2:30
also generalize this concept to multiple dimensions. So what you
2:35
can see is this bowl shape or parabola shape. And the loss is
2:41
minimum for a certain value of the weights. So if the value of
2:46
the weight is too large, you can see the loss goes up. Or maybe
2:50
it's easier to see it like if we go to the right of the weight is
2:53
larger, you can see it has a higher loss in the same way for
2:57
this weight here that is too small. So there is a so called
3:03
global minimum that we want to find. So we want to find this
3:13
global minimum for the weights so that our prediction error or
3:16
loss will be minimized. We will do that for of course, all the
3:20
weights. So if you think of this in three dimensions, so if we
3:24
have this w one and a second weight, this would be a like a
3:28
bowl like a cereal, like a cereal bowl or something like
3:32
that, where you want to reach the bottom of the cereal bowl.
3:36
But yeah, it's easier to think of it as maybe it was one
3:38
dimension. Yeah, let's now see what happens if we use the
3:45
concept of gradient descent. So what we do is we have to start
3:50
with a certain weight, let's say this weight, this is our
3:56
starting point. So in practice for linear regression, we
4:00
usually initialize the weights to all zeros or small random
4:03
numbers. So if I had initialized the weight with the value zero,
4:07
we would be over here. And you can see also, yeah, the loss
4:10
would be pretty large here at zero, we want to find basically
4:15
this global, global minimum. That's our goal. So if you
4:24
think back, if you have seen the optional video on the
4:28
derivatives, so this is like almost like the squared function
4:32
that I talked about, so x squared, right. So and we can
4:38
compute derivative of this function. So the derivative of
4:42
this function with respect to w one, for example, if we
4:46
consider our starting weight, so this is the weight we currently
4:50
consider or we start with, let's say this is small, random
4:53
number, we can compute the function derivative at this
4:56
at this point. So here, so and then using this, we can. So I
5:03
should say, actually, the derivative should point upwards
5:07
here in this direction. But this is this arrow here is the
5:10
negative, the negative slope. So this arrow here is the negative
5:18
slope. And we can use this negative slope in multiple
5:22
dimension, you can think of it as a gradient instead of a
5:24
derivative, we can use this function gradient to guide the
5:29
weights into the direction of the global minimum. So the slope
5:35
would tell us how steep the function is. So at a given point,
5:39
how you how steep the function is, but we are interested in
5:43
the negative slope, which is also giving us the steepness of
5:48
the function, but instead of pointing upwards, it's pointing
5:51
downwards, it's pointing towards the minimum that we want to
5:55
reach. So we can use then this value, this negative slope or
6:00
negative gradient to guide the function downwards towards this
6:05
global minimum. So we make small steps towards the global minimum,
6:10
one step at a time. And for that, we have, as I've showed
6:14
you, I think in the second video of this lecture, we had a so
6:17
called learning rate at a and so the learning rate at a together
6:22
with how steep it is guides how much we update. So you can see
6:28
here at the bottom, it becomes a bit flatter, right? So the
6:32
function is not as steep anymore. So in these cases, we
6:35
also make smaller steps because the update really depends on the
6:38
steepness, and also on the learning rate. So let the
6:42
learning rate would all scale these on slopes by a constant.
6:48
So the learning rate is usually a constant that scales all of
6:51
these slopes. That is like an optional step, you don't have to
6:54
use learning rate. But in practice in deep learning, it's
6:58
kind of required to have a learning rate. And also, there
7:01
will be extensive tuning into what is a good learning rate. So
7:05
this is something where you would have to try different
7:08
learning rates and see what performs better. But this is
7:11
something that will be done later in this class. And I will
7:14
probably also make a homework about that way you have to play
7:17
around with this a little bit. So if you have a learning rate
7:23
that is too large, what might happen is that you might
7:26
overshoot. So if you choose a learning rate that is very large,
7:30
you may make an update. So let's say you make an update here,
7:34
this is maybe a little bit exaggerated. So you move from
7:37
this weight position to this one. And then the next update is a
7:42
large update here. So in this case, the update has been too
7:47
large. So you're overshooting the global minimum and depending
7:51
on what you find here, you may overshoot even more and then you
7:55
kind of lose the way so your loss will increase, you can see
8:00
that happening in practice, if you use a learning rate, it is
8:02
too large. So notice here also, I'm only again, always looking
8:06
at one weight, but there are weights in multiple dimensions.
8:11
So in that way, there's a lot of possibilities, something like
8:15
that can happen if we use a large learning rate. So it's
8:17
actually better to make like smaller baby steps to watch at
8:21
what the towards reaching this global minimum. However, if we
8:25
make the learning rate too small, it will just take a very
8:29
long time until we reach this bottom. So we make all these
8:32
little baby steps that will take a lot of iterations or a lot of
8:35
updates to reach this global minimum. In practice, for a
8:39
convex loss function like this one where we have a global
8:42
minimum, that is easy to reach because everything is convex,
8:46
then it's not a problem usually to have a small learning rate,
8:49
we have to just be patient. In practice for deep learning, this
8:52
would be a problem because the algorithm can get stuck. So in
8:57
deep learning, we usually have loss functions that are not
9:01
convex. So we can have a loss function that we draw you an
9:03
example, we can have a loss function that is somewhat,
9:08
let's say like like this. So if we have then a weight where we
9:13
start here, let's say we go down here, then it goes down here.
9:18
Okay, this would actually be a good case. Sorry. Um, let's
9:21
let's start here. So if we start here, we make small steps, then
9:25
we may end up in this, in this pit here, this is a local minimum.
9:34
So actually, I made it relatively steep. So you would
9:37
probably end up in this one eventually, anyways, but let me
9:40
make a maybe a flatter one, like something like this. So what
9:50
could happen is if you have a very small learning rate, you go
9:53
from here into this pit, and then you get stuck here. And
9:57
because the learning rate is not large enough at this point here
10:00
to jump over this, for example. So in this case of having a too
10:04
small learning rate can also be a little bit bad. But in
10:07
practice, we will later talk about algorithms that have a so
10:12
called momentum term and yet to overcome these little challenges
10:16
also. Okay, so but moving on. Yeah, you have the overview of
10:21
the online mode again, just for reference to just show you what
10:25
we want to get at now. So what we want to do is we want to find
10:29
this global minimum. So just pay attention to the right hand side
10:32
here. This is the stochastic gradient descent. There's also a
10:35
batch gradient descent, I will say a few words about that. But
10:38
here, for simplicity, consider the case where we update one
10:42
training point at a time. So in this case, what we do is we
10:46
compute the gradient of the loss function here. So you can see we
10:51
compute the gradients here. And we have this for w and the bias
10:57
and in that case, it would be just the partial derivative, not
11:01
a gradient. But let's use the same symbol, the number for
11:05
everything. It's I think simpler compared to switching between
11:08
different symbols. So then our update is based on the current
11:13
weight, and then the learning rate. So this is the learning
11:17
rate again, times the negative gradient, you can see there's a
11:23
negative now the negative sign. So this is because we want to go
11:27
towards the global minimum and not upwards, right. So we don't
11:31
want to make the loss larger, we want to make the loss smaller.
11:33
So we take a step into the direction of the negative
11:36
gradient. So here, we use actually these gradients to
11:39
update. So what are these values? So where's this value,
11:46
and this value come from? Where does these values come from? So
11:50
for that, we can yet derive our loss function, right. So we can
11:53
derive our loss function with respect to w, and with respect
11:57
to B.
12:02
Yeah, let's not arrive the loss function with respect to w. So
12:07
here, we are only taking a look at one of the weights on w j.
12:12
Just to keep it simpler, we could also do this for the weight
12:15
vector. But yeah, recall, the gradient of the loss would be
12:21
just a collection of these individual partial derivatives,
12:24
right. So we would have the partial derivative of the loss
12:27
with respect to w one, w two, up to w m. So that would be a
12:38
vector. So here, we are only taking a look at one of these,
12:41
for example, the first one, let's call it w j, some of the
12:45
arbitrary entries here in this gradient vector. So we are
12:51
considering here the sum square error loss. So in the previous
12:54
slide, I showed you for simplicity on the stochastic
12:57
version where we only update or compute the gradient based on
13:01
one training example at a time, which would be an approximation
13:04
of this overall loss function, right. So if I only consider one
13:08
data point without the sum, so if I ignore the sum, this one
13:12
would be only an approximation of the overall loss function on
13:15
the training set. So here, using the whole training set, it's
13:19
actually more accurate. This is also sometimes called just
13:22
gradient descent or batch gradient descent, if we use the
13:26
whole training set where we have i equals one up to n. And then we
13:34
can also consider the smaller case where we only have a mini
13:38
batch. So if we have a mini batch, if this is, let's say a
13:42
mini batch of size k, and k is smaller than n, this would be
13:48
the mini batch version. This goes back to what I explained
13:51
at the very beginning of this lecture, where we have this
13:53
online mode, mini batch mode, and batch mode, how we compute
13:57
the gradient, it's the same concept, except that here, we
14:00
have this sum everywhere, but you can also ignore the sum, and
14:04
then it would be for the online mode. Alright, so what we do
14:08
now is let's, yeah, we are deriving now the loss with
14:13
respect to the weight. Let's take a look here. This is just a
14:16
sum squared error loss that I have written down again. Now we
14:19
are differentiating this loss with respect to w j. So first
14:24
step is I'm expanding this term here, the prediction. So if you
14:28
recall how we compute the prediction, it's the weights
14:33
times the feature values plus the bias, right. So here, I'm
14:38
ignoring the bias, let's say it's implicitly included in the
14:42
weights. So we are only looking at everything without the bias
14:46
just for simplicity. I've actually included it here, but
14:48
maybe ignore this for now. Yeah, and then we have the activation
14:55
function. And the activation function was just an identity
15:00
function. So I'm just using this one here, writing it more
15:03
compactly with using vector notation w transpose x using
15:10
vector notation here. So that's what I'm what I have here. So I
15:16
just expanded this one. And now we are using the chain rule to
15:23
compute the derivative. So the chain rule is the outer
15:27
derivative times the inner derivative. So here, notice we
15:32
also the outer function would be this one basic. So this is the
15:38
inner in red, and then the square t would be the outer
15:41
function. So what I'm doing is I'm deriving now the outer one
15:44
this is this part here, this is the outer derivative, we write
15:48
this down using the power rule. And then on the left hand side
15:52
here, that's the inner derivative for the outer derivative, we
16:00
are basically done. So we don't have to do anything on the left
16:04
hand side. So the left hand side is done. Now let's take a look
16:10
at the inner derivative. So if we take a look at this inner
16:13
derivative, we see, okay, there is another chain rule application
16:19
required, right? Because again, we have different things going
16:23
on here, we have the activation function, and then there is the
16:26
value inside the activation function. So let's now consider
16:32
the chain rule again, when we compute the outer and the inner
16:36
derivative. So the way I've written it here is again, on the
16:39
left hand side, the outer derivative. So this would be
16:44
what would be the auto derivative, the derivative of
16:50
this activation function with respect to its input. So the
16:53
input is this term wt, w transpose x. And then on the
17:01
right hand side, I have the derivative of the inner part. So
17:06
this would be the inner part, notice, we cancel the minus y,
17:11
because this is just a constant. So this goes away.
17:14
All right, so looking at this here, now, this term, what if we
17:25
compute the derivative of this, this whole term with respect to
17:28
w, the result would be x, right? So because we computed the
17:34
derivative with respect to w, j. So the of this term, with
17:41
respect to w, let's say w, j, because w is a vector would be
17:51
oops, xj, because all the other values in that vector would be
17:56
constant. So this is what we have here. So that's what we
18:03
have left over if we derive this part. Now we are left still with
18:08
the outer derivative to do. So the outer derivative, if we
18:13
compute that the derivative of sigma with respect to its input
18:16
is one. So why is that because we have the identity function
18:21
here, right? So the derivative of this function. So let me
18:28
write this down. This would be one, right? So this goes away.
18:34
So what we are left here with is just xj. So the derivative of the
18:42
loss function with respect to the weight is y hat. So if I
18:47
would condense this, again, actually would be two times y
18:52
hat minus y times xj. And this would be the derivative of this
18:58
loss function with respect to this w j. And in each iteration,
19:04
when we do the update or the training, we can compute this
19:06
value and update the weight values, right? So we can use
19:11
this term now to update the weight. So if we have the weight,
19:17
we update it by itself, plus then the learning rate times the
19:26
negative version of this whole part. This would be how we
19:30
update the weights in each round to minimize this loss function.
19:36
So here I have an alternative notation of this whole thing.
19:39
This is actually what people do in practice. So usually to make
19:44
this a little bit more stable with in terms of the learning
19:46
rate, so that the learning rate doesn't depend on the size of
19:49
the training set, we actually compute or use the mean squared
19:54
error. So here, we have a no one over n. So just averaging the
20:00
rest is all the same, except that I know have this one over
20:03
n. But also notice that it's not only one over n, it's over two
20:07
n. And again, this is really to make things more convenient,
20:12
because then when we use the power rule, so if I use the
20:16
power rule here, the two goes in front, right, so I have two over
20:20
two n, and then the two cancel, and then I'm just left with one
20:26
over n. And this is a little bit more convenient, convenient. So
20:29
this one is usually the one that is used in practice, because
20:33
then if I use this one, for updating the weights, I can
20:37
choose a learning rate that is independent of the size of the
20:40
training set or independent of the size of the mini batches.
20:42
Otherwise, if I change my data set or my mini batch size, I
20:46
have to find the learning rate every time from scratch again.
20:50
Actually, it's important to find the learning rate for each new
20:53
data set anyways. But if we play around with different, different
20:58
mini batch sizes, it would be more robust if we use the one
21:02
over n, this is usually what we do in practice. Yeah, so here's
21:06
how gradient descent looks like for a loss function with Yeah,
21:13
so here's again, how gradient descent looks like using a
21:17
surface plot. So here we have again, the mean squared error
21:20
loss, and we are looking at two weights now. And the global
21:24
minimum is here in the center. Now, suppose we start with a
21:33
weight here, let's say this is our starting weight. And the
21:38
lines here, these contours indicate how large the losses.
21:42
So of course, the other closer you get to the local minimum,
21:44
the smaller the loss. And that's where we want to get at, we want
21:47
to get to the global minimum. Now, if we use the batch gradient
21:52
descent, where we derive the loss function based on the whole
21:58
training set, let me just quickly write this down here
22:05
again. So if we compute the derivative of this one with
22:10
respect to the whole, yeah, considering the whole data set,
22:14
then we will make direct leaps towards the global minimum. So
22:18
each update will be perpendicular here to the contour
22:22
lines. If we use something like stochastic gradient descent, so
22:27
that is if we only update based on one data point at a time, or
22:31
based on a mini batch, then the updates will be a little bit
22:35
noisier. So instead of going straight to the center, there
22:39
will be like this little zigzag. For linear regression, this is
22:43
probably not ideal, because it's Yeah, why would we want to do
22:47
that? It's there's no point doing that. If we can do these
22:51
direct steps, make these direct steps, why would we do one step
22:54
at a time, maybe one advantage is if you have a very, very,
22:57
very, very large data set, then this will train the linear
23:01
regression model quicker, because you will be having more
23:05
updates per epoch. So if you have batch gradient descent, you
23:09
only have one update per training epoch. And with mini
23:13
batch gradient descent, you have more updates per epoch. However,
23:18
each update itself is noisier. Again, for linear regression, it
23:22
probably doesn't make sense to use mini batch gradient descent.
23:25
But later, when we talk about deep learning, we have non
23:28
convex gloss functions. So we probably won't be reaching the
23:31
global minimum anyway. And in this way, using these little
23:35
stochastic gradient descent updates, I say are actually
23:38
better than these complete gradient updates. Yeah, also one
23:44
more note about data normalization. So I think I
23:49
mentioned it before that it is important to normalize the input
23:52
data so that the features are all on the same scale. So this
23:57
is not a problem. For example, if we have something like Iris
24:01
where everything is already on centimeter scales, but it's still
24:04
helpful to make these values smaller, because there will be
24:07
certain weight initialization schemes, we will talk about this
24:11
in a separate lecture, how to initialize these weights well.
24:15
But if we have, let's say data sets where we have features on
24:19
me at different scales, let's say one is something like income,
24:25
and the one is H. So if let's say H, and income is your
24:29
features and income is a dollar amount. So let's say you have
24:33
something like, I know $50,000 or something per year, and the
24:38
age is maybe 23 or something like that. So these are very
24:42
different scales. So one scale is from maybe 10,000 to 10
24:47
million, whereas H is between, let's say, zero and 100. So in
24:53
this way, what happens, what the problem is, is that these
24:58
contour lines will be more like skewed, so they will be more
25:01
like elliptic. And then it will be harder to update, because
25:06
remember, we are computing the gradient of the loss. So that
25:09
considers all the directions. And then we may make these steps
25:15
that are not directly pointing towards them. I mean, they are
25:20
pointing towards the minimum in a way in one direction, but in
25:22
the other direction, we make maybe a larger leap. So actually,
25:27
maybe if we we, we overshoot basically, and then we also end
25:31
up zigzagging. So this way, it helps actually initializing the
25:36
weights with small random numbers, but also normalizing
25:39
the inputs. About the weight initialization, we will have a
25:42
separate lecture talking about different strategies for
25:46
initializing the weights. Well, of course, for a simple case,
25:49
like linear regression, it doesn't really matter that much,
25:52
but it will matter when we talk about deep neural networks. So
25:56
you can really think of deep neural network training as
25:59
applying the same concept that we talked about in this lecture,
26:02
exactly the same concept, but to a more complicated network. But
26:06
we will also be computing the derivative of the loss with
26:09
respect to the weights. But in the network, we have multiple
26:13
layers and multiple weights. But except that it's very, very
26:16
similar. Alright, so then, yeah, to end this lecture, let's talk
26:22
about training a single layer neural network. So an extension
26:27
of linear regression for classification. So the adeline
26:30
the adaptive linear neuron.

##v39:

0:01
Yeah, so the last couple of videos included a lot of
0:04
mathematical details, which may not be super exciting. So let's
0:08
now take a look at a more hands on example, and do something
0:12
get more hands on training and adaptive linear neuron in Python.
0:15
So here, I will just give you the overview of how things
0:20
relate to the airline. So recall the airline, that is what we
0:25
covered briefly in the history of deep learning lecture, that
0:28
is a model by Woodrow and Hoff in developed in 90 and around
0:33
the 1960s. So actually was a physical device, but you can of
0:36
course also nowadays, yeah, implemented in software. And
0:40
this is a nicely differentiable neural model. So the perceptron
0:45
model that we talked about before is not differentiable
0:48
because of this threshold function. So this airline, you
0:51
can think of it as an advancement of this perceptron
0:54
that is now also converging, even if the data is not
0:57
linearly separable. So yeah, just for comparison, so how the
1:03
perceptron looked like, so recall in the perceptron, you
1:06
will we compute the net input first, and then we pass the net
1:10
input through a threshold function, and then the
1:13
threshold function produces our output. So the output is the
1:19
predicted class label, which can be either zero or one. And if
1:25
the prediction matches the actual label for that given
1:30
training example, then we don't do anything. But if it doesn't
1:37
match, if it's different, then we have this error term that we
1:42
computed. So we have the difference between the two. And
1:45
we use that to update the weights. So we update the
1:48
weights, which then will change the decision boundary to make
1:51
to make the prediction correct. So that is how the perceptron
1:55
works. But a threshold function is not differentiable. So here,
2:00
we couldn't use calculus, there was just this rule that was
2:03
developed by I would say thinking hard about this
2:06
problem. So it was more like an empirical update rule. Now, we
2:10
can actually improve that by using calculus. So at the
2:15
bottom is the airline. So here, you can think of this part here
2:19
as the maybe base model. And this is like linear regression
2:24
works. So again, we also compute the net input similar to the
2:28
perceptron. Now we have as an activation function, we have
2:32
this identity function, which is not doing anything. So if it's
2:38
not doing anything, if my activation function is just the
2:41
identity function, why do I write it down in the first
2:44
place? That's because next week, or the week after that, we will
2:48
be talking about nonlinear activation functions, we will be
2:52
talking about functions that are, for example, sigmoidal
2:57
function, like, like this one, for example, so we will be
3:02
covering other types of activation functions. And we
3:06
will need them to develop multi layer networks, because this
3:10
will help on multi layer network to produce nonlinear decision
3:15
boundaries for solving complex problems. Because if we would be
3:18
using linear activation functions in a multi layer
3:21
neural network, then the multi layer network would be just a
3:24
combination of linear functions. And the sum of linear functions
3:29
is also just a linear function, so we wouldn't gain anything. So
3:32
later on, we will be talking about nonlinear activation
3:34
functions. And here, you can think of it as a placeholder, we
3:38
will replace that later, I'm just including it here in the
3:41
notation. Because it's a more general notation that would
3:44
apply to also nonlinear activation functions. Okay, now
3:49
consider this linear regression base, in order to turn this
3:53
linear regression model into an adaptive linear neuron into the
3:57
Adeline model, all we have to do is now adding a threshold
4:01
function, because the Adeline model is a classifier. So this
4:05
is a classifier for classifying data points similar to the
4:10
perceptron. However, note the difference here really, between
4:14
the perceptron and the Adeline is where we compute the error.
4:18
So for the perceptron, we compute the error after the
4:23
threshold function. And in the Adeline, we compute the error
4:27
before the threshold function. So here, we don't have the
4:31
problem that things are not differentiable, because we
4:34
computed before the threshold function, the threshold function
4:37
still is not differentiable. But we don't worry about that,
4:41
because we compute the gradients before that. So in that way,
4:45
it's not a hindrance, and it will become more clear when I
4:48
show you the code example. So here's just conceptually how it
4:53
looks like when we fit an Adeline model. So here, what I'm
4:56
just doing is I'm showing you the class label on the y axis.
5:00
So for binary classification, where we have to classification,
5:08
where we have two class labels of one and zero, I have plotted
5:12
them here. So the class labels can be either one or zero. And
5:17
then we have only one feature value for simplicity here. And
5:21
yeah, we want to predict that in the linear neuron is a linear
5:25
model. So essentially, what it will learn is will fit a linear
5:29
line similar to linear regression. So this would be very
5:33
similar to linear regression, right? Except now the difference
5:36
is really that in linear regression, we usually have
5:39
continuous values, not only zeros and ones, and we don't
5:42
have the threshold function. So in the Adeline, after fitting
5:45
this model, we apply this threshold function, let's say at
5:49
point five between zero and one, and we say, then if something
5:57
if something is bigger than a certain value, so if the it's
6:03
maybe a little bit unfortunate, I wrote class table here,
6:05
because this is the threshold, if the prediction, let's say,
6:09
prediction, if the prediction is greater than point five, produce
6:14
class label one, and otherwise, produce class label zero. So in
6:22
that way, we turn the continuous prediction into a class label.
6:26
Again, this will become clear when I show you the code
6:29
example. So I prepared some code examples. Let me pause this
6:34
video and do this in a fresh video. So there will be another
6:37
video where I will go over these code examples.

##v40:

0:00
Yeah, now let me show you a code example of linear regression and add a line trained with gradient descent. So I prepared two code
0:08
files, one is called linear rigor, or regression, gd. So gd
0:13
here, this would be the regular gradient descent version. And then I will train an airline model with stochastic gradient
0:20
descent. However, note, you can also do it the other way around, you can train the linear regression model with stochastic
0:25
gradient descent, and you can train the airline model with gradient descent. So it's kind of interchangeable. And if you like, you can play around with that later on. So let's do one
0:34
thing at a time. So I have my watermark here again, just to show you what software versions I'm using here. And then now
0:41
here, the linear regression model with gradient descent. So what we're doing is we're training this model here. So the
0:48
training is up to this point. And then the threshold function is only used later on when we do the prediction of the class
0:55
labels, that's after training. So for training, we don't need the threshold function. All right. And yeah, again, like
1:02
know that they are very similar. So here on the left, so on the left hand side, I have an overview of the code that I'm
1:11
implementing below. So now these two are exactly what I implemented in these two notebooks, I was just screenshotting it to show
1:18
you that they are indeed the same. I have them on the left hand side as linear regression on the right hand side as
1:24
Adeline. And they're exactly the same, the same code, except after training, we can for Adeline, then here use a
1:31
threshold function to produce the class labels, but know that these are indeed the same codes that are used here. So we will
1:39
go over these codes, of course, in this notebook. Alright, so we initialize some stuff that we will be using some libraries, I
1:47
prepared toy data set here, just some simple data set containing
1:52
two features x one and x two. So tail is showing the last five lines of this data set of the CSV file. And there are 1000
2:01
training points. So yeah, we have two features x one and x two and one output value y. So this is a regression problem. So
2:10
it's a continuous output value here. So okay, let's start by
2:15
creating here our design matrix and pytorch. So here, we will
2:20
have a design matrix consisting of the two features, and then the class label as a separate tensor. I'm also shuffling the
2:28
data set. So I'm shuffling it and dividing it into a training and test set. So I'm again using this index trick that explained
2:37
to you earlier. Later, we will be using so called data loaders when we use more complicated data sets like large image
2:44
databases, where we have then some automatic functions in pytorch that do these steps for us. Here, I think it's sometimes
2:53
good to just see how you would do that conceptually, like seeing or looking at the code to see what we are doing here. So
3:00
what I'm doing here is I'm creating these shuffle index indices. So let me show you how they look like. So these shuffle
3:09
indices are just the indices one to 1000 shuffled. And then I use them to select the training data. So first, I'm actually
3:19
using it to shuffle the data set. So here, this is just the shuffle indices, I select all the data points in the shuffled
3:25
way, for both the training and also for both sorry, the features and labels. So note that here, because we use this
3:35
same shuffle index, they are shuffled in a way that is consistent, because otherwise, if we use different shuffle
3:42
indices, x might be shuffled differently than y. And this is also why we just can't use simply this shuffle function
3:49
that is implemented in NumPy or pytorch, because the shuffle function would shuffle them individually, and then the
3:55
features won't match to the corresponding labels anymore. So what I mean is, so this one, this entry here might be then
4:03
belonging to train data point 1999, 998, by accident, if we just shuffle them individually. So this is why we use a
4:09
consistent shuffle index. And then I select 70% of the data.
4:14
So this is just the size of how many data points are 70%. So
4:20
let me, this should be 700. Like that, right? Like, let me double check that. Yeah, 700. But this is just in general
4:28
implementation that would work with any size of data set. And yeah, this is how then I'm selecting the training and the
4:36
test set. So the first 70%, the first 700 data points will be
4:42
training and the remaining 70% will be for testing and the same thing for the labels. And then here I'm normalizing. So this
4:51
procedure is also called standardization. It's kind of
4:56
yeah, giving the data the properties of a standard normal distribution, it won't be a standard normal distribution. So
5:02
we don't change the shape of the distribution, but it will have the same parameters. That means it will have zero mean and unit
5:09
variance. Alright, so after we've done that, we now implement our linear regression model, that is where it becomes
5:16
more interesting. So we use this class based implementation,
5:22
because this is also something that we will be doing in pytorch later for complex models. So pytorch gives us a lot of
5:28
convenience functions like convolution layers, fully connected layers, and so forth. But we still apply the same
5:34
concept by saying what our parameters are, and then how we use our parameters in which order, the backward function is
5:42
later something pytorch will implement for us automatically. So pytorch will actually create this backward function for us,
5:49
we don't have to do it ourselves. Here, we do it ourselves, because this is like a very low level implementation
5:56
where I do things from scratch. In pytorch. Later, we can just use a fully connected layer and the backward function will be
6:03
done automatically. But I think here for now, it's maybe easier, or not easier, but at least, like better for your
6:10
understanding, if we walk through this step by step, and do it ourselves, before we rely on automatic ways of doing that.
6:18
So first, we define the number of features in the initialization method. And then we assign the weights of our
6:25
model, we just use zero weights, can be also small random numbers for this model, it does not matter. We initialize our
6:33
weights, we need, we need to know the number of features, right? So we use that information here. Because, yeah,
6:40
the if I scroll up, the number of weights depends on the number of input features, of course, let me go down again, we have a
6:48
separate bias unit, because it's computationally easier to handle. So we don't have to modify the input features when
6:54
we get them from the training set. So we also initialize it to zero, we only have one bias unit, so there's only one value.
7:04
And then we compute the net inputs. So this is similar to the perceptron that we've used before. So we multiply x, the
7:11
features and the weights, and we add the bias. So I'm writing this in a complicated way, you can technically I think you
7:18
could write it also as x at self dot weights plus self dot bias,
7:27
it should do the same thing. Not sure why I was using it. So in a complicated way, I think I just wanted to show you that I
7:33
was using pytorch here. Okay. Yeah, so then we have the
7:40
activation. So the activations are just the net inputs, because the activation function is a linear function. So I could
7:47
also could have done something like that on self deviation
7:52
function x and then return x and then use this one. So I should
7:59
use self and then just do this, basically. So it would be the
8:09
same thing should also work. That's not really matter. Okay,
8:16
then we get the activation. So now the view here is just to make sure that the shape is the same shape. So we are sorry,
8:25
that this is like a singular vector. So it's one dimension,
8:32
not two dimensional, just for convenience. And then now in the backwards method, what we are doing is we are computing the
8:40
gradient, this is what we have done on this in the slides. So remember, the gradient is y, so the gradient of the loss
8:49
function with respect to y hat. So starting at the back, so we're doing in two steps. So this is so if our loss function, let's
8:57
write it down again, if our loss function is y minus y hat
9:04
squared, then the derivative is two times y minus y.
9:12
Sorry, that should be the other way around. And then this should
9:20
be the derivative. All right, so that's what we have here. And
9:25
then we compute the gradient of y hat with respect to the weights, which was x and the gradient of y hat with respect
9:33
to the biases minus one. And then we put these two things together. So using the chain rule, the inner times auto, this
9:42
is what we've done in the slides. So we multiply the weights as a transpose with y hat. So this is a little bit
9:51
tricky, all these types of things, the view and things like that. This is really like to make the dimensions match. So
9:59
later on, we won't have issues with that when we use pytorch automatic functions, because they will take care of it for
10:05
us. If we do things manually, we always have to make sure that the dimensions are right. And then because we compute, or we
10:14
have gradient descent, based on the whole training set, we divide by the size of the data data set, this is basically for
10:22
the mean squared error instead of the sum squared error. So this is our the loss of the sorry, the gradient of the loss
10:30
with respect to the weights here. And this is the partial derivative of the loss with respect to the bias. And then
10:38
we return the negative gradients. So this is exactly what we have done in the slides. Now, we have a method where we
10:47
compute the forward path, the predictions, and then we can compute the negative gradients. And these gradients will be
10:56
used then for updating the weights to minimize the loss
11:02
function. So here we have, we have the training and evaluation functions. So check something. So here we have the loss
11:13
function. And yeah, that's the mean means where error loss
11:24
here. And here we are training our model. So now we have this
11:31
for loop, this is a batch gradient descent. So we have the
11:39
training function, which takes our model, the input data, the number of epochs and the learning rate. So we also take
11:48
keep track of the cost or loss. I typed it as cost here, but you can think of it as the loss.
11:54
Um, yeah, so what we do is we iterate then over the epochs. So
12:02
for each epoch, we compute the predictions. So this will be a vector, my head will be a vector, because the predictions
12:08
are for the whole data set. Then we compute the negative gradients using our backward model or method. And then we
12:16
update the weights and the bias. So like we discussed in the slides, this is the learning rate times the negative
12:24
gradient. Let me see if I can bring up the slides here.
12:33
Somehow, it's not working. Okay. Um, just want to show you where
12:39
we are. Yeah, we are at this step here right now where we update basically, so we compute the negative gradients here in
12:47
step B. And then we update right now with these negative gradients. So that's what is going on here, the learning
12:54
rate times the negative gradient. So that's how we update the weights. And this is it. And then we go up here. So
13:00
here, this is just for logging, that we are just logging. We
13:06
are just logging the loss, current loss, and print some
13:15
outputs, we print which epoch we are currently in, and the mean squared error loss, because then we can see whether it decreases
13:21
or not. Actually, we don't have to compute that one because we
13:26
already had that from the first iteration is like a little bit wasteful. I don't know why I did that, actually. Um, yeah, so I
13:38
think yeah, because otherwise, this would be the first I see now, because this would be the zero epoch. And this is after
13:44
we updated, so I could actually technically remove that. And then show it to you with starting at the zero epoch. But
13:55
then we won't know what the last gradient update looks like,
14:00
right? Because when we update the weights, and then we don't compute the last prediction with updated weights, we don't know
14:07
how the final model looks like. So this way, in the last iteration, we know also how the final model looks like, I mean,
14:15
we can do it other way, other. In other ways, we could have this actually, let me see, we could actually comment this out.
14:24
And then outside the for loop, we could when the epochs here
14:29
have finished, we can compute the prediction, but it was just fewer code, fewer lines of code and a bit simpler. Alright,
14:36
because here everything is fast anyways. Alright, let's define
14:42
that. And let's now run this model. So here, I'm not calling this train function. Oops, what an error. Okay, I have not not
14:50
executed this. So we have to define this and define this. Now we can still not train it. activation function is not
14:59
defined. Okay, I don't know why this should not be defined. Oh,
15:06
yeah, it should be a self. This is also something I just added. So you don't have to use this activation function. It's not
15:12
doing anything anyways. Okay, so now it was training here. Okay,
15:17
you can see we start with a relatively high loss, like 1532. Notice that let me scroll up. Again, to the data set, these
15:26
are relatively large values, which is why the mean squared error loss is so large. If I would divide all these values by
15:32
a factor of 10, these mean squared error losses would also be smaller by a factor of 10. So the absolute number doesn't
15:40
really matter. So you don't have to really pay attention to the absolute number. What you want to see is the relative decrease
15:47
that it goes down over time. You can see the longer we train the smaller the mean squared error becomes. So it's training here.
15:54
And you can see, there's a point where it doesn't go down any much, it stays at 371. So that means it kind of converges and
16:04
it has probably reached a global minimum. So okay, what we see
16:09
here, let's plot the cost now, because remember, I was keeping track of the cost, which is the loss over each epoch. It's just
16:17
like, to not confuse the loss for the stochastic rain descent
16:24
with the one over the epoch. But it doesn't really matter. The terms are usually used interchangeably. Where was I?
16:30
Yeah, here. So here I have the cost that we can also call it loss, actually, it's maybe easier. Let's call it loss. And
16:41
I think I have the loss function that is called loss, which is why it was confusing. Okay, let's leave it at cost here.
16:47
Alright, so we compute the cost or initialize it to an empty list here. And then in each iteration, we add the current
16:56
loss to it. So this will be a list of all the losses over the training. So this will be a list of these values here. So we can
17:04
plot that and take a look at how it looks like. So we can see it starts out very large, and then it goes down smoothly until it
17:12
converges. So here, at that point, we can say the model has converged, it has probably reached the global minimum of
17:20
the loss function. Alright, so now, after we train the model, we can now use it for prediction. So let's now
17:26
predict on the training set and the test set. So this is similar to the training just for reference, let's compute the
17:32
mean squared error on the training set and then to the tested. Alright, so you can see here, the training set MSE is
17:39
lower than the test set MSE, which means the model is overfitting a little bit to the training set, but it's not too
17:46
bad, I would say. Now, let's also compare that with the analytical solution. So if I, if you recall, somewhere here,
17:55
somewhere here, I showed you in the slides, the analytical
18:02
solution, I don't know where I had it.
18:11
Think it was here. So we have this analytical solution where we get the optimal weights using these matrices, the matrix
18:20
inverse here, times x transpose y, this is the analytical solution. So let's compare our gradient descent solution with a
18:29
analytical solution to see whether they match. So ideally, they should be very close. So here are the model weights from
18:38
our own model from from our gradient descent model. So we see for the weights, feature one weight is point three six and
18:45
feature two weight is point 379, approximately, and the bias is
18:51
minus point five, four. Now, here's the analytical solution where implemented what I had on the slides when I just showed
18:58
you. So when we execute that, you can see this one and this one, they are very close. And also, these are virtually an
19:06
identical and also the bias unit is identical. So we can see this
19:12
gradient descent implementation works. And it gave us the global minimum here. Yeah, an ungraded homework exercise just for you.
19:22
So Mike, or the task for you is modify the training function such that the data set is shuffled prior to each epoch. Do
19:29
you see a difference? Yes or no. So you can try this out in practice. But you can also just think about it whether you would
19:36
see a difference whether you shuffle prior to each epoch or not. And yet, try to come up with an explanation for your
19:42
observation or intuition, and then maybe post this on Piazza, just to check your understanding, whether shuffling
19:49
would make a difference here, yes or no. So you can try that out in practice. But also, you would be able, I think to answer
19:56
this without even changing the code. Alright, now let's take a look at the airline model with stochastic gradient descent. So
20:05
we could also implement it with gradient descent, it doesn't really matter. But here, we use the stochastic grand descent,
20:10
the mini batch mode, because this is something we will also be using later on when we implement deep neural networks. So again,
20:17
these steps are all the same. Okay, just using a different
20:22
data set. Now we are using the iris data set, where we have four features x one, x two, x three, and x four. So that's a
20:29
separate length, separate width, petal length, and petal width. This is our class table, the predicted class table. So they
20:35
are actually simplified it, so that there are only two class labels. So let me see. So this should be class label zero, the
20:45
first data points. So I'm only using data point 50 to 150 here,
20:51
I think. So here, I'm, yeah, I'm applying class label one. So
20:58
yeah, I'm selecting. So what I'm doing precisely is I'm selecting only data points 50 to 150. And then these would be class label
21:06
one, two, one and two, but I changed them to zero or one.
21:11
Otherwise, our function would not work. So I am binarize our class labels. This is just to make this problem work for
21:19
headline. And also, that same would be true for the perception. Later, we will be seeing models that can also deal
21:25
with multiple class labels. So here, this is exactly the same
21:30
code as before, where I'm just using the shuffle indices now use 70% again, for training and 30% for testing. And I'm also
21:40
standardizing the features, just to visualize how the data looks like. So this is our data set two classes, blue dots and the
21:49
orange dots here. And this is for the training set, how the training set looks like, sorry, the test that looks like above
21:56
is the training set. And now we are implementing our airline model. Note that this is exactly the same as before. So I don't
22:05
have to go over this again. So this is exactly like the same code. And so yeah, I have made screenshots side by side. So you
22:14
can see, if you look at it closely, there's no difference between the two. So how we got that again is by let me see by
22:24
deriving was a long lecture here. So this is basically what
22:32
we do in the backward pass where we compute. See, so where we
22:38
compute the derivative. So this is the outer derivative. And these are the inner derivatives. So if I go back, we have the
22:46
outer derivative, this is this part here where we have the
22:51
power rule, we bring the two upfront here. So this is this part here. And then this is the inner part, this is here, this
23:03
x basically, for the weights, this is the x. And for the bias
23:08
unit, it's just minus one. Because if we would compute the derivative of this one with respect to the bias unit, this
23:19
would be one. Sorry, where are we here? So here, sorry, if we
23:24
compute the partial derivative of this net input with respect to the bias unit, the this one will be so let me write this down
23:35
somewhere. So we have the W transpose x plus w, if we
23:43
derive with respect to B, so this would be a constant. So this goes away. And the derivative of this one with
23:51
respect to B is one, right? So in this one, this case, the derivative would be one, but we are also interested in the
23:57
negative gradient, so it would be minus one. Alright. Yeah,
24:08
alright, so and then we define the training and evaluation functions, this is the same as before. compute the loss, we
24:17
have our training function, the same as before. Because nothing really changes, because we don't use our threshold function yet.
24:26
Let's see our model trains. Not defined. Yeah, I'm forgetting
24:33
to execute them step by step here, which is a issue that can happen in Jupyter notebooks. Alright, so now we see we start
24:40
again with a very large loss. Now, sorry, I mentioned it was
24:45
the same, but one difference is now we're using mini batch gradient descent instead of batch gradient descent. So
24:51
really, the difference is that we have now these mini batches here. So before, maybe just showing that side by side.
25:03
Before we are just iterating over the epochs here, here, we iterate over the epochs and inside, we also iterate over
25:10
the mini batches. So I'm creating a mini batch here, sorry, the image shuffling, and I'm creating multiple mini
25:18
batches here by splitting this into mini batches of a certain
25:24
size. So I'm using a size 10. So I'm splitting it into multiple vectors where each vector will contain 10 attend training
25:33
examples. And then for each mini batch, I'm doing my forward
25:38
pass, and so forth. So now, I have the mini batch training so
25:44
that I have, if I have 150, so 101234567, I have seven mini
25:52
batches in each iteration, because I have 700 training examples. So I can divide them into 10 mini batches with 70
26:02
training examples each. So we start out with a large mean
26:08
squared error. And then you can see it goes down. But it is now now a little bit noisier, you can see, it goes down here, and
26:16
down, but then it goes up a little bit. Sorry. And you can see then it's a little bit noisy at these updates. Yeah, and then
26:25
overall, per epoch, we can see that things go down. So at some
26:36
point, yeah, we have converged. So we can see, it's fluctuating a little bit, but it's not going down significantly, it's going
26:43
a little bit up and down. So it's a bit noisier than the gradient gradient descent, the mini batch gradient descent is usually a bit noisier. Alright, so time to evaluate it. So it's
26:53
easier actually to look at it in a plot compared to these lists. This is something if you train complicated neural network
27:01
models, it might be helpful to print it on a command line on a server if you don't have any plotting functions available. But
27:07
after training, it's usually good to at least take a look at this. Because here, it's a little bit more clearer to see.
27:13
So you can see it goes down very steeply. And then you can see it fluctuates. So it's not converging completely because
27:19
it's more stochastic. So there's more noise. But overall, we can say it kind of converged, maybe we could have changed the
27:26
learning rate, making the learning rate a little bit smaller. And later on, we will also learn about something called learning rate schedulers, where we make the learning rates
27:35
smaller over time, so that we converge better also. Alright,
27:41
so let's take a look at the model weights and the bias from the training and then compare to our analytical solution again.
27:48
So we can see the weights are point or 7 and 0.4 here, 0.488.
27:57
And yeah, if we look at our analytical solution, it's close, you can see it's quite quite close, but it's not as
28:04
close as before before we used gradient descent instead of stochastic gradient descent. So before it was a little bit more
28:11
accurate. So what you can change this code also to do gradient descent. Later on, when we talk about multi layer networks,
28:18
yeah, regular gradient descent wouldn't really be very useful. So it's actually good to use stochastic gradient descent here
28:24
as a practice already. All right, so let's take a look at the prediction accuracy now. So how good is our classifier that
28:31
we trained. So for this one, we now need the threshold function. So we set the threshold at point five. So this is if I go back to
28:39
my slides. So this is what I'm doing right now here. So for a
28:45
given value, if the value exceeds point five, the prediction exceeds point five, we assign it class value, class
28:53
level one, if it's below point five, we assign it class level zero. So this is what I'm implementing here. If my
28:59
predictions are greater than point five, we predict once. So I have actually prepared a vector of once. So this is one
29:09
limitation of the torch where function. So how the torch where function works, if you remember from the perceptron is if you
29:15
have value. So if you meet this condition here, then you return this value. If you don't meet this condition, you return the
29:23
second value. So I'm preparing these vectors already as outputs, I don't have to recreate them. So this is the ones and this is
29:29
the zeros. And now I'm also then computing the mean. So what is
29:35
the mean? It's basically the number of so we are computing the sum of the number of ones on the correct predictions here.
29:44
Because I have the equal sign. So it's maybe going on or there's a lot of things going on in one step, I could make maybe a
29:53
separate step predicted labels and assign that here might be
30:02
easier to read. And then I would like this might be easier to read. So here, first, I'm like I said before, I'm creating these
30:12
predicted labels. And then I'm checking how many of the
30:17
predicted labels match my true labels. So this will be a vector of zeros and ones. And then I sum up all the ones and divide by
30:26
the number of data points. So this is what the mean is doing. So it's, yeah, basically telling me on average how many are
30:33
correct. So it will be a value between zero and one. Um, yeah, and I do the same thing here for the test set. So let's execute
30:42
that. So we get 90% training accuracy and 96% or point 6%
30:48
test accuracy. It's a small data set, usually, you will find that in a real world case, the test accuracy is usually lower
30:54
than the training set accuracy because of overfitting and stuff like that. But this is a very small data set. And this might
30:59
be just due to chance. So I'm just to illustrate in what this value here is. So this is a vector of zeros and ones or no
31:08
sorry, trues and false, but you can actually convert it to integers. And then it should be zeros and ones. And then you can
31:16
compute the sum. So this gives you the number of ones. And then
31:24
if I divide it by the number of training data points, which is let's say,
31:32
label starts size zero. So this is my 90% here. So I can then
31:38
multiply it by 100. That's my 90% training accuracy. Alright,
31:43
so let's take a look at the decision boundary. So this is the same code as from the perceptron class or lecture. And
31:52
we can see now. So on the left hand side, this is for the training set. And on the right hand side, it's for the test set. It's actually doing better than the perceptron. It's
32:00
something this would be a problem where the perceptron wouldn't be able to solve it. Because here, you can see now
32:05
this is a case where the classes are not linearly separable. So there is no decision boundary where you get perfect accuracy.
32:13
So a perceptron here would have really problems, it would change, it would like have a decision model like this, and
32:18
like this, this, this and would flip back and forth. But this model converges, you saw that based on the training error. So
32:25
it's, it's kind of finding a good boundary here. And this is for the test set. So yeah, this is it for this lecture. In the
32:31
next lecture, we will be taking a look at how we compute or how we can compute these gradients automatically in pytorch. So
32:38
on next lecture, we will see how pytorch computes this one
32:45
automatically so that we don't have to do this by hand. Because I mean, right now, what we had here, where was it? What
32:56
we had here was relatively simple, a very simple function. But even for that, we needed a lot of not a lot of steps. I
33:02
mean, you can do it in fewer steps. But it's kind of complicated when we have multiple layers, nonlinear activation functions and stuff like that. And it would be
33:09
really tedious for every neural network architecture to do that from scratch. So pytorch actually implements some
33:15
functionality to compute this backward function automatically by analyzing the forward function. All right, we will
33:22
see how that works then next week.

##v41:

0:00
Yeah, hi, everyone. So all good things come in threes. And I'm
0:03
back with stuff in the news. Number three. Last week, I
0:07
talked a lot about language models for deep learning. And
0:10
this week, my new section will be more focused on computer
0:12
vision models, which is also a little bit closer to my research
0:15
area. Because there happened a lot of interesting stuff around
0:18
computer vision this week. There are lots of things to talk
0:21
about. So let me get started and dive in.
0:25
Yeah, let's start with a good old fashioned computer vision
0:28
application image recognition. So here, the title of the paper
0:31
is high performance, large scale image recognition without
0:35
normalization. So here, the researchers developed a deep
0:39
neural network that can achieve new image classification, state
0:44
of the art results without batch norm. So if you encounter this
0:48
work here, SOTA, this usually stands for state of the art and
0:55
means that you achieve a state of the art performance in terms
0:59
of the best possible performance or among the best possible
1:03
performances compared to other cutting edge state of the art
1:07
models. So here, what was the novelty? So here, the novelty is
1:11
that they achieve this state of the art performance without
1:14
batch normalization. So batch normalization is something we
1:17
will be covering later in the semester. And it's a technique
1:20
that has been used in the last I would say, four or five years to
1:24
get your stable and good performing models. It's like a
1:28
type of data normalization technique. And we will cover
1:30
this in more detail later in class. So here on what's new is
1:34
basically that they achieve the good performance now without
1:37
batch normalization, basically making models simpler again. So
1:42
what did they use here? So here, they developed an adaptive
1:45
gradient clipping technique to overcome the instabilities that
1:48
arise from not using batch norm. So there have been also some
1:51
other models recently in the last couple of months or years
1:55
that achieved state of the art performance without batch norm,
1:59
but they were usually more unstable, so more unstable
2:02
towards little fluctuations in the data set, and so forth. So
2:06
here, they achieved really good performance without this
2:09
normalization technique. So they developed so called normalizer
2:13
free residual networks. So resonance or residual networks
2:16
are also something we will be covering in the semester in the
2:19
convolutional network lecture. So we will likely also
2:22
revisiting this paper then. What is also interesting is how they
2:27
evaluated the performance. So here, I have a screenshot from
2:31
the paper on the y axis, you see the image net top one accuracy.
2:37
So recall from the introductory lectures, I mentioned the
2:41
challenges with image net, where you can have multiple possible
2:45
labels. So in this way, usually people also call or compute the
2:49
so called top 5% accuracy. Because, yeah, if there's
2:53
something, let's say you have a bus, or a car in an image, there
2:58
are multiple possible labels, for example, it could be a
3:00
vehicle, car, automobile, and stuff like that. So there are
3:04
multiple possible ways to have a correct label. And sometimes
3:08
there are also multiple objects in an image here. Yeah, for
3:11
some reason, I mean, the researchers use the top one
3:14
accuracy, I think top five accuracy, both are important
3:17
things to look at. In any case, what's interesting here is the
3:21
x axis. So here, on the x axis, the research researchers also
3:24
focused on computational efficiency. So here, they call
3:28
it the training latency as I think it's seconds per step on
3:32
the TPU. So that's like the tensor processing unit
3:36
equivalent to a GPU or similar to a GPU. And they looked at a
3:40
batch size of 32 per device, they used multiple devices,
3:44
multiple TPUs in parallel. Yeah, but what is interesting, though,
3:50
is to think of it as just like the efficiency. So the right
3:54
hand side, so here, it's more expensive. And this one here on
4:02
the left hand side would be cheaper, like cheaper to train
4:05
faster to run. So and why is that interesting to look at?
4:09
It's because you can also think of it as if you make a model
4:12
larger, you have more parameters, you will likely get a
4:14
better performance. But then at the same time, also, these
4:17
networks become more expensive. So depending on your
4:21
application, you are interested also, sometimes in smaller
4:24
models, because you cannot run these large models, for example,
4:27
on a cell phone or iPhone or something like that, where they
4:30
have on device machine learning algorithms. But then also at the
4:35
other hand, otherwise, you can make the argument together, the
4:38
model, the better the performance. And you want to
4:40
also see whether the method just works for smaller models. So
4:44
here, they have different flavors of the method f zero to
4:48
f5. I think these are just different sizes of the model.
4:52
And you can see, in terms of accuracy, their method is better
4:57
than all the other methods here. And these are actually pretty
5:00
good methods. It's like all the efficient methods, but it's
5:03
called efficient net, for example, on lambda net, I think
5:06
this stands for data efficient image transformer, and so
5:09
forth. So you can see for all types of model sizes, their
5:13
method performs better than these alternatives. But again,
5:16
these are different architectures, we will talk more
5:18
about the convolutional network architectures later in this
5:21
course. What was interesting really here is that you can also
5:24
achieve good performance without using batch normalization.
5:30
Yeah, here's another interesting thing I found this week, it's
5:33
not so much a news article, but a Reddit discussion from the
5:37
Reddit machine learning subreddit, which has sometimes
5:40
really interesting and useful, insightful discussions. So here
5:44
someone asked about deep learning theory, like wondering
5:48
about the recent advances of or in the theory of deep learning,
5:51
like certain understandings, how we think of deep learning. So in
5:55
the last couple of years, there were some hypotheses that were
5:58
particularly popular, for example, the lottery ticket
6:02
hypothesis, which is essentially about saying that, just by
6:06
chance, if you train a large hyper over parameterized network
6:12
with lots of combinations, just by chance, there is a high
6:15
probability that at least one of them will have optimal
6:18
performance, just because you considered so many variations or
6:21
combinations that just one of them performs well by chance.
6:25
And there's a lot of evidence in favor of this hypothesis. But I
6:29
also recall, like a couple of weeks ago, or months ago, I
6:32
think it was 2020, there was a paper, like, giving evidence
6:36
against this lottery ticket hypothesis. And in this way, I'm
6:40
actually not sure in how far this hypothesis is still a
6:43
valid hypothesis. Anyways, um, the other one is the double
6:48
descent hypothesis, which is also particularly interesting. So
6:51
here at the bottom, I have a screenshot of this hypothesis
6:54
from a different blog post article, because it was just a
6:57
nice image. So what is shown here is the test and the
7:01
training error. So in contrast to the previous slide, the lower
7:04
is better. So in the previous slide, we had accuracy. So the
7:07
higher was better here, it's the lower is better. And here we
7:11
have, for example, the view, the expected view, the classical
7:14
statistics viewpoint. So here, you can think of it in a
7:21
classical statistics viewpoint, that you start with a model that
7:26
has a high error. Why is the error high? Yeah, that is
7:30
because usually, your model is too simple to capture the
7:36
complexity in the data. So your model doesn't have enough
7:39
parameters, and then it's too simple and cannot achieve a good
7:43
classification performance. Because for example, think you
7:45
have a think of a nonlinear decision boundary that you need
7:49
to classify the data, but you only have a linear model. And
7:52
this way, the model is too simple to capture the patterns
7:56
in the data. And as you make your model more and more
7:59
complex, maybe think of adding more layers to a new network,
8:02
then your training error will go down and the test error will
8:05
also go down. But at some point, the test error will go up again,
8:09
because you have now so many parameters that your model
8:11
starts overfitting. So in this way, your model will perform
8:14
worse with a given size. So here, they use the residual
8:17
network, we will talk about residual networks also later in
8:20
this class. Yeah, so this is the classic statistical viewpoint
8:26
with, let's maybe let's consider the modern, modern view, modern
8:33
view is usually the more data you have, the larger, sorry, the
8:38
larger the accuracy, but also the smaller the arrow,
8:40
basically. So but the reality is that there's usually this bump,
8:44
that is what researchers found out I think in the last couple
8:47
of years. So if you look at it in practice, you start with a
8:51
high accuracy, the accuracy, sorry, high error, the error
8:54
goes down. But then it goes up again, for some reason. So and
8:59
then there's this bump, and then it goes down again, which is a
9:02
little bit weird. So people call that the double descent
9:06
hypothesis, because you go first down, then you go up, and then
9:10
you go down again. So right now, I think it's also still a
9:12
discussion whether this is a valid thing, or whether this is
9:16
maybe due to accidental experimental errors, like
9:20
someone, maybe at some little bug in the code or something
9:23
like that. But so far, all the evidence shows that this is
9:26
indeed a phenomenon that can be observed. And yeah, that was
9:29
another interesting hypothesis that is currently still under
9:33
discussion. So if you're interested in more of these
9:34
types of things, check out the subreddit, there are way more
9:39
hypotheses listed below there in the thread. So people discuss
9:42
these types of things. And I think it's just interesting if
9:45
you are curious about these things.
9:47
Um, yeah, another interesting research article I saw was this
9:54
one here entitled, removing biased data to improve fairness
9:57
and accuracy. Sounds like a relatively straightforward
10:00
approach. Like if you have an unfair system, and this is like
10:05
also a very important topic, due to your data set, sometimes in
10:09
other reasons, machine learning systems can be unfair towards
10:13
certain subpopulations, for example. And here, the researchers
10:17
tested the idea that removing biased data, whether this can
10:22
improve the fairness and maybe even the accuracy of the system.
10:27
And what they found, what was quite interesting is that they
10:31
achieved a low discrimination of almost 0%. When they trained the
10:36
model on the biased data. So by just changing the data set, they
10:40
were able to reduce the discrimination of the model. But
10:44
what was also interesting is that they said, or observed a
10:48
higher accuracy compared to models trained on the full data.
10:51
So basically, they removed biased data points. And not only
10:55
did they improve the fairness of the machine learning model, but
10:58
they also achieved a higher accuracy. So and according to
11:03
the authors, for example, other methods that are being used to
11:05
make machine learning more fair, usually achieve this fairness at
11:09
the expense of accuracy. So usually, when people want to
11:12
make a machine learning model more fair, the accuracy goes
11:15
down. And in here, they found the opposite, you make it more
11:19
fair, and the accuracy goes up, which is which sounds like a
11:22
win win situation. So here's just a brief overview of what
11:26
they did. So they started with the biased training data. And
11:30
they had a feature extractor generated similar pairs. So
11:34
similar passes. In terms of you have a data point from so maybe
11:40
let me step back, take a step back. So they evaluated it on
11:44
eight data sets here, where they had multiple attributes. And
11:49
they had also a sensitive attribute, for example, the sex
11:53
of a person or the race of a person. And what they wanted to
11:57
predict is, for example, different things like income,
11:59
creditworthiness, exam scores, and so forth. And they, for
12:03
example, generated similar pairs with, for example, someone who
12:07
had or whether some instances where the sensitive attributes
12:11
were different, but everything else was the same. So they found
12:15
individuals treated unfairly. And they trained algorithms based
12:22
on this biased model, they then ranked these instances by
12:28
influence of how much influence these instances had on the
12:31
model. And then here, they sorted the training data,
12:34
removed the data points, and trained model on this
12:39
debiased data set, measured the discrimination. And then if the
12:44
discrimination decreased, they did another round and removed
12:48
more data points. So they kept going until no improvement could
12:51
be made. And they found by by this simple approach, they
12:55
could improve both the fairness and the accuracy, which it
12:59
sounds like a good idea. But I'm not an expert in this area. But
13:03
it sounds like something that should be explored more and
13:07
maybe also applied to some deep learning models. So I found this
13:09
interesting. Related to also the training data influence, I saw
13:15
this article by Google AI research teams. So they had a
13:20
blog article, but then in the blog article is also a link to
13:23
the paper to the original paper. So they call their method trace
13:26
in, which is a simple method for estimating the trainer training
13:30
data influence. So what they do is on during training, they
13:35
record the changes in the prediction caused by an
13:38
individual training example. So they train a model and then look
13:42
whether the training performance is how much the training and
13:46
performance is influenced by this particular data point. And
13:49
this technique is especially then useful for detecting
13:51
outliers. And also what you can do with this technique is you
13:55
can explain predictions. So to get some insights into the AI
14:00
model from the training examples, rather than the
14:02
features. So most techniques for interpretability usually focus
14:07
on the features, it's basically about saying, okay, this and
14:11
this attribute in the training set is important for making
14:13
predictions. Here, they look at it from the perspective of
14:17
training examples, like which training examples have a large
14:20
influence on the model. And I can imagine, if you think back
14:23
of the previous slide, this model on fairness, I think
14:27
those two methods might be also interesting to combine in a way
14:31
that might be a good or interesting thing to look at
14:35
these influential training examples and how they maybe
14:37
influence the fairness might be a future reach a research
14:41
direction. Anyways, um, or could be something interesting for
14:44
your class project. In any case, so here's a figure from this
14:47
blog post. So here on the x axis, they have the updates
14:52
during training. So the different model updates on the y
14:55
axis is the loss. And here, they take a look at the class
14:58
zucchini. And they notice, for example, if they provide a
15:02
training example that contains zucchinis, then the loss goes
15:06
down as expected. So you go down with the loss. But then for
15:10
example, if you encounter a training example, seatbelt,
15:13
which has nothing to do with the zucchini, then the training
15:15
loss for zucchini goes up. So if you want to improve the zucchini
15:20
classification, then you shouldn't show it seatbelt
15:22
samples. But then of course, your problem is probably a
15:26
multiclass classification problem where you also have
15:28
seatbelts. So it's like a trade off, right? Should you show the
15:31
seatbelt? I mean, then you make maybe the seatbelt
15:33
classification better, but then you lose on the zucchini
15:36
classification. So in this way, they give it here another
15:40
seatbelt, it goes up. And here goes down, we're doing some
15:46
other I don't think they show every training example, they
15:48
only show the most influential ones, the proponents and
15:52
opponents, and seatbelt, it goes up again, zucchini, it goes down
15:56
by a lot, and so forth. And sunglasses, that's interesting.
16:00
For sunglasses, also, the loss goes down on zucchini. Yeah. And
16:05
so here, they can kind of better understand what influence the
16:08
data set or data example have, for example, here, one seatbelt
16:13
has more influence than another seatbelt. And this way, you may
16:15
also find interesting, weird outliers in a data set. Yeah,
16:22
another interesting research article was related to
16:26
generative generative adversarial networks. So this
16:29
is also something we will be covering towards the end of the
16:31
class. And this might be also general, though, on interesting
16:34
application or idea for your class project. So there were
16:39
some projects in the past called, this person does not
16:43
exist where people used generative adversarial networks
16:52
to generate faces of people that don't exist in real life. So for
16:57
example, this person does not exist in real life, it's made
17:00
up by the model. And if you go to this website and refresh it
17:03
every time you will see a different face that does not
17:06
exist in the real life. And also similarly, there's a website
17:10
called this cat does not exist where people did the same thing
17:14
for cat images. So here you can generate cat images. Yeah, and
17:21
now researchers applied the same idea to genome research. So here
17:26
was an article linking to a research article that was
17:31
recently published, where the researchers described that in
17:34
our work, we apply a similar concept to genetic data to
17:37
automatically learn its structure and for the first
17:39
time, produce high quality, realistic genomes. So why is
17:44
that important or interesting? Currently, there's a lot of
17:48
research being done on DNA and genomes. But one problem is
17:51
really like privacy, because your genome is unique to for a
17:55
given person. So if you do research on genomic data, you
17:59
kind of have to be careful of about how you handle the data.
18:02
If you have realistic genomes that are totally realistic, but
18:06
don't belong to a certain person, then I can imagine this
18:09
can make certain types of research easier. For example, if
18:12
you if you train large scale classification models for
18:16
different genes, and you have a data set, and your model learns
18:21
from this data set, the model will contain contain some
18:24
information about the data. So it's kind of, yeah, a little
18:28
tricky to make this model available for people or to
18:31
people who might find it useful, because maybe someone would be
18:34
able to extract some personal information from that model. If
18:37
you train a model on this fake DNA, and it works well on real
18:42
DNA as well, I can imagine this can help with some of these
18:45
privacy issues around that.
18:49
Yeah, one last thing about computer vision or related to
18:52
computer vision, which might also be useful as inspiration
18:56
for a class project. So I also saw this project where the
19:00
company, I think it's called Rebeck company trained computer
19:05
vision model to estimate the price of a handbag. So here,
19:11
based on the article and interview with the person, they
19:14
trained it on millions of data points. And it took like six
19:18
years to develop six years to develop this app. But yeah, it
19:22
sounds like a fun project where you can take a picture of your
19:26
handbag, and then it estimates the price. So it's like a
19:30
simple, straightforward computer vision project, I think, not too
19:33
complicated. But I guess the trick here was to really get a
19:36
lot of pictures of handbags and make it accurate. So that might
19:39
be also like an inspiration for a class project, of course, not
19:43
with handbags, but maybe with something else. So yeah, these
19:47
days, people maybe sell a lot of cell phones or laptops or
19:50
something like that. So in that way might be also interesting.
19:53
Of course, it's not only then based on the picture, but also
19:56
some other statistics like processor speed, the age of the
20:00
computer and stuff. But yeah, I think this is also maybe an
20:02
interesting, fun class project to develop a simple computer
20:06
vision app that can take pictures of something and then
20:09
estimate the resale value. Alright, with that, this is all
20:13
I have for this news week. And I wanted to also wish you a happy
20:18
lunar new year. Hope you have a nice weekend and I will see you
20:21
back in class on Tuesday.

##v42:

0:01
Yeah, hi, everyone, I hope you had a nice weekend. So last
0:05
week, we talked about gradient descent and topics and calculus
0:09
to understand how we can compute the partial derivative of a loss
0:13
function with respect to the weights of the model, so that we
0:17
can optimize the model to do good predictions. So this is, I
0:21
think, still very important to understand from a bottom up
0:24
perspective, like understanding why we compute gradients and how
0:28
we compute gradients. However, in practice, especially when we
0:32
work with these big neural networks, it will be very
0:35
tedious to implement these gradients by hand by deriving the
0:39
loss function manually by, let's say, pen and paper, and then
0:43
coding it up in Python, Python code, and things like that. So
0:46
we will use pytorch, actually, to make our life easier. So in
0:50
pytorch, there is a sub module called autograd, which is a
0:54
module for automatic differentiation. And as the name
0:58
automatic implies, it will automatically derive the loss
1:02
function with respect to the weights for us. So in that way,
1:06
we don't have to worry about it ourselves. And in this lecture,
1:09
I will show you essentially how this works. And we will be then
1:12
also using it later in this course, when we work with more
1:15
complicated networks, like convolutional networks or
1:17
recurrent neural networks. So with that, let us get started,
1:20
then. Yeah, like I mentioned, the focus of today's lecture
1:28
will be on computing partial derivatives more easily and
1:31
automatically using pytorch. And I structured this lecture into
1:36
five parts. So the first part will be really just on your
1:39
Python resources. So where you can find information about pytorch
1:44
and more reading material if you need it, where you can find
1:48
useful tutorials. So in addition to this class, I think this is
1:51
just also useful for you to know where to find more information
1:55
and keep up to date with the other pytorch development in
1:58
terms of new version releases and so forth. So then I will
2:02
introduce the concept of computation graphs. So this is
2:05
basically how we think of a series of computations in the
2:10
computer, like this computation graph that we can use to
2:14
visualize a computation like a prediction in a neural network.
2:19
And then using the analogy or the concept of a computation
2:22
graph, I will explain how automatic differentiation works
2:26
in pytorch. So pytorch is under the hood, building such a
2:30
computation graph. And then based on this computation graph,
2:34
it backtracks the computation to compute the gradients. We will
2:39
then see how that applies to add a line. So last lecture, we
2:44
trained the airline manually. So we computed the derivatives by
2:48
hand in the lecture slides. And then I showed you a code
2:51
implementation of that. So today, we will see how we can
2:55
do this automatically using pytorch. So in pytorch, that is
2:58
the so called backward function, which can do things automatically
3:03
that we have done tediously by hand last week. And yeah,
3:07
lastly, I want to end this lecture today by taking a closer
3:10
look at the pytorch API. So there are two main sub API's
3:15
object oriented and a functional API, which are both useful. So I
3:19
will also explain to you how the API works in a bigger picture
3:24
sense. And we will be using these concepts then later, when
3:27
we talk about implementing multi layer neural networks. So with
3:31
that, I think this lecture may be one of the longer ones
3:34
again. So it could be that is a little bit above the 75 minutes.
3:38
However, on Thursday, there will be a shorter lecture where I
3:41
will go over just optional concepts like how we can run
3:45
code on the GPU using free cloud resources. So Thursday's lecture
3:51
will be I think relatively short or more like optional. So you
3:54
will have also plenty of time to catch up this week if this
3:58
lecture ends up a little bit longer. Okay, but with that, let
4:02
me not spend too much time here and get started with part one
4:06
pytorch resources.

##v43:

0:00
Yeah, we will be using pytorch quite a lot in this class. And I
0:04
assume you will also be using it extensively for your class
0:07
projects. So in this video, I want to briefly show you where
0:11
you can find out more information about pytorch, like
0:14
beyond the scope of this class, if you ever need it. So I'm
0:18
also I want to briefly summarize what pytorch is again. So
0:21
pytorch is the learning library for pytorch for Python. And as
0:26
you have seen, it's quite similar to NumPy. So there are
0:30
these tensors and NumPy with the multi dimensional arrays, which
0:33
are essentially the same thing. But yeah, beyond that, pytorch
0:37
has some convenience functions for deep learning. So yeah, I
0:42
have a summary here, like pytorch at a glance. So pytorch
0:46
is based on torch seven, which was a deep learning library,
0:49
very popular, like five to 10 years ago, but it had one big
0:52
weakness, it was implemented based on Lua. Lua is a programming
0:57
language, I think they chose it because it was convenient to
1:00
work with C files in the context of Lua. And Lua was very
1:04
similar to Python. However, the weakness is it's not Python. And
1:09
lots of people prefer really working in Python. So around
1:14
2016 efforts started like porting torch seven to Python,
1:19
and the project was then called pytorch. So pytorch initially
1:23
used a lot of the torch seven code, but it got gradually
1:26
replaced by more, I would say, rewritten code later on. So but
1:31
originally pytorch started as a library based on torch seven,
1:37
that was then but also compatible to Python. And one of
1:41
its focuses is really on the flexibility and minimizing the
1:45
cognitive overhead. So there are two aspects you can make a
1:49
programming framework really easy to use by abstracting a
1:52
weight all of its complexity. However, one problem is also
1:56
then if you make it too simple, and provide certain building
2:01
blocks, it will become hard to do some custom research where
2:04
you for example, have to develop your own layers and things like
2:07
that. So pytorch has like a summer in between, it minimizes
2:12
the cognitive overhead, so keeps keeping things simple. But it
2:16
also provides you with flexibility for research. Yes,
2:21
so the core features of pytorch are automatic differentiation.
2:26
So this is like, when you have a computation, you can
2:29
automatically compute the derivative. So you don't need to
2:32
know much math for that, which is very convenient. And also it
2:36
has these dynamic computation graphs. In contrast to dynamic
2:40
computation graphs are static computation graphs. And there
2:44
were some libraries before that, for example, Ciano or early
2:48
versions of TensorFlow, which were static. So and that was not
2:52
very convenient to work with. So you had to define a computation.
2:56
And then after you define the computation, you could run it.
2:59
But then it was really, yeah, a little bit hard to debug if you
3:04
had a problem in your computation graph, because it
3:06
was very abstract. So in that way, pytorch has this dynamic
3:10
approach, which is more similar to NumPy, where you Yeah, you
3:14
execute some line of code, or you define the computation, the
3:18
code, and it immediately runs, you don't have to compile
3:21
anything, a graph or something like that. So in that way, it's
3:25
way easier to work with. But I should say this is nothing like
3:29
pytorch invented, they were inspired by the autograd API, in
3:35
another library called chainer, for some reason, chainer never
3:38
really became that popular, although they actually pioneered
3:41
this API. So autograd is automatic differentiation. So
3:47
autograd for automatic gradients, it's also a sub
3:49
library inside pytorch, as we will see later. Yeah, today. So
3:55
yeah, and pytorch also has NumPy integration. So you can
3:58
convert NumPy arrays into pytorch and the other way
4:03
around. However, usually, yeah, we try to avoid using NumPy when
4:06
we are in pytorch. Because, um, yeah, it makes certain things a
4:11
little bit clunky if we have to convert back and forth. So
4:14
usually, we keep using pytorch tensors as long as we can,
4:18
sometimes it's necessary to convert it from, let's say,
4:21
exporting results into other tools. But usually, yeah, we can
4:24
nowadays use most of the stuff implemented in pytorch to do
4:29
most of our work. I should say also one more thing about how
4:34
code is implemented in pytorch. So most of the code under the
4:38
hood is written in c++ and CUDA. That is why pytorch is
4:42
also very efficient compared to regular Python code. So c++, as
4:46
you know, is a low level language, very efficient for
4:49
scientific code. And CUDA is kind of like similar to c++, but
4:53
it's a language, especially for the GPU. So it's you can think
4:57
of it as c++ for the GPU. It's like a simple simplification,
5:03
but it's essentially you can think of it like that. And
5:06
Python really is like more like a wrapper around the c++ and
5:11
CUDA code, making everything convenient. So I call that the
5:15
usability glue, it's like some glue, putting gluing together c
5:19
plus plus and CUDA to make it easy to use. Um, yeah, so just
5:26
briefly, why is why are we using pytorch and not NumPy if both
5:31
are actually also very similar as we have seen in previous
5:34
lectures. So really, why we use pytorch is really we have GPU
5:38
support, which is important for training deep neural networks in
5:41
a time efficient manner. So it can be hundreds 1000 times
5:45
faster than our training on the CPU, for example. Then yeah,
5:50
also, it has additional functionality to distribute
5:54
actually computations across multiple devices like multiple
5:59
GPUs even, which can also be super helpful for especially
6:03
very large models. And then there's also the aspect of
6:07
keeping track of the computation graph, and the operations
6:11
created that created them. So NumPy doesn't do that. So it can
6:17
be a blessing and a curse. So if you don't need a computation
6:21
graph for let's say, computing gradients, it can be memory
6:25
intensive to compute this graph. But most of the time when we do
6:29
deep learning, we want to differentiate results. And for
6:32
that, we can have this graph that pytorch builds in the
6:37
background for differentiating it for computing gradients for
6:41
minimizing the loss function with respect to the weights as
6:43
we will see later. And also, um, yeah, we can deactivate this
6:47
computation graph. So it's not necessary to have that. So we
6:52
can actually use also pytorch without that computation graph,
6:54
as we will also see. So it's really like a really great, nice
6:59
convenient framework. It's essentially NumPy with
7:02
additional convenience functions that make our life as deep
7:05
learning researcher much easier. Also, yeah, I should say, yeah,
7:09
this is the official website. And we will also I will highlight
7:12
some aspects from it, like tutorials and documentation and
7:18
further resources and so forth. So this would be the main
7:20
website, if you want to learn also more about pytorch main
7:23
website to visit. Or I should also say one more word about
7:28
the speed, the speed of pytorch. So according on to the deep
7:33
learning with pytorch book, which was written by Eli
7:36
Stevens, Thomas Fiemann and Lewis Antigua, if I remember
7:42
correctly, so some of them are they are basically main, main
7:49
contributors also to pytorch, I think Thomas Fiemann, especially,
7:52
and I have a lot of experience with this framework. And
7:55
according to this book, based on experiments, or based on the
7:59
experience, taking Python of the out of the computation loop, only
8:04
improves performance by up to 10%, because you don't have to
8:08
use pytorch only in Python. There's nowadays intermediate
8:14
representation, it's called a torch IR, and there's also a C
8:18
plus plus API. So you can use pytorch code or torch code in C
8:24
plus plus only. So just using it without any Python, and the
8:29
performance is not much different. So this is basically
8:32
saying that Python is not really detrimental to the performance
8:37
because some people say, okay, Python is such a slow language,
8:40
why would we want to do deeper learning in it? Actually, it
8:43
turns out, Python is really, I mean, it is really slow compared
8:47
to other languages. But since everything is implemented in C
8:50
plus plus, and could anyway, there's not much that really is
8:57
performance prohibitive in Python. So it's really doesn't
9:00
matter whether we run it in Python or not. The only reason
9:04
why there's also a C plus plus API for torch is, for example,
9:09
not all devices support Python runtimes. For example, if you
9:13
think of a cell phone, like a smartphone, there, you don't
9:17
really have a pytorch, sorry, a Python runtime. So sometimes it
9:22
can be useful to use the C plus plus API. It is possible though,
9:26
and also very easy nowadays to convert, let's say from the
9:31
pytorch Python model into the C plus plus API. So there's this
9:38
intermediate representation that I mentioned, and also on the
9:41
website, they have tutorials for converting between those. So if
9:44
you ever need to implement a model, let's say on a mobile
9:47
device, it's not an issue. That's what people nowadays also
9:50
do very routinely. It's kind of very, very easy. Installation
9:57
wise, I posted about that on canvas, I think it was last
10:01
week, with some write up and recommendations. Just to
10:04
summarize it again, if you have a laptop, I recommend to not not
10:10
run this on the GPU. Because, yeah, honestly, unless you have
10:14
a high end gaming computer with a G force, sorry, I think G
10:19
force Nvidia graphics card, then it will probably get too hot if
10:24
you run it on a GPU, even if you have a compatible graphics card.
10:28
Personally, I use only my laptop for debugging. So I usually
10:32
write all my code on the laptop first, see if it runs on the
10:36
CPU. And then there's only a very simple switch that we have
10:38
to make, I can show you to you later in the code. It's like one
10:42
line of code. And then everything runs on the GPU.
10:45
And after I made sure that it runs on my laptop on the CPU,
10:47
like, for a very, like five minutes, very short time, then I
10:50
would let's say run it somewhere else on the GPU. So my computer
10:54
personally, I only install the CPU version. And in order to
10:59
find out how you install it, I also recommend you to visit on
11:04
the pytorch website. And they have if you scroll down like
11:08
this menu here, where you would select the version, so I
11:11
recommend the stable version, then your operating system.
11:15
Personally, I have a Mac, but of course, you can also use Windows
11:18
or Linux, if you have either of those operating systems. I use
11:22
a corner for the installation. And yeah, Python, so you have
11:27
also the C++ or Java API is here. And I don't use CUDA CUDA is
11:32
the graphics card library that I mentioned the C++ library for
11:38
the graphics card. I don't use that one. Yeah, and then I
11:41
install it like as follows. And notice there is also torch
11:44
vision and torch audio, which are supporting libraries for
11:48
computer vision, and audio data. So we will work with torch
11:53
vision also later in this course. So I just recommend
11:55
actually installing all in one go. So then you have all
11:59
everything together. If you have a desktop on Linux, that is, for
12:05
example, one of my computers, a server I have, it's not at home,
12:09
for example, it's like in a separate location, I usually
12:12
only look in via the terminal. But there I would, for example,
12:15
install GPU version. And then I would install also the latest
12:20
CUDA version. But you have to make sure if you do that, that
12:22
you have a compatible graphics card, it is has to be an Nvidia
12:26
card. And also it has to have a certain driver version to
12:31
support CUDA here. And for this course, I will on Thursday show
12:35
you some websites where you can use a GPU for free. So also for
12:40
this course, you don't need to have like a really lot of GPUs
12:44
or something like that. It's really only it's sufficient to
12:48
have access to a free GPU for this course, we we really focus
12:52
on understanding deep learning and running some introductory
12:56
deep learning models. And yeah, we are not like a big company
12:59
running like 1000s of computations on GPUs in this
13:02
class. So for that way, for that manner, you don't have to buy
13:05
anything for this class, I will show you on Thursday how to
13:08
utilize some free resources. Okay. Oh, yeah, also, one
13:13
little tidbit here. Because there was some message I got
13:16
also on canvas on Piazza private message where some students
13:21
tried to import on pytorch. So there's one quirk if you import
13:26
pytorch, note that it is import torch and not import pytorch. So
13:31
that's like something to keep in mind. It's a little bit
13:34
confusing. I think that's because originally, it comes
13:36
from torch torch seven, like I mentioned, and it pytorch is
13:39
just the API. So I guess this is why the designers made the
13:42
choice to import it as torch and not pytorch. All right, so yeah,
13:49
I wanted to mention if you go to the website, here, there's a
13:53
tutorials link, there are lots of useful tutorials out there.
13:57
Of course, you don't have to read them. But I recommend to
14:00
check out one of them, which is the deep learning with pytorch
14:04
60 minute Blitzman. So that's a short video. And there's a short
14:09
run through, like using pytorch and has a good explanations, I
14:12
think, to get you started with pytorch. But of course, in this
14:15
lecture, I will also explain things to you a little
14:18
differently. So I recommend though, after this class here,
14:22
after this lecture, I also recommend you to read through
14:24
this tutorial. It's a really nice one.
14:27
Yep, that's this one. There's also a pytorch book now. So this
14:31
is by Eli Stevens, Luca Antigua. It's an old screenshot. I think
14:36
Thomas
14:39
Femen is also Femen is also a co author on this book. So you can
14:44
find the version here on this website, it's available for free.
14:49
And there's also a print version that is available via the
14:52
publisher. Um, I should also say there's a very, very nice,
14:58
friendly community around pytorch. So if you go to the
15:02
discussion forum here, if you have any questions, like very
15:05
technical questions, usually someone is always able to help
15:08
with that. And also usually providing answers pretty fast,
15:12
which is very impressive. You can see within the last couple
15:16
of hours, there have been already lots of answers to
15:18
particular, very detailed questions here. So it's a very
15:21
friendly and active community there. And it's also a very
15:24
helpful resource for asking questions. So beyond just the
15:29
other class context. Okay, so in the next video, I will then
15:34
introduce computation graphs. And then after we talked about
15:37
computer computation graphs, I will explain to you how we
15:41
utilize them for automatic differentiation in pytorch.

##v44:

0:01
Yeah, in order to understand automatic differentiation, I
0:04
think it's helpful to take a look at computation graphs. So
0:09
computation graphs are a graph of a computation or calculation
0:13
that we define or execute in pytorch. So in pytorch, in
0:17
particular, when we implement new network models, there will
0:21
be two methods, one is the forward method, and one is the
0:30
backward method. So in the forward method, this one
0:34
constructs the graph, and then backward essentially computes
0:45
gradients by walking backward. So forward graph is constructing
0:50
a graph, if we have a graph with multiple inputs, some
0:54
computations, this is like the forward method, and then the
0:56
backward method, based on the output, we compute the
1:01
derivatives of the output or the loss with respect to these
1:06
inputs, for example, the weights that we want to update. So in
1:10
this lecture, I want to in this video, I want to briefly go
1:12
over, yeah, what such a computation graph is, and how we
1:16
work with it conceptually, before we see how pytorch handles
1:20
that. So yeah, in the context of deep learning, and pytorch, it
1:26
is helpful to think about neural networks as computation graphs,
1:29
because neural networks are really just a chain of
1:32
computations like nested computations. Yeah, so that we
1:37
have a concrete example, let's take a look at a activation
1:41
function that is not a linear activation function. So if you
1:44
recall the Adeline model, what we had is what we had was a
1:50
computation that computed the net input, which was then passed
1:56
on to a threshold function. So the net input is considered one
2:00
weight, one feature was computed as follows. And then we had an
2:06
Adeline, this activation function, which was just an
2:10
identity function. So this one was just an identity function.
2:19
And now we are taking a look at a function where the sigma is
2:23
not an identity function. So we are now taking a look at to make
2:26
it a little bit more interesting at this relu function. So in
2:30
this case, now what we have is the sigma is the activation
2:36
function is this relu function that I have written down here.
2:40
So the relu function in the context of a neural network
2:43
usually takes also the net input. So this is our net input,
2:50
you can think of it as the net input. And we will revisit the
2:54
relu function also in a later lecture and also talk about why
2:58
it is so commonly used in deep learning. So for right now, just
3:01
think of it as an activation function that is almost like a
3:05
linear function, but not quite. So the shape of this function is
3:09
as follows. So on the in the plot, I'm showing you how it
3:12
looks like for different inputs. So here, we have the input to
3:17
the function, for example, the net input z. And here, we have
3:21
the output on the y axis. And the relu function is defined as
3:27
almost like the identity function. So it returns z, the
3:32
input, if z is greater than zero and zero otherwise, so it really
3:38
is this region, an identity function. And here, not it's not
3:50
doing anything on the left hand side. So it's, it's clipped, you
3:54
can think of it as a clipping here. So why is that useful in
4:00
the context of deep learning? We will talk about this more, but
4:02
this is essentially yet to have a non linearity in the
4:05
multilayer network. Because if we have multiple linear
4:08
function, regular linear functions, the combination of
4:11
linear functions is also a linear function. So in a sense,
4:15
our network won't be able to approximate nonlinear
4:18
functions. But yeah, that would be going a little bit too far
4:23
ahead, we will talk about this more in detail here, we just
4:26
care about the computation. So also note for this relu function,
4:32
this one would be not differentiable in a mathematical
4:35
sense. Yeah, just to briefly redraw the relu function here
4:39
for reference. So how it looks like is that it is zero, if the
4:43
input is smaller than zero, and the identity function of the
4:47
input is larger than zero. So here, we have this little kink
4:51
at zero. And now for the left hand side, because there is no
4:55
slope, right, we can immediately see the derivative of this
5:00
function is zero. On the right hand side, it's an identity
5:03
function. So if the function is this, then the derivative of this
5:10
function would be one, right? So slope one. So on the right hand
5:14
side, we have a slope of one on the left hand side, we have a
5:17
slope of zero. But here at this kink, we have a problem. Now, if
5:20
you recall from calculus classes, this would be a
5:23
function that is not differentiable. So in this case,
5:26
we have a derivative of zero, if the input is smaller than zero,
5:30
the derivative of one of the input is larger than zero. But
5:34
otherwise, if the input is exactly zero, then the
5:38
derivative does not exist. So yeah, what do we do now? So in
5:42
computer science, or in the computational context, we are
5:44
not that picky, we just make a small adjustment. So we adjust
5:49
the derivative as follows, that it is zero, if z is smaller or
5:54
equal to zero. So that's just adding this smaller equal to
5:59
here to fix this issue. And otherwise, sorry, this should
6:02
be actually a one, it's one if z is greater than zero, notice
6:06
that we could have also otherwise written it the other
6:09
way around, we could also write it as smaller and sorry, larger
6:16
or equal. It doesn't really matter. Because it's so rare
6:20
that we hit exactly zero anyways, that this will probably
6:23
never happen in practice anyways. Because yeah, usually
6:26
we work with floating point numbers like lots of digits of
6:31
the decimal point. So it's very rare to hit an exact zero
6:34
anyways. So even though it's not differentiable, in a mathematical
6:39
sense, we make in the computational sense, this little
6:41
adjustment and define the derivatives as follows. Okay,
6:46
but yeah, let's move on to the computation graph. Just to
6:49
summarize, now we have the following activation function,
6:52
just just a summary. It's a multivariable function. Where we
6:57
have three inputs, we have the features. So here, we only have
7:02
one feature for simplicity. So let me actually annotate it
7:06
here, one feature, one training example for simplicity, we have
7:11
the bias unit, and the weight parameter. Also, for simplicity,
7:15
only one weight parameter corresponding to the one
7:18
training examples feature. So as you recall, we usually come
7:23
calculate the net input, for example, in airline, and then we
7:27
would pass it to an activation function. In this case, we use
7:30
this relu function. So right now, we don't even have to think
7:34
about your networks, if you don't want to here, you can just
7:38
think of it as a simple computation that we want to
7:41
represent using a computation graph. So how would we do that?
7:47
So here would be a computation graph of this function. So I
7:51
use some intermediate variables to make this a little bit easier
7:54
to read. So we define this computation as you, and we
7:59
compute define this computation as V. So we have three inputs,
8:04
like I said, input one, the bias inputs to the feature input
8:09
three, the weight, what we do is the first part is we compute u
8:13
here, right? So this is multiplying x and w. So this is
8:17
this multiplication here. So we define u as a placeholder here,
8:21
u is equal to w x. And then what we do is we add the bias unit
8:27
here, right? So we have u plus b. So we have this operation
8:32
here, which gives us another variable V. And then V goes
8:38
through this. Yeah, activation function. Also, I could have
8:43
used z, because this is like really the net input. But for
8:47
some reason, I used to be here shouldn't really matter. Just
8:50
think of it as a computation here that we then represent as
8:54
such a graph. So yeah, in the context of deep learning, we are
9:00
usually interested in computing the partial derivative of the
9:03
loss function with respect to the weights, or the bias unit.
9:08
As we've seen in the Adeline lecture last week, and we can
9:11
actually decompose that into smaller sub steps, right? Using
9:15
the chain rule, we can also decompose it into the partial
9:19
derivative of the loss with respect to the activation, and
9:23
times the derivative of the activation with respect to the
9:28
weights and so decomposing it. So here we have a simpler
9:32
computation graph, I haven't included a loss function here.
9:35
So what we're actually looking at here is only the activation.
9:38
So we are in this example, only walking through this part. So
9:43
the partial derivative of the activation with respect to the
9:46
weights, which we can also further decompose into sub steps
9:49
using the chain rule. So that's what I'm doing here. But I'm
9:56
well, that's what I'm going to show you in the next couple of
9:58
slides. So here I have the first step. So computing the
10:02
derivative of the activation with respect to the input of the
10:07
activation. So here, this is the term the derivative of a with
10:12
respect to B, that's the first step. And using this computation
10:17
graph, we can really make this super easy, like computing this
10:20
whole part by doing it in in smaller steps. So the next step
10:25
would be, for example, computing the derivative of V with respect
10:29
to B. So because we are interested in both on usually
10:33
also the bias, because the bias is also like the weight and
10:36
model parameter, which we can then also write as follows. So
10:45
this part here would be sorry, this whole part here would be
10:51
this one here, what we're looking at right now. So the
10:54
next step is computing the partial derivative of B with
11:01
respect to B. It's left in here. Yeah, then we can do this also
11:08
for the other parts. So what's so nice about a computation graph
11:12
is that we can do it step by step, right. So we can, for each
11:16
computation, do a backtrack here and annotate our graph. And then
11:22
we can put everything together. So if we're interested in the
11:25
derivative of a of the output with respect to the input, we
11:28
just need to use the chain rule, right. So we can then write this
11:31
as B, B, times the times the V. So this is a thing mathematicians
11:46
usually don't like, but we can actually cancel these. So this
11:51
is why we get this one using the chain rule. And we can also do
11:56
this here at the bottom, right. So we can do this for this part.
12:00
So the derivative of a with respect to W would be putting
12:06
all these together. D, D, B, and then you can technically see how
12:18
things cancel, right. So this is how we get this one. But
12:23
technically, this is not a right way to do I mean, we shouldn't
12:26
cancel things here. But I use use it all the time as a memory, I
12:30
would say, memory bridge here or something. Alright, so yeah,
12:36
this is what I've done here. If you want to step through that in
12:39
the slides. So I was just putting things together here.
12:43
Yeah, let's now take a look at a concrete example with some
12:47
some actual numbers. So assume the base unit is one, the weights
12:51
are two, and we have an input of three. So the intermediate value
12:57
u would be then six, right? Because two times three, six,
13:02
and then six plus one is seven. And for the relu function,
13:07
because it's positive, it's an identity function. So it's also
13:10
seven. Now let's differentiate. So the derivative of the relu
13:15
function, if the input is greater than zero is one, right,
13:19
because it's an identity function. So the derivative of
13:22
this part here would be one. Then, yeah, let's compute the
13:27
derivative here and here. So if we look at V, so V, you can
13:33
think of it as a sum of two functions here. So the
13:37
derivatives can be then computed separately. So if we look at,
13:41
let's say the upper part here, let's take a look at this one,
13:44
the derivative of V with respect to B. So in this case, u is a
13:48
constant, so we can ignore that and the derivative of B would be
13:51
one, so there should be a one. And similarly, the other way
13:56
around, at the bottom here, B becomes a constant, and the
14:01
derivative of V with respect to u is then also one, right, so we
14:05
can also put a one here. All right, moving on. So we have a
14:09
derivative here. So what do we have here? So this is just w x,
14:14
if we compute the derivative of u with respect to w, then the
14:18
derivative would be x, and x is what is x, x is three. So here,
14:24
we should have a three. And yeah, then putting everything
14:28
together here, the partial derivative of the activation
14:32
with respect to w would be three times one times one is equal to
14:36
three, because we are combining with a chain rule. These here,
14:41
and similarly, we can combine on the results for for this part
14:47
here, too. So in this way, the result here would be also yet
14:52
one, because it's one times one. Alright, so this is how we use
14:57
computation graphs. And I will show you in the next video, how
15:01
we can implement this in pytorch, where it computes these
15:05
derivatives for us. Of course, this example is a trivial one.
15:09
It's very simple, right? That's something you can do in a few
15:12
seconds by hand. But if you rethink of computational graphs
15:16
as new networks that are more complicated with many layers,
15:19
and on lots of input features and stuff, it would be tedious
15:23
to code it all up in pytorch by yourself or in NumPy. So that is
15:27
why there's this automatic differentiation that I will show
15:30
you where pytorch will construct this graph here under the hood.
15:35
Like, we can actually print out the graph, but we don't have to
15:38
have to, it will do it automatically for us. Yeah, just
15:42
some more computation graphs that will be relevant, or that
15:46
are kind of related to deep learning, just to complete this
15:49
video here. So yeah, here, we have an example of a graph with
15:54
a single path. So you can maybe also think of it as a as a
15:59
simple add a line or logistic regression model, which we will
16:02
be covering next lecture. So you can think of it as an airline is
16:05
maybe simpler when you think of the sigma here as an identity
16:09
function. So this would be the full graph based on what I've
16:13
shown you earlier. So in the previous slide, I showed you
16:16
only this part here. Now also think of the output where we
16:21
compute the loss, for example, an airline, the mean squared
16:25
error between the prediction or the output and the actual class
16:31
level. So if we have a case like that, then we compute the
16:36
derivative of the loss with respect to the weights. And this
16:39
can be decomposed into the loss with respect to the output. So
16:43
this would be this part here, then the output with respect to
16:47
the activation. So this would be this part, and then the
16:51
activation with respect to the weights, this would be this
16:53
part. And this is what we had in the last slide as an example. So
16:59
this would be a simple case of graph with a single path. So in
17:05
practice, there will be oscillator some more complicated
17:08
constructs, for example, imagine a graph with weight sharing, it
17:13
is kind of related to what's going on in convolutional
17:16
networks, that will be something that will be covered later.
17:19
Here's a simple example. Imagine, we have a case, we
17:23
have a single input, and then we have a weight parameter that is
17:27
that is shared. So that's the same weight that goes here to
17:31
compute some activation. So these could be different
17:34
functions, a one and a two could be on different functions. And
17:40
then we compute some output. And then also here the loss like on
17:45
the previous slide. So if we have a case like that, we have
17:48
to use the multivariable chain rule because there are no two
17:52
paths, like there's some some weight sharing going on. So if
17:57
we want to update the W, it depends really on this path
18:02
here, and this path, right. So we have to combine them. So we
18:05
have the multivariable channel, we compute the loss. So here,
18:11
the derivative, this is the same, you can use blue here. So
18:14
you can see this is the same here. And then we have two
18:20
different derivatives. So we have this one here. And so here
18:26
at the bottom, we would have Oh, for some reason, I haven't
18:29
written it down. A two, this would be this one here. And
18:34
then which color didn't I Okay, let's use this one. And then
18:37
this derivative here. And then I'm running out of colors, I
18:41
use black, and this one here, and then putting it together
18:44
with a multivariable chain rule. Right. So that would be a case
18:47
where we have weight sharing. So here would be an example of a
18:53
multi layer perceptron, which we will be covering next week. So
18:56
here, we also have multiple paths if we want to update
19:00
certain weights. So this is a multi layer perceptron with two
19:04
hidden layers, you can see there are no two levels of
19:07
activations, one level is here, and one level is here. So this
19:12
is the first hidden layer, and this is the second hidden layer.
19:21
And again, this part is like the same as in the previous slide,
19:24
the loss. Um, let's say we are interested here in computing the
19:29
derivative of the loss with respect to this weight here, W
19:32
one, one, in the first hidden layer. So in order to do that,
19:36
we compute the loss. So sorry, the compute the loss, but then
19:40
also the derivative of the loss with respect to the output that
19:43
would be this part here. And then we go here, this would be
19:52
this part. And then we go here, which would be this part. So we
19:59
are skipping across some parts later, and next week, we'll do
20:03
this step by step in more detail. And then so I'm skipping
20:07
here a lot of steps. So because this could also be decomposed as
20:11
as sub steps with a net input and so forth, but let's not do
20:15
it here. And then we have this part, which is the derivative of
20:20
this activation, the a one with respect to this weight, let me
20:23
use the green color here. So this is here. So we are
20:29
computing with respect to one here. All right. However, note
20:40
that there's a second path, right? So we can also let's use
20:44
the red here. Let's go to the second path. So it's again, the
20:47
same line one is like this one. But we have no also the second
20:53
path. Oh, sorry, I said was wrong. The second path would be
20:58
this one. And this one, see, it's actually not so easy to see
21:03
what is going into here. So this would be the second path. If I
21:08
use a different color, let's say pink for the forward here. So
21:11
you can see this one, this one, and this one is one path. And
21:14
the other one is this one. And this one, and this one, so they
21:19
both go in there. So the second path would be then the same as
21:26
before and the end here. But then this one is a little bit
21:29
different because it's now the second unit here. And then this
21:34
one is also the second unit. This is this connection here. And
21:38
then we compute this part here, which this is the same. So in
21:42
that case, you can see actually things can become quite
21:45
complicated if we have a multi layer network. And now imagine
21:48
coding this by hand, like computing the derivatives,
21:51
implementing them in code. It's very error prone. It's important
21:55
to on the big picture, you understand what's going on. But
21:59
you're implementing this in by hand. And this is only for one
22:02
way, it would be very error prone, which is why we actually
22:04
use deep learning frameworks that can do this automatically
22:08
for us. So in the deep learning framework, we only have to
22:11
provide the forward computation. And then the backward
22:14
computation is yet derived automatically because you can,
22:17
yeah, you can implement simple rules to do that automatically,
22:21
you just have to be careful implementing these rules once
22:23
and then you can always apply them to any arbitrary
22:26
computations. Okay, so in the next video, I will show you how
22:30
we can do this automatic differentiation in pytorch. And
22:33
then in the next videos, I will also do this in a more
22:37
comprehensive example using the airline that we talked about
22:40
last week. And then we will also take a closer look at the pytorch
22:44
API, the convenience functions. All right.

##v45:

0:00
Yeah, so in this video, let me briefly go over the basic
0:03
concept of automatic differentiation in pytorch. And
0:08
then in the next video, we will take a look at a more
0:10
comprehensive example, training and align the adaptive linear
0:14
neuron using the other automatic differentiation concepts in
0:18
pytorch. So here, I just want to show you the computation graph
0:23
that we talked about in the previous videos in the context
0:25
of pytorch. So here in this notebook, I should also say, or
0:30
you can find it here on GitHub, I will upload it to GitHub after
0:34
you have finished recording. And I will also add a link to canvas
0:37
so you can't miss it. In case you want to play around with it.
0:41
So yeah, let me clear the outputs and then execute it one
0:46
by one. Of course, starting with watermark to see what versions
0:50
I have, you can also run this with a newer older version, it
0:53
should work the same way. So yeah, here, I'm imparting now the
0:59
autograd API, which is the automatic differentiation API.
1:04
So autograd, you can think of it as automatic gradient. Later on,
1:08
when we train deeper neural networks, we don't have to use
1:11
autograd explicitly. So there are functions that in pytorch
1:16
that we define like layers, convolution layers and the
1:18
backward function that will use autograd under the hood. But I
1:22
think it's useful to understand how autograd works, because you
1:25
may also want to use this in some other contexts. Alright, so
1:29
let's import these. And here's the computation graph that we
1:33
talked about in the previous video, same thing, so I don't
1:36
have to go over this again, I think. So here, I'm defining
1:40
this computation graph in pytorch. So I have my input
1:44
vector, or tensor x, a weight, w, bias B, and the activation,
1:51
that's the relu function. So I could have also used these
1:55
intermediate variables, but I think it would be a little bit
1:57
overkill, we don't really need to do that. Um, then then
2:02
now there's a attribute here, or a value that I said requires
2:06
grad equals to true. Why am I doing that? That means I am
2:11
interested in computing the gradient or derivative here. If
2:15
I don't do that, by default, it will be if I don't do that, it
2:19
will be equal to false if I don't do anything. So it's
2:25
actually a good decision by pytorch, because not always when
2:27
we use pytorch, we are interested in computing
2:29
gradients. And now when I run this code here, we can't see it
2:34
here. But under the hood, it will actually create a
2:37
computation graph similar to this one and save it internally.
2:41
And of course, this takes up memory in the computer. So if we
2:44
don't need a computation graph, it doesn't create it. But we can
2:49
say we want it because when we want to compute gradients, we
2:52
need that because we need to know how we can go backward. So
2:55
in this case, we set requires gradient equals to true. This
3:00
means we will later on compute the gradient. So please construct
3:05
this computation graph. So you can just say I see that the
3:09
result is indeed the one that we have here in the figure. Now,
3:14
um, yeah, we are computing the gradient here. So using this
3:19
grad function here. So if I go up again, this is something I
3:23
imported here from the autograd API. So I'm importing this grad
3:28
function. And now I'm computing the gradient of a with respect
3:32
to W. I'm also saying retain the graph, the computation graph, I
3:39
say, do it like set it to true. So it will retain it. Let's do
3:43
this. So this computes the gradient of all the partial
3:47
derivative of a with respect to W. The reason why it's gradient
3:51
and not partial derivative is it's usually working, of course,
3:54
with, um, yeah, vectors and matrices. And this is a very
3:58
simple example. In this case, we only have scalars. But this is
4:01
a general function that works also, yeah, with vectors and
4:03
matrices. So yeah, the partial derivative here is three. So
4:08
that's what we also got here, if you recall. So everything makes
4:13
sense and looks good. So now I'm doing this, um, again, for the
4:18
bias unit here. So I get my derivative of one. So also just
4:22
to double check, this is also what we have here. So everything
4:25
makes sense. So notice now I didn't set or retain graph to
4:30
true. So I didn't do it. And if it's not set, then it will
4:34
actually destroy the computation graph after calling grad. So
4:38
why is that usually in the context of a deep neural
4:41
network, we don't need the graph again, until the next forward
4:45
path pass. And since it's a dynamic framework, the forward
4:49
path pass might change. So actually, the graph is
4:53
constructed every time from scratch. But this is not a
4:56
detail we need to be concerned with right now. What I mentioned
5:00
or what I wanted to show you here is if I now execute this
5:03
again, it won't work, because we have destroyed the computation
5:07
graph, it says, or it basically tells us why this error occurs,
5:12
is this because we haven't retained the graph, so we can't
5:16
do it twice? Why is that done? It's usually yet to save also
5:19
memory, because imagine, you wouldn't do that. And you have
5:23
a deep neural network. And you call the forward method multiple
5:27
times, then in each epoch, or in each iteration, the graph
5:30
would be bigger and bigger and bigger and bigger and bigger.
5:32
So in this case, it's getting destroyed after each update, or
5:36
after each grading computation, and then rebuild from scratch to
5:39
prevent having it growing infinitely large. Okay, so but
5:44
this was just a basic concept of how this works. I will show you
5:49
in a later video next video, how this is done automatically by a
5:53
pytorch using the backward function. But it's still good to
5:56
understand, like these basic concepts, because that's, yeah,
5:59
it's just from a also scientific point of view, just
6:02
interesting to understand what's going on under the hood in
6:05
pytorch. Alright, so here, um, also, we can compute derivatives
6:12
of arbitrary functions. So if we implement them ourselves, so here
6:16
have an if and else. Also, this would work. We don't have to
6:20
define our own riddle function, because there is already a
6:23
riddle function and pytorch. So I actually skipped over this.
6:27
But notice, I also imported here, torch dot function, and
6:33
n dot functional. So I will explain this later on in a later
6:37
video this today. So this is an N is a neural network sub library
6:42
that contains a lot of convenience functions for neural
6:45
networks. And functional is the functional API, I will also go
6:49
over more details about that. Here, I'm just using the
6:52
shortcut F, because otherwise, it would be much more to type. So
6:56
pytorch developers me included lazy, so we use F as a shortcut
7:01
for an n dot functional. And here's the relu function I use
7:06
from this functional sub API. However, if I wanted to, I can
7:11
also implement the relu function myself, it's quite simple. But
7:14
if there's already an existing function pytorch, I actually
7:17
recommend using that one, because it's usually more
7:19
efficient than our own implementation. But here, that's
7:22
just to show you that we could equally implemented ourselves.
7:27
And this would also work. Alright, so what I'm showing you
7:32
here is that even if it's an if and else, like these pytorch
7:35
Python statements, it can also correctly deal with those. And
7:41
also, in case we have something where it's not defined, the
7:46
gradient is not defined, it will also be automatically able to
7:49
do something reasonable. So for example, here, this has the case
7:52
the case where the input is minus one, w is one, so we have
7:57
minus one times one is minus one, plus the bias is zero. So
8:02
the gradient of that one, or the partial derivative of the
8:05
relu with respect to the input should be zero, right? Actually,
8:09
it should be not defined. But like we said earlier, in the
8:12
lecture, we use the trick, so it can be adjusted to zero. And
8:16
let's see if it is also doing it. Yep, so it's working here. So
8:20
it's doing something reasonable, it is not crashing here, right?
8:24
So if I show you my slides, again, we said that earlier,
8:28
some time ago here, where the derivative is not defined, but
8:33
it would do something reasonable. So in that case,
8:35
pytorch is also doing something reasonable, it's not crashing.
8:38
And it works. So yeah, this was briefly how the automatic
8:42
differentiation works in pytorch using this grad function, and
8:46
really what it is doing, it's going on constructing a
8:49
computation graph under the hood, and then is it's going to
8:53
compute the derivatives for us. And in the next video, I will
8:56
show you how we can do that for model training for training
9:01
guideline.

##v46:

0:01
Okay, now in this video, let me explain how we train Adaline
0:05
using the concept of automatic differentiation and pytorch. So
0:09
I prepared a code notebook here, where I have three different
0:14
implementations of Adaline. First is the manual implementation
0:18
that we saw last week, then I have an implementation using
0:23
the grad function that I just explained in the previous video.
0:26
And then I show you an even more automatic way using the
0:29
backward function that pytorch automatically creates based on a
0:34
forward function. And that is also a topic I will then dive in
0:38
more in the next video. So here, I want to just show you how it
0:41
works. And then next video, I explain it a little bit more.
0:46
Alright, so starting again with watermark checking our versions
0:50
here, I can also make this a little bit bigger. So here again,
0:54
this is our Adaline model that we talked about extensively last
0:57
week, where we have multiple inputs, the weights, the net
1:01
input function, the activation function is just a identity
1:06
function, and then the threshold function for prediction.
1:10
Alright, let's import some libraries, we will be using the
1:13
grad function I explained in the previous video, and we will also
1:16
make use of the functional API. Again, the function API will be
1:20
a more discussion topic in more detail in the next video. So we
1:25
will be working with the iris data set again, because it's
1:28
simple. So we can then focus more on the code rather than on
1:31
the data set. So here we have no data set. And this is exactly
1:37
the same as we have done in the previous week week. So if you're
1:40
unsure how this works, this is exactly the same code as last
1:44
week. So you can go to the video from last week. So everything is
1:49
explained in that video last week. Alright, so also just to
1:53
recap, this is exactly the same code that we were using last
1:57
week. So here, this is our airline implementation, where we
2:00
first initialize the weights and the bias, we have our forward
2:04
function that computes the net inputs, and then the activation.
2:08
And then we have the backward function where we computed the
2:12
gradient by ourselves. So what I mean by that is we derived it in
2:16
the slides, we had a slide on how we derive that gradient. And
2:19
then here, this would be the equivalent code implementation
2:22
of that. Yeah, we have some training and evaluation wrappers
2:28
just to make things a bit more convenient to look at. So we
2:32
have a loss function, then we compute where we can plot the
2:35
loss function during training. So here in our training function,
2:39
again, like in last week, we have a cost list with where we
2:42
compute the cost, which is actually the loss over the epoch
2:48
or mini batch, actually. So let me see. So what we do is we
2:52
iterate over the epochs. So for each epoch, we shuffle the
2:56
data set. And then we create the mini batches. And for each mini
3:01
batch here, we perform the forward pass that is like
3:05
predicting the class labels. And then we compute the backward
3:11
pass. So here, this is computing the negative gradients, the
3:16
negative gradient of the loss with respect to the weights and
3:20
the bias. And then we update the weights. So we updated by
3:27
Yeah, we have the original weight, we updated by adding the
3:30
negative gradient multiplied with the learning rate. Why for
3:35
some reason commented that out? Yeah, I think it was just too
3:37
much output. And I wanted to keep this notebook short,
3:41
because there will be other codes. And it was too long.
3:43
Otherwise too detailed. We don't need that level of detail here.
3:46
Here, we are just printing the number of epochs and the loss
3:51
for each epoch. So let's define it. So note, this is not running
3:55
any code, because it's just setting up the functions here.
4:00
And then here, we are defining or initializing the model. So x
4:08
train size, this is the same, I could have used shape, this is
4:11
the same as shape. So it's the number of features. It's the
4:15
same as shape one, some more features. Then yeah, here's our
4:22
data sets. input, the number of epochs 20 learning rate point or
4:29
one, the random seed, so we can reproduce these results. So that
4:33
means if someone else like you runs this code, you should get
4:36
exactly the same results. And then the mini batch size, how
4:40
many mini batches we use in each iteration, not the random seed
4:45
here is only used for shuffling the data set, right? If I go up
4:48
again, this is being used when we shuffle the data set. So if
4:53
you change the random seed, you might get some different
4:56
results. Alright, so let's do this. So this is training and
5:02
this is super fast. So you can see the outputs are immediately
5:05
here. Usually for deep learning, it would take maybe depends
5:09
really, but it could take 10 minutes per epoch can take an
5:12
hour per epoch depends really on the data set. So let's take a
5:15
look at the loss. Okay, this is converging, it's not converted,
5:21
but doesn't really matter. Because here, the point is
5:24
really explaining the automatic gradient computation in the next
5:28
code. I want to why I'm showing you this is so that you can
5:33
compare the automatic way of pytorch of doing this with this
5:37
one, and you will see it's exactly the same result. So just
5:40
to show you that our conceptual thing thing that we did manually
5:45
last week is actually correct. And while other way around that
5:49
pytorch is actually correct. Alright, so here, that's the
5:53
predictions for computing the test and training accuracies.
5:58
Also, it's essentially the same concept as last week. So nothing
6:02
new here. Now, after we just recapped, yeah, the manual
6:08
implementation of the underlying that we talked about last week,
6:11
now let's do this semi automatically or semi manually
6:15
using this autograd API from pytorch. So there will be only
6:21
very subtle changes. So this one is exactly the same as before.
6:27
Now, the only difference is in the train method. So let me
6:31
scroll to the relevant part. So notice everything here is the
6:35
same. What has changed is now how we compute the gradients
6:39
here. So now we use this grad function to compute the
6:43
gradients of the loss with respect to the model weights.
6:49
And then we retain the graph. Remember from last video, this
6:53
is if we need again gradients, we need to retain it one more
6:57
time. So because we want to compute the bias here, too. And
7:01
then here, we don't care because in the next round, it will be
7:05
constructed from scratch the graph. So here, we don't need to
7:08
retain the graph. Why the minus one. So that is because we want
7:13
to have the negative gradient, because then we, we add the
7:16
negative gradient to the model weight. We could also just skip
7:19
this step. Of course, right, we can do it like this, and add a
7:25
minus here. Oops, same thing. But just to keep it consistent
7:31
with the implementation that we had before our manual
7:34
implementation, I wanted to make it as similar as possible.
7:38
Alright, so the only difference to before is now that how we
7:43
compute the gradients, notice that there is no backward
7:46
function. Now, if I scroll up again, show it to you again, in
7:50
the previous time, we had backward here to compute the
7:55
gradients where backward was our manual way of computing the
7:59
gradients. Now, we do it automatically. See, this is
8:03
actually because of this scrolling is why I commented on
8:06
the logging because otherwise, it would be a lot of stuff to
8:08
scroll here. All right, um, back to the thing here. So yeah,
8:15
here, here, this is the difference. Instead of using
8:18
backward with our manual gradients, we now use this grad
8:20
function. Except that everything should be the same. I made a
8:25
small modification here to the logging. Notice that I use with
8:29
torch no grad, because when we just do some logging here, we
8:33
don't do any model training here, we don't need to
8:36
construct the graph, it would be computationally wasteful to
8:39
build the graph, because otherwise, it will create the
8:43
graph in our forward method. So here, this one, because we have
8:48
set a request gradient to true, if this is set to true, every
8:52
time this is used, it will create this computation graph.
8:55
Okay, so here, the computation graph gets destroyed, because we
9:00
don't have retained graph to true. So every time we do the
9:03
for loop here, it makes a new graph. Here, we don't call grad,
9:10
right. So here, it would create a graph, but we don't need this
9:14
graph. And it would be just computationally wasteful. It's
9:17
just a good habit. If we don't need a graph, if we don't need
9:19
to compute gradients here for logging, then we can use this
9:24
with torch, no gradient context, and everything that is indented.
9:30
So everything that is below here does not construct a computation
9:35
graph, it's just to save computational resources. Here is
9:38
such a simple code, it doesn't matter. But it does matter for
9:41
deeper neural networks. All right, so defining it, then
9:47
again, same as before, we initialize the model, notice
9:50
that there's no other lines to instead of a line one, then
9:54
training the model. So we can see again, the loss goes down,
9:59
dot up, dot up, dot up. And let's take a look. plot should
10:03
look exactly like before. Let's compute the training accuracy
10:08
and test accuracy. Also, the same as before, you can actually
10:12
double check, these are exactly the same numbers as the ones
10:18
here. All right, so this is now doing things more conveniently,
10:22
right? So, because you can think of it, um, if I scroll up again,
10:27
you don't want to scroll that much. But I think it's useful
10:29
here in this case. So if this forward one would be a very long
10:32
complicated function using multiple layers and stuff like
10:35
that, you can already see how it's convenient to not implement
10:39
this backward method by hand by deriving that by hand, right? I
10:43
mean, it's a good exercise, still, but it is also very
10:47
it is also very error prone for deep neural networks. So it's
10:50
better to rely on these automatic functions. However,
10:53
there is an even more convenient way to do this that I want to
10:56
show you now. So this is usually how people most people use
11:01
pytorch. So you can actually use the so called linear layer
11:07
here. So this is as I explained last week, this is computing the
11:12
net input. I have now an additional step. So here I have
11:19
this zero. So what's going on here? So usually when we use
11:25
torch dot n dot linear, it's thinking we want to implement
11:29
some multi layer neural network, because that's what most people
11:32
do in deep learning. And then it will initialize the weights to
11:36
small random numbers. This would be also totally fine for our
11:40
edeline here. However, to make our edeline combination here
11:44
more comparable to the previous two codes I showed you before
11:48
where we use zero weights, I also want to use zero weights.
11:51
So I'm setting these weights to zero here. So just to show you
11:56
what I mean, let me just do this. Alright, let me just use
12:03
this. And then I should have of course, assigned it to something,
12:09
you can see that these should be small random values, see that.
12:14
And if I set them to zero, they will be oops, the problem you
12:23
have to detach it, it doesn't like it. If you have a variable
12:28
defined, and you want to modify it, like in place, leaf variable
12:34
means a leaf, it's like an endpoint. And it doesn't like it
12:38
if you modify it with an in place operation, because it's
12:41
also error prone, this is usually something you don't want
12:43
to do in a network. So it's kind of warning you. So you have to
12:48
detach it from the graph here. Oops, there we go. So now I set
12:53
it to zero. Also, notice I didn't, I didn't do this here
12:58
equal to, because there's a convention in pytorch, there are
13:03
these so called in place operations, these with an
13:06
underscore, they do an operation in place. So there's no return
13:11
value, actually, it just takes the existing vector and over
13:15
writes it. This is also done for computational efficiency,
13:19
because imagine you have a very large vector. And then you want
13:24
to override it with all zeros, you would have to memory briefly
13:27
create two vectors, you have the original one, then the zero
13:30
vector and the zero vector overrides the original one. So in
13:33
a brief moment in time, you would have two vectors in
13:36
memory, and it would take twice as much memory. So if you do
13:38
this with large matrices, it can in certain GPUs be a problem.
13:43
I mean, it's just wasteful. So in this case, these underscore
13:45
operations, modify something in place. But yeah, I'm getting
13:50
sidetracked here. Let's go back to what's going on here. So here
13:55
I'm now defining the forward path, pass, sorry, the weights
14:00
used in the forward pass using this linear wrapper. We talked
14:04
about this briefly last week. And then so I'm signing it to
14:09
self dot linear. And then I'm using it in the forward method
14:12
here. So here, computing the net inputs using self dot linear,
14:18
then I'm computing the activations, activations, that's
14:22
nothing an identity function. So I'm just overwriting it. And
14:26
then I'm returning it. Alright, so here, now I'm training it
14:31
again. Notice, the only things I define are this weight layer
14:38
here. And this forward method here, I'm not defining anything
14:41
else. In the train function, this is fundamentally very
14:45
similar to before. Except now, see, I'm computing the loss
14:51
here. So I'm computing loss function, I'm using here, the mse
14:57
loss, I could use my own loss. But like I mentioned, if there
15:00
is a function that is already implemented in pytorch, I
15:03
recommend using that one over your own implementation, because
15:05
it's usually more efficient. They use some tricks under the
15:08
hood, also c++ code to implement things more efficiently. So
15:12
here, we are using this mse loss. And then we are resetting
15:20
the gradients using zero grad, and calling backward. So
15:24
multiple steps that are new now that are happening here. So
15:30
calling forward to predict the outputs, the class label, so
15:34
compute outputs, then it's actually not the class name, it
15:37
is the net inputs, the because it's before the threshold
15:40
function, let me scroll up one more time. So we are we are
15:46
here, this this value here, we are computing this value.
15:52
Alright, we're computing this value y hat. Oh, this is the
15:58
previous one, sorry. Okay, here, for it. So we are computing
16:04
this y hat value, then we compute the prediction error,
16:10
using the mean square error here. Notice that I'm resetting
16:15
gradients from the previous iteration. So this will be
16:17
running multiple times. And there is how pytorch works,
16:23
there is a dot grad attribute that will be set for these
16:27
variables after each iteration. And we are resetting it,
16:32
otherwise, you would be accumulating the gradients. So
16:37
usually, it's not the case in deep learning, we usually
16:39
compute the gradients, update the weights, then do the next
16:43
round, compute the gradients updates the way update the
16:45
weights. But there are some applications where we want to,
16:48
for example, not update the weights after each epoch, for
16:52
example, we can do two forward passes and then update the
16:54
weights. So this would be possible, we could, for example,
16:59
skip zeroing the gradient. So we, we could technically, for
17:03
certain research experiments, accumulate the experiments. So
17:08
this is why pytorch has this implementation to allow certain
17:11
researchers to do some more flexible research, but it also
17:14
is a normal user forces us to remember to zero the gradients.
17:20
So here, the opt so we are also using, I should say an
17:24
optimizer, stochastic gradient descent, that is more automatically
17:30
than what we have done before. So prediction, computing the
17:36
loss zeroing the gradients from the previous round, calling
17:40
backward that computes our gradients, and then updating the
17:44
weights. So this is usually a typical pytorch workflow, that
17:49
is what people do, usually in practice, and what we do when we
17:52
do implement neural networks. In the previous round, we had it
17:58
manually. So we had computed forward, and then we had our
18:05
loss function. But then we computed here, the negative
18:08
gradients, and we did the stuff here, the update automatically,
18:13
this is what in our code information below is equal to
18:18
optimize step. So how does optimizer know that we want to
18:25
update the weight and the bias? Well, that is because we feed
18:29
it with the parameters I will show you. Here we are, we
18:35
provided TSC with model parameters. So there's also a
18:39
concept, if you use these functions like torch that linear,
18:43
these will be registered as model parameters in this module
18:46
here. So here, this will automatically contain the model
18:51
parameters, let me actually show it to you. So here we have,
18:56
where was it first grow up, we haven't actually defined it yet,
19:00
sorry. So let me execute this part first, and then I will show
19:04
you more details. All right, so I already ran this, so
19:11
everything should work and actually also, it's fine. So here
19:15
you can see, okay, maybe can't because it's a generator. So you
19:23
can see there are these two entries, one is actually the
19:28
weights, and one is the bias. So they are registered under the
19:31
parameters. So these are really the values that we have as
19:34
model, dot FC dot weights. What was it? How did we save it one
19:44
second, or linear, we call it linear, not FC. Okay. So you can
19:51
see, these are corresponding to this one. And this one is
19:56
corresponding to this one. So this is how the optimizer knows
20:01
what to update when we call step. I can maybe also show you
20:06
on model linear, weight, there should be a grad. So this is the
20:13
gradient, the gradient from training it. So from the
20:17
backward pass, and if we call backward, the next round, it
20:22
will add to this gradient, so it will grow. So this one should
20:29
actually make it zero. Let's execute this doesn't work. Oh,
20:39
it's, it's because it's defined outside this outside this
20:44
function here. That's a bit unfortunate. Um, yeah, it would
20:50
be tricky to show it to you here. Maybe I can can do it
20:55
differently. I can do it here before. After. All right, it's
21:19
actually none. Also, okay, no, it's something else. So I think
21:22
the first round, so you can see it first, it's this and then
21:26
after zero, this and then it's this and this, you can see how
21:31
it's computed, then zero to computer zero. If I don't do
21:35
this one, it will just grow larger and larger. You can see
21:41
that. Maybe not because it's positive or negative, but you
21:45
can see how large it becomes. That's actually not good. So
21:50
here, the model wouldn't learn anything useful, I guess. Let's
21:54
see. Yeah, you can see it's not learning anything useful. So
21:58
let's fix that. All right, let's fix this and run it properly.
22:10
All right. And you can see this is the same as before. When I
22:16
compute the test and training accuracy, look at these values,
22:20
values 92.86% and 93.33%. And this is exactly the same accuracy.
22:26
Let me scroll up to our manual implementation is exactly the
22:34
same number here. So you can see pytorch is performing exactly
22:38
the same thing we do manually. So our manual derivatives are
22:42
correct. And vice versa pytorch is also correct. So I will talk
22:46
about this more in the slides explaining this again. But I
22:50
think if this is still unclear, maybe focus on this part. So
22:55
this is really how we use pytorch like forward, compute
22:58
the loss, zero, the gradients backward update. And this is
23:04
essentially a pytorch in a nutshell. And we can use this
23:06
API for all types of models. So the only difference is really
23:10
here when we define the weight parameters and the forward pass.
23:16
So this is the only difference, the training loop is essentially
23:19
always the same. All right, then let me stop this video, and then
23:23
go back into the slides and explain to you a little bit more
23:26
about the pytorch API.

##v47:

0:01
Yeah, so in this last video for today, I want to go over the
0:04
pytorch API in particular, discussing the subtle difference
0:08
between the object oriented and functional API's, because it
0:11
will become useful in the future lessons. So here's an overview
0:18
of a multi layer perceptron. So we haven't really talked about
0:22
in detail how it works. I only showed you some graphs of how it
0:25
looks like. So here for this purpose, it's really just
0:29
sufficient to think of it as a multi layer neural network.
0:33
Because we have the same concept really applies for all types of
0:37
networks, when we work with pytorch, or almost all types of
0:40
networks. So that's like this general template that you can
0:44
think of, where we have, or where we use usually a class to
0:50
define the model. And then for this class, we inherit from this
0:54
torch dot n n dot module. So this gives us some certain
0:58
convenience functions automatically. So this is
1:01
usually how we set up a network in pytorch. And then there's
1:06
this constructor, the init constructor, that is something
1:09
we can define ourselves. So there's one line that we use
1:13
here, this is really just for inheritance. So it inherits the
1:17
init method from a module. But then everything else has
1:20
something we can define ourselves. So here, I'm setting
1:25
up a neural network with one, two hidden layers and one output
1:30
layer. And each layer is a torch and dot linear, a fully
1:35
connected layer here. And these are really in the init method,
1:40
only the parts that need to be updated, like the model
1:44
parameters. So how the network runs like the forward pass, that
1:50
is what we define in a forward method. So here, the input to
1:54
the forward method is just a data input that will be
1:58
provided during training. And then we define really how the
2:02
computation works. In this case, this is a network where we
2:05
first compute the net input, then we use the relu function, we
2:09
discussed a relu function earlier in this lecture, then we
2:13
have another fully connected layer net input, then another
2:17
relu, and then the output. And then we compute also our
2:21
probabilities for the output, we could technically skip this
2:25
step and only return the logits. It's really just a matter of
2:28
preference. And we will also discuss what softmax is and what
2:32
the logits are later in the upcoming weeks. So here, I
2:37
really want to emphasize that in the init method, we define
2:42
model parameters. And then in the forward method, we define how
2:47
and in what order the model parameters are used. So that is
2:52
just like the general outline here. And this is also similar
2:55
what to what we have done on in the previous video when we
2:58
talked about the adder line in the last step in the automatic
3:01
step. So here, consider step one as the setup or module
3:09
definition step. Because here, we are not really running any
3:12
code yet, we are just setting up our Python class. So then step
3:17
two, we actually instantiate or create our model. So here, I'm
3:21
just setting my random seed. Because if I go back one slide,
3:27
here, these, like I mentioned in the code examples, these will be
3:31
based on small random weights. Personally, I like to have my
3:35
code reproducible. So I usually set a random seed before I
3:39
initialize the model. So every time then you run the same code,
3:43
it will use the same random seeds if I use the same value
3:46
for random seed. However, in new network training, of course, it
3:50
requires sometimes to change the random seed because sometimes
3:53
you can have bad starting weights. I will talk also about
3:56
that more later. So I'm not always using the same random
4:01
seed. But if I want to reproduce these experiments, I write down
4:04
the seeds I use. And then if I have someone else execute the
4:08
code, they can use the same seed. Anyway, so here we
4:12
initialize the perceptron model. And then this is an optional
4:16
step to device. This is really very, very cool if you want to
4:21
run your code on the GPU. So the only line of code you really
4:25
need to change, I mean, there will be some other lines, but
4:27
the main line you have to change is this one. If you provide GPU
4:32
setting here, it will run all the code on GPU. So it will
4:35
transfer all that code to the GPU and run automatically on the
4:38
GPU, which is really convenient. And then another thing we set
4:44
up is the optimizer here. So here, like I also explained in
4:48
the previous video, it gets the model parameters. In this case,
4:51
if I go back one slide, sorry, we have a lot of model
4:55
parameters here, all these linear ones contain weights and
4:58
biases. So here, we tell the optimizer, what are the model
5:02
parameters, what needs to be updated during gradient descent.
5:06
So this is stochastic gradient descent that we discussed also
5:17
last week. So it's a stochastic gradient descent optimizer. Later,
5:21
we will see the other types of optimizers like different
5:24
flavors of stochastic gradient descent. Alright, so this is
5:28
what I described before. So we can provide if we have a CUDA
5:33
device, a GPU, we can specify it here, and then the code or the
5:37
model will be executed on the GPU, which can make training
5:40
much more faster. And then Thursday, I will show you some
5:44
some free platforms where you can use a GPU for free. Alright,
5:50
so step three is then the training step. So that is also
5:54
the same concept as I explained in the airline code in the
5:58
previous video. So much of it, what I'm showing you here on the
6:01
slides is really very similar to what I've shown you in the
6:03
previous video. I'm just walking through this a little bit more
6:05
slowly. So here, I have my loop over the epochs. Notice that we
6:12
set model train, this is a good practice because later, there
6:17
will be certain functions where we have a different behavior
6:23
during training and evaluation. For example, there's a concept
6:26
called batch norm or drop out. And it's a good habit in each
6:31
epoch to set it to train. And then when we do some logging or
6:35
evaluation, to set it up to evil, it's just a good habit. So
6:39
that is something that's always good to do. So I will also make
6:43
sure my code examples that I provide to you that this is
6:46
indeed specified. And also notice, you don't really have to
6:51
memorize this. Because in practice, when you write a new
6:55
neural network, or implement a new neural network, you would
6:58
never start from scratch, you would never like start with a
7:01
blank, empty script, and write down all these codes. What you
7:05
would do is you would copy and paste the code here, you would
7:09
copy and paste this as existing code. And then yeah, you would
7:12
just optimize or modify it. So you would never really start
7:16
from scratch totally. So in that way, you don't really need to
7:21
memorize, you just have to know where to find this information.
7:24
If you want to, yeah, if you want to write some encode, you
7:28
use usually a template to start with. Where was I? Okay, so here
7:33
we iterate over the epochs here we iterate over the batches,
7:39
there will also be a training loader that I will show to you
7:42
where we batch up our training set in a pytorch data set
7:47
context that makes also the iteration over the mini batches
7:49
a little more convenient. Here, this is like a requirement
7:54
because I'm I created this example for MNIST. And MNIST are
8:00
images 28 by 28. And my model here is a fully connected
8:04
network, it needs this long tabular data set this long
8:07
vector. So I'm just reshaping it. But this is a detail, don't
8:11
worry about it here at this point. There's one more thing.
8:14
If my model sits on the GPU, also my data has to sit on the
8:18
GPU. So that is something that is like required, we can't do a
8:23
computation, let's say multiplication, or matrix
8:26
multiplication between a matrix sitting on the GPU and the CPU,
8:31
they have to be either both on the CPU, or both on the GPU. So
8:37
personally, how this can be very, very easily handled is by
8:40
specifying somewhere in your code, something like oops,
8:46
something like device equals to either CPU or GPU. So usually
8:51
there's something you would want to use like torch dot device,
8:55
sorry, torch dot device. And then you would either set it to
9:00
CPU. Or let's say the cooler device. Usually, if you have one
9:08
GPU, you would set it to zero. If you want to use a second GPU
9:12
that you have in your computer, you can change it to one. So
9:15
this is like a really an index here. But I will also talk more
9:19
about this in the next lecture. So if you set this somewhere in
9:24
your code, then this variable will be used here. And here, so
9:30
you don't have to change anything. So it will just work
9:33
whatever you have either CPU or GPU. So then moving on, this is
9:38
the forward pass. So this is the forward pass of your model.
9:42
Notice that we don't actually call forward, we don't do model
9:49
dot forward features. We just call model features. It's almost
9:58
the same thing. I actually have a note here to remind you of
10:02
that. It's actually the same thing. But there's one extra
10:07
step if we don't do forward. So internally, Python, how classes
10:12
work in Python, there's some something called a call. And this
10:17
one will actually do some extra stuff and then inside run
10:23
forward. So if you do it like this, there will be another
10:28
method called basic dot underscore underscore squall.
10:31
And this one will do some checking, just making sure
10:35
everything looks okay, and then run dot model, model dot
10:38
forward. So in this way, this is usually how we do the forward
10:43
pass looks a little bit weird. But this is like how the forward
10:46
pass works. Then we compute the loss, set the gradients to zero
10:52
from the previous epoch. That's something I explained in the
10:54
code in the last video. Then we do the backward pass to compute
11:00
the gradients. And then we update the model parameters. So
11:04
that's, that's the major part in the training loop. And like I
11:08
said, you can always copy and paste this code and just adjust
11:10
it to your new network, you never really have to memorize
11:13
it. Personally, I also, I mean, I've done or looked at this so
11:17
many times, I could probably write this down. But why
11:21
memorizing this, if I can just use existing code and just
11:24
manually adjusted, what's really only important is that you
11:27
understand this, you have to understand what's going on. But
11:31
except that you don't have to memorize code. And I mean, like
11:35
I said, no one does that. All right. Um, yeah, there's just
11:39
some more written stuff of what I explained. So you can also on
11:43
the slides read through this more slowly, it's just some
11:46
annotation. So if you want to take a look at it at home, in a
11:49
quiet moment, you have also my annotation here. Sometimes
11:55
easier to listen. Sometimes it's easier to read than to listen,
11:58
I think. So the way I annotated everything. All right. And this
12:06
is also something I will explain when we talk about logistic
12:10
regression and multi layer perceptrons, why we use
12:12
logits.
12:15
Alright, so the main point here, the remaining point in this
12:18
video, is that there are two types of API in pytorch, there
12:23
is the object oriented API, and the functional API. And we can
12:28
actually use both or a mix of both. So with functional, I
12:32
mean, functional programming, like the concept of functional
12:36
programming versus object oriented programming. So
12:39
functional usually means that we have something without an
12:44
internal state. So the torch and torch dot n n functional API is
12:49
an API without an internal state. So what that means is, if
12:57
you take a look at the left hand side here, this is the perceptron
13:00
that I showed you earlier in this video. So where we define
13:03
the parameters in, in the constructor in the init
13:08
constructor, and then we call these things. Notice that for
13:15
certain parts where we have this F, so I'm importing torch dot n
13:19
n dot function as F just for brevity. So in certain parts, I
13:24
have this F here. So this is all using the functional API. So I
13:32
could have done it differently. I could have defined relu as a
13:37
class. So here, I could define it as a class. However, this
13:42
would be a little bit overkill. Because if you think about it,
13:46
what relu is a relu is just a function. Max, let's say x zero,
13:53
it just returns whatever value is higher, right. So it's like
13:57
this piecewise function, it doesn't have any weight itself,
14:00
or any bias unit or weight parameter or something like that.
14:03
It's just a function. So while that it's kind of overkill to
14:06
implement it as a class, because classes usually create objects,
14:10
and then this object, I mean, it doesn't have any parameters. So
14:14
it's kind of overkill, we can just use a regular Python
14:17
function for that. So this is like the difference between
14:21
using an object oriented and a functional API. And where does
14:24
it matter? So, like I showed you before, on the left hand side
14:28
is again, the implementation I showed you where I created these
14:31
weights here, the layers, the weight layers, and then I'm
14:35
using them in the forward pass. However, there's something that
14:40
is more convenient, it's the so called sequential class here. So
14:45
the sequential class executes things in order. So you can see
14:52
here, my forward method on the right hand side is much shorter
14:56
than on the left hand side. So what's going on here? So here on
15:00
the right hand side, I'm using sequential, it's, it's
15:03
essentially like a Python list. And everything that is inside
15:06
essential gets executed linearly. So one by one, so
15:12
first, it will execute linear, relu, linear, relu, linear, but
15:16
it won't. So how can I say it will define it first. So it will
15:21
define it in the sequential thing. And then we can use it in
15:25
forward. So I really like this, because it's very compact, but
15:30
it's using this object oriented API here. But it's still compact
15:35
because here, we define the parameters. And then we have to
15:41
memorize them in what order we use them. And then here, we call
15:46
them see that. So here, I have linear one, linear two, which I
15:51
have here in the same order. And if you have a deep neural
15:54
networks with, I don't know, 20 layers or something, it's easy
15:58
to make an error and copy and paste some values and accidentally
16:04
copy and paste them out of order and make mistakes with a
16:07
with a sequential one. Here, you define the order, when you
16:12
create the thing. And then let's say I'm assigning it to my
16:15
network. And then here, I'm calling it my network, but I
16:18
don't have to redo all the forward pass, it's automatically
16:22
in the sequential thing. So I like this actually back in the
16:25
day when I learned pytorch the first time and four years ago, I
16:28
was using mostly this API, because I felt like okay, this
16:31
is better because I'm avoiding the object oriented API for
16:36
things that don't have attributes. But then over the
16:38
years, I kind of run to prefer this API. Because here, it's
16:45
harder to make mistakes, it's easier to define everything in
16:48
the right order here, I find. But sometimes, of course, we
16:52
also, yeah, we need to be flexible. Sometimes it makes
16:55
more sense to use the API on the left hand side. For example, if
16:59
we have custom research projects where we want to tinker a little
17:02
bit more with the code, because there's one downside of the
17:08
sequential API. So the sequential here, the sequential
17:12
class, the problem is if you want to get intermediate
17:14
results. So with that, I mean, if you want to know what, let's
17:19
say the size of this one, or there's a buck or something, and
17:22
you want to print the output of this one. So if I go back one
17:25
more slide here, anywhere here, let me use a different color.
17:30
Anyway, here, I can just insert a print out, for example, to
17:37
print the output value of this one, if I'm curious at it, if I
17:40
want to look at it, it's very easy to just insert a print
17:43
statement. On the right hand side, you can't just insert a
17:46
print statement here, it won't work. For that, we have to
17:50
create so called hooks. So we have to compute, for example,
17:55
forward hook or register forward hook. So that means really, we
17:59
are hooking into this API. So you have to kind of first take a
18:02
look at the order. So the indices. So here, after
18:08
implementing this sequential thing, this should actually be
18:14
net dot dot my network. So if I print out my network, you can
18:22
see there are these indices 01234. It's essentially like a
18:25
Python dictionary, almost. And then I can access this. So if I
18:30
want to have, or if I want to see the output after this linear
18:34
unit here, I can access it here, register this forward hook.
18:41
It's a little bit weird. But then, when I call the model, it
18:44
will print the output here. So it will print out the result
18:48
that comes after here, it's instead of inserting, inserting
18:53
this print statement here, I have to register this hook. And
18:58
you can see, this is actually more work to register this hook.
19:02
So sometimes it can be a little bit more cumbersome to use the
19:05
sequential API. In some ways, it might be easier to do it like
19:09
this, where we can just play around with it more. However,
19:12
like I said, if you have a very large network with like 28
19:14
layers, it's also more easy to make a mistake here to somehow
19:19
have some repetition here, or things like that. And if you
19:23
have only this one where you define it in order, and it gets
19:28
executed in the same order you define it, it's hard to make
19:30
mistakes. So you have to decide for yourself what API you
19:33
prefer. I mean, it's really up to you. There's no right or
19:36
wrong, both work the same way. It's just a matter of, yeah, I
19:41
would say matter of taste. And I will probably switch more to the
19:45
sequential API for the code examples I provide to you. But
19:48
you can also for your class project use whatever you like.
19:53
But also, yeah, if the multi layer perceptron stuff is a
19:56
little bit too complicated, we will talk about multi layer
19:58
perceptrons in next week's lecture. So that will be also
20:02
something we'll be revisiting. So you don't have to memorize
20:05
any of that stuff right now, you will see that multiple times
20:08
later in this class again. One last thing about pytorch and
20:14
style and things like that. So I found a very cool GitHub
20:20
repository recently, a couple of months ago, where someone wrote
20:24
down like the best practices for pytorch. And I thought that
20:27
might be also something cool to look at. There was also an
20:30
interesting section about Jupyter notebooks versus Python
20:33
script. And that's exactly what I was also recommending. So the
20:37
person here recommends also, to start with a Jupyter notebook to
20:42
do some exploration and stuff like that. Maybe do some coding
20:45
basic coding, and then later on move everything to Python
20:48
scripts and deploy it on a server. It's like, yeah, because
20:52
there are some advantages of using Jupyter notebooks. But
20:55
there are also some advantages of using Python scripts.
20:58
Personally, for teaching, I really like Jupyter notebooks
21:01
because like you've seen before, I can insert figures and show
21:05
intermediate results and things like that, which is really cool.
21:08
But it's a little bit more inconvenient to run Jupyter
21:12
notebooks on a server. So here also, like the person mentioned,
21:17
the files can become huge, if we have one single Jupyter notebook
21:21
and because especially if you print the output in the notebook,
21:24
they will become very long. And yeah, sometimes, sometimes
21:30
computation get interrupted in Jupyter notebooks for some
21:32
reason. So in that way, it's also not ideal for long training.
21:35
And yeah, it's it's easier to make mistakes in Jupyter
21:40
notebook because the I find the debuggers are not that good. I
21:45
mean, they list here debugging as a pro as a pro argument.
21:50
Personally, I find debugging and Python scripts honestly easier
21:54
because you have more helper functions or utilities and, for
21:57
example, py charm or Visual Studio code. I most of the time
22:01
use Visual Studio code, but also many people use py py charm,
22:05
which is also very nice. So Python scripts have the
22:08
advantage of that they are more robust when you want to run
22:12
longer computations. And it's also easier to track changes if
22:16
you use GitHub and want to look at changes, although there are
22:19
some plugins for Jupyter notebooks. But to be honest,
22:22
it's still simpler with Python scripts. I find debugging easier
22:27
with Python scripts. However, yeah, also, like they say, it
22:30
means rerunning the whole script. But an advantage of
22:33
Jupyter notebooks is that you can run one computation or one
22:37
cell at a time. But either or I mean, there are pros and cons on
22:41
both sides. As a deep learning practitioner, I think you
22:46
probably want to use a mix of both, maybe for simple things
22:49
and analyses, using Jupyter notebooks. And then later on, if
22:52
you have more sophisticated projects using Python scripts.
22:56
In this class, I will also use a mix of both. I think for
22:59
teaching Jupyter notebook is really nice. But for the some
23:03
codes that I will provide later, I think Python scripts make more
23:06
sense. All right, last thing also from this GitHub
23:11
repository. So yeah, also some recommendations regarding the
23:16
naming convention. So usually we use lower case conventions with
23:23
these underscores for package modules, const as of not
23:27
constants for instances of objects, methods and functions
23:32
and variables. And for constants, we use capitals with
23:37
underscores is just a common convention. That is also what
23:39
I'm going to use for the code in this class. It's like a common
23:44
convention. Okay, but yeah, you can read through this read me
23:47
sometime also later during this course, it's not like super
23:50
important. But if you read through this rather earlier than
23:54
later, then yeah, you don't learn that say bad habits that
23:57
you have to unlearn later. So it doesn't hurt to read this. Yeah,
24:02
and more pytorch features will also be introduced step by step
24:05
later in this course, when we start working with more
24:07
complex, complex networks. Because yeah, I don't want to
24:11
bombard you with too many things right now, because you haven't
24:14
really seen the more complex networks like convolution
24:17
networks. So there will be many things we will introduce one by
24:21
one when we need them. So this was more like the big picture, I
24:24
hope that made sense to you. And if not, we will see this
24:28
multiple times again in class. So we will be using this general
24:32
pytorch layout for almost everything. Alright, so with
24:37
that, yeah, that was the week here, or the first part of the
24:40
week, talking about pytorch, it was a little bit long, I think
24:43
the Thursday lecture will be a little bit shorter, I just want
24:45
to show you how to use some free computer on GPU resources. And
24:50
that is because it will probably be shorter, also a good time
24:53
then to catch up with other things in class. Alright, so see
24:59
you on Thursday then.

##v48:

0:00
Yeah, hi, everyone. So in this video, I want to show you some
0:03
computational resources that you might find helpful for your
0:07
later homeworks, but also for your class project, where you
0:10
can use a GPU for free to accelerate the training of
0:13
certain new networks. So with that, let me minimize this
0:17
screen and then show you hands on how we would do that.
0:22
Yeah, to start with, I found this very nice GitHub
0:25
repository called deep learning in the cloud, I will share the
0:29
link with you. And here, the contributors and maintainers put
0:33
together a really nice list of all the different tools that are
0:36
available for training deep networks in the cloud. So most
0:41
of them also, yeah, supported GPUs, because that's the whole
0:44
point. So it's like for cloud GPUs. And yeah, not all of them
0:48
are free. But here, the most popular ones, as far as I know,
0:52
most people, when they use free cloud GPUs, they use either
0:56
Google Collaboratory, or Kaggle kernels, both of them are free.
1:01
There are some limits, though, in terms of the runtime, I
1:03
think you can only use one GPU, and it resets after 12 hours.
1:08
But it's still nice to have an option here to use free services,
1:11
especially as a student. We have the CHTC on campus, which is a
1:16
high performing computer cluster. However, this would
1:19
require, I think more like more experience from your side, like,
1:23
it would be more something for later research projects, if you
1:26
don't have experience with Linux yet, it might be a very steep
1:29
learning curve, in addition to everything we use in the class,
1:34
here in our lecture class. So in that way, I think to get going,
1:38
if you're new to everything, these are definitely more
1:41
beginner friendly. Alright, so he has a lot of options, some of
1:47
them have a fixed number of free hours, or they give you a
1:51
startup credit, for example, free $300 of credit for these
1:55
types of things. And at the bottom, I also wanted to mention
2:01
there is I think, yeah, there's more stuff. So also, especially
2:05
for students, there are some extra special offers, which are
2:09
also super nice. So for simplicity, I will walk you
2:13
through Google Collab, how we can use Google Collab for a
2:18
project. So let me click on this. And then it should open up a
2:23
new notebook here. So notice that this is a notebook
2:27
environment. It's Yeah, it's a blessing and occurs notebook
2:30
environments are easy to use. And what's nice is you can also
2:33
see the results in there. But as code becomes more complicated,
2:37
sometimes a cloud environment would be also nice where you
2:40
have Python scripts. But yeah, you can explore the list and see
2:44
what's best suited for you. Ultimately, it's really up to
2:48
you what you want to use for your class project. So there's
2:50
no requirement using one environment over the other, it's
2:54
really up to you. Because this is a relatively beginner
2:58
friendly, let me cover this one here. So one important thing if
3:02
you want to use this is to actually select a GPU to make it
3:06
available. For that you have to go to runtime, and then change
3:10
runtime type, and then choose GPU, you can also use TPUs. But I
3:15
recommend for this class to use GPUs. Alright, so and then we
3:21
can check if pytorch is available. So let me type import
3:26
torch, and then torch dot version just to see. I don't
3:35
know why it's so slow. It's loading 1.7, which is a recent
3:39
one, which is nice. And also, I think this is like a Google
3:43
specific thing, because usually that is something that doesn't
3:46
show up when you import torch on your normal computer. I think
3:49
this just means that it has CUDA 10.1 support. Also, just to make
3:53
sure that it indeed recognizes the GPU. Sorry, CUDA is
4:00
available. Just to make sure it shows true. For example, we just
4:06
try this if the GPU is not available, it should return or
4:10
did I say this, it should return faults. Yep. So if you see
4:23
faults, make sure you have GPU checked here. Alright. Now, what
4:33
we can do is we can open notebooks. So we can, for
4:36
example, add a new notebook. So it's a new window here. Okay.
4:42
There might be also Yeah, that's what I wanted to know. Open a
4:45
notebook. So you can actually open notebooks directly from
4:47
GitHub. So for example, you could technically go to our
4:50
class repository here. And then let's choose what we covered
4:55
last on Tuesday. So add a line with autograd and pytorch. Let's
5:01
use that one. So I'm opening that here, and I'm copying it.
5:07
And then I can directly have the link here. So which is very nice.
5:11
So I can need to search it first. Yeah, I can directly open
5:15
it. Okay, I think I just can click on it. No, stay on page.
5:23
This was not the right one. Okay. Yeah, let me try this
5:27
again. Think I need to click this one. Open notebook a new
5:33
tab. Okay. Sounds good. So yeah, here we have now our code so I
5:39
can choose the runtime, the GPU. And then we can actually run it
5:45
right. So let's do it. Watermark this didn't work. Oh, okay. So
5:52
this is a warning message because it's a notebook not from
5:55
Google. Just like wanting let's say run anyway. Okay, so we get
6:00
an error. What is the error module watermark has not been
6:03
found. So this is because Google Collab comes with some packages
6:08
pre installed. But of course, it doesn't have every possible
6:12
Python Python package pre installed. So some packages we
6:15
have to install ourselves. It's actually not too complicated. We
6:17
can just use this exclamation mark, which is a terminal
6:22
command for executing a bash terminal command. So we can run
6:26
for example, pip install, so pip install watermark, and then it
6:31
should install it. Yep. So it's loading it and then successfully
6:37
installed. And then this should work. Right, this works. So this
6:44
is just a general way of how you can install packages. Then if
6:48
you have packages that are not already installed in Google
6:51
Collab, okay, moving on, loading torch, pytorch, now loading our
6:57
data set. Oops, another problem. So yeah, the thing is we loaded
7:02
the notebook, but we didn't not lot the data, right. So if I go
7:05
back here to the repository, there's this data sets, sub
7:10
folder with an iris data set, which this notebook doesn't know
7:14
about because the link is this one here. So how, how can it
7:17
know where to load the data from? I mean, one way would be
7:20
for CSV files to just copy the link here, this should work, I
7:30
guess, it's loading because pandas can log directly from CSV
7:34
file. So this worked. So I can just show you that X train
7:38
should be loaded. But usually in practice, consider a case where
7:43
you have a data set that is not on GitHub that is maybe on your
7:47
computer. And it's also not a CSV file. So you want to have a
7:50
more general solution. So how can you do that? For that, you
7:53
have to mount your Google Drive folder. So this is a little bit
7:59
complicated, I will I have already actually put together
8:02
some slides that I will share with you after recording this
8:05
video. So assume we have this data set locally, let's download
8:11
this here. So I'm downloading it right now. So then I'm opening
8:16
it here. And then let me go to my Google Drive. So I have a
8:23
Google Drive folder here, my drive, and then I have a sub
8:27
folder colab notebooks, this should be originally or
8:31
automatically generated. Actually, let me save this
8:34
notebook. So it says cannot shave same changes. And this is
8:40
because Yeah, we, we don't have permission for saving it yet. So
8:47
we have to make a copy. So it means basically doesn't. It's
8:52
loaded directly from GitHub, it doesn't allow us to overwrite
8:56
the GitHub repository, which makes sense. So let's make a
8:58
copy of this in our Google Drive. It's completed. Okay, new
9:03
tab. So this is our copy of Adeline. If I load this
9:07
directory now, or if I refresh this Google collapse, you will
9:10
see here, this is now in my colab notebooks folder. So you
9:15
can also directly go here, if you have code on your computer
9:20
and just drag and drop it here. And then you can go right click
9:26
open with Google Collaboratory. That is also a way to do that.
9:31
Now, assume I have my data set that I want to connect with my
9:36
notebook. So I let's say I have a data set here on my hard drive
9:41
or whole data set folder, I can just take that and also drag and
9:45
drop that here. So it's now data set data sets. So it's the same
9:52
structure as shown here. So it's next to my notebook. So let's
9:59
see if we can load it now. Too many sessions. Okay, let me
10:07
close this one. And this one. Okay, there's still too many
10:16
sessions. Okay, let me terminate this one. And this one. And
10:23
maybe also this one. All right. Let's try again. Okay, now it
10:29
works. Okay. So technically, we might think, okay, we can load
10:39
the data now, because it is relative to our notebook in this
10:42
data sets up folder. So it's located here, right? However, in
10:47
practice, there's still a file not found error. And this is
10:50
because, yeah, that's like a little quirk, we have to mount
10:54
our Google Drive to or into this notebook. So how we do that, if
11:00
I recall, it's from Google, dot, call up, import, mount, and
11:09
then, sorry, I think it's sorry, from Google, important drive,
11:16
and then drive, mount. And then, let me just look this up,
11:22
because I've actually made that in my slides, just to make sure
11:29
I type the right thing here. Okay, mount content and drive.
11:35
Interesting. Okay, so from Google, colab, import drive, and
11:42
then mount content, I will share the slides with you after this
11:48
video. So we can do this. Then it asks us to enter an
11:53
authorization code, which we can do by following this link. Let
11:57
me just confirm this. Yep. And I can copy this, enter it here.
12:05
All right, this my authorization code now it should be mounted.
12:13
Take some time. Okay. So now it should work. So let me load the
12:18
data. Still a file not found. Okay, so the reason is, we have
12:23
no mounted this drive, but it is, it requires a little bit
12:27
more information about that. Because the notebook, you can
12:30
think of it, it sits in some arbitrary place on a Google
12:33
server. And this data set sits on my Google Drive. So you have
12:36
to be a bit more specific and provide a concrete address. So
12:39
it would be, let's see, content, drive, my drive, and then call
12:48
up notebooks. So this is essentially, if you follow here,
12:55
my drive, Google, call up notebooks, and then data sets.
12:59
So this is what we have here now. So this should now work. So
13:05
yeah, this finally worked. Um, it seems a little bit
13:10
complicated, but technically, it's not that complicated. I
13:12
showed you a lot of things that don't work to motivate or to do
13:16
it here step by step. But technically, you can also just
13:18
leave these lines in your notebook, and then it should
13:20
work. So you only have to do it once if you and then for the
13:24
next project, you can copy and paste it. But there's also one
13:29
little addition I want to make. And that is there are two
13:33
computers involved here right now, or at least two servers,
13:37
one is Google Drive, where your data set is sitting. And one is
13:41
this notebook that is running on a different computer instance
13:45
at Google. And the communication between those computers can be
13:48
a little bit slow, slow, because it goes over the internet. So to
13:52
speed things up, when we work with more complicated data sets,
13:55
it's actually better to copy this data to the same computer
14:00
that is running this notebook. So for example, what you could
14:04
do is you can do on a copy. So you can say,
14:11
be tree. So you can copy.
14:19
Yeah, that's what I want. You can copy these data sets here
14:22
to a local folder for data sets. So you copied it, and then you
14:29
can again use the original link. And if you have large data sets,
14:36
the training will be faster when we use pytorch data loaders if
14:40
the data set is located locally like that. So yeah, I just
14:43
copied it from Google Drive to this local directory called
14:47
data sets. So this is what I would recommend. And even for
14:51
other than that, I would actually recommend if you have
14:53
more complicated data sets to make a zip file. So here, for
14:57
example, in my case, I could just go, go here, compress data
15:01
sets. I have this data sets dot zip file. And then I go to this
15:06
folder here, and drag and drop it here. So it's not data sets
15:11
dot zip. And then I go here. And instead of copy tree, because
15:18
it's a single file, I will just copy data sets dot zip. So I'm
15:28
just copying it here. And then I can unzip it and zip data sets
15:35
dot zip. Oops, I need the exclamation mark, because this is
15:42
not a Python command. This is a bash terminal command. And it
15:47
asks me to overwrite this because I already have a data set
15:51
like this in my drive. So yeah, this should work now. Okay. So
15:59
this should then also work. In that way, this is my recommended
16:04
way, using the zip file, and then unzip it on on this
16:08
machine. Of course, for something simple like Iris, it's
16:11
overkill. But later, we will see we will be working with data
16:14
loaders. And for example, large image data sets like MNIST,
16:18
where you have 50,000 images, and it's just faster to upload,
16:23
or copy a single file and then unpack it compared to uploading
16:27
50,000 files like small little files. So in this way, it's like
16:32
my recommended approach, if you use Google Collab. Alright, so
16:35
this is yeah, then how you use the GPU. Actually, we haven't
16:40
used the GPU in this notebook here yet. Just to quickly
16:44
continue. So if you wanted to use the GPU, you have to do one
16:48
additional step, you have to touch device, use the GPU,
16:55
actually. So there's only one GPU in this computer. So we use
16:59
the index zero, which stands for the first GPU, this one would be
17:02
the second GPU, third GPU, fourth GPU, and so forth. He has
17:05
only one GPU. So we can just transfer it to the one GPU. Oh,
17:15
okay. So one issue is this is our manual implementation. So
17:20
this, of course, doesn't support the GPU, because it's not using
17:23
the model class. So let me yeah, doing this very spontaneously
17:29
here, let me run this regularly. And then go to the automatic
17:35
one. So auto line automatically, this is the one using module. So
17:40
if you do that, then this one will technically support the
17:45
GPU. So we do this one. And then it should run on the GPU. We
17:50
have to make one more modification for the training
17:52
data set, I assume. We'll see if that runs. All right. So yeah,
18:00
see, it says some argument is on the CPU, while it's expected to
18:04
be on the GPU. So that is because we also have the same to
18:08
do the same thing for the data set. So let me see. I assume we
18:15
can simply
18:20
do the same thing.
18:23
For this one, and this one.
18:27
Let me get a typo here. Oh, yeah, one.
18:38
Yeah, so now it works. So I also transferred the data to the GPU.
18:41
If you have the model on the GPU, it also expects the data to
18:45
be on the GPU. So in the later code examples, I will have a
18:49
flag to do this more automatically, where you only
18:51
have at the top of the script, where you only have to specify
18:54
it once. And then it will automatically update it
18:58
everywhere where you want to use the correct device. Alright, so
19:04
yeah, that is just a quick tutorial how to use the GPU. I
19:08
have also these slides here for the Google Collab, and I will
19:11
also upload them. So I hope that was useful. And let me know if
19:15
you have any questions.

##v49:

0:02
Yeah, hi, everyone. I hope you had a nice week. I just noticed
0:05
we already completed week four, which means Yeah, one fourth of
0:08
the semester is already over. Time is running so fast. I hope
0:12
you like the content on pytorch and the cloud computing
0:15
resources from last week. So in today's stuff in the news
0:18
section, I just wanted to give you a brief update again on
0:22
what's happening in the deep learning world. Also,
0:24
coincidentally, there were some interesting tools around pytorch.
0:27
And also some interesting news regarding cloud computing, and
0:31
its implications on the environment. And also, yeah,
0:35
maybe some not so nice applications of API of deep
0:39
learning regarding ethical AI and these types of things. So
0:43
yeah, there's a variety of news again this week. And yeah, let's
0:46
dive in and talk about it. Yeah, let's start with a fun library I
Free Wire
0:54
saw this week called free wire, freely wired neural networks. So
0:59
this is a pytorch extension library for creating optimized
1:02
freely wired neural networks to run on CUDA, the GPU essentially.
1:07
So you have seen already in the lecture, how a multi layer
1:11
perceptrons work fully connected layers. So where each unit in
1:15
one layer is connected to every unit in the following layer. And
1:20
we will discuss that also in more detail next week in the
1:22
course. But yeah, here, what's different is that we can
1:26
arbitrarily connect these nodes. For example, consider in this
1:32
drawing on the left hand side, consider this case of this unit.
1:36
Let's say this is the input layer. This is the first hidden
1:41
layer. And then we have the second hidden layer. So we have
1:47
this unit here, for example, that is only connected to one
1:50
other unit. In a typical fully connected context, what we would
1:54
see is we would see also a connection to this one year. But
1:57
here, here, it's more arbitrarily connected. Or you
2:00
can also see this input here is connected to this unit. And this
2:04
unit, as you would expect in a fully connected layer, but then
2:07
there's also a connection to a consequent layer. We will see
2:11
later, some flavors of that also in the context of convolution
2:14
networks and residual connections. It's also something
2:17
that is popular in transformers. But here, it's really more
2:20
arbitrary than in other architectures. So it's just a
2:24
tool for allowing you to create these types of architectures. I
2:28
thought it was like a cool thing. If you want to run some
2:30
crazy experiments, that's might might be something. Yeah,
2:33
interesting to look at. So where would this be useful? So for
2:38
example, one thing that came to mind is this paper exploring
2:42
randomly wired neural networks for image recognition. So that
2:46
is a paper I saw like two years ago, approximately. And here,
2:50
the researchers proposed a method for, you know, randomly
2:53
connecting neural networks on getting these random
2:57
connections, I think also involving convolution errors. So
3:00
in this way, and they used when I recall correctly, they used
3:05
evolutionary algorithms or genetic algorithms to learn
3:08
these by optimizing fitness function. And they found that
3:13
this architecture, this randomly wired one performs better, for
3:17
example, than existing one based on resonant. So resonant is
3:22
also something we will talk about in this course, the
3:24
resonant architecture achieved 77.1% accuracy on this data
3:30
set. It's image net. And this randomly wired one achieved a
3:36
higher accuracy, even though it seems arbitrary. So when I read
3:39
that paper, like two years ago, I thought really, that's maybe
3:42
the time when these hand designed convolution networks are
3:46
going out of fashion where people start using these
3:48
automatically wired ones. However, I must say, personally,
3:51
I haven't seen any randomly wired network since Yeah, since
3:56
I read this paper, actually. So maybe this is because it's hard
3:59
to implement. Also, it's also, I would say computationally more
4:02
intensive. And maybe there's also less logic behind. So for
4:07
regular CNN architecture, you can maybe make some arguments
4:10
why it's supposed to perform better with a randomly wired
4:13
one, it's maybe a little bit more like a black box, and
4:16
people don't like that. But yeah, again, with this tool, I
4:19
showed you in the previous slide, there might be an
4:21
opportunity to explore this further, because now it's maybe
4:24
easier to implement such randomly wired networks. Yeah,
Computer Vision
4:31
also, this week, we got a new computer vision data set. So in
4:35
this new data set, the researchers compiled 1.5
4:39
million images from 565 classes. So what's novel or interesting
4:45
about this data set is that it is focused on object categories
4:48
that are important to humans, at least that's what the
4:51
researchers aimed for. Yeah, so this paper will be actually
4:55
published in three days. So it's today the 20th. And the paper is
5:00
already available on the website of a PNAS. If you want to take a
5:04
closer look at it. And also the researchers provide code
5:08
examples regarding pre pre trained convolutional networks
5:13
trained on this data set. And also how you can load this data
5:16
set. There are some other interesting aspects from this
5:19
data set, how the data set looks like the statistics, the basic
5:23
statistics, but then also how they collected this data set. So
5:27
I wanted to just briefly also walk through this because I
5:29
thought that was interesting. So here's an example of some of the
5:33
565 classes, man, house, car, woman, phone, bed, so things that
5:39
are relevant to humans. And so here, they also looked at these
5:44
categories on for example, 60% of things or labels are
5:49
artificial, 40% natural. So for example, a car would be
5:53
artificial and a tree would be natural, and so forth. So they
5:57
have some interesting analysis here. Also, regarding the number
6:02
of images, note that the number of images is different for each
6:06
class. So it's not a balanced data set, it's imbalanced, which
6:12
makes certain things like the evaluation a bit more
6:14
challenging. So instead of, for example, using the regular
6:17
accuracy, something like the class balanced or balanced
6:20
accuracy might be something more worthwhile or not worthwhile,
6:24
but more reasonable to use here. So some students who took the
6:28
451 class last semester, we talked about the balanced
6:32
accuracy, that would be maybe one measure that would be also
6:35
appropriate here. So and also notice that these images have
6:39
different aspect ratios and resolutions, which is also shown
6:42
here. So if you work with this data set, you also have to make
6:45
sure of course, that you find a common denominator for the input
6:49
sizes, if you work with certain architectures, which are
6:53
restricted to certain input sizes. But that being said,
6:57
let's skip to the more interesting part, how they
7:00
collect the data set. So what they did is they try to kind of
7:05
filter for labels that occur frequently in large text
7:11
corpuses. So it's like a proxy for saying how important class
7:17
or word is unknown. And they also had this concreteness
7:21
rating. So this was something quite interesting. So here they
7:25
employed data from human observers. So how that works is
7:31
that they asked people to rate on a scale from one to five, how
7:35
concrete a certain noun is. So in terms of how easily can you
7:41
visualize the concept. So as an example, for example, consider
7:46
on one end, strawberry. If I tell you the word strawberry, I
7:53
think you can easily visualize this. So it would have a very
7:55
high concreteness. But when I mentioned a noun like hope, for
8:01
example, which is a little bit less concrete. So here, it's
8:04
kind of harder to visualize how hope looks like as a as an
8:07
object. So in this way, it would have a very low concreteness
8:10
rating. So by using these types of ratings, they also filtered
8:14
for very concrete, very concrete things like items. And from that
8:21
they extracted then the top 3500 words based on frequency and
8:26
correctness, they had a certain index for calculating calculating
8:30
that. Um, yeah, and then they had each now describing basic
8:34
level category and excluding subordinate category. So making
8:38
sure it's not too hierarchical, like picking the common
8:42
denominator categories, and also merging synonyms, for example,
8:48
automobile and car into one word. And after they basically
8:54
extracted these class labels, they were interested in what
8:58
they then did is they downloaded corresponding images from image
9:02
net flicker and Bing. Then they also performed duplicate removal
9:07
to make sure there are no duplicates. So here they used
9:10
principal component analysis. So they decomposed the images with
9:14
principal component analysis. And then when I remember
9:17
correctly, what they did is, yeah, they looked at the factor
9:20
loadings of the PCA, and then looked at the correlation
9:24
between these factor loadings. So I believe they did that in a
9:27
pairwise fashion to filter out then duplicates. Also, what they
9:33
did is here, they manually excluded misclassifications from
9:37
from all categories. Here, they don't say anything specific.
9:40
Here, they say something with a 4% error rate. And in the
9:44
paper, they say basically that they sampled 100 images
9:48
randomly from each class. And then they, as a human looked at
9:52
how many of these images are incorrectly labeled. So if you
9:56
look at them, and you see, okay, this label label doesn't make
9:58
sense. If the rate was more than 4%, like for more than four
10:03
images out of the 100, then they looked at all the images from
10:07
this category and cleaned that out. And otherwise, I think
10:12
I think they left it as is. So you can see or can think of it
10:15
as in the worst case scenario, you can only have a classifier
10:20
that is as good as 96% accuracy, considering there are up to 4%
10:26
mislabeled images in this data set, but it's still a reasonable
10:29
good. And then they merge these images from the different
10:33
databases, removed the duplicates again. So now
10:37
checking for duplicates from image net versus the flicker and
10:41
Bing images. Then they pruned the data set removing the
10:47
images or some of the images so that these labels or sorry, that
10:52
the examples are approximately between 705,000 per class. And
10:58
then they obtained this final data set. So 94% of the images
11:02
are actually from image net, which is a big number. 5% are
11:05
only from Bing and 1% is only from flicker. I actually don't
11:09
recall exactly how image net images were collected. I think
11:12
they were collected from Google. But there might be also just
11:16
some overlap between image net and Bing. And that's why there's
11:18
such a high number of image net images compared to the other
11:21
images. But yeah, exactly why there's such a high image net
11:25
percentage, I don't know. But yeah, so it's an interesting
11:27
data set. It's yeah, just another cool data set that can
11:31
be used for testing your models. Yeah, moving from large scale
11:40
image data sets to large scale models. So there's also a common
11:45
or popular discussion nowadays, that these AI or deep learning
11:48
models become more and more expensive to train. So here was
11:53
an article called the billion dollar AI problem that just
11:56
keeps scaling. Yeah, luckily, we haven't reached the point where
12:00
we have model training costs $1 billion. But it can easily end
12:04
up costing multiple million dollars even nowadays when you
12:07
consider these big models. So for example, here's a chart
12:11
from the Megatron model from Nvidia. So here, what they did
12:16
is they trained on or they had a system called Celine. And this
12:21
consisted of 280 dg x a 100 systems, where each of these
12:26
systems, if you would buy them would cost $200,000. And then if
12:29
you consider, let's say 15%, on top of it for networking costs,
12:33
like connecting everything, and then also 20% for storing this,
12:38
yeah, this would be easily or if you would consider the list
12:41
price, it would easily end up being like $75 million just to
12:45
buy the system. And also in this article, they did a calculation,
12:49
like how expensive would it be to run this model, if you would
12:53
rent the hardware on AWS, so the Amazon server or service would
12:59
also easily be like around 80 million, if you just rent this
13:02
computational resource for three years. So in this way, I'm also
13:06
I should say electricity is not included, it's becoming more and
13:09
more expensive to train models. So for this model, they really
13:11
use like this huge system, where they had around 3000 GPUs. So
13:18
3000 GPUs and the model had around 200 billion parameters.
13:23
So things become more and more expensive, which can be a
13:25
problem. So also regarding your parallelization, there are two
13:29
techniques. So also, it's kind of computation and interesting
13:33
problem. One is a data parallelism where you split up
13:37
the batch. So you make the batch larger and larger and larger,
13:41
and then you split it up onto multiple GPUs where each GPU
13:45
receives a fraction of that original mini batch. And then
13:49
each of the GPUs computes the gradient and then you combine
13:53
the gradients by averaging over these gradients to update the
13:56
models. But there is also a limit for you're doing that as
14:00
like limiting, diminishing returns, as you would say, if
14:04
you have higher and higher data parallelism. So also, newer
14:08
methods, consider tensor parallelism, where you can
14:11
efficiently compute, let's say, matrix multiplications across
14:16
different GPUs. That can also be a little bit tricky, though,
14:20
because you have to consider the connection between the GPUs, you
14:23
have to make sure they are connected with fast connections
14:27
like infinity band and these types of things. So it's
14:30
actually not a trivial problem. So if you have more GPUs, it's
14:34
not necessarily saying that it's easy to parallelize. So it's
14:39
just an interesting research problem. But yeah, one problem
14:41
with that is really environmental friendliness
14:44
also.
Federated Learning
14:47
Yes, speaking of environmental friendliness, a recent study
14:51
showed that federated learning can lead to reduced carbon
14:55
emissions. So what is federated learning, federated learning
14:58
means essentially computing things on multiple devices, and
15:03
then gathering the results from these devices. For example,
15:06
these could be cell phones or different data centers. So, for
15:10
example, you can think of if you I'm not sure if you remember
15:13
this, when I was a kid, there was something called folding at
15:17
home for PlayStation, and people could sign up for the service.
15:22
And then if you had idle, idle cycles on your PlayStation,
15:26
these were used by, let's say some research center to help
15:31
with protein folding. Or another example would be our HTC condor
15:35
on campus, where we have where we can use different computers
15:39
like desktops in different offices if they are idle, which
15:42
is actually pretty cool. And they found if you do that, it
15:45
can lead to lower, let's say carbon emissions. And yeah,
15:49
likely, this is due because of the heating because if you have
15:54
computers in different locations, and they only used a
15:56
little bit, you may not need any extra heating, sorry, cooling
16:00
for preventing the heat, exposure or overheating of the
16:04
device, compared to let's say, a big data center where you have
16:07
to pump in constantly like lots of energy to keep it cool. And
16:13
yeah, also just the numbers were just impressive. I mean, these
16:15
data centers nowadays, they use 200 terawatt hours per year,
16:19
compared to our average US home, which only uses on 10,000
16:22
kilowatts per hour. And I just looked up what a terawatt is a
16:26
terawatt is actually, I wasn't actually sure I was not sure if
16:28
it's 1 million, it's actually 1 billion kilowatts. It's like a
16:32
huge amount of energy they use. So if this federated learning
16:35
can help, why not? However, the researchers also noted that it
16:38
there's like a little caveat. So it's actually not quite clear
16:42
because federated learning can also be less efficient. For
16:46
example, if you consider prolonged training times, due to
16:49
distributed databases, so if you want to train a model using
16:53
multiple devices, but you have your database sitting in a
16:55
location that has to be accessed, well, that will
16:58
properly make training longer. So you have, you have to keep
17:03
your device running for longer time. But then also, you will
17:07
have eventually then some more data data transfer via Wi Fi,
17:10
which also takes energy. And then also, you have to consider
17:14
that these devices may be less efficient, like using the same
17:18
energy, but being less efficient. One example would be,
17:20
for example, the new arm, what is it an M1 chip, the arm chips
17:24
in the Mac box, they are they have the same speed as the top
17:29
and Intel CPUs. However, they are more efficient. So in that
17:33
way, you have to also consider certain devices are not as
17:36
efficient. So if you use federated learning, this could
17:38
also be maybe, um, yeah, less efficient. But I think it's
17:42
still interesting that people started looking at that, because
17:44
yeah, I think we also have to be aware of the environment and be
17:48
resourceful when we do deep learning. And you're related to
17:53
that. I also saw there's another new startup, I think it's
17:57
pronounced new reality, but I'm not exactly sure. So also one
18:00
trend is really that people work on making chips for deep
18:04
learning more efficient. So this would be yet another company
18:07
that focuses on deep learning chips, or instead of GPUs, like
18:12
having specialized chips for deep learning. And this article,
18:15
they said, basically, the chip can perform inference with 15
18:19
times higher performance per dollar than the competition. Now
18:23
that they don't say that the chip is faster than GPUs, really
18:27
here, the focus is on the performance per dollar. But it's
18:31
not a bad thing. I mean, maybe this chip overall is slower, but
18:34
you can see 15 times higher performance per dollar. So per
18:38
dollar, it's not clear whether this means like manufacturing
18:41
cost or also usage cost in terms of electricity, but I bet it's a
18:45
mix of both. So it's probably a chip that is smaller, less
18:49
powerful than a GPU, for example, but probably more
18:52
energy efficient, but we'll see. Yeah, so here I have some news,
AI for Job Applications
18:58
which is I think, yeah, not such a good use of AI or deep
19:01
learning. I find this always questionable, like these types
19:05
of applications, but I think it's still important to talk
19:07
about it. So here, this is about a system trained to rate your
19:12
applicants during job interviews. I think also, when
19:16
people develop these systems, so the aim is really to make things
19:20
more objective. Like if you think of it as a human, you have
19:23
probably some biases towards certain candidates. And if you
19:26
have an AI system, you may be hoping that this is less, let's
19:30
say, it's more objective, less subjective, and probably also
19:33
scales better. So you can have more applicants. But yeah, so I
19:37
think, I'm not sure. But I think these are all developed in good
19:40
faith, but they can also be very problematic. So here was a
19:44
questionable use of AI for job applications. I also recommend
19:48
you to read this full article. It was a very interesting
19:51
analysis. It's a short article, but very, very well written. So
19:55
um, yeah, essentially, here, the researchers developed an AI to
20:00
rate job applicants. So they trained the AI on videos from
20:07
more than 12,000 people from different ages, gender and
20:10
ethnic backgrounds. And an additional 2500 people rated how
20:15
they perceive them in terms of personality dimensions, and so
20:17
forth. And I think it's not quite clear. But I think how
20:21
this works is basically, they had people rating these job
20:24
applicants, and then collected these scores, and then trained
20:29
the AI on these scores. And that way, you can think of it, or
20:32
maybe the model, yeah, just mimics what the humans are
20:36
doing during the rating. So they had like these different
20:38
rating terms, like openness, conscientiousness, extraversion,
20:42
agreeable illness, and neuroticism. And these were like
20:45
the different labels for the personal traits. Yeah, and then
20:49
the researchers employed actors to do mock interviews, and
AI for Mock Interviews
20:53
interviews. So keeping everything constant, like speech
20:57
and content of the text during the interview. And they also
21:00
repeated that multiple times. So make sure that making sure that
21:04
the results are stable. And then they, for example, varied
21:10
different aspects. So here, for example, they are the actress
21:14
was wearing glasses and comparing the results to not
21:17
wearing glasses. And you can see in blue is the original without
21:21
glasses. And then in yellow with glasses, and you can see that
21:26
based on these ratings by the AI, that the scores for
21:29
openness, consciousness, conscientiousness, extraversion,
21:33
agreeable illness were less when the person was wearing glasses.
21:37
So this is also one of the reasons why I'm not wearing
21:39
glasses when I record my lectures. No, I'm just kidding.
21:41
No, I think this is like a little problematic, because I
21:44
think wearing glasses are not shouldn't influence any decision,
21:48
right? So this is maybe something that is not going so
21:51
well here with this AI, and even worse. So when the results were
21:55
even more different, they had a person doing a mock interview
21:59
with and without a bookshelf in the background, where everything
22:02
else was constant. So and you can see that with a bookshelf,
22:07
the scores improved a lot. So this is also a very questionable
22:11
result by the AI. So there shouldn't be such a difference
22:13
whether someone has a bookshelf in the background or not. And
22:16
yeah, this is maybe also reason why I have a bookshelf in my
22:18
background here. I'm just again kidding. But yeah, so this is
22:21
again, it's actually a serious topic. I think this is something
22:24
when you develop such systems, you should make sure that such
22:28
problems don't occur, because I think this is incredibly, yeah,
22:32
unfair, because really, if I mean, it really shouldn't have
22:36
anything to do with your skills as an applicant, whether what
22:40
type of background you have, and things like that. So yeah, this
22:43
is some some very problematic result. And I think in general,
22:47
maybe this is an area where AI shouldn't be employed. Yes. So
Why does this happen
22:51
why does this problem happen? So there was one comment by
22:54
Katharina Zweig, which I think hits the nail on the head. It's
22:58
the fundamental problem with face recognition by machine
23:01
learning is that we never know exactly which pattern in an
23:04
image, these machines are responding to. So yeah, deep
23:08
learning can sometimes or often be more like a black box. So you
23:11
never know, really, which parts of the image, the machine
23:15
learning system is using, right, because you provide the whole
23:17
image with background and everything. So do you really
23:20
know what the machine learning is paying attention to? I don't
23:24
know if that solves the problem. But if you think of zoom, for
23:27
example, where you can easily switch these backgrounds, having
23:31
these videos with data augmentation, swapping
23:33
different backgrounds may help at least with this bookshelf
23:36
situation. But there are, of course, more issues to be
23:38
addressed here. But yeah, this is something if you develop
23:41
systems, you should probably be aware of that and test also
23:45
things like that and make sure that these these things are
23:49
filtered out and not causing problems, especially in a real
23:53
world application. So yeah, I'm related to looking into what
23:58
deep learning does how it behaves. So I also saw another
24:02
interesting tool called cockpit. It's also for pytorch. So it's
24:07
a practical debugging tool for training deep neural networks.
24:11
Think it might be something that could be helpful in the class
24:14
project, for instance. So the authors say when engineers train
24:19
deep learning models, they are very much flying blind. So here,
24:22
they offer a collection of instruments to look into the
24:24
inner workings of machine learning models. I don't know, I
24:29
somehow screwed up the sentence here. So it's really useful for
24:32
troubleshooting during training. And you can find a tool here on
24:36
GitHub, just to show you one example here. So here, they are
Learning Rate Tuning
24:41
focused on the problem of learning rate tuning. So
24:44
usually, when you want to find a good learning rate, you usually
24:47
just try different things and see what works and tune it by
24:52
hand and see you make it larger and smaller and see whether it's
24:55
better or not. And then sometimes you also employ
24:59
learning rate schedulers, which decrease the learning rate over
25:02
time, we will discuss that in a future lecture actually in two
25:04
weeks. But here's an example where the researchers looked at
25:09
the loss curve. So they have mini batch training loss here
25:13
plotted on the y axis. So that's the loss per minute batch over
25:17
the different iterations. And orange and blue, these two lines
25:20
are corresponding to different learning rate settings. Now, if
25:24
they use a look at the loss landscape here in two
25:27
dimensions, again, it's kind of hard to see, but in orange, they
25:32
have one setting the orange one and blue, the other one. So
25:38
here, what they want to illustrate is that the orange
25:40
one is only updating a little bit and then it stops. So the
25:45
learning rate is likely too small. And the blue one has a
25:48
learning rate that is, is too large, you can see it's
25:51
overshooting. So here would be the global minimum global
25:58
minimum. So they are overshooting here. So the blue
26:01
learning rate is too large, and the orange one is too small. And
26:05
they offer some tools, for example, this alpha distribution
26:08
here as a debugging tool. So this is like what they call a
26:12
normalized step length. And zero would be where you would directly
26:17
be stepping into the right direction of the of the minimum,
26:21
the global minimum, or I think this local minimum in that
26:24
context, wasn't actually quite clear. I think the paper, I
26:29
think the tool looks great. The paper wasn't my favorite to read.
26:32
It wasn't very well written. Maybe it was well written. I
26:36
didn't understand it properly. I don't know. And a little bit of
26:38
a hard time understanding certain things there. But what
26:42
you want, what theoretically would expect is stepping into
26:45
this, yeah, into this direction, directly, if you have a
26:49
learning rate that does that, it would be optimal. And with this
26:52
tool, you can see whether you are too small, like in the
26:55
orange case, or too large, and then you want to adjust it more
26:58
to the middle. Surprisingly, though, when they did some
27:01
experiments on different data sets here, they found that the
27:04
ones that resulted in the best generalization performance in
27:08
terms of test accuracy, were slightly above the zero. So
27:12
here, they found on these lines, these lines here correspond
27:17
solid lines on the vertical lines here, they correspond to
27:21
the models that had the best performance. And you can see,
27:24
those are, at least, yeah, I would say zero or larger than
27:28
zero in terms of this normalized step length here, they have the
27:32
mean normalized step length. So, but in any case, this, I think
27:36
might be a useful tool, if you are tuning the learning rate,
27:39
you can just maybe see where you are here compared to the zero
27:43
and then maybe focus on changing it to be somewhere in this
27:47
region here. But this is something I haven't tried
27:50
personally. So this is also something that's new to me, I
27:53
usually, like many other people tune the learning rate by hand,
27:56
but it might be something useful to look at in the future. So
27:59
with that, I think that's all the news I have, I think it's a
28:01
long video. But yeah, with that, let me end this video and I
28:05
will see you back in class next week.

##v50:

0:01
Yeah, hi, everyone. I hope you had a good weekend. And
0:04
everything went smoothly with the homework one submission. I
0:07
noticed that there were still some challenges around the
0:10
understanding of single layer neural networks. So today, we
0:14
will have another chance to take a look at it. So today, I want
0:17
to talk about logistic regression as a single layer
0:21
neural network. And that really helps, I think, with understanding
0:24
the basic concept of a forward and a backward pass. And then we
0:27
will also in this lecture, generalize this concept from
0:30
binary classification to multiclass classification.
0:34
Because yeah, there will be also later on more multiclass stuff
0:37
going on. Because in real world scenarios, we often have data
0:41
sets where we have more than two classes. So in this lecture, we
0:43
will talk about logistic regression as a binary
0:45
classifier, and then multinomial logistic regression, also known
0:49
as softmax regression, which will be a good starter for then
0:54
understanding multi layer perceptrons, which is the topic
0:56
of the next lecture. All right, because there are lots of things
0:59
to talk about, let's get started.
Recap
1:03
Yeah, let's briefly recap what we have done in the previous
1:06
lectures. So one thing we did in the previous lectures was
1:09
implementing the perceptron that's already long time ago, it
1:13
had convergence issues, if data was not all the classes were not
1:17
linearly separable. But we solve that convergence issue by using
1:21
Adeline, which was based on a mean squared error loss function
1:25
and gradient descent. And then last week, we conceptualized
1:29
gradient descent using computation graphs. So if you
1:32
recall, that is how Adeline looked like. And here is a data
1:38
set example that could, for example, not be easily solved
1:41
by a perceptron. I mean, a perceptron would also be able to
1:44
come up with a decision boundary, but it would never
1:46
converge, which is a little bit trickier to handle in practice
1:49
because the decision boundary would jump back and forth if we
1:52
if we train it here, because we have these data points like this
1:57
one, which are outliers. So in this case, on this one, you can
2:00
never get a perfect classification with 100%
2:04
accuracy, if you have a linear decision boundary in this case,
2:08
and a perceptron would have the challenge that it would flip
2:10
back and forth. So now, we kind of continue with the concept of
Improvements
2:17
Adeline, but we make some improvements. So one of these
2:20
improvements is to use a loss function called cross entropy,
2:24
instead of the mean squared error. And another improvement
2:28
is to extend this neuron model to multiclass classification. So
2:33
for that, we will be using multiple output nodes and a so
2:36
called softmax activation function, I briefly sketched it
2:40
here on the left hand, in the left hand corner, we will talk
2:44
about this in more detail later in this lecture. But essentially,
2:48
we will have multiple outputs here. And that will allow us to
2:52
classify data sets that have more than two classes. So here's
2:57
an example of the iris data set, where we have three flower
3:01
classes, Iris versicolor, the Guineca and setosa. Before, we
3:06
could only do binary classification. Now you can see
3:08
that could be three decision boundaries. So one way would
3:11
be here, this way, we have three linear lines or same model, the
3:17
data looks a little bit different. It can also look like
3:20
this here. Those are both so called softmax regression models,
3:25
which we will be talking about today. So yeah, just to give you
Topics
3:30
a big picture overview of all the topics, it looks like a lot
3:33
of nine topics. However, I think they will be relatively short.
3:37
So I hope they will be short, like shorter videos, like 10
3:40
minutes max, but we will see videos always turn out to be
3:43
later, longer in practice than you might think when you make
3:47
them the slides. So the topics I have in mind for today are
3:52
basically discussing logistic regression as an artificial
3:55
neuron. So showing you how logistic regression relates to
3:59
the concept of an align. And then we will introduce the loss
4:05
function of logistic regression, which is the negative log
4:08
likelihood. And then also, I will show you how we can use
4:12
gradient descent, which we talked about before, we will use
4:18
gradient descent to train the logistic regression model. And
4:21
then here, there's just some terminology called the logits
4:25
and cross entropy. These are some terms you will find in deep
4:29
learning. Yeah, and a lot of deep learning concepts,
4:32
actually. So logits and cross entropy are like, I would say,
4:36
jargon in deep learning. So we will just briefly see what these
4:42
terms mean. And yeah, then I will show you a logistic
4:46
regression code example. So all this stuff here, this is about
4:51
the I would say regular, or let's call it binary, binary,
4:59
logistic regression. So that's the original logistic regression.
5:06
For binary classification, only for two classes. And then this
5:09
one here, or the second part would be multi class, or also
5:18
called multinomial. Oops. Yeah, logistic regression. And another
5:30
word for multinomial logistic regression is softmax
5:34
regression. So we will talk about that. And for that, so
5:38
here, first, I will introduce the model. For that, we will
5:42
need something called one hot encoding, which I will then
5:45
introduce, it's just like a format that we can use to
5:48
represent categorical data. And then I will also introduce the
5:52
multi category cross entropy loss, which is an extension from
5:56
the binary cross entropy here. Then we will talk about the soft
6:01
max regression learning rule, essentially gradient descent
6:04
again, no for softmax regression. And then I will
6:09
also show you a code example. And then in the next lecture on
6:12
Thursday, what we will do is we will just add a hidden layer to
6:15
the softmax regression model. And then we have a multi layer
6:18
perceptron or first, on small deep neural network. Alright, so
6:22
with that, let's get started with logistic regression as an
6:25
artificial neuron.

##v51:

0:02
Alright, let's dive into the topic of logistic regression by
0:06
viewing it as a single layer neural network. And yeah, this
0:11
is why I emphasized the identity function in Adeline so much.
0:16
Because if we look at this figure here, this is a single
0:20
layer neural network, where we have the inputs x, the weights
0:25
w, and then we compute the net input here, and the activation
0:31
here. And then an output here where we, for example, could
0:36
apply a threshold function. But for training, we can ignore the
0:41
threshold function for training. We usually use the output from
0:44
the activation. So in Adeline, this activation function was an
0:49
identity function. So this was in Adeline. And in Adeline,
0:54
then we use the mean squared error as a loss function
0:58
between we computed it between the activation and the true
1:01
class labels. So here, a, this is the activation here. And then
1:06
we had some true class labels y and computed the mean squared
1:09
error. Now, the only difference really between Adeline and
1:13
logistic regression is that we have a different activation
1:17
function. So one difference is that we now use this logistic
1:22
sigmoid function instead of the identity function. So in
1:26
Adeline, again, we had just the identity function z. So input z
1:30
output z. Now we have this nonlinear function. So this is a
1:35
nonlinear activation function. I will show you in the next
1:42
slides how it looks like. And another difference between
1:46
logistic regression, and Adeline is that we now have a different
1:50
loss function, I will cover the loss function and logistic
1:53
regression in the next video, though, so that we can keep this
1:57
video a little bit shorter. Alright, so here is how the
2:01
logistic sigmoid function looks like. So that's just from the
2:04
previous slide. So what I showed you on the right hand side is
2:08
this one, I mean, there are two forms, you can write it as
2:11
usually on this one is the more common form in deep learning on
2:15
deep learning contexts, we will be using this activation
2:19
function also in the context of multi layer perceptrons later.
2:23
So how you get from here to here loops from the left hand side to
2:26
the right hand side is just by dividing by dividing by e to the
2:30
power of z. So if you divide this by e to the power of z, you
2:39
get the right hand side because yeah, this would be one, this
2:42
would be one, and this part will be e minus z, right? Because of
2:50
this relationship. Alright, so here's how it looks like. So we
2:54
have the activation here plotted on the y axis, and the net
2:58
input, which is passed to the activation function on the x
3:01
axis. So this is really the input to the activation function
3:04
here. And you can see that it's centered around zero. So it's
3:11
centered around zero. And if the input is zero, then the output
3:16
will be point five. And it saturates here at one, so the
3:24
maximum value is one set approaches one. And here on the
3:29
other hand, it approaches zero. So it's a function between zero
3:33
and one. All right, so but you can see you have to have very
3:39
negative or very positive values. So this is how this
3:43
function looks like. So yeah, I will explain to you how the
3:48
logistic regression loss function works, like in the next
3:51
video, here, I just wanted to summarize a few things. And it
3:54
may be that you have to think a lot a bit about this, because it
3:57
can look a little bit complicated at first glance.
3:59
But essentially, it's not that complicated. So let me just use
4:04
this notation here to summarize the logistic regression model,
4:08
where H, you can think of it as the hypothesis in traditional
4:12
machine learning, or you can more simple terms, think of it
4:15
as the model, this is our logistic regression model, which
4:18
receives as input, the net input. And then you have this
4:25
logistic sigmoid activation function that I showed you in
4:27
the previous slide, which returns a value between zero and
4:32
one. And you can actually think of this whole model here as a
4:35
model that computes the posterior probability, the
4:38
probability of class label y, given a feature vector x. So y
4:44
is the class label. And x is the
4:52
feature. Oops, vector. So you can think of it as this. And now
5:00
let's say we have, um, yeah, we have class label one. So let's,
5:08
let's look at a concrete example. Let's consider the
5:11
iris data set, where we have class label one. As let's say,
5:17
setosa, it's a now for simplified case of a simplified
5:21
scenario, think of it as a binary classification problem,
5:23
we have one as setosa and zero as versicolor, these two
5:30
classes. Now, if I want to compute the probability that a
5:37
given feature vector belongs to setosa, to class one, I can
5:41
write it as this P, y equals, let's say one because it's
5:45
shorter given x, and this is computed as, as this one, and
5:51
the probability of y equals zero is computed as x, which we
5:57
can write as one minus h of x. So these are the feature vectors
6:05
here on these axes. Now, so imagine the probability for
6:13
setosa is point eight, then equivalently, the probability
6:24
for versicolor would be point two. Right? So if this is
6:31
indeed true, so if the flow is indeed versicolor setosa, then
6:36
this would be actually pretty good. So let's say we assume we
6:39
have a true label, let's assume that true label is actually one,
6:49
then it would be actually pretty good to get an accuracy of 80%
6:53
the higher the better, though. So we want to actually have a
6:55
high probability. But if the true label is zero, then a high
7:04
probability would actually be bad. If the true label is zero,
7:09
what we want is actually a high probability for p y. So I can
7:18
I can just maybe use different color. What we want here is we
7:24
want to have a high probability for this case, then if the true
7:27
label is indeed zero, then we want to have a 80%, maybe for
7:32
this case. So that is what I'm summarizing here at the bottom
7:35
of this slide. So if we have a binary classification problem
7:40
with possible class labels, zero and one, what we want is these
7:45
probabilities to be close to one for the respective class. So if
7:50
the class label, the true class label is zero, then we want the
7:54
probability for y equals zero to be close to one. If the true
8:01
label is one, then we want the probability for this scenario to
8:06
be close to one. So in this case, it's, yeah, it's depending
8:12
which probability we want to be maximized depends on the true
8:15
label here. So we will look at that how we can do that with a
8:21
loss function in the next video. But this is like the basic
8:25
setup. So we want a high probability given the other
8:29
certain class. So vice versa, we can also think of it like this.
8:33
If we have a setosa label, we want this one to be large, which
8:41
gives us the scenario for class one. So if we have a setosa case,
8:47
make this one large, make this one small. However, let me erase
8:56
that because we don't have that much space. If we have a true
8:59
label, versicolor, then make this one small and make this one
9:07
large. So this is essentially what we want to achieve. And I
9:11
will show you how we can do that in the next video.

##v52:

0:00
Alright, let's now take a look at how we compute the loss
0:03
function for the logistic regression model, the so called
0:06
negative log likelihood loss. So here, that's just a slide I
0:12
already showed you at the end of the previous video. And I just
0:16
want to recap some of the main aspects here. So there are two
0:19
things going on on this slide. So one is how we compute this
0:23
probability. And here at the bottom is what we want this
0:26
probability to be. So let's take a look at what we want first in
0:31
this case. So we want this probability, the class
0:34
membership probability for class zero to be one to be maximized,
0:41
if the true label is indeed zero. So this is on the left
0:45
hand side, this is the class membership probability, we want
0:48
this to be as high as possible for equal zero, if the true
0:54
label is indeed zero, right. And vice versa, we want the class
1:00
membership probability here for class one to be as high as
1:04
possible. Also, approaching one, if the true label is one, right.
1:10
So given so what we want is we want to maximize the probability
1:16
for the given label for the true label. Now, how is this
1:21
probability computed? That is what is shown here. So here,
1:25
again, this is how we compute these probabilities. So the
1:29
class membership probability for y equals one. So here, this is
1:35
not really the true label you think of you can think of it as
1:40
as this one in this function here. So we compute the class
1:46
membership probability for y equals one. So this one here at
1:51
the bottom, by just the activation. So this is simply
1:55
the activation. So the logistic sigmoid applied to the net input.
2:03
And for the second case, so this one can be computed by one
2:08
minus the activation. So this would be this one here. Okay, so
2:18
this is just like a brief recap. Now we can actually rewrite this
2:23
piecewise function here how we compute this class membership
2:25
probability using this more compact notation. So this
2:30
combines or this essentially summarizes this piecewise
2:35
function in one line, one equation. So how it works is,
2:41
yeah, let's just plug in some numbers. Or first, let's let me
2:44
clarify about what this a here means. So this a is the
2:47
activation, it's just instead of writing h of x, let's just
2:52
abbreviated with a letter a, it's like nicer to look at or
2:56
look simpler. Now let's consider the case where we have the class
3:02
membership probability for class one, given the feature vector x.
3:08
So if y equals one, then this term remains as a, and this one,
3:20
nothing happens here, this one becomes one, right, and one
3:24
minus one is zero. So this cancels or becomes zero
3:30
essentially, and something to the power of zero is one,
3:33
right. So this whole term here becomes one. So this whole
3:38
equation here reduces to just a, right. So a is equal to h of x.
3:46
So this one here, so we satisfy this first term here. So this,
3:51
I'm just showing you right now that this function indeed
3:53
summarizes the piecewise linear function. So now consider the
3:57
case, oops, y equals zero, given the feature vector x. So here,
4:08
now consider, let me erase this a little bit. So we have more
4:10
space. Okay, so we're looking now. This one here, so where y is
4:24
equal to zero, so y is equal to zero, then this is a zero. So
4:28
this whole thing becomes one. And we have this, this becomes
4:36
zero. So this term here becomes one. So what we have then what
4:41
remains is one minus a, right, which is this one. So you can
4:47
now see that this equation here at the bottom summarizes this
4:51
piecewise linear function here. Just a different notation. Now,
4:58
yeah, what we want is we want to maximize the class membership
5:02
probabilities. So and usually in a data set, we not only have one
5:06
single data point, we have n data points. So this is the
5:10
size of training set. And yeah, we want to maximize the class
5:22
membership probabilities for all these examples in the training
5:26
set. So you can think of it as the probabilities here
5:31
multiplied. So the conditional probabilities, and we want to
5:35
find the model parameters because it depends here on our
5:43
model, right. So the probability here, the prediction probability
5:46
here depends on our model parameters. That's how we
5:49
compute these probabilities. So we want to find good parameters
5:53
that maximize the class membership probability for the
5:56
right class. So this concept is also known as maximum likelihood
6:02
estimation. So the we want to maximize the likelihood, the
6:06
probability of observing the data given the model parameters.
6:11
And you probably know this from other statistics classes. So I
6:15
don't want to go into too much detail about maximum likelihood
6:18
estimation here. So just assume now we want to maximize this
6:23
term here. So here, what I'm doing is I'm just rewriting this
6:30
with the simpler notation I showed you before. So if I go
6:34
back to slides, so this notation here at the bottom, that's what
6:42
I'm doing here. So I'm replacing this, right? This is something
6:47
you have seen before on the previous slide, I just showed
6:49
you, I'm replacing this now with this more compact notation here,
6:55
where before I abbreviated as a, I don't know why I expanded
7:00
it here. And I think I just wanted to show you how it's
7:02
computed. Where a is the logistic regression model, where
7:10
this is sigma is the logistic activation function and z is the
7:15
net input. Alright, so you can think of it also as the loss
7:23
function then so as the logistic loss, which we compute as
7:26
follows the probability over the whole training set. And I said,
7:31
we want to maximize this, right, we want to maximize the class
7:34
membership probabilities. In practice, it's actually easier
7:39
to maximize the natural log of this equation, which is also
7:43
called the log likelihood function. So why is that if we
7:47
apply the log here, then we can replace the product by a sum.
7:53
And also here, this multiplication, we can replace it
7:57
with a sum. And numerically on a computer, this is just more
8:01
stable to implement, it's more, more stable when we use, for
8:05
example, gradient descent. But you can think of it also as
8:09
maximizing the likelihood also maximizes the likelihood. So
8:16
it's like the same kind of the same thing as if you maximize
8:20
one, you also maximize the other. So in that way, this is
8:23
why we can do that. So here at the bottom is the lock, and was
8:30
just taking the look of this party at the at the top. So we
8:33
have now y is the true label times lock, the activation. So
8:39
this is the class membership probability. So just me for
8:44
completeness, this would be why given x, and of course, also the
8:50
model parameters, but I'm omitting the model parameters
8:52
here just for simplicity. And yeah, this is the lock
8:57
likelihood. I mean, it's not quite the likelihood loss,
9:03
because there's one more modification. So in practice,
9:07
also, when you recall from the pytorch code that I showed you,
9:11
we have the stochastic gradient descent. And in stochastic
9:16
gradient descent, let me write this maybe down.
9:18
Stochastic gradient descent, we want to minimize. So this is a
9:31
process where we minimize something, if we wanted to
9:37
maximize something, we would have to use stochastic gradient
9:42
ascent. That is like the other way around, we want to we would
9:47
maximize something. So what we don't want to so if we think of
9:54
it, maybe as a loss function, so as a function, so gradient
9:58
descent would be like this, where we go down this hill. And
10:03
gradient ascent would be this way where we go up that hill.
10:09
Now, in pytorch, and many other libraries, it just happens just
10:12
for simplicity. There's an implementation of gradient
10:16
descent, where we minimize something. So in that way, we
10:21
would just give it a log likelihood function as the loss
10:25
function to optimize, then it would actually make a minimize
10:28
this loss, which would actually very bad. So what we would get
10:31
is very small class membership probabilities for the correct
10:35
labels. So what we can do now is just to turn around this
10:40
problem. So instead of maximizing the log likelihood,
10:45
we can minimize the negative log likelihood, just putting a
10:49
negative here in front, and then we turn this maximization problem
10:53
into a minimization problem. And then we can just use the
10:56
stochastic gradient descent implemented in pytorch. So it's
11:01
just like a little trick we do by flipping around the sign
11:04
here. And another trick we can do in code is that we usually
11:07
add a one over n scaling factor here to scale over the number of
11:16
data points in the training set or the batch size, the mini
11:19
batch size. So last time, we also talked about mini batches.
11:23
So we can also excuse me. So we can also consider the mini batch
11:28
size here. And then it makes the training numerically more
11:34
stable. Yeah, so to just have a little checkpoint here to
11:38
summarize, so doing logistic regression, by that, I mean, our
11:42
training logistic regression is actually similar to what we have
11:45
done before in edeline. In edeline, recall, we minimize the
11:49
mean squared error loss here. But yeah, the difference is that
11:54
in logistic regression, we maximize the likelihood.
11:58
Because it's numerically more stable, instead of maximizing
12:02
the likelihood, we can also maximize the lock likelihood.
12:06
But like I also mentioned, the tools that we usually have
12:10
available are developed for stochastic gradient descent, so
12:13
that we don't have to rewrite those tools, we can just turn
12:17
this maximization problem into a minimization problem. So we can
12:22
minimize the negative log likelihood, which is the same as
12:24
maximizing the log likelihood. So yeah, it was probably a lot
12:28
of information in this short video. In the next video, I will
12:32
talk a little bit more about this training and how the loss
12:36
function actually looks like. I think this will probably
12:39
clarify some thoughts that you might have. So if you have some
12:42
questions right now, maybe don't think about it too hard. Maybe
12:47
watch the next video. And then if you have questions, then
12:51
maybe think about it more. But I think the next video could
12:54
potentially clarify some points.

##v53:

0:00
Yeah, let's now take a look at how we train a logistic
0:02
regression model. By that I really mean like computing the
0:06
gradients of the loss function with respect to the weight and
0:09
bias parameters in the logistic regression model, so that we can
0:12
then use gradient descent to update the model. And then in a
0:17
later video, we will see how we implement that in code to do the
0:21
actual practical training. So yeah, let's take a look at the
0:26
logistic sigmoid function again. So here on the left hand side,
0:30
that's the logistic sigmoid activation function that we
0:32
talked about before, where we have the net input on the x
0:35
axis and the output on the y axis, it has this sigmoidal
0:39
shape. And you can already see, just by looking at this
0:44
function, what the gradients might be. So you can see here,
0:49
the function on the answers, it's relatively flat. So the
0:52
gradient should be also very flat, like zero around that
0:56
region. And the steepest part is here. So this should also be
1:00
where the gradient is the largest or let's say the partial
1:04
derivative with respect to the input is the largest. Now, on
1:10
the left on the right hand side, I was computing the derivative
1:14
of the sigmoid function with respect to its input. So yeah,
1:19
if you use the simple calculus rules, so that's how you would
1:23
all compute the derivative of this part, right, because you
1:27
have the derivative of the, what is it called numerator, which is
1:33
e to the power of minus z, the one cancels, and then you have
1:37
this square term in the denominator. And when you solve
1:42
that, I'm not doing it here. So when you solve that, if you're
1:45
interested, I've done that in the Python machine learning
1:48
book, I think it's in chapter 12, somewhere, but I can also
1:51
share that if you're really curious about that, but you can
1:53
probably also find examples of on the internet. It's quite
1:55
involved, it will take you a few sheets of paper, I guess. But
2:00
what the result is, is this one here, on the right hand side,
2:03
that's the derivative of the logistic sigmoid function. And
2:07
you can see it's relatively simple, right? It's just the
2:10
sigmoid function times one minus the sigmoid function, right. So
2:14
that's what I mean, it has nice derivatives. That's actually one
2:17
little Yeah, not so nice part about this activation function,
2:21
it's derivative, we will talk about that in a future lecture.
2:24
So what's not so nice about it is actually that these, these
2:27
parts here are of the derivative are actually zero. So here, we
2:30
don't have any power to update the function. So if these terms
2:36
are zero, this might be a problem when we have multilayer
2:40
neural networks, and then you have a chain rule where part of
2:45
the chain rule is zero, because then the whole loss gradient
2:49
becomes zero. But this is something we will talk about
2:51
later. So let's now just focus on how this function looks like.
2:54
So in the right, lower side here, I have the derivative of
2:59
this logistic sigmoid function. And you can see like by as with
3:02
our intuition here, this part, where z is zero, that's where
3:08
the gradient is the highest or the partial derivative is the
3:10
highest, you can see the partial derivative is point two, five,
3:14
the largest value. And then for very negative and very positive
3:18
inputs, the derivative goes down to zero. It's Yeah, you can see
3:23
that here where it's also very flat, right. So this is how the
3:26
logistic sigmoid derivative looks like. So here's how the
3:31
loss function looks like. So at the bottom, here, this is again,
3:37
my negative log likelihood loss I talked about in the previous
3:45
in the previous video. And me like we talked about before,
3:49
there are two parts really of this loss function, you can
3:51
really think of it as the part when the class label is one and
3:56
the part when the class label is zero. So here, we really talk
4:00
about the true label in the data set, the label of the training
4:05
example. And this is also the true label. So these are the
4:09
true labels provided in the training data set. Again, we
4:13
only compute, I mean, this might sound trivial, but just to
4:16
recap it, we only compute the loss function during training,
4:20
not during prediction, right, when we have a test set or
4:22
something, and do a prediction, we don't use the loss, it's
4:25
really just to find the weight parameters of the model. So we
4:28
are given these true labels from the training set. So what
4:33
happens if the true label is one, let's, let's consider this
4:38
scenario of the true labels one, we have one here right on on
4:42
the bottom, and we have one here. And if we have a one here
4:46
on the right hand side, then this whole term here becomes
4:49
zero. And then we have zero times something. So this whole
4:53
term cancels. So if the true label is one, we really only
4:57
focus on this part here, the true label is one, then our loss
5:02
function is minus lock. And I can just write this part as a
5:07
the activation. It's minus lock of the activation. Now, if my
5:13
arm label is zero, then let me erase this as maybe a little
5:19
bit messy here. So we set minus lock A. And for this right hand
5:26
part, if y is zero, then this part will be zero, zero times
5:30
something cancels. Here we have a zero. So this will be one. So
5:35
if the true label is zero, then the loss function is minus lock
5:43
one minus
5:48
a. Now let's take a look at the shape of these curves here. So
5:55
if we let me use, I should have maybe used yellow minus lock one
6:00
minus A. So it matches this orange or yellow line here. So
6:06
you can see, for the value here of the sigmoid function. So this
6:10
is really like the logistic sigmoid, the class membership
6:13
probability. And recall, this one is for the black color. This
6:20
is for
6:23
the class label equals one, so the class membership probability
6:26
for one plus one. So this is really like this probability
6:31
here. So if what we want, so what we want is this probability
6:38
to be high, if the true label is one. And we want this probability
6:44
to be low, if the probability is zero, so but we can also write
6:49
this as one minus
6:50
y equals zero. This is it's easier to think about. So let's
7:00
let's take a look at now what happens if this probability here
7:03
is high. So if this whole term is high, this means if we have a
7:08
low probability that this is indeed class zero. So if we have
7:14
a term here, we have a low probability for this one, this
7:20
one will have the whole term with a one minus included will
7:23
have a large probability. And you can see, we have a high loss
7:28
in this case, if a probability for class one, so this is really
7:31
like the class one probability. If this is high at one, then we
7:37
have a very large loss, you can see that. So the loss approaches
7:40
infinity, if we have a high probability, vice versa, the loss
7:51
approaches zero, if we have a low probability, right, so you
7:55
can see that on the closer I get to a low probability, the closer
8:01
I get to a low probability that the class labels one, the smaller
8:06
the loss, because a low probability for class one means
8:11
a high probability for class zero, which is what we want. So
8:16
here, if the true label, if the true label is indeed zero, we
8:23
want a low probability for class one. So here, we have a zero
8:28
loss, if we have a zero probability for class one,
8:31
because then the probability for y equals zero will be large
8:35
because of this relationship here. The same way, now, let's
8:40
take a look at the blue color, the case when the class table is
8:45
one, the same way, when we have a low probability for class
8:50
membership, one, we have a high loss, it approaches infinity,
8:54
right? Because I mean, we will never really have a probability
8:59
of zero, we will hopefully have something like very, very small,
9:03
because otherwise, it will crash our lock function. Or Yeah, so
9:08
we will have lock of minus lock of zero, right? So we'll be a
9:14
very small number. And then this approaches oops. This loss
9:21
approaches infinity, basically, if we have a low probability,
9:25
and we have a high loss, sorry, we have a high. If we have a
9:30
high probability, the loss will be very low. That's what I
9:32
wanted to say. So the takeaway here is really, this is how our
9:36
loss function looks like, what we want is we want to have a
9:39
high probability for the right class and a wrong probability,
9:44
like a low probability for the right class, or a high
9:48
probability for the wrong class, consequently, will result in a
9:51
very large loss. And you can see it's like, steeply increasing
9:54
here. So that's the takeaway. So there's a large penalty for
9:57
making a wrong prediction. Yeah, how does the learning rule now
10:02
look like? I mean, this is the same gradient descent rule that
10:05
we used before, when we trained a linear regression model, or
10:08
add a line using gradient descent. For that one, what we
10:12
needed was the derivative of the loss function with respect to
10:16
the weights. So that's the partial derivative of the loss
10:19
function with respect to the weight. And we also compute the
10:22
partial derivative of the loss function with respect to the
10:24
bias, that's the same concept. So in order to do that, we can
10:28
compose it into three terms, that's the same as we done, we
10:32
have done for edeline and linear regression. So we compute the
10:36
derivative of the loss with respect to the output of the
10:39
activation function, then we compute the derivative of the
10:42
activation function with respect to the input for edeline, this
10:45
was just one because the activation function was your
10:49
identity function. And then what we also compute is the
10:52
derivative of the net input with respect to the weight. And that
10:56
was just x, right, xj, similar to edeline. So here at the
11:01
bottom, I've written this out. So all these three terms. So
11:08
this one, by the way, this is the negative log likelihood
11:15
hood loss that we talked about in the previous slide. And if
11:18
you look at this, the only thing that's really different from
11:20
edeline is that these and these values are of course different
11:25
because we have a different loss function and edeline. We had the
11:31
MSE, right, where the derivative, so the MSE was, for
11:36
example, written like this, let's say like this with the one
11:40
half in front. And we can also do the one over n if you like.
11:44
But okay, so let's do it. And then we bring the two up front
11:50
for the derivative. So it's two over two n, so the two
11:54
cancels. So we just have one over n times just one minus
12:06
should be y hat minus y. So that would be the derivative of our
12:13
MSE. Now, of course, we don't have an MSE, we have this
12:17
negative log likelihood for which we have the following
12:20
derivative with respect to the activation function with respect
12:23
to its input. And this one for edeline was one. And this one is
12:32
the same because the net input is the same. Now, the only thing
12:36
we have to do really is to put those together, right, we have
12:38
to just multiply them using the chain rule. So it's the same
12:41
like for edeline for the name just looked simpler. But if
12:45
edeline we just had one over n times y hat is y times x j,
12:54
right. So that was one for edeline for the logistic one, it
12:58
may look more complicated because we have no this term and
13:01
this term. However, there's something nice that's happening.
13:05
So we can actually show what I've done here, we can actually
13:08
simplify this. So this part and this part when we put them
13:13
together, it simplifies to this one here. So you can work out
13:20
the math if you like, but it's a simple, very simple derivative
13:23
here. So you can see that these cancel each other nicely. And
13:27
this is why I said that the logistic regression or the
13:32
sigmoid functions has nice derivatives. That's because
13:36
things cancel here nicely. And then we just add the x to it.
13:40
And you can see, actually, this looks exactly like the edeline
13:44
learning rule, right? This looks exactly like the linear
13:47
regression one, right? Isn't that quite cool. So here is just
13:51
from the previous slides that we had on edeline and linear
13:56
regression. So this was the stochastic gradient descent
14:00
learning rule here, where we had the initial weights, the for
14:04
loop over the training epochs, and then the for loop over the
14:08
training examples, it could also be for mini batches. Then we
14:11
compute the prediction, the gradients here. And then we do
14:15
the update here. And then we have the learning rate at here.
14:19
We can use exactly the same rule for logistic regression. Also
14:24
note, there was also discussion on Piazza. We can actually
14:29
write rewrite this, because I think I've done it the other way
14:32
around in code, we can actually rewrite this as on, of course,
14:36
like y hat minus y, right? So same thing, because with minus
14:40
and minus, and that is what I had in the previous slide, if I
14:44
go back, I have a minus y instead of y minus a, so I
14:49
should say that a is equal to y hat here. So that's the output
14:54
of the logistic regression model. So a y hat are the same
14:58
thing here. So let me write just a year. So what I mean, we can
15:05
also write this, maybe it's if it's more clear, I can erase
15:10
more. Let's maybe write this as a minus y, xj. And this one
15:20
should be just a minus y. So this is exactly the same
15:27
learning rule as for Adeline. What's the difference? Now, why
15:30
is this a logistic regression? Well, the big difference here is
15:33
that a is computed differently, right? So a is now computed by
15:38
by others on nonlinear function. Whereas for linear regression,
15:43
it was Adeline, it was just computed as the identity
15:48
function. So in the case of Adeline, or linear regression,
15:51
this was the net input. So but yeah, that is, again, why I said
15:56
it has nice derivatives, because we don't even have to change our
15:58
learning rule. The only thing we have to change is how y hat or
16:01
basically a is computed. All right, so a few last things
16:09
about this. So here, we can think of this as the whole
16:14
computation graph. Again, this is our logistic regression
16:17
computation graph. We haven't talked about this output yet,
16:20
right? So we do the training here. So here's where we
16:27
compute the arrow. So we have a true, let's say, a true label.
16:35
Let's call it true label y that goes in here. And here, what
16:42
comes out is our a or y hat, let's call it y hat. It's
16:47
actually a probability. So there's maybe more clear to call
16:49
it a. So we have our a and our true y. And from that one, we
16:56
compute the negative log likelihood, compute the
16:58
gradients, the gradients, or the pressure of the loss with
17:02
respect to each weight and also the bias. So I'm actually not
17:06
showing the bias I just see. So it should be technically also
17:09
bias unit. So we compute that one, and then we update the
17:14
weights and the bias units with that one. And this right part
17:18
here, this comes after training, this is just for the prediction.
17:21
So for that one, we can use a threshold function similar to
17:24
the line. So logistic regression, we can use the
17:28
following threshold function here to compute the real y hat.
17:32
So I should have maybe be more consistent and say y hat is the
17:36
predicted class label. And a is the probability class membership
17:41
probability, I will be more careful of that when I write the
17:45
code for the next video. Anyways, so we can say with this
17:50
threshold function of the probability. So this is a if
17:54
this is greater than point five, then return class label one, and
17:59
otherwise return class label zero. Actually, we can do it
18:03
even more computationally efficient during prediction, we
18:07
can even skip the activation function, we can just operate
18:10
with z, we can say if the net input is greater than point, if
18:15
it's greater than zero, then the label is one, otherwise it's
18:20
zero. Why is that? If we take a look at the logistic sigmoid
18:26
function again, so here, that's the net input at zero. So at
18:31
zero, the output is point five. So we know, so we, we can say
18:35
everything above here, above point five is class label one,
18:40
say y hat, class label one, and below here, y hat is class zero.
18:50
But we know if we have the threshold point five, it
18:54
corresponds to a net input of zero. So we can also just say if
18:58
the net input is greater than point greater than zero, then
19:02
it's class label one, if it's smaller than zero, then it's
19:05
class label zero. So that's just what I wanted to say about
19:08
logistic regression. In the next video, I want to talk a little
19:13
bit about the logits and cross entropy. These are just two, I
19:18
would say, jargon words about or regarding logistic regression,
19:24
logits and cross entropy, or just briefly discuss what those
19:27
mean. And then I will show you logistic regression in the code
19:31
example. And if everything in this video was a little bit fast
19:34
and confusing, I think the code example will probably clarify
19:38
that because then we will put everything together, we will do
19:41
the forward pass, compute the gradients and update the weights.
19:45
So what I mean is we will really implement this whole stochastic
19:51
gradient descent learning rule in code and that I hope
19:54
clarifies everything.

##v54:

0:01
Yeah, since we talked so much about logistic regression now, I
0:05
thought that might be a good opportunity now to introduce two
0:08
terms logits and cross entropy, because that's what I will also
0:13
use quite often later in this class. And that's because also
0:18
it's a very common. These are two common terms in the deep
0:22
learning literature. I sometimes refer to it as the deep learning
0:25
jargon, because, yeah, we sometimes use these terms a
0:28
little bit differently in statistics, compared to deep
0:31
learning. So I just wanted to briefly clarify how they relate
0:35
to the concepts we just discussed. If this doesn't make
0:39
complete sense, I mean, we will be using these terms later. And
0:42
you will then have something to refer back to. Okay, so in deep
0:49
learning, when we have multi layer neural networks, let's
0:52
say, I will just draw a very simple one here, we will
0:56
actually talk about them on Thursday. So if we have multi
0:59
layer perceptron like this, everything is connected to
1:03
everything here, it's a fully connected layer. And then we
1:06
have this one output node. And in this network, we also have
1:10
net inputs similar to add a line or logistic regression. But now
1:14
we have two net inputs, one is here, let's call that z one. And
1:18
one is here, it's z two, we will talk more about that on
1:21
Thursday. But yeah, in deep learning, it's very common to
1:24
call these here, the net inputs that come before the output to
1:29
call them the
1:33
the logits.
1:36
In statistics, the logits have a specific meaning. This is the
1:40
logarithm of the odds or log odds. And in the context of
1:45
logistic regression, which we just covered, these logits are
1:48
naturally the net inputs.
1:51
So where does that come from? This is the inverse of our
1:55
logistic sigmoid function.
2:02
That's our logistic sigmoid function here, just, I just
2:07
abbreviated it as P. So the log of P over one minus P, this
2:13
function is the inverse of this function. And yeah, so in deep
2:22
learning, though, it does not necessarily any relationship
2:27
between the log odds and the net inputs of the last layer. It's
2:31
just like, I think it's derived, the term is derived from
2:34
logistic regression, people call that logit logits in the context
2:37
of logistic regression, and then just generalized to this wording
2:42
to arbitrary multilayer perceptrons, where we may not
2:46
even have a sigmoid function, as we will see later. So you can
2:49
just think of it as the net inputs of the odd of the last
2:54
layer, basically. So here, just for reference, so here on the
2:59
left hand side, the logistic sigmoid function and here on the
3:03
right hand side, the logit. So the logit function is the
3:06
inverse of the logistic sigmoid function. So basically how it
3:09
looks like, I don't think I have to go into do that into the
3:12
to that in much detail, because we have seen that before. And
3:14
this is essentially just flipped. So there is another
3:20
concept that is maybe a little bit confusing, but it's exactly
3:25
what we've covered before. Actually, we had a seminar at UW
3:29
last week, where we also, yeah, it was briefly mentioned,
3:32
coincidentally, there was like a question whether it's the same,
3:35
the negative log likelihood and cross entropy. So yeah, the
3:39
negative log likelihood and the binary cross entropy are
3:42
equivalent. And in practice in deep learning, people just say
3:46
cross entropy, multi category cross entropy, which would be a
3:51
multi class version of the negative log likelihood, which
3:53
we will cover later in this lecture when we talk about the
3:57
softmax function. So just to keep it brief, the negative log
4:02
likelihood that we just covered a few videos ago, is the same as
4:07
what people call the binary cross entropy, they were just
4:10
formulated in different contexts. So negative log
4:14
likelihood comes more like from, I think it's like, it's probably
4:18
from a statistics context, I don't know the first paper, or
4:21
reference that mentioned that. But this is something usually I
4:23
see in statistics papers, and the binary cross entropy thing
4:27
has originated from the field of information theory, or computer
4:32
science. So we have actually seen that, or not, the cross
4:37
entropy, where we have seen the self entropy, or just entropy,
4:40
and statistics 451. For those who took this class, in fall
4:45
semester, where we had used the entropy function in the context
4:49
of the information theory and decision trees, but we used a
4:54
lock to instead of the natural algorithm, but yeah, it's kind
4:59
of somewhat related, if you have taken any class where you
5:03
talked, for example, about the KL divergence, or callback
5:10
Leibler divergence, which measures the difference between
5:13
two distributions, the KL divergence is essentially the
5:17
cross entropy minus the self entropy. Of course, you don't
5:25
have to know that it's just like a fun tidbit here. The only
5:28
thing you have to know is or should know, because it's useful
5:31
to know, is that the negative log likelihood is the same as
5:34
the binary cross entropy, this is like a useful thing to know.
5:37
And this is what we've discussed in the previous videos. And
5:42
there's also a multi category version is the multi category
5:45
cross entropy, which is just a generalization of the binary
5:48
cross entropy to multiple classes. So in order to make
5:53
that negative log likelihood or binary cross entropy work for
5:57
multiple classes, we assume a so called one hot encoding, where
6:02
the class labels are either zero or one for some reason, it was
6:05
cut off here. But this is something we of course, haven't
6:09
discussed yet. And if this doesn't make sense yet, we will
6:12
actually discuss that after the logistic regression code
6:14
example, when I will introduce the multinomial logistic
6:18
regression model. So again, all I wanted to say here is the
6:21
logits in deep learning, usually refer to the net inputs of the
6:28
layer that just comes before the output. And the term binary
6:34
cross entropy and negative log likelihood are essentially the
6:37
same. Alright, so in the next video, I will show you a
6:40
logistic regression code example. And then we will take
6:43
a look at this multi category cross entropy.

##v55:

0:00
Yeah, before we move on and talk about the multiclass example of
0:04
logistic regression, the so called softmax regression, let's
0:08
just wrap up everything we talked about in the previous four
0:11
videos in a code example. So I prepared a code notebook, you
0:15
can find it on GitHub, I will share the link on canvas, where
0:19
I have implemented two things. So the first thing is logistic
0:24
regression from scratch, just yeah, from the ground up, low
0:28
level implementation of logistic regression, really
0:30
like on implementing the learning rule that we talked
0:34
about here. And then I will show you how we can do that using the
0:39
pytorch utilities, the module API that we talked about last
0:44
week, where we have this n dot linear layer and so forth. This
0:48
is something we would do in practice when we have of course,
0:50
more complicated networks, but I thought from scratch
0:53
implementation is still useful from a learning perspective. So
0:56
you get a better feeling of how logistic regression works. So
1:01
let's get started. So of course, first, my watermark, you can
1:05
ignore the torch version, this torch version doesn't exist.
1:08
Actually, I yesterday, compiled a torch from source to test
1:14
something. So this should also work on torch 1.7. So no worries
1:18
can ignore that. Um, yeah, so then the part of matplotlib,
1:25
which we'll be using NumPy, we will be using, and then the
1:27
torch stuff, we will be using. So just some inputs to get them
1:30
out of the way, we will be using some simple toy data set. That's
1:35
like, yeah, just, I think that is what I gave you also for the
1:38
homework. To be honest, I have to double check I made multiple
1:41
of these toy data sets. Yeah, that's just a simple binary
1:45
classification data set. Now here is my logistic regression
1:51
implementation. So how does it work? So I'm using the roughly
1:57
same way how we would implement that using pytorch with a module
2:01
API. So here I am implementing forward and backward manually.
2:06
These are the two methods where forward is the forward pass and
2:10
backward is the gradient descent computing. Yeah, the gradients of
2:15
the loss function. I actually let me modify this. Let's call
2:20
that loss with respect to so WRT means with respect to I think it
2:26
makes it clearer. So that's the gradient of the loss with respect
2:30
to the output and so forth. We'll just modify it everywhere
2:34
here. All right. And then let's do it step by step here. So then
2:44
here in the init function, this is like the function or method
2:48
that get x gets executed when we instantiate a new object from
2:52
this class. What we have is the weights and the bias unit. So
2:59
the weights, we initialize them to zeros. So we use the zeros
3:03
function to initialize them to zeros, it's a vector, a one.
3:08
It's a row vector, basically a one times num features vector.
3:11
So our matrix, so it's essentially a row vector. So um,
3:18
num features is the number of features in the data set. So the
3:21
number of weights is equal to the number of features just like
3:23
an adder line. And we only have one bias unit. All right, so the
3:29
forward method, yeah, this is computing the net input, right?
3:32
So this is the net input can also call it z can, we could
3:38
technically call it net input, but you know what we mean,
3:41
right? I mean, I can rewrite this maybe doesn't really
3:45
matter.
3:49
I can just leave it like that. I think I'm underestimating you, I
3:53
think it's probably all clear to you, I don't have to use these
3:56
different words. All right. Um, sorry. So the backward method is
4:03
yeah, computing these gradient terms, this is going back to
4:06
what we've done here. So here, I'm computing the gradient of
4:10
the loss with respect to the output. So this is essentially
4:14
this part here, then the grain of the loss with respect to the
4:19
weight, this is this part here, where I put those two things
4:24
together. So this should probably be with respect to the
4:29
Z, the net input, it's maybe clear instead of saying output.
4:32
Um, so this is matrix multiplication between x. And
4:40
this term, I just rearranged that to make the dimensions
4:43
match, which is why I have the transpose, you to be honest,
4:46
don't have to memorize these details, you will probably find
4:49
out by tinkering with the code. If you ever implement something
4:53
from scratch, because here, this is really for one weight. And
4:57
here, I have that as a vector implementation for multiple
5:00
weights, right, because we have the number of weights equal to
5:03
the number of features, that's a bit more complicated, but the
5:06
concept is the same. So this line here really is this part
5:11
here. I can actually also maybe go to this part here. So this
5:17
this part here, this is essentially this one here, the
5:21
gradient of the loss with respect to the weight. And then
5:25
the same for the bias, which would correspond to this part
5:28
here. Here, this is the threshold function, predict
5:32
labels. So I'm calling forward, that gives me the probabilities
5:36
a, so a is the probabilities for us, I call them problems,
5:41
because in the lecture, I said also, it was a bit complicated,
5:44
when we had y hat, and it was confusing. So I referred to a as
5:49
the probabilities, that's the sigmoid activation here. And
5:54
this is the threshold function, where if the probabilities are
5:58
greater than point five, return class label one, otherwise
6:02
return class label zero, I could however, also do it as with the
6:07
net inputs, I could say if the net inputs are, let's call them
6:12
zero or greater than zero, then return one, otherwise zero. This
6:16
is because what we discussed here. So here's the threshold
6:22
function. And because the probabilities with their point
6:27
five, the net input is zero. So either we can operate directly
6:31
on the net input or the probabilities here. So you have
6:34
that with the probabilities, but doesn't really matter that much.
6:39
Okay, so he has just an evaluation function. So this is
6:42
not super interesting. He I'm predicting the labels, which in
6:46
turns, in turn uses this method here, which computes forward,
6:50
and then the threshold function here, the threshold function.
6:57
And then in order to compute the accuracy, we sum over the
7:04
correct predictions. So every time the class label matches the
7:11
predicted labels here, matches the actual class labels, every
7:15
time they match, we sum that up. So this is a number of correct
7:20
predictions, and then divide by the size of the training set. So
7:24
it's a value between zero and one, it's the proportion of
7:27
correct predictions. Why do I do float here? It's because the
7:32
class labels are integers. And yeah, in pytorch, it's a little
7:35
tricky to compute or compare things like floats, the labels
7:39
are floats here. And then this is integer, I think I could have
7:43
I could have omitted this year, it's maybe a little bit
7:45
complicated, I could have also think done that would also have
7:50
the same effect. So but anyways, okay, anything else? Yeah, this
7:58
is a sigmoid function, which you have seen a lot of times. So
8:01
there's this function here. Yeah, the loss function, that's
8:06
the negative log likelihood, which we have right here at the
8:10
bottom. That's the logistic cost function. And here's the training
8:17
function. So here, again, let me jump back to this one, we we
8:24
are right here now. So for every training epoch, for e in the
8:29
number of epochs, we compute the outputs, which is here, that's
8:34
the probabilities, the ACE. So this is really, this should be
8:38
an A actually. So remember, this was copied from the adder line
8:43
should have probably adjusted it to an A here. But you probably
8:47
know what I mean. Um, then we compute the gradients. So these
8:51
are under B here. Then we update the weights, which is C, this
8:59
part here. And this is it. And this is just for logging, just
9:03
keeping track of everything, like looking at the results and
9:07
the loss curve, which can be useful. So let's actually do
9:10
that. Let's
9:12
yeah, do that here. What I'm doing is I'm converting the
9:15
NumPy arrays to torch tensors. Because if you go up here, you
9:21
can see I used NumPy here. So to load the data. So yeah, I'm
9:27
just converting them to torch tensors, then I'm initializing
9:33
my logistic regression model. So this will be actually step one
9:37
initializing. And then I'm calling train, train would be
9:42
everything under two here. And then I'm printing the model
9:46
parameters, the weights, the bias, just to take a look at
9:48
them. And I'm training for 30 epochs with a learning rate of
9:52
point one. So I think that's the mistake I always make talk
9:57
through this, but I usually forget to execute this. Okay,
10:00
now we are running the code. Okay, we got an error here. Okay,
10:05
I need to change the name one second, let me fix that.
10:14
Alright, so it's training, you can see it's blazing fast, starts
10:18
with already a very high accuracy after the first epoch,
10:22
to be honest. So it's, yeah, it's actually training super
10:24
fast, the cost is very low. But you can see, if I do more box,
10:28
it goes even lower, the accuracy goes up to 100% here even. But
10:32
you can see, even though the training accuracy is already 100%,
10:35
the loss still goes down. I could have trained more and
10:40
would go maybe down further. But that at that point might not be
10:44
necessary. Might be overfitting.
10:48
Alright, wanted to execute this part. Okay, there's some message
10:54
here. I think this message comes from NumPy, because I recently
10:59
installed a very recent version of NumPy. And it must be
11:02
something in Matplotlib here, you can actually ignore that
11:05
that this is not an error message that is just a warning.
11:09
So if you see warning or deprecation warning, that means
11:13
things are still working. So don't worry about them. But in
11:17
future, if there's an even newer version of a software library
11:20
in Python, this may not work anymore. So here, this is
11:26
nothing we are doing wrong. This is probably something inside
11:29
Matplotlib. And I'm sure they are already aware and working
11:32
on that. So don't worry about this warning. Everything still
11:35
works fine. There will be probably a new Matplotlib
11:39
version that addresses this issue at some point, but
11:41
everything is fine. Um, yeah, you can see here is how the
11:45
lock, the negative log likelihood loss looks like. So
11:49
it should be the negative log likelihood loss to be precise.
11:54
And then over the number of epochs, you can see, maybe it
11:57
will go down further, you can see it's actually going steep
12:00
down. But whether it's actually helping, I don't know, because
12:03
we already get 100% training accuracy. So let's take a look
12:07
at the test accuracy, it's only 96%. For completeness, we will
12:12
also take a look at the Yeah, at this year. So yeah, we can see
12:17
actually here on the training set, the decision model looks
12:19
quite good. So it's dividing both classes, class zero and
12:23
class one on the test set. Yeah, it's not performing so well,
12:27
because there's this one outlier point, right. So here, this one
12:33
is not classified correctly. So if this decision body would go a
12:37
little bit more to the right, then we might get this one
12:39
correct. But at this point, this model only sees the training
12:42
data doesn't know of this point here on the right hand side. So
12:45
in this case, I think training the model further wouldn't
12:48
really help because this is already doing a good job here,
12:51
actually, maybe putting a little bit more to the right would help
12:54
actually, because then would be more here. Yeah. Anyways, this
12:59
is just an example, of course, I just implemented this quickly in
13:04
a way that I didn't really fine tune anything. And this is a toy
13:07
data set anyway, so don't over interpret this. Okay, so the
13:13
goal here was really to show you if I scroll up again, to show
13:17
you how we implement this from scratch, like, the most
13:21
interesting part, I would say is this backward function, which is
13:24
a little bit different from the airline function, the rest
13:27
should be all the same as in the airline implementation. So it's
13:30
not that new to you, I hope. Now, I want to show you though,
13:35
how we use the module API to implement this logistic
13:40
regression model. So here, this should do exactly the same
13:45
thing, but now I'm relying on inbuilt or built in pytorch
13:49
functions. So I'm using this self dot linear here to refer to
13:53
my torch dot n dot linear layer, this is a layer that computes
13:58
the net input. However, note that by default, this will
14:03
initialize the weights to small random numbers later on, this
14:07
will be very useful, but it is not that useful to compare to
14:10
our model above because if you recall, above, I initialized my
14:14
weights and bias to zero. So I want to do the same here. So I
14:18
can compare the two models. So what I'm doing is manually
14:21
assigning zeros to the weights and bias unit. Yeah, and then we
14:28
have the forward method. So here, the forward method, we
14:31
compute the logits via the self dot linear, which is this fully
14:35
connected layer or linear layer. And then we have built in pytorch
14:39
function that computes the sigmoid activation function. So
14:43
you can see a logistic regression model is actually
14:46
super simple. Actually, we can also it would train just fine if
14:49
we have this one, just for comparison person reasons, I
14:53
have this one, but you can see how simple it is. And it will
14:55
already implement the backward function for us, we don't have
14:58
to do it ourselves. Here, we are using the stochastic gradient
15:04
descent optimizer. So this will update the weights then. So this
15:13
will compute the gradients via the backward and update the
15:16
weights. So we are just specifying what weights we want
15:19
to train. This is the model parameters here, model two. So
15:23
this is one of two or one logistic regression model to
15:27
model one was the from scratch implementation. Right. So here's
15:30
just an accuracy function to compute the prediction accuracy.
15:35
We are training also for 30 epochs. Like before, what I'm
15:38
doing is I'm casting the NumPy on a raster tensor, I've already
15:43
done that. So it's pretty redundant. And now here's my
15:46
training loop in pytorch. So for each epoch, I compute the
15:52
outputs, these are the probabilities, this is from the
15:55
forward pass, this is these probabilities here. Then I use
16:02
this cross entropy binary cross entropy function. And this is
16:05
essentially why I spent some time in the last lecture, last
16:09
video here when we had when we had this topic here, why I spent
16:14
some time, yeah, just telling you that the negative log
16:18
likelihood and binary cross entropy are equivalent. Same
16:21
thing. Yeah, I'm saying reduction sum, because that's
16:27
what we have done here. It's the sum, or we can also do the
16:30
average, actually, if I change this, it will be the average or
16:36
mean by default. But since we implemented above the sum to
16:41
have the sum here, I'm also for comparison reasons use the sum
16:44
here. In practice, I think using the mean is more stable for with
16:49
regard to learning rates and different batch sizes. Yeah, and
16:54
then this is really like what we've done in the last week when
16:57
we trained at a line using these automatic things, we have the
17:02
following we compute the loss. I traditionally use the term cost,
17:09
but I think loss is more natural nowadays, then we set the
17:14
optimizer zero grad, which will reset the gradients from the
17:20
previous round. Otherwise, the gradients will accumulate like
17:23
I explained last week. And then we compute the gradients for
17:27
the current round, and then update the weights. And this is
17:31
essentially it. Let's run this. All right, error. Model two is
17:36
not defined. See, I always forget to execute things. All
17:39
right, let's execute this one. And then this one. Yeah, trains.
17:42
Okay. So and you can see if you recall, these have the same
17:45
values as we've seen before, I can just scroll up in a second
17:48
and just to show you and also take a look at these weight
17:52
parameters, can just copy and paste them. So yeah, you can
18:03
see they're exactly the same. So we learned exactly the same
18:06
using pytorch, which gives us confidence, I hope that we
18:11
understand gradient descent correctly and implemented the
18:17
gradient here correctly. So it's the same as in pytorch. All
18:22
right. Um, yeah, and this is it, essentially. So evaluating the
18:27
model, same test accuracy, because it's the same weights
18:30
and bias. So it should be the same decision boundary, which we
18:33
can see here. Yeah, so this is how we implement logistic
18:39
regression. I hope that was helpful, like understanding a
18:42
little bit better, how these different concepts here in the
18:46
slides work. You may also want to work through this more
18:49
slowly. I think that might be also helpful. But yeah, that's
18:52
it. So the next video, we will then talk about how we can
18:56
generalize these concepts to multiple classes. That means
18:59
like more than two classes.

##v56:



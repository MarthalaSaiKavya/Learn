##v1:

Transcript


Search in video
0:01
Yeah. Hi everyone. Welcome back to the new semester. I hope you had a nice summer break.
0:07
So in this brief video, I want to just go over some of the course material and.
0:12
We'll talk about how we are going to, um, yeah. Work together in this course, because it will be a little bit
0:18
different than a usual course where we have in person sessions. So for this cost, my plan is to record the lecture asynchronously.
0:27
That means I will record. I bought them ahead of time and share them with you at the beginning of each week.
0:32
So you can watch the material whenever it's most convenient for you. And I think this is.
0:38
Yeah, useful to you because instead of doing it live this way, you can watch them when it suits you best.
0:46
So, and you can also watch them multiple times if you need to. And, uh, also some of you may have slow internet connection, so you can
0:54
download the video to your computer so that you don't have like streaming issues during watching each video to make this a little bit easier.
1:02
I'm trying to. Break down each lecture into multiple videos by topic. So by that, what I mean is I will, for each lecture have like
1:10
these, um, different topics here. So I will this lecture just when this first video just call and
1:16
talk about the cost in general. So a little bit about the syllabus, the topics we are going to cover and so forth.
1:21
And so then I will talk about what machine learning is and put the different categories of machine learning are notation, approaching, machine
1:29
learning, application and so forth. So these are all the topics of lecture one, and I will divide that up into six videos.
1:37
Yeah. And with that, that I mentioned, we will have like just asynchronously
1:42
disadvantage itself cost that you can't. Ask questions during the lecture, but I will have live office hours so
1:49
we can talk life about office hours. And I will talk a little bit more about the details in a second.
1:55
So let's get started with lecture one and I will go through my slides and talk a little bit more about the course and the other machine learning related topics.
2:11
So first let us start with. The course itself, let us talk about, yeah, the course content and what
2:18
we are going to do this semester. So I divided the semester into seven parts.
2:25
You know, we will be spending a lot of time together until mid December. So I thought it makes sense to split it up into kind of parts or modules here.
2:35
So in the first part, I'm going to give you an introduction, um, like explaining you something about the cost, like right now, um, talking about machine learning
2:44
itself, and then also giving you a simple example of a machine learning algorithm called K nearest neighbors.
2:52
After you got a taste of what machine learning is. I'm going to cover some of the computational foundations.
3:01
And with that, um, I mean, I will give you a very, very short introduction, short
3:08
intro to Python, and then talk about and.
3:17
So I could learn. So most of you have taken, um, introductory programming class.
3:27
That is one of the requisites for this course, the cost. Um, and this course will be using Python.
3:34
Although I know not everyone has experienced with Python. It's I think very easy to learn.
3:39
I mean, there's a reason why Python is so popular. It's probably the most easiest programming language to learn.
3:45
We will not be using Python very extensively. I mean, we will be using Python extensively, but, um,
3:51
I mean that we won't yeah. Use all of its features. So for this class, it will be sufficient to have a very
3:59
basic understanding of Python. Um, because most of the time we will be using specific libraries in Python.
4:07
That is non-pay, which is the linear algebra library and psychic learn, which is the main machine learning library that we will be using.
4:15
We will be implementing some machine learning algorithms from scratch using num PI.
4:20
Um, and there are also some other libraries that will be important, like MedPro for plotting graphs.
4:28
Um, but yeah, that is something we will. See then in part two and as a voluntary homework exercise, I highly recommend it.
4:37
Also. I will post some interactive exercises on canvas that you can do to prepare yourself
4:43
if you don't have a Python experience yet, but don't worry too much Shabbat.
4:49
It usually all the students did fine. I mean, in previous years, instead of four 79 students who didn't
4:56
have Python experience, they. Were able to learn it like in a couple of days.
5:02
So of course they were not expert programs, but it's also not required in this course because the focus is more on machine learning.
5:10
Okay. After the computational foundations, I will talk about tree based methods.
5:16
That means decision trees, random forests, great boosting. These are certain types of insomnia will machine learning algorithms and so forth.
5:27
After the tree based methods, we will talk about model evolution. I think that's a very important topic which was by, we will be spending
5:34
quite some time on that topic. And the reason why I think this is important is that
5:39
it allows you to compare. Machine learning algorithms and models fairly.
5:45
So if you, after this class, want to learn about some other algorithms or train some models and you want to use them in a real world application, you usually want
5:54
to know which model performs better, or which algorithm you should consider and how you compare different algorithms.
6:01
So for that, um, yeah, we need to evaluate models and algorithms, and that will be
6:07
covered in parts for, um, After part four, we will go to part five dimensionality
6:16
reduction and unsupervised learning. Um, don't worry about the term unsupervised learning yet.
6:22
It sounds maybe a little bit fancy right now. We will talk about that shortly in this lecture.
6:27
So just for context, this will be naturally supervised learning, and then
6:37
we will have unsupervised learning here. After that I hope we will have some time left and so that we
6:44
can cover Basie and learning. So basically learning no, that's like an umbrella term for just
6:52
methods relying on base theorem. So with that, what I am planning to talk about is space optimal classifiers,
6:59
but also a naive based classifiers and also based in networks if there's time.
7:04
But yeah, I, um, Hope we will find the time, if not, well, I will probably just give you a brief taste of busy in learning, but
7:11
we'll see how the semester goes. And then at the end of the semester, we will have your
7:18
class project presentations. I will talk about the class projects more later in the semester, but I
7:24
will also give you a short overview of what that means in a few moments.
7:30
Cause I just uploaded the website, the course website here, where I also have some more information about everything related to this class.
7:38
And we can go through this briefly. Um, I highly recommend that you also carefully read through this document
7:44
and then also ask me any questions during office hours on Piazza.
7:50
Um, yeah, for that, the reason also why I made this an online website and why it's not on canvas is there are currently many students.
7:57
On the waitlist and the waitlist just students don't have access to canvas yet.
8:03
So I thought for those who, um, yeah, still on the wait list, it might be good to have this resource in a way that they can also repeat it anyway.
8:11
So let me go to this link and talk a little bit more about the course contents.
8:18
Okay. Let's see what we have here. So there is a lot of content, so you can see there's a long.
8:24
Table of contents here on this website. Um, yeah, I recommend reading through all of it, but let me
8:29
just give you the highlights here. So at the top, because that's usually what people mostly ask
8:35
about these other course topics and, um, it's not really a calendar. It's just like, um, By my lecture.
8:42
So I have a lecture, one, two lecture, 19 mapped out here. So that's my plan. It's just a more detailed version of what I've shown you in the slides.
8:50
So the seven parts introduction, computational foundations, and so forth.
8:58
The corner, this description, that is something you probably already have seen in the course syllabus.
9:03
Um, the one on enroll.wisc.edu. So I don't really need to go through this because if you are
9:09
already enrolled in this course, you per, he should know about this. Okay.
9:15
Next cost information, resources and communication. That's the important part. So for this cost, we will be using canvas.
9:22
So I thought just using fewer technology of your tool tools will make it, I
9:29
guess, more manageable for you because you will be taking several classes and having all the content for one class in one canvas costs maybe makes the
9:37
everything a little bit easier for you. So if I go to canvas, well, I don't really want to leave the site here.
9:47
Okay. Let me. Not sure what's going on. Let me cancel this and go to canvas manually.
9:55
Alright. Canvas seems to be slow today. Great. Um, the, um, so four or five one.
10:09
So I won't just show you the student view for now.
10:20
So right now, what you can see here, um, is the menu menu bar.
10:26
That's the important part. And for every week I will post the material and, uh,
10:33
like this module thing here. And right now there's only my welcome message.
10:39
And. Little getting to know your quiz. So here, I just set up a simple quiz where I'm just asking to introduce
10:47
yourself, which is, I think Naya saw that we can get to know each other in the context of this course. So that helps me understand what your programming background is and so forth.
10:56
This is not graded. This is M Wallen quiz, so you don't have to complete it, but
11:01
I would really appreciate that. So that's yeah, some basic information.
11:07
Um, what do you think about machine learning, what your background is and so forth, but again, this is not graded, but it would just help me to understand
11:15
my audience because this semester is a little bit weird because we have everything online and not in person.
11:21
So just to make this a little bit nicer to getting to know you would be nice if you could fill out this quiz.
11:27
Okay. Um, yeah, so most of the information, like I said will be on canvas.
11:34
And that's also including lecture videos and so forth.
11:39
So like I said, I will have these modules here set up.
11:45
You should just, if you go to home, you should just see the modules that may leave the student view for now, because I already
11:52
prepared the lectures for week one. It is really slow here, huh?
12:00
Okay.
12:05
So this is also just an explanation while I just mentioned everything will be on canvas.
12:12
There will be links to let's say, get hub. Files, for example, the code examples and homework, I will upload them to
12:20
get up because they are coding files and it will be easier to view them. And also update them get up is a very common way for machine learning
12:29
researchers to share their coat for their papers, for their research papers. So I rethink this is also useful for you to familiarize yourself with the
12:38
typical environment that a machine learning researcher would work with.
12:43
Alright. So what I wanted to show you is week one. So I will create one page, one canvas page for each lecture content for each week.
12:51
So this is week one. And after that, I will, at some point create week two, week three, and so forth.
12:59
Right while it's loading. I can maybe talk a little bit more or scroll through here.
13:05
Yeah. Also assignments will be submitted through canvas and platin announcements here. I will also make why canvas, because I think Wiscon UWU is, um, retiring the
13:16
WISC dot lists system, the emailing lists. So in a way we will use canvas announcements.
13:24
You can click on the announcements to see all the announcements, but also check your emails.
13:29
So every time I send out an announcement that you should receive an email, if you don't receive an email, if you haven't received the email for the
13:39
latest announcement I made yesterday. Please check your canvas settings so that you also receive these emails.
13:46
There may be at some point something important to share. So it would be good that if you keep up to date with announcements, there
13:53
could be something like on, I dunno what you hit, but there might be something important at some point.
13:58
So please enable the notifications for the announcements. If you don't or if you didn't get this announcement yesterday,
14:05
if you got it, then it means you announcement notifications are enabled.
14:11
So this is I'm going back to the pages week one, the
14:16
lecture overview for week one. So I will post links to the slides and to the lecture notes, the lecture
14:25
notes you can read after the class, not every week, it will have lecture notes. It's just for your convenience.
14:31
So for some lectures, I wrote my lecture notes first, and then I did the slides. So this is why I have them. But.
14:37
For certain weeks, I won't have lecture notes. Um, yeah, I recommend downloading the slides before you watch the videos.
14:45
So you can take notes on the slides. Usually students find that very helpful. If you can always you take notes on the slides or next to the slides.
14:54
Um, yeah. And then I will have the videos and you can see here, things are not working.
14:59
Um, this is because we are in Safari here. I try it. Uh, these.
15:05
Oh, there's option three here, but it still didn't work. So what I recommend for canvas for this class, or in general
15:12
is using Firefox or Chrome. So I have the same page here and I will show you that this hopefully works.
15:24
Okay. So usually the videos should lot now also I should mention.
15:29
Yeah, then we are so. Last couple of days. I also had problems with loading the videos on and was because
15:37
this is using Katurah media. And I think this is because the semester started at a lot of
15:42
universities at the same time. And I think either canvas or Katurah media was a little bit
15:47
overwhelmed by the number of. People using it. So I will probably also applaud at least in the first few weeks
15:55
until they sorted things out. I will probably also upload the videos to YouTube. So I try not to have backup links.
16:01
So if for some reason, Katurah media doesn't work in canvas here. Then you can also watch them on YouTube.
16:08
You can also download them here. So, if you have a slow internet connection, you can download the videos
16:13
and once they finished downloading, you can watch them on your computer. Um, you can also, for most of them, you should be able to control the quality.
16:22
Okay. I, I'm still in the process of creating this first page. So this is why it looks a little different than two versions.
16:28
One with the donut button and one without the dot line donut button. But I will add the donut button for all of them.
16:35
And yeah. Um, I will, of course the video I'm recording right now.
16:40
I will insert it here yesterday. I already recorded it, but I disconnected my good microphone.
16:46
That means I have two microphones. Um, it was just using the built in one and the quality was so poor.
16:51
I first posted the video, but then I thought, okay, I will just rerecord it because it was so bad. Okay.
16:58
Yeah, anyways. Um, I will add to the video I'm recording right now, right here. And this will be the first week's content.
17:08
Okay. That will be some homework at the bottom. So I will also add some homework.
17:13
Um, next questions. So four questions.
17:20
We will be using Piazza. So Piazza is a forum that is also embedded in canvas.
17:28
Let me go to the Firefox version. So if you go here to the left hand side, there's a tab called Piazza, and this is
17:38
just an online forum for asking questions and, um, for general questions, that would be great if you could use that.
17:45
Uh, I really prefer that over emailing me because I get so many emails every day.
17:50
From all kinds of people. So that, uh, that I don't always keep up with email.
17:55
I'm not able to, because otherwise I wouldn't find the time to make the lecture content. So, but I will be checking Piazza and on Piazza, there are different options.
18:06
You can post things to the entire class or to individual students or instructors.
18:11
So I prefer if you have a general question about the cost to ask that for the entire class, that means yes.
18:17
Um, everyone will be able to see the question because often students ask questions that are important for everyone.
18:24
For example, if there's a question, Hey, can you clarify when the exam is or something like that, it would be useful for other students to know that too, if
18:31
they had a question so I can answer it and other students can see it, or if you have a question about the lecture content, however, if you have questions that.
18:41
Let's say include partial solutions to the homework or your homework solutions. And you want to show me some aspect of it, then please don't
18:49
share it with the entire class. So Don share solutions with the other people in the class for that
18:54
you can use the instructor here. So you can, I think if you type my name, oops, if you type my
19:01
name here, you should be able to. Ask me the question directly.
19:07
Alright. Um, let's think, let me try. Let's try. I'm not sure thing because I'm an instructor right now.
19:16
It doesn't work, but for you, it should work if you type that. Um, okay.
19:24
What's next course. Logistics. Yeah. Everything will be online.
19:29
Um, my name is Sebastian Russia. If, uh, Yeah, you didn't know yet.
19:34
So I will be your instructor. Our teaching assistant this semester will be Junger.
19:39
You. He will also introduce themselves very shortly. I will have office hours every Thursday, unless there's an
19:47
exception from four to 5:30 PM. And we will also be using the tool that is in canvas.
19:55
It's called BB collaborate. It's a video conferencing tool. So you can find it also here on the left hand side.
20:02
So just clicking on it, blips.
20:12
And then yeah, you will be able to join the office. Just see it says 5:00 PM. I will change it to 5:30 PM.
20:22
Alright, so this will be live office hours. So in that way you can ask me questions live in tactively resources.
20:31
So. It would be, so there's no required textbook for this class, but it would be helpful.
20:36
I think, for you to take a look at certain chapters of the Python machine learning book.
20:42
Um, because for my lecture slides, I'm familiar with this book because I was writing this book.
20:49
So I was using a lot of figures and topics from this book. So the lectures are kind of inspired by this book, but
20:55
yet they are quite different. However, I still think. Um, the book would help you with certain aspects about psychic learn and num
21:04
PI writhe, regard to machine learning. I will ask an each, um, week I will post also links and chapter recommendations.
21:16
Python resources. So, like I mentioned before, some students haven't worked with Python yet, and I
21:23
thought it might be useful to have some basic resources for you that you can quickly brush up on your Python skills.
21:30
Um, so the ones, I try to select one resource from each category.
21:36
So there are video lectures. I thought these were really nice and accessible. A relatively new video series by people at Microsoft it's available on YouTube.
21:46
Then there are the interactive tutorials learn Python tutorials, and I will,
21:53
uh, does as an optional homework. Also, these, some of these exercises for week one.
21:59
And then if you prefer books, I found illustrated guide to Python is a pretty accessible book.
22:07
There's another resource and it's also pretty nice. It's um, uh, and Indonesia, I think Python, the second edition,
22:14
there's a PDF version available year, and there's also Python. Like you mean it, which is also, um, good online tutorial, but yeah, of course you
22:24
don't have to go through all of that. Just pick maybe one resource that fits your learning style best.
22:31
Regarding the grading. So that will be the problem sets exams and class project.
22:38
So problem sets we'll be homeworks, but I will also make some small
22:43
quizzes throughout the semester. Um, yeah, the exams that will be one midterm exam and one final exam.
22:49
More on that later. And the class project will be divided into three parts, a project proposal, a project
22:56
presentation, and a project report. And I will also talk more about this later on.
23:02
Here's a bit more about the plant grading scheme, but of course you to COVID-19 it's a little bit hard to.
23:09
Predict how well you all will be doing online this semester compared to let's
23:14
say the regular in person classes. So, um, if I noticed for example, that the grades are really bad this semester,
23:19
for some reason, I will also consider curving the grades this semester. But, um, this will be, we will be using this grading scheme unless maybe I, um, I
23:29
noticed there's something weird about it. I just see, I should update this. This should say, uh, 900 2,880.
23:38
840 and so forth because, um, the number of points is 1000 in this class and the
23:47
percentages are corresponding to that. So dividing this number by 10, then you get the percentage.
23:53
And you can see this was what I use planning to use, but because of COVID-19, I lower the threshold from 93% to 92 from 92, 88 and from 85 to 84.
24:05
But I just forgot updating it. I'm making a note here on my piece of papers.
24:11
I will not forget updating the greats. Okay.
24:18
Um, exams. So the exams will be at a specific time.
24:23
This would be our lecture time if it was a in person session. So the midterm exam will be on third, say October 15th,
24:30
between four and five, 15:00 PM. And I will on canvas as a quiz.
24:36
And the final exam will also be a quiz on canvas. And that will be on December 20th, 14th, the Monday between
24:44
ten five and 12 5:00 PM. For the class project that is usually the most fun part.
24:52
This is what students like most about this class. Also, it's usually the part that is mostly creative, where you get
25:00
to design your own machine learning project, like a little research project, and then you will work with.
25:06
Three students or in a team of three students on this class project. And this entails writing a proposal.
25:14
That's a two to three page proposal that is due mid semester. I will give you the date later.
25:22
And there, this, um, proposal where you are telling me what you're planning to work on, and I will give you some feedback and tell you whether that's a good idea or
25:29
not, or maybe also make some suggestions. And after the proposal you start working on your project.
25:35
I mean, you can also start a little bit early if you like, but yeah, after the proposal, you would start working on that project and carrying
25:42
out what you proposed and at the end of the class, um, the last couple of days of class, uh, I will ask you to.
25:50
Give a presentation and for the other students. So we'll have some, it's like little conference talks where you present your
25:56
project in a talk and then also submit a final project report, six to eight pages, which looks a little bit like, um, small research paper and, um, For that,
26:09
I set up some proposal latex files and we will be using Natech for the proposal and the report, because that will make things more consistent and similar to
26:18
using GitHub that I mentioned earlier, it will also introduce you to the real world environment that machine learning researchers use, because usually in
26:27
statistics and machine learning, we use LayTec to write our reports and papers.
26:33
I will give you an example report. I will make a note, um, Part example so that you can take a look at what other
26:43
students did in previous semesters. So you get a better feeling for how the report will look like, but of course
26:50
the report is due at the end of the semester in three and a half months. So don't worry too much about it yet.
26:57
Um, so these are just some grading guidelines for the report. Um, the assessment and so forth, you can read through this later
27:04
when the time comes the project presentation, this will be a eight to 10 minute presentation in class.
27:10
On this semester, it will be recorded and we will post that to canvas.
27:16
And here's just an example of previous talks that students gave
27:21
last semester in the deep learning class at a slightly different class, but the format is very similar.
27:27
And yet these students volunteered to have their talks on YouTube. Of course, this is not a requirement, just optional students
27:36
wanted to have them on YouTube. So that what's a nice thing to do. So you can take a look at.
27:43
Um, let's try the introduction. Uh, some of the previous projects that the students worked on
27:49
and how they presented them. Alright,
27:58
so there will be three of warts, one best oral presentation award, the most creative project award and best visualization award.
28:06
So other students will. Basically assess your talk and then we will have some smaller awards, which is,
28:12
I think also cool, motivating thing to do. Yeah. There's a lot of the assessments, or you can read through this
28:19
later when the time comes. All right. So other important cost information.
28:26
So I will have a late submission policy the semester, and this is mainly due to
28:31
maintaining fairness because some students work really hard to make the deadlines. So it would be unfair towards the students if some students submit things late.
28:40
So for up to six hour late submission, that will be a 10% deduction
28:46
of the maximum possible points. If you submit submitted six to 24 hours, late hour, 20%.
28:54
And if you say more than a day, late, more than 24 hours late, and there will be no points for either homework or other class related submissions.
29:02
This is just to maintain fairness because some students work really hard to make the deadlines and it would be unfair towards them.
29:09
Yeah. If some students submit the homework late, Okay. Um, then there are some other important, um, considerations.
29:18
So the rules, rights and responsibilities, uh, academic integrity.
29:24
Accommodations. So you should, um, please also read through all of that. This is, uh, starting from here to the bottom.
29:31
This is not something I have written. This is the campus guidelines. So chances are, you have already seen that.
29:37
Um, if you have not seen that, it's very important that you read through this and, uh, familiar with what we expect at UWA medicine, how you should conduct
29:47
yourself in terms of academic integrity and what accommodations we provide.
29:53
And also how we, um, guarantee diversity and inclusion. It's also very important.
30:00
So this semester we have, uh, yeah, unfortunately, an online semester and
30:05
the current challenges with COVID-19. So this is also from the campus guidelines. If you are new to campus and you have not seen this in another syllabus pre uh,
30:15
please also read through these guidelines. Okay with that, I will end the video now and because it's already very
30:24
long, but in future, I will talk more about the class project homeworks and so forth when the time comes.
30:30
I just don't want to overwhelm you at this point yet. Alright, then, um, I will see you maybe at the office hour on Thursday.

##v2:

0:00
okay now after we covered the logistics
0:02
of
0:03
this course let's get to the more
0:04
interesting parts and
0:06
talk about machine learning and learn
0:08
what machine learning is
0:10
so what is machine learning for that
0:12
let's
0:13
look at some i would say interesting
0:16
quotes so one quote is by john
0:19
hennessy a former president of stanford
0:22
and
0:23
he basically said machine learning is
0:25
the hot new thing
0:26
so it sounds like machining is something
0:28
cool but of course it doesn't really
0:30
tell us what machine ring is
0:32
so let's see what bill gates has to say
0:34
about that so
0:35
bill gates said a breakthrough in
0:39
machine learning would be
0:40
worth 10 microsoft's so based on that
0:43
statement it sounds like machine
0:45
learning is something pretty important
0:47
so what is it really i really like this
0:50
quote by rana
0:51
l kalubi and uh yeah she's a co-founder
0:54
at
0:55
effectiva and ceo of effectiva which is
0:58
a company focusing on
1:01
recognizing emotions from images and
1:03
videos
1:05
i agree i mean it can be a little bit of
1:07
a controversial topic like to
1:09
recognize emotions from face images and
1:11
things like that
1:12
but uh yeah if you're interested search
1:14
for some of
1:15
her interviews and she makes a pretty
1:18
good and compelling point
1:20
why this is actually sometimes really
1:21
useful so anyways
1:23
what she said is learning is a
1:26
subcategory within the field of computer
1:28
science
1:30
which allows you to implement artificial
1:33
intelligence
1:34
so what this basically says is um
1:36
machine learning helps us to
1:38
create artificial intelligence so
1:42
actually then says so it's kind of a
1:44
mechanism to get you artificial
1:46
intelligence
1:47
so machine learning and um
1:51
machine learning and artificial
1:53
intelligence they are closely related
1:56
and in fact machine learning
1:59
was originally created with a desire to
2:02
create artificial intelligence so
2:03
artificial intelligence is
2:05
much older it's a older field
2:08
and in order to implement artificial
2:10
intelligence researchers developed
2:12
a couple of approaches and one of the
2:15
promising approaches was
2:16
using machine learning so here based on
2:19
this slide
2:20
we kind of learned as a relationship
2:22
between machine learning and artificial
2:23
intelligence
2:25
today so back then
2:28
i would draw the relationship like this
2:30
where we have
2:32
artificial intelligence and machine
2:34
learning as a
2:36
subfield nowadays i would say it's
2:38
rather
2:39
like this where we have um
2:42
the big field of ai and machine learning
2:45
is
2:47
uh intersecting with
2:51
ai because there are many machine
2:53
learning approaches
2:54
applications that i would say are not
2:56
necessarily
2:57
ai and we will see some of them also in
3:00
this class or
3:01
in this course so nowadays i think the
3:04
fields are of course
3:05
very closely related but not um i would
3:08
say not all of machine learning is ai
3:10
but a large a very large portion of
3:13
machine learning is actually ai in any
3:16
case let's get a little bit
3:18
uh more precise now what machine
3:20
learning actually is
3:24
so in order to explain machine learning
3:26
i uh really
3:27
like this quote this is actually a
3:29
classic that you can find also in most
3:31
online material or other materials about
3:33
machine learning and i guess it's so
3:36
often used because it's actually really
3:37
concise and really captures
3:39
the idea of machine learning so
3:42
what arthur l samuel said is that
3:46
machine learning is the field of study
3:48
that gives computers
3:49
the ability to learn without being
3:52
explicitly programmed
3:54
so what we have here the key words are
3:58
the ability to learn
4:02
without being explicitly programmed so
4:05
there's also an aspect mentioning
4:09
programmed and here with machine
4:11
learning we want to achieve something
4:13
without having something be programmed
4:16
explicitly
4:18
so what does that mean
4:22
here so in order to understand the
4:24
previous quote
4:25
i have a flow chart or a diagram here
4:29
to illustrate the traditional
4:31
programming paradigm so with traditional
4:33
i mean
4:34
just a yeah i would say regular software
4:36
development
4:37
cycle so that's for the sake of the
4:40
example to make this a little bit more
4:42
i would say um yeah to visualize this
4:46
with a concrete example let's assume we
4:48
want our task is we want to implement an
4:50
email spam filter
4:52
let's say our task is uh
4:55
implementing an email
4:58
spam filter and we have an email program
5:01
and we want to now
5:03
develop a let's say a separate program
5:05
that filters our spam
5:07
and um in order to illustrate that let's
5:10
walk through it step by step
5:12
so if we have an email spam filter we
5:14
have some inputs
5:16
so in this case our inputs would be
5:19
the emails that we want to filter or
5:22
recognize a spam and not spam
5:26
and the program that we want to develop
5:27
this is our
5:30
spam filter and
5:33
the inputs in order to develop this
5:35
pamphlet and the traditional paradigm
5:37
we look at the email so we as the
5:40
programmer
5:40
we take a look at these emails and see
5:43
okay
5:44
what makes them different or what makes
5:46
spam
5:47
email different from non-spam email and
5:49
how
5:50
could we maybe implement some rules to
5:53
distinguish between them
5:54
and that takes actually a lot of work so
5:56
we have to read ideally a large number
5:58
of emails
5:59
do a lot of thinking and comparisons to
6:01
find out what makes them different and
6:03
what do spam and non-spam email have in
6:06
common so we don't
6:07
accidentally classify something as spam
6:09
and so forth
6:10
but let's say we looked at 10 000 emails
6:14
came up with some good um rules we can
6:17
then write our program our spam filter
6:19
which is basically a bunch of rules like
6:22
in traditional programming a
6:23
bunch of if else statements
6:27
basically um and this is our spam folder
6:29
that goes
6:30
then to our computer so well it's
6:32
implemented on our computer
6:33
the computer itself executes this and
6:36
then classifies
6:37
the emails as
6:41
oops classify
6:47
spam or
6:51
not spam so our outputs would be the
6:55
labels
6:55
spam and not spam so that's the
6:58
traditional paradigm
7:00
so how on how does machine learning now
7:02
come into play
7:04
so how is machine learning related to
7:05
that traditional paradigm
7:10
so machine learning helps us to
7:13
do this more conveniently or
7:15
automatically so
7:16
the computer now has the role of
7:18
developing the spam filter
7:20
so before we as the programmer we
7:22
developed the spam filter so again
7:24
so this top part is just the same as i
7:27
showed you on the previous slide so this
7:28
is the
7:31
traditional paradigm
7:37
and here at the bottom so
7:40
this part this is basically machine
7:42
learning so what do we have here what's
7:44
different between the traditional
7:45
and the machine learning paradigm so
7:48
here
7:49
notice that we have now the outputs on
7:51
the left hand side
7:53
before they were on the right hand side
7:55
and yeah that's basically the only
7:57
difference so we
7:58
have here a data set that is labeled
8:01
later we will see not all machine
8:03
learning algorithms are about
8:05
labeled data sets some approaches exist
8:07
also to work with unlabeled data
8:09
the goals a little bit different but now
8:11
let's say we have this
8:13
approach where we have labeled data with
8:15
that label data remember
8:17
the outputs previously they were the
8:19
spam
8:21
and not spam
8:24
so again here the outputs are spam
8:28
and not spam these are our labels
8:32
for our emails so we have now a data set
8:35
consisting
8:36
of emails and the correct classification
8:40
the correct spam and not spam email and
8:42
such a data set could be created for
8:44
example by
8:45
um yeah taking a look at your inbox and
8:48
labeling the emails let's say you go
8:50
through again 1000 emails
8:52
you label them but now in contrast to
8:54
the previous
8:55
paradigm here let me use a different
8:58
color
8:59
here you develop the rules so here you
9:02
developed
9:03
rules as the program but now
9:06
we let the computer develop the rules so
9:09
we have the
9:09
computer look at the labels the spam and
9:12
not spam
9:14
look at the emails and come up with a
9:17
spam filter here
9:20
and it's learning
9:24
the spam photos so the computer doesn't
9:25
does the learning work now
9:27
so instead of us instead of us having a
9:30
look here
9:31
at all the emails the computer now looks
9:34
at um
9:35
labeled examples of emails and then
9:37
develops the program
9:38
which is so i should have um yeah so
9:42
this is the process of learning the spam
9:43
filter
9:44
and what comes out of it is the spam
9:46
filter
9:47
so here the computer has now the role of
9:50
learning from looking at
9:52
examples that we provide so yeah that is
9:54
uh machine learning in a nutshell i
9:56
would say
9:57
let me briefly follow up on the previous
9:59
slide
10:00
so there's a very i think important
10:03
quote by faith
10:04
lee so what she said is we will not only
10:06
use the machines
10:08
for the intelligence we will also
10:10
collaborate with them
10:11
in ways we cannot even imagine and i
10:14
think the previous slide may
10:16
may have made it look like that machine
10:19
learning is
10:19
there to replace humans but i think this
10:22
is not really true i mean
10:24
in some cases yes but it's not entirely
10:27
replacing all kinds of human labor i
10:30
mean there are cases where it makes
10:31
sense to use machine learning and there
10:32
are cases
10:33
i think where it really doesn't make so
10:35
much sense to use machine learning
10:37
for the email example that i showed you
10:40
on
10:40
discussed in the previous slide i think
10:42
it's really uh
10:44
yeah still we are still developing
10:47
programs that we like to use
10:48
so you can maybe imagine in a distant
10:52
future that some computer is developing
10:54
or some machine learning algorithm is
10:55
developing an email program
10:57
but i think um nowadays
11:00
we are not even close to that yet and we
11:03
have
11:03
people thinking about okay what is good
11:05
usability what do i want what features
11:08
do i want
11:08
and we have programmers designing email
11:10
applications or email interfaces
11:13
however we can use machine learning to
11:16
make the life of the programmer easier
11:18
so instead of having the programmer to
11:21
read through 50 000 emails and deciding
11:23
what is spam and what is not spam
11:24
maybe maybe maybe uh making bad choices
11:27
we can have a computer
11:29
doing maybe a better job at that and
11:31
making the life of the programmer easier
11:32
by
11:33
developing the spam filter by learning
11:36
by machine learning so that way we free
11:39
up the time of the programmer to focus
11:40
on other things
11:42
and also don't have the programmer doing
11:45
like boring things like reading through
11:47
50 000 emails and making decisions about
11:49
spam and what's not spam
11:50
so that way we can use machine learning
11:53
to enhance
11:54
certain workflows not really entirely
11:56
replace them
11:59
okay but now back to the definition of
12:01
machine learning
12:02
so if the previous slide was a little
12:05
bit
12:05
confusing where i was drawing the flow
12:08
chart or the
12:09
diagram maybe i can help you making this
12:12
more confusing
12:13
so um no i'm just kidding so i just want
12:16
to offer an alternative definition
12:18
and this is by tom mitchell so he
12:20
described the
12:21
learning process so the process of
12:23
learning as follows he said um
12:26
a computer program is set to learn from
12:28
experience e
12:30
so this is the experience with respect
12:33
to some class of tasks t so we have
12:36
tasks t
12:38
and performance measure p if its
12:42
performance
12:42
at tasks in t
12:46
as measured by p improves with
12:49
experience e
12:51
then this is the learning process so we
12:53
have
12:55
some tasks and we learn
12:58
basically from the experience and we
13:01
measure
13:02
some performance p and we want to
13:06
learn from the experience to become
13:07
better at task t
13:09
and this has to be some way we can tell
13:12
that we
13:12
make progress and that is the
13:14
performance measure and there are
13:16
many different types of tasks many
13:18
different types of
13:20
performance measures and the experience
13:22
itself is basically
13:24
in the case of machine learning like
13:25
learning from the data
13:27
so like i said this can maybe be a
13:30
little bit more precise
13:31
because we have now some yeah letters
13:34
here
13:34
so in mathematics you know natural
13:36
symbol symbols help making things more
13:38
precise
13:39
i'm not sure if that's necessarily true
13:40
for that quote but i think it really
13:42
defines machine learning or the learning
13:44
process nicely
13:46
so in order to yeah kind of make this
13:49
maybe more clear let me um give you an
13:51
example a hands-on example
13:54
so here that is a handwritten
13:56
recognition example
13:57
so what we have is the mnist data set
14:00
it's uh
14:01
m nist so that is a data set consisting
14:05
of
14:05
50 000 images
14:09
handwritten digits the digits are zero
14:12
to nine and there are handwritings so
14:17
there are if there are 10 classes and
14:20
they are uniformly distributed in this
14:21
case
14:22
we have 5 000 images per
14:27
digit so here on the right hand side i'm
14:30
just showing you an example of
14:31
each of each digit
14:34
so this is an example of the letter zero
14:36
one and so forth
14:37
and for a human of course it's very easy
14:40
to
14:41
tell what digit that is but yeah for a
14:43
machine
14:44
we have to teach it to recognize what it
14:46
is so
14:47
now maybe as a optional exercise maybe
14:51
pause the video and think about
14:54
how this handwritten recognition example
14:57
maps to
14:58
the definition by tom mitchell where we
15:00
have the task t
15:01
the performance measure p and the
15:04
training experience e
15:05
so maybe pause the video and think about
15:07
it a little bit and
15:08
uh then continue
15:12
okay after yeah pausing the video and
15:15
thinking about it a little bit
15:17
i hope you have some ideas of what the
15:19
task t
15:20
could be and it's actually just here the
15:23
handwritten
15:24
digit and recognition so here it would
15:26
be the
15:30
hand written
15:35
digit classy
15:40
classification
15:42
um we can also say handwritten digit
15:45
recognition but classification is the
15:47
usually the more common term in the
15:49
field of machine learning
15:51
and we will also see exactly how this is
15:53
defined in a few moments later in this
15:55
uh or in the next video actually
15:58
so next the training experience e
16:02
so that would be the 50 000
16:06
images and they are
16:08
labeled so they are labeled images
16:11
labeled means again that we have the
16:13
information available in the data set so
16:15
we have
16:16
the images and and also the labels 0 1
16:19
2 3 4 five six seven
16:23
eight nine so that we can show the
16:26
computer the images but also
16:28
the computer has the information about
16:30
the labels to learn
16:31
uh to associate a given image consisting
16:34
of pixels
16:35
with a given class label so now the
16:38
performance measure p
16:39
what could that be and that is maybe
16:41
something uh
16:43
you or we could discuss in a discussion
16:45
forum so maybe uh
16:47
i suggest you open a new question on or
16:50
new thread
16:50
on the piazza
16:55
forum on canvas and then we can uh have
16:57
a discussion maybe i will let you go
16:59
first you make some suggestions and
17:02
other students can maybe chime in and
17:03
discuss what the performance measure p
17:05
could be that would be a good exercise
17:08
to yeah double check
17:09
whether yeah what your ideas are and
17:12
what possible performance measures we
17:14
could use and
17:16
maybe what are the advantages and
17:17
downsides of different performance
17:19
measures
17:20
so that is maybe a good question for
17:22
piazza before i
17:23
provide you with this information
17:27
okay lastly some applications of
17:29
machining we talked a little bit about
17:31
the email spam filters so that would be
17:33
um
17:34
one application email spam
17:39
versus uh none
17:42
spam classy
17:46
vacation uh many many other examples of
17:50
machine learning uh in fact i would
17:53
honestly have a hard time thinking about
17:55
anything
17:56
nowadays any like software or
17:59
application that is not using machine
18:01
learning
18:02
so maybe another intuitive example would
18:04
be sorting letters
18:06
in the post office it's just related to
18:08
the handwritten digit
18:10
classification example from the previous
18:12
slide so for example if we have a
18:13
postcard
18:15
with a classic post stamp then
18:18
on the sender's address and then
18:22
the address where it has to go there's
18:24
usually a zip code for example
18:26
i think the university's zip code would
18:28
be five three zero
18:30
no five three seven zero um
18:34
four or something so let's say you have
18:36
written the
18:37
zip code on the letter at the post
18:38
office um
18:40
the they receive a lot of letters they
18:42
go to different cities in different
18:43
states
18:44
so it would be kind of efficient to have
18:45
an automatic sorting system and that is
18:48
something where you have the handwritten
18:49
digits could be computer printed but
18:51
also handwritten and you have a machine
18:52
learning algorithm
18:53
yeah recognizing these digits and
18:55
sorting them another classic example is
18:58
you have your smartphone
19:01
and you have like a little camera there
19:04
and nowadays you don't have any buttons
19:05
but you have just a
19:06
screen usually the screen goes edge to
19:09
edge so you just
19:10
if i would draw a modern smartphone it
19:12
would just be a square with a little
19:13
circle here for the camera
19:15
and it usually unlocks if it sees your
19:18
face
19:19
so there's some face
19:22
recognition going on it's also one of
19:25
the areas i'm working on my
19:27
research areas i'm working on face
19:29
recognition in any case that would be
19:31
also a typical example of machine
19:32
learning
19:33
there are many many other examples um
19:36
could go on and on and on but that is
19:38
maybe also an interesting um
19:40
yeah threat for piazza so maybe on
19:43
piazza
19:44
open a new discussion thread and have a
19:46
discussion with the other students and
19:48
maybe come up with some ideas um i will
19:50
chime in then and maybe
19:51
provide you with more ideas or also
19:54
maybe just discuss
19:55
some ideas you have related to machine
19:57
learning whether it's a machine learning
19:58
application or maybe not
20:00
um yeah so maybe that's a cool question
20:02
for piazza too
20:06
okay so in the next video we will talk a
20:09
little bit more about the different
20:10
categories of machine learning

##v3:

0:00
So we learned about machine learning.
0:02
Let's talk a little bit more about the different categories of machine learning
0:05
or different types of machine learning.
0:08
The broadest or biggest category of machine learning is supervised learning
0:14
supervisor learning deals with labor data.
0:17
And in the case of the email spam classification, the
0:21
labels were spam and not spam.
0:27
And what do we want to do is we want to predict the output.
0:31
So come and the outcome is.
0:34
Also the label itself.
0:36
So we want to predict whether an email is spam or not spam on future emails.
0:41
And there's also a direct feedback loop.
0:43
So if we make a correct or wrong prediction, we use that information
0:46
to, uh, improve the algorithm to make a better classification.
0:51
So like I mentioned before we have, uh, the term, or I said
0:55
the term before classification.
0:56
So one sub category of service learning is classification.
1:02
So that is about learning how to assign class labels in spam and not spam.
1:07
We have the class labels.
1:08
Yeah.
1:08
Not spam, spam and not spam.
1:10
And you make classification in this finger here.
1:13
We have two class labels, mindless and plus, and the goal is to distinguish
1:19
between minuses and pluses, given two, um, types of information X month and X two.
1:25
So let's just imagine this is a.
1:27
Continuous scale between zero and 10 and here's zero and 10.
1:33
We have some numbers here, some measurements and based on the X one.
1:40
Oops.
1:40
So X one and X two information is this data point minus or a plus?
1:48
So that's the goal and what the machine learning algorithm sees is.
1:52
These measurements and it makes a prediction.
1:55
And then we give it the label and say, whether it's right or wrong and all the
1:59
time, the machine learning algorithm will learn how to assign the correct label.
2:04
And after seeing it, none of these examples give them this data set,
2:08
where we have plenty of examples.
2:10
It may learn to draw this line here, which is the decision boundary.
2:13
So if I have then a new data point, for example, let's put it
2:17
here, everything right to the.
2:20
Decision boundary would be classified as a plus.
2:22
So this data point would be likely classified as a plus.
2:26
If we have a data point here on the left hand side, this would
2:28
be likely classified as a minus.
2:30
And the goal really is for the machine learning algorithm here to draw this
2:34
decision boundary, because there are infinite ways to draw a decision Monterey.
2:39
So we could have one in a stake here, but it's maybe not a good idea.
2:42
Maybe here.
2:44
We're here and so forth.
2:45
And usually the machine learning I go to them is all we define it like this.
2:48
We train it such that it minimizes the number of making wrong predictions.
2:54
So in this case here, this one would be a pretty good line.
2:56
I would say.
3:00
Another type of supervised learning algorithm is regression
3:04
or regression analysis.
3:05
So regression analysis, that's also a big field of research.
3:08
As you may know, from statistics that deals with assigning a target or output
3:14
or outcome, that is a continuous value.
3:16
So before our.
3:20
Target that's called target Y and classification.
3:23
That was either the previous case.
3:26
It was either a plus or minus.
3:30
And by the way, it could be more than two classes.
3:32
If we only have two classes that would be, um, this would be a case
3:38
of, we call it binary classification.
3:44
Cause binary from computer science.
3:46
Yeah.
3:47
Yeah.
3:47
The binary value is zero and one or minus and plus in the
3:51
case of the previous slide.
3:52
So that would be a binary classification task where our output
3:55
variable, Y would be, um, class label in regression analysis here.
4:01
Why is the continuous value and the goal is given some input feature.
4:05
So here I only have one input feature.
4:07
So that would be a case, for example, where we may use
4:10
a simple linear regression.
4:12
That's a model with one input variable, and we want to predict the output.
4:15
Y and, um, for example, at least squares regression would learn to fit a.
4:21
The line through these points to minimize the, um, offset.
4:25
So, um, making good prediction based on the mean squared error on all data
4:31
points and the key differences, um, between classification and regression is
4:36
regression deals with continuous venues.
4:38
So the Y here is really a continuous number.
4:41
Could be also, let's say, on the.
4:43
Scale from zero to some arbitrary, let's say 100.
4:47
It depends really on what your data is.
4:48
You can also normalize that.
4:50
Um, so there's like a continuous value, not just, um,
4:53
labeled, like plus and minus.
4:57
Um, we just talked about supervised learning, which deals with labeled data.
5:03
Now another category of machine learning is unsupervised learning
5:08
and unsupervised learning.
5:09
We don't have any labels or, um, we don't have any target information and
5:14
we also don't have any real feedback.
5:15
So we can't really measure how well the algorithm is doing
5:19
and updating it based on that.
5:21
So the goal really here is to find a hidden structure in the data.
5:25
So to have unlabeled data and maybe find some patterns in the data, that's kind
5:30
of the goal of unsupervised learning.
5:34
One example of unsupervised learning is clustering.
5:37
So imagine you have a data set.
5:39
So, uh, where you have some measurements again like X one and
5:42
X two, but you don't have any class information, but you still maybe want
5:46
to analyze something about the data.
5:48
So in this case, if you just ignore the pink dotted lines here, what you would
5:55
have all these different dots on the X one and X two X's, and you can see.
6:01
There are some dots make here.
6:03
They are Clover closer together to each other.
6:05
Okay.
6:05
Petrel dots over here.
6:08
So you may think, okay.
6:09
There's something about the dots that are maybe make them more or related
6:14
to other dots in this plot here.
6:16
So you can say me, this is, um, This is a cluster and maybe this is also a customer.
6:22
So you can, um, assign these cluster, um, justice based on some, let's
6:30
say densities or other metrics or other ways of measuring it.
6:33
There are many different ways of clustering.
6:35
Like k-means DB scan, this density density.
6:39
It's clustering or hierarchical, clustering schemes, and so forth.
6:42
So unsupervised learning is one part of it is, uh, yeah.
6:46
Clustering algorithms, um, that can be used for, for example, if
6:50
you have a data set that is not labeled and you may want to group
6:53
it in different types of categories.
6:56
I mean, there are many, many different types of applications of that,
6:59
just so the idea here is between.
7:02
Well, the difference between supervised and unsupervised learning is really
7:04
that in supervised learning, we have labeled data and unsupervised learning.
7:07
We have to make sense of a data set where we don't have any level information.
7:12
Now that common example of unsupervised learning is dimensionality reduction.
7:17
There are supervised versions of it, but usually it's unsupervised.
7:21
So, um, dimensionality reduction, that is a case where we remove
7:26
or reduce the number of features.
7:30
So I don't want to go into too much detail here because we will have a dedicated
7:35
lecture to this later on in this course.
7:38
So here again, remember, this is just an introduction.
7:41
I just want to briefly go over some examples or techniques.
7:44
So you have the big picture overview.
7:46
So dimensionality reduction, like I said, is compressing features, so that
7:51
are reducing the number of features.
7:53
If we had two features before, like X one and X two, We could reduce that to
8:00
a single feature Z and we could do that by either dropping one of the features.
8:07
All we could combine and transform or mix them in a way that we get a feature Z
8:14
that represents a feature that catch us.
8:17
Most of the information that would be also one of the goals
8:20
of principle component analysis.
8:22
If you've heard of it, we'll discuss this later in this course, in that
8:25
case here, I'm showing you an example, applied to a dataset called Swiss roll.
8:31
It's just a toy dataset, but it's, um, oops.
8:33
It's illustrating the problem where we have three features and we
8:37
want to reduce it to two features.
8:41
While maintaining, let's say the information about the features or
8:45
the neighborhood of the features.
8:46
So here in the Swiss roll, the data points that have a similar color
8:51
are, let's say, closely related.
8:54
And there are algorithms that can remove one of the features by combining.
9:00
So it's, it's, it's merging in a certain way, these features and transforming
9:03
them, such that we only, that we have a new two dimensional space where the.
9:10
Neighborhood between the points that's still preserved.
9:12
So you can see the red points are still very close together,
9:15
similar to here, for example.
9:17
So, yeah, that would be one example of a future transformation.
9:22
We also say, um, feature extraction, feature extractions, a subtype
9:30
of dimensionality reduction.
9:32
The other subtype would be feature selection.
9:36
But we will come at this in way more detail later on.
9:41
So let's get to the last category of machine learning.
9:44
And that is reinforcement learning before we had a labeled
9:50
data set and, or no labels.
9:52
And we were just looking at the data points and just making a decision, for
9:56
example, whether it's supposed to have a certain class label or whether it
10:00
belongs to a cluster or not in the case of dimensionality reduction, we didn't even.
10:05
Assign anything, no cluster or class label, but we were just
10:09
transforming features here.
10:11
Now, when we are learning as a process, like a learning a series of actions
10:17
and for that, we use the reward system.
10:19
So it sounds a little bit, uh, yeah, weird.
10:23
Maybe.
10:23
So let me show you a sketch of how the setup looks like.
10:29
So also to give you maybe a hands on example, it's
10:32
considered the example of chess.
10:35
Where we want to play chess and chess is very different.
10:40
If you think about it compared to classifying email as spam and non spam.
10:46
So then we had a label that were attached to an email.
10:48
Now we want to learn how to play chess, whether, I mean, what
10:53
kind of moves we have to perform to win or lose at the game.
10:56
So we want to ideally win at the game.
10:58
So what are the necessary moves here that we have to learn given a certain.
11:03
Environment in state.
11:06
So in chess, we, in order to learn the series of actions, we have an
11:11
environment that would be our chess board.
11:16
I mean, just the pieces of the chess part that we can move
11:18
around and stuff like that.
11:20
And the state is the current configuration of the board.
11:23
So in where the pieces are on the chess board, uh, the agent that would be
11:27
the player in that case, the computer.
11:32
And that's also a reward, whether we make a good move or not.
11:35
So the reward, how it's defined is a little bit tricky.
11:38
So usually you start with some initial rewards for each move and
11:43
then you play a game, see whether your chest agent wins or not.
11:49
And then based on that, you update the rewards and so forth.
11:53
So, and the action would be making it move on the chess part.
11:57
This is, um, let's say the configuration.
12:00
Where the chess pieces are.
12:03
Um, yeah, that is in a nutshell reinforcement learning.
12:06
So we are learning a series of actions to win a chess.
12:10
For example, there are many, many more examples.
12:13
One, a popular type of example is now playing video games.
12:17
For example, they are StarCraft players or, uh, All the Atari games,
12:22
or usually a deep mind works in that where they develop agents to play
12:26
video games and stuff like that.
12:28
Uh, right.
12:29
Yeah.
12:29
This is out of the scope of this cost and this cost, we are not talking
12:34
about reinforcement running in my book.
12:36
Uh, the latest last in the latest edition, but also in the last chapter,
12:41
we have a whole chapter like 30, 40 pages about reinforcement learning.
12:44
If you want to learn a bit about it, but it's really not.
12:47
Um, Required for this class because it's really a big topic and there
12:52
are, um, special causes or causes just dedicate or enforcement only
12:56
because it's just a broad topic.
12:58
So in this course, uh, reinforcement will not be covered, but if you're interested,
13:02
you can read more about this in the Python machine, on in book and the last chapter.
13:07
Okay.
13:07
So just to show you some examples of reinforcement learning.
13:11
So here there's an agent that runs yet to run the puck Hoover of like.
13:17
I'm managing to run in a certain tricky environment.
13:21
It's trained by DeepMind.
13:24
So this agent learns how to avoid certain obstacles, not hitting the
13:29
red ones or jumping and so forth.
13:31
And how it learns is by just trial and error, it would start out, um,
13:35
making some moves, the moves, don't work wrong, the agent crashes into the
13:38
obstacles and so forth, and then it would learn to become better at it.
13:43
So that's one example of reinforcement learning.
13:45
It's very, um, popular in robotics.
13:47
For example, let's say Amazon warehouses, they use robots to
13:53
find packages, certain occasions and bringing them to destination.
13:56
Or you probably also know the vacuum cleaners that move in your apartment
13:59
or can move in your house and apartment to vacuum and avoid obstacles and
14:04
learning the environment and so forth.
14:07
Yes.
14:07
A maybe more interesting example.
14:09
That is what happens when reinforcement learning fails.
14:13
So you can see, um, yeah, quite some funny outcomes here.
14:18
So also you can see the agents here are flipping their hands,
14:22
which is very interesting.
14:23
Um, especially this one, I think that happens because there's no
14:27
constraint really on what the robot has or agent has to do with the hands.
14:31
So in this.
14:33
setting just as to jump and move around.
14:36
And there's no incentive maybe to put the hands in a certain position.
14:40
And like I said, it's like a trial and error.
14:42
If the agent learns to master the core and it gets through it and it does some
14:47
random action with their hands, it's not.
14:50
Kind of hinder, not a hindrance.
14:52
It's not penalized for that.
14:53
Then it learns to do funny hand movements, but of course you can also
14:57
modify your algorithms to kind of have some additional constraint that should
15:01
maybe use or waste energy by doing these weird movements and so forth.
15:05
But yeah, that's just an example of reinforcement learning.

##v4:

0:00
Now that we discussed what machine learning is and what the major categories of machine learning are, let us know return to supervised learning.
0:10
Remember that the biggest category of machine learning, supervised learning, and talk a little bit about the notation terminology and brought
0:19
our concepts of supervised learning. So supervised learning, the main workflow looks like this.
0:26
Um, recall supervised learning. We. Said there are two categories or subcategories, regression
0:32
and classification. And here I am referring to either a regression or
0:40
classification could be both. So that's the main workflow where we have a training data set and
0:47
in the training data set, there are the so-called features. Yeah, just rod training data, but you can also say a features or observations.
0:57
And then we also have the target information, the labels, for example, class labeled in the case of classification.
1:06
So we provide this training data set then to the machine learning algorithm.
1:12
And there are many, many different types of machine learning algorithms, which we'll see later in this course, and the algorithm will turn
1:19
the data into a predictive model. So the model is learned by the algorithm from the training data, and it can then
1:27
be used to make predictions on new data. So for example, if I have new data, which has the same form as my training
1:35
data, so the same features, then I can. Use my model that has been trained on the training data to make new predictions.
1:43
So that's the main workflow later we will return to this workflow figure and
1:49
look at more details, but just for the big picture, that's how you should be a supervised learning workflow works.
1:56
Okay. Let's now talk a little bit more about the more formal aspects of supervised learning the notation.
2:03
So here I have a train dataset. Let's call that deep. And this training data set consists of N training examples.
2:17
So I have N one, two N training examples and each training example.
2:22
So that is one training example
2:30
consists of a feature Makita.
2:39
And a label. So the target inflammation and I'm using the superscript I here to
2:48
denote the ice training points. So the position or the data point on data pair the pair of feature X label in
2:56
the training set later, we will use as a sub script for something else, which is why we use the superscript here.
3:03
So instead of writing it like this, um, I'm writing it with this superscript and
3:09
why it will become clear later because we will use the subscript for something else.
3:15
Okay. So that is the training set and there has to be something
3:20
that generated the pass here. So there was some, some function that assigned.
3:29
The label to the particular feature. And, um, this is usually an unknown function.
3:34
So usually we have a dataset, um, or there could be a function in a way that could be a human labeling emails as spam and non spam.
3:43
So in that case, the human would be the function providing these labels. But again, if you would ask a human how the human would assign spam
3:51
and non spam, this is kind of. Yeah a function that you can usually not describe in words, it's you just recognize it.
3:57
Okay. This is spam and this is not spam. Um, so there's usually some underlying unknown function or natural phenomenon
4:04
that, uh, sciences, um, labeled to the features and the goal. Then also let's call this function F of X that are science, the
4:13
labels, and the goal then in machine learning is to learn a model that
4:18
approximates this function, ideally. To learn this exact function, but this is usually a tricky.
4:24
So because yeah, that's an arbitrary number of possible function. So machine learning usually tries to find a way a function that provides
4:34
also a similar mapping between X and Y as this unknown function.
4:43
And. We call that in machine learning traditionally the hypothesis.
4:48
So this is, you can also think of it as the machine learning model, the hypothesis or model would be a function learned by the machine learning
4:56
algorithm that makes the predictions. I call them here, why head?
5:01
So this is a prediction of the class. They will given a feature ecto and Y would be the true label.
5:08
And then when we, when we evaluate our model, We usually have a separate data
5:13
set, but we will discuss that in more detail later, but we would basically compare how close the predictions are in the case of regression.
5:22
And in the case of calcification, we would check whether the true label is the same as the predicted label.
5:29
So maybe at this point you can pass the video and think about.
5:35
In the case of classification. If I have a feature vector here, which is, um, a vector usually
5:42
consisting of real numbers. So this would be my feature vector.
5:48
And yeah, I have one too for regression. So if I give it the feature vector, and I mentioned this already multiple times
5:55
when I was talking about this slide, what should go here on the right hand side? So the hypothesis takes in this X and what does it output?
6:05
So just a. Maybe way to double check that you follow the concepts on the slide. Maybe pause the video now.
6:11
And I will resume in a few seconds now.
6:17
Okay. So here in this case, the classification I grow them would take in a feature vector
6:26
X and the output would be the class label. So this would be a set of possible values.
6:34
It's right. As in set notation and usually in machine learning, we use integer
6:40
numbers, for example, zero and one for binary classification. Problem. If we have three classes, three possible classes, we would have three labels.
6:50
Hello. Um, it is kind of arbitrary. We use usually use inter just because it's, um, easier to program
6:58
in a computer, but we can also use. Some arbitrary letters for denoting.
7:07
The class labels AB AB Z or a B D ABC, whatever you like.
7:13
Really. So there is also no order in these labels in classification, there's a special
7:19
type, um, called ordinary regression or classification, which is a little bit out of the scope of this lecture.
7:25
So in regular classification that is not ordering in these labels. And if you see something like zero one, two, it can sometimes falsely give them
7:33
pressure that there's an order in the label, but in classification, These are nominal, not ordinary classes.
7:39
So this is nominal. Yeah. Not ordered. So there's, there's no ordering relationship.
7:45
You can say, um, that zero is smaller than one and one is smaller than two in terms of classes.
7:53
Any case that's going on a tangent here. So going back to what should go here in the regression example, that
8:00
would be the continuous class label. So why would be continuous label? So we would usually have a real number here.
8:08
Okay. So let's briefly talk about feature vectors. In the previous slide, you may have noticed that I used a bold version for X.
8:17
So for the training example, I had the bold X for referring to it as a feature vector.
8:24
And I used a non bold version for the label. That is because the label was a single.
8:31
Data point or a single value and X here was the vector. So this is a vector and this was why was it a single value or scale?
8:41
The scales? I don't use both fund for Vectrus. I use bolt fund. If I do my handwriting, it's kind of tedious to make this bold fund.
8:49
So I will try in this course to use a X with an arrow above to refer to the vector.
8:56
So vector can consist of many different features. So a feature vector is just a list.
9:02
If you will, a vector or a list of feature values. So here in this case, I F M feature that I use for this feature vector.
9:11
So if this is the ice training example, I would put the eye
9:16
above here as a superscript. And that is also why I'm using this a square bracket notation for.
9:24
The training index. So the data index of the training set, whereas the subscript
9:31
here, that's the index for the feature in the feature vector.
9:36
Now each feature vector corresponds to one training example.
9:44
However, in practice, the data set, the training data set consists of multiple training examples.
9:49
So usually we have N. Training examples in the training set.
9:56
And in order to denote that we can use a matrix where each row in the matrix corresponds to a feature vector.
10:03
So I'm using the transports here to transpose each feature vector.
10:10
So the transposed version, this would be then the feature vector X one X, sorry, X two X three.
10:22
X M and each row here would be one training example, unfortunately,
10:30
because we have the transports up here. It's kind of a little awkward to put the index up there also as a
10:37
superscript, but this would be one too.
10:43
And, and instead of using these subscripts here, maybe a little bit more clear
10:49
in that way, and there's actually a particular name for this matrix where we have multiple training, examples as rows.
10:56
So that's the first training example, the second and N drag example.
11:05
Um, and again, this is the first feature.
11:12
Actually first feature would be here. First feature, second feature and M feature.
11:29
So if I have this representation, there's a particular name for this. And I think you've probably seen that in other statistics courses before.
11:37
And that would be an excellent point now to pause the video briefly and brainstorm how this particular representation is called, just to maybe make the connection
11:46
for yourself to previous courses. So I. I have some blank letters here, that two words to the
11:53
notice kind of representation. So pause the video now and think a little bit about how this representation is called.
12:00
Okay. So that is, if you don't know it, I think it's probably hard to guess
12:05
it's a little bit of an awkward name, but it's called design.
12:11
Matrix. So that's the design matrix notation, and we will use that design matrix usually to
12:16
refer to the training set or in general to data sets and machine learning. So that is a very common representation and something you should ideally be
12:25
familiar with going in a bit further. So if you found this representation of the design matrix a little bit
12:32
confusing, um, there's also another way to write this out and here.
12:39
On the right hand side, I'm just expanding it. So again, that was what I was showing you before.
12:47
So this is one feature vector of the first training example. And here I'm just, so I'm taking this one, transpose it to roll vector.
12:58
So this is the rollback tunnel, and which would be corresponding to this man here.
13:06
And here I put the index one because it's the first training example. And there are one, two M features in that case, of course, this isn't a design
13:16
matrix and does exactly the same design matrix just written more explicitly.
13:25
Okay. This is just some of the notation. It's just something to keep in mind. It will become very familiar to you over the.
13:31
Yeah, because of this course, because you will be also writing this in code later on in Python and psychic learn using matrices.
13:39
So in a way, this mathematical notation will be exactly the same
13:44
format that you will be using in code. This was a little bit too abstract. Let me show you these concepts in the context of a real data set example.
13:54
So this is the Iris dataset, which was a data set.
13:59
Collected originally by, um, Ethicon Anderson and published in a paper by
14:07
Ronald Fisher, which is why it's also sometimes called the fish us Iris dataset.
14:13
And this Iris dataset consists of flower measurements. So there are these Iris flowers.
14:23
And the different measurements about the petal and sepal leaves. So I'm not confident that I got it correctly, but I think these are
14:32
the pitfalls and these leaves, these kinds of leaves are the seaports.
14:38
And I think I was incorrect. I think this is the pitfall and yeah, this is a simple and for each.
14:47
Flour. There is a measurement about the word concerning the width and the height.
14:55
Same for the SEPA, the width and the height. And these four measurements.
15:01
We have two measurements here, two measurements here. These measurements are feature.
15:07
So two and two that's four. So we have four measurements. These are our features.
15:14
So. Yeah, this part, let's call them the features.
15:20
And then we have a label information. So the goal in this data set is to predict a flower species
15:27
based on these measurements. And there are three different kinds of flowers or Iris flowers. So then these are subspecies of Iris flowers.
15:35
This is the TOSA class versicolor and virginica so three different classes or three possible classes.
15:42
So these are our. Labels in this column here, then we have 150 of these measurements in class labels.
15:53
So we have in the training set. So our training examples.
16:02
From one to 150. So usually in this class, we'll try to stick to the same notation for
16:10
basic basic things, like number of features and number of examples. So N would be the number of training examples that is 150 and we have
16:21
M equals four, four features. So. One two, three, four, and that is an Iris other popular Iris dataset that we will
16:31
be working with throughout the semester. When we look at different machinery algorithms, of course, we will also talk
16:38
about different datasets, but I think it's, um, I mean, it's kind of overused this data set in machine learning, but I think it's still a good data set to
16:45
explain basic concepts because it's not very complicated and helps really helps us focusing on the method and not getting distracted by what different
16:54
data features mean and stuff like that. Because I think this is very intuitive.
16:59
We have flow measurements and we want to predict the flower species.
17:06
After the previous slide you bring on all, there are two types of vectors. There is the vector containing the input features, and we can also
17:15
use the vector for representing the class tables in the training set. So that was the right most column in the picture in the last slide.
17:23
So if we have multiple training examples, one to end, we can also use the vector Y uh, to represent the labeled.
17:31
So we would call that the label. Oops label vector.
17:37
Whereas this is our future victim.
17:43
I have a note, don't confuse those two because, um, this is over the number of features and this is over the number of training examples.
17:51
So if we want to represent all the feature that because of a training example, we would have to use the matrix, the design matrix, where we have.
17:59
One feature of ecto as a role vector in each row. So up to and of them.
18:07
Um, yeah. Okay. That was what I wanted to cover about the notation. We will see some monetization later in this course, but this is basically
18:15
the basic, uh, dataset representation that we will be using most of the time.
18:21
For your personal reference. I created here a overview slide containing the different terms we heard about so far.
18:28
So we have the term training example to refer to a particular data point in the training set.
18:34
For example, the single flower in the Iris dataset, we have a feature,
18:39
the trunk feature, which refers to measurement for this particular flower. For example, the SEPA.
18:47
Length, we have the targets where a target would be in the class navel in
18:54
the case of the Iris flower example, that would be for example, the color.
19:00
And then we have the output or prediction, which would be the predicted class.
19:06
So that could be any of the three, but ideally our model would predict the
19:12
same as the true target, for example. Rosie cannot listen in this case.
19:19
Uh, yeah, there are many words on this slide. I don't want to read them on out. Uh, it's probably a good idea though, to look over this because yeah, I
19:26
was summarizing all the different words for the same concept that came to my mind because, um, sometimes depending whether you read computer
19:35
science, papers, statistics, papers, electric, electrical engineering papers.
19:40
Researchers and machine learning, they use different words to refer to the same thing. And here I was just trying to listen, um, all of them that I've heard before.
19:49
So it's very common to say training example, but sometimes you can also, well, some people saying observation training, record training instance.
19:58
What you've been training sample. This is very common in citizen. However, I don't want to use the term training sample here
20:05
because it can be confusing. Cause sometimes we refer to sample as a collection of data points and some papers.
20:14
They use the word training sample to refer to a single data point, which is then I think confusing.
20:20
So if you just say training sample, it's not clear whether you mean one data point or multiple data points.
20:27
Um, so we will try to stick to the common terminology and machinery and using training example to refer to one data point in the training set, then
20:36
the feature, I mean, in statistics, we also sometimes say predictor or covariate sometimes also variable input or attribute so many different
20:45
words again, for the same thing. We'll try to use the term feature because that's most common in machine learning.
20:52
Targets for that. We also have different words, outcome output, ground-truth response,
20:57
variable dependent variable, and in the case of classification class label.
21:02
Um, yeah. And then lastly, the output and prediction. So that is, we can use the same terminology as here, like output,
21:12
but with output, we usually mean what's predicted by the model. So this is the prediction.
21:19
By the model and the target is in the actual yeah.
21:29
Target the, we also often say ground truth, the real one, the real label that we want to predict.
21:35
So we want to use the model to predict this, this value with a model.
21:41
And that is the output of the model is called the output or prediction then. Okay.
21:47
There's one more term. I want to cover here. That's the hypothesis space. We will encounter the word hypothesis space multiple times in this cost,
21:56
which is why I briefly want to highlight what I mean by that.
22:02
So I hypothesis, I mentioned that before, this is kind of synonymous to model more classifier, just simply, it's just a, I would say more
22:11
classic way of referring to a model. Um, and what I want to show here is that there are multiple different
22:21
hypothesis that we can learn in every function that can be learned, can be
22:26
represented in this hypothesis space. So if there's something that some function that maps the features to the labels,
22:40
The entire hypothesis space consists of all such functions that map X to Y.
22:47
And using machine learning. We want to find the one that approximates the true function best.
22:53
Ideally, we want to find the true function, but there are so many different possibilities. It's hard to find the, so sometimes we just approximate
23:01
the label generating function. So it's just assumed there's this whole space of possible
23:07
hypothesis that we can search. So these are all the possible functions.
23:13
And then when we use a machine learning algorithm, we usually only sample or evaluate a subset of this.
23:21
So we, you can say this is almost subset. And in this case, let's call these, um, well, it's a machine learning,
23:33
uh, learning algorithm category. So for example, this could be on the
23:40
tree. Based algorithms. So are multiple tree based algorithms.
23:47
There's a cart decision tree.
23:54
There's ID three decision tree.
24:00
There are random forests. There are many different types. Of tree based.
24:06
I agree rhythms. And if we consider all the possible tree based algorithms, we would maybe have
24:12
X this space of the hypothesis space. So we, there are certain functions that we can't find using tree based algorithms.
24:18
So we only have access to a, then let's say we pick a particular case
24:27
in particular tree based algorithm. Let's just say we focus on this cart decision tree.
24:33
And we will talk about decision trees and way more detailed later in this course. I'm just trying to give you an example of what I mean by hypothesis space here.
24:41
So picking one particular type of algorithm from the family of tree based algorithms.
24:47
What I have is I again, have a subset of possible hypotheses or models that I can sample.
24:54
So this is now here. A much smaller set. And then if I have a training set, a particular training set, and
25:01
there are also certain options I can set in the algorithm, like how deep the tree should be maximally.
25:06
Um, how, um, uh, yeah, uh, what kinda, and a function I use for
25:11
information gain, we will talk more about information getting nature. Then they come up with a very particular model fit to my dataset and this
25:19
particular model is then my hypothesis. So what I'm just saying is if we want to.
25:25
Sample the whole hypothesis space. And we have to consider a whole, I mean, every possible function,
25:32
which is usually not feasible, which is why we use machine learning to approximate this, or to approximately find a function, um, in the space.
25:42
And depending on whether we use certain types of algorithms, we have access to
25:47
certain areas in this hypothesis space. For example, if I would use, um, Logistic regression.
25:54
I would have maybe only excess to do this part of the hypothesis space.
26:00
Maybe put a chair, so different algorithms, sample hypothesis, the
26:05
hypothesis space in a different region, but it doesn't mean so the, the true function, maybe no of the, none of the algorithms is able to sample it.
26:14
So usually we are already happy if we can approximate the true function.
26:19
Okay. There was a long, um, Yeah, monologue here. Let us just move on to the next slide.
26:27
Like I explained in the previous slide, there are different types of machine learning algorithms that sample different sub spaces in the hypothesis space.
26:37
So here are the major families of machine learning algorithms. For example, generalized linear models.
26:44
One example would be, um, logistic regression.
26:51
And then we have support vector machines. Then we can have a linear support vector machine.
26:57
And there's something called a radius spaces, function, Colonel machine it's called it's RBF kernel.
27:06
Be M we have artificial neural networks like the multilayer perceptrons or
27:14
they also recurrent neural networks and convolution neural networks and so forth.
27:22
Okay. Um, we have tree or rule based models. For example, decision trees.
27:31
Then we have graphic graphical models. One example would be Beijing
27:40
networks. Then we have in sambal methods, one case would be the random forest.
27:49
We have instance based learners, which, um, you know, for example, could be a Kenyan neighbor.
27:56
I grew them.
28:02
So yeah, there the many different types of feminists I'm trying to list the main, main ones.
28:08
And in this course we will cover most of them. Um, so we want to talk about logistic regression in this course.
28:18
And we will not talk about neural networks because there will be a separate course.
28:24
I will be teaching in spring, which is step four, five, three.
28:31
And this is the introduction to deep learning in this course, I will talk
28:42
about most of the elephants deep learning. What'd you do perceptrons convolutional neural networks were current in the
28:48
networks and in the introductory parts, I will also cover logistic regression because you can think of logistic regression as a special case of a
28:57
single layer artificial neural network. So in that case, I don't want to come at the topic in both classes
29:03
because I know many students take both classes, the machine learning class and the deep learning class.
29:09
So these two topics. Are covered in the stat four 53 class will not cover support vector machines here
29:18
in this class either, but we will cover all of these methods and they are plenty.
29:23
And in addition to these machine learning algorithms, I will also talk a lot about other concepts related to machine learning, like machine
29:31
learning, model evaluation, and so forth, which are very important. And once you understand the basic concept of machine learning, you can easily learn.
29:39
About additional algorithms later. So here in this class, we are trying to lay the groundwork, uh, introduce some
29:45
machine learning algorithms of cost, not all of them, because there are so many of them, but after this course, you should be able to do, um, get more reading and
29:53
learn about additional algorithms that we don't have time to cover in this course.
30:00
So the next video, we will then talk about how we approach a machine learning application.

##v5:

0:00
okay after talking a little bit about
0:03
the notation and formalism surrounding
0:05
super based learning
0:06
let us take a look again at the
0:08
supervised learning pipeline and
0:10
also discuss how we approach a machine
0:13
learning
0:13
problem in practice and what the
0:15
individual components are that we
0:17
usually worry about
Supervised Learning Workflow -- Overview Labels
0:19
so this figure is the figure that i
0:21
showed you previously the supervised
0:23
learning workflow or overview and that
0:26
is a very simplified figure
0:28
where we have a training data set
0:32
that is a labeled training set
0:36
so we have the labels for the features
0:39
and then we have a machine learning
0:40
algorithm
0:41
which learns yeah the model learns to
0:44
fit the model from the training data so
0:46
we
0:46
get a model from here and then once we
0:49
have the model we can
0:50
provide the model with new data
0:53
and the model then makes the predictions
0:56
of course
0:57
the assumption is always that the new
0:59
data comes from the same distribution as
1:01
the training data
1:06
here is a flow chart that is a little
1:08
bit more detailed
1:09
so the basic components are the same as
1:12
on the previous slide
1:14
so i have my training set i have a
1:16
learning algorithm
1:17
and i get a model and then we can use
1:19
the model to make predictions on new
1:21
data
1:23
however here are a few more details so
1:25
in practice before we get the training
1:27
data
1:28
we also usually have to do some
1:31
pre-processing
1:32
so unless you download the data from
1:34
someone who already
1:35
prepared the data set for you you
1:37
usually have to think about what
1:38
features you extract
1:40
from the data this is especially
1:42
important in traditional machine
1:43
learning
1:44
so if you think back of the iris flower
1:47
example
1:48
where we had iris flower measurements
1:51
and we wanted to classify the iris
1:52
flowers it could be for example that we
1:55
have an iris
1:56
on flower
1:59
image data set or we just observe the
2:01
iris flows in
2:02
in nature in the real nature and
2:06
based on that we have to extract some
2:08
features that we want to provide the
2:09
machine learning algorithm with
2:11
so we could give the machine learning
2:12
algorithm the raw pixels from the image
2:15
but in conventional machine learning
2:16
it's usually better to
2:18
you know use pre-processed features or
2:20
extracted features
2:22
in the iris example that was for example
2:26
the
2:28
sepal length
2:31
and sepal width and so forth usually
2:35
uh it really depends on the problem but
2:36
usually we also involve
2:38
domain experts who know a little bit
2:40
about the problem
2:41
so maybe a botanist who knows about iris
2:44
laws could help us
2:46
picking some features that may be useful
2:48
for classifying the flowers
2:51
so assume now you have extracted these
2:53
features so from the raw data
2:55
let's say the images you get the
2:57
training set consisting of
2:59
the sample length sample width petal
3:01
length and petal
3:02
width there can be additional steps
3:06
of pre-processing for example on
3:09
scaling the features or selecting
3:11
features for example
3:13
maybe you only want to select the petal
3:15
dimensions not the sepal dimensions
3:18
dimensionality reduction which is
3:20
another broad topic that combines
3:22
feature extraction feature selection
3:24
we can also combine features
3:27
and yeah subsampling the data set and so
3:30
forth
3:30
there are many different pre-processing
3:32
steps and we will talk about
3:34
a selection of them later in this course
3:38
and so assuming we have done the
3:40
pre-processing
3:41
we would then provide the learning
3:43
algorithm with the data
3:44
fit the model but when we have the data
3:48
set we usually divide it into two parts
3:50
so we have
3:51
a training set and a test data set
3:54
the training data set is used to fit the
3:56
algorithm
3:57
to obtain the model and then we use the
3:59
test data set
4:00
as an independent data set to evaluate
4:03
the performance of the model
4:05
so before we before we use the model on
4:08
real
4:09
new data we want to see how well it
4:11
performs
4:12
so in this case we
4:16
pass after we train it we pass the data
4:18
set to the model to the final model
4:20
i'm writing final model here because
4:24
in the learning steps there are also
4:27
evaluation steps there's something
4:28
called model selection cross validation
4:31
like um different steps to evaluate the
4:33
model during training to tune
4:35
the hyper parameters this is something
4:37
that we will cover also in this course
4:39
very extensively
4:40
we have about four lectures just devoted
4:42
to model
4:43
evaluation selection cross validation
4:45
and so forth
4:46
just um for now keep in mind that this
4:49
already encompasses also some
4:52
some evaluation procedure so once we
4:54
have
4:55
the final model here we use our test set
4:59
and evaluate the performance and that
5:01
works like this that we use the model
5:03
to predict labels so these labels are
5:06
the
5:07
labels predicted for the test set and
5:09
then we compared
5:11
to the true labels of the test set so
5:13
there's a comparison
5:14
and after we evaluated our model
5:18
in a classification example we usually
5:21
use the
5:21
classification accuracy or
5:23
classification error so for example we
5:25
can maybe say we get
5:26
95 accuracy in terms of classifying the
5:30
flaws correctly
5:31
and after we evaluated the model we can
5:34
then use it on new data
5:35
so then we have some new data and then
5:38
also do some predictions
5:39
in in a real world application so this
5:42
slide is
5:43
maybe a little bit confusing at this
5:44
point there's a lot of information going
5:46
on here
5:46
but we will cover these individual steps
5:49
in
5:50
way more detail later in this course
5 Steps for Approaching a Machine Learning Application
5:54
so in practice when we develop a machine
5:56
learning application
5:57
there are usually many steps involved
5:58
and i try to condense it to
6:00
five major steps here so first of all
6:03
when we start
6:04
working on a machine learning
6:05
application or problem we have to define
6:08
the problem that we want to solve just
6:11
taking the previous example again
6:13
of the email classification the
6:16
yeah the task would be classifying
6:21
or filtering
6:24
spam email
6:27
then we would have to collect a labeled
6:29
data set so
6:31
for example in this case we would
6:33
collect
6:34
a body of emails like 10 000 50 000
6:37
emails
6:38
and also have the labels whether the
6:39
emails are spam or not spam
6:42
then we would choose an algorithm class
6:44
and with that uh
6:46
this is not like doesn't have to be a
6:48
particular class of algorithms
6:50
so it could be multiple algorithm
6:52
classes here i'm just saying is that
6:55
certain types of algorithms are better
6:57
for certain types of problems
6:59
certain types of data but on the other
7:01
hand certain algorithms have certain
7:03
properties
7:04
sometimes we care about speed or we care
7:07
about
7:07
interpretability and we have different
7:10
goals maybe for our machine learning
7:12
application in that way
7:13
we want to select certain algorithms
7:15
that meet our criteria
7:17
so we not necessarily evaluate all
7:19
possible machine learning algorithms
7:22
um then after we defined our algorithm
7:25
class
7:25
let it be for now maybe decision trees
7:28
we will talk about
7:29
different types of algorithms later
7:33
then we will choose um an optimization
7:35
metric
7:36
and optimization metric so i'm also
7:38
writing measure because not
7:40
um every yeah metric is a every measure
7:44
is a proper metric there are certain
7:46
criteria for metrics for example
7:48
mathematically
7:49
symmetry and the triangle inequality and
7:52
so forth
7:53
but let's not get distracted by these
7:55
details so we
7:56
choose an optimization metric or an
7:58
objective function that we want to
7:59
optimize
8:01
and for example in the case of decision
8:03
trees
8:04
common ones are the guinea impurity
8:07
information gain
8:10
entropy and so forth we will cover this
8:13
in
8:13
two or three lectures and then after we
8:16
defined what we want to optimize
8:17
for training the model we have to choose
8:20
a metric that we use to
8:22
evaluate the model that could be
8:24
something like
8:26
um prediction
8:29
accuracy on the test set so how many
8:34
predictions the model gets correct in
8:36
the test set for example it could be
8:38
one metric and it's usually good to
8:40
define
8:41
all of this up front um so that we have
8:43
an
8:44
action plan where we develop our machine
8:46
learning application
8:50
so regarding the objective function the
8:52
optimization
8:53
metric we want to uh we use the
8:56
objective function to optimize a
8:58
optimization metric or measure so there
9:00
are different types of
9:01
objective functions i'm just listing
9:04
some of them here because you may have
9:06
heard of them already so we can for
9:08
example maximize the posterior
9:09
probability that is
9:11
done in naive bayes classifiers you can
9:13
maximize the fitness function which is
9:15
usually done in genetic programming
9:17
you can maximize the total reward or
9:19
value function which is
9:21
usually typical of reinforcement
9:23
learning
9:24
maximizing information gain um that is
9:27
what we do in decision trees in
9:29
particular um
9:31
card decision trees there are multiple
9:32
types of decision trees as we will learn
9:34
about later
9:36
or in regression trees or linear
9:39
regression we minimize the mean squared
9:41
error
9:43
maximize the likelihood in um
9:47
or minimize the cross entropy in neural
9:49
networks or logistic regression
9:51
and minimizing the hinge loss that's
9:53
something we do in support vector
9:55
machines
9:56
so you don't have to memorize that i'm
9:57
just showing you there are different
9:59
objective functions that we optimize
10:02
depending on what type of machine
10:04
learning algorithm or model we choose
10:08
so there are also different optimization
10:10
methods for
10:11
the different learning algorithms so we
10:13
have these objective functions that we
10:16
optimize and also there are different
10:18
ways we
10:19
would optimize them so there are
Optimization Methods for Different Learning Algorithms
10:22
combinatorial search greedy search
10:25
algorithms which are for example in
10:27
decision trees
10:30
or for an unconstrained convex
10:32
optimization there are examples like
10:34
linear regression or logistic regression
10:37
there's
10:38
constraint convex optimization that
10:40
would be
10:41
support vector machines for example just
10:46
write this down
10:48
logistic regression
10:51
um non-convex optimization
10:54
so for example using back propagation
10:56
which is based on the chain rule
10:58
that's the same or in this case the
11:00
process of reverse auto differentiation
11:02
if you heard of it
11:04
um this would be in neural networks
11:07
which we won't cover in this course
11:08
though it's
11:10
a topic for spring
11:13
and there's constrained non-convex
11:15
optimization
11:16
which is um the non-convex optimization
11:20
with a constraint
11:21
so for example there's something called
11:24
semi
11:24
adversarial networks
11:28
one of my research areas that i
11:30
developed with
11:31
some colleagues uh but also this is uh
11:34
beyond the scope of this class
11:35
just um trying to show you here there
11:38
are many different ways you
11:39
can approach an optimization problem
11:42
after talking about the optimization
Evaluation -- Misclassification Error
11:46
and the objective functions now let's
11:49
briefly discuss the evaluation so
11:51
evaluating a model that has been fit to
11:53
the training data
11:55
so one common measure is the
11:57
misclassification error
11:59
that is computed as follows so we use a
12:02
so-called zero one loss
12:05
this one here and we assign
12:08
for a single data point is zero if the
12:11
prediction
12:12
matches or is the same as the actual
12:15
class label for a data point in the
12:18
test data set for example and we assign
12:20
a one
12:21
if the prediction does not match the
12:23
actual label and then we
12:25
do this for all data points in the test
12:28
set for the n
12:29
data points in the test set and sum up
12:32
these errors so this part would be
12:36
the total number
12:40
of errors
12:43
and then we average over it so we get a
12:45
number between zero and one
12:48
a fraction and usually we multiply this
12:52
by 100 so we get a number between
12:56
0 and 100
12:59
for the classification error similarly
13:01
we can also predict the
13:03
classification accuracy by just um in
13:06
this case
13:07
doing one minus the arrow so one minus
13:10
the arrow
13:11
and if we have the percent we would of
13:13
course have one hundred percent
13:15
minus the arrow in percent
13:19
so that would give us the classification
13:21
accuracy both
13:22
are commonly used error and accuracy
13:24
because they are essentially the same
13:26
thing
13:26
and usually this is the most common
13:28
evaluation metric if we don't have any
13:31
particular reason to use something else
13:36
um so now that i talked about
13:39
the um zero one loss and then the
13:42
classification error
13:44
i want to briefly say something about
13:48
the term loss function so here
13:51
i use the term loss usually in
13:53
traditional machine learning
13:55
loss refers to a single um
13:58
data point so we compute the loss based
14:01
on a single data point
14:02
and then when we look at the whole data
14:04
set or
14:06
a sample if we have multiple data points
14:09
like here
14:10
the end data points we usually call this
14:13
the the cost
14:15
but this is a traditional uh distinction
14:18
between loss
14:19
and cost nowadays it's not so
14:22
um yeah people are not so picky anymore
14:24
so in literature
14:25
you often find the term loss to refer
14:28
to the error as well so whether we use
14:31
loss or cost it does not really matter i
14:34
try to make the distinction though for
14:35
clarity
14:36
to use the term loss when i refer to a
14:39
single data point
14:41
and the term cost when i
14:44
refer to multiple data points
14:49
so but yeah like i said nowadays it's
14:51
usually synonymous
Other Metrics in Future Lectures
14:58
so next to the classification accuracy
15:00
or error
15:01
there are many other evaluation metrics
15:04
for example
15:05
the receiver operating characteristic
15:07
area under the curve
15:09
precision recall sometimes they're also
15:11
there's a flavor
15:12
called f1 score that combines both of
15:15
them
15:16
cross entropy likelihood squared error l
15:18
norms
15:19
utility functions fitness functions and
15:21
so forth
15:22
or measures and there are many different
15:25
ways you can evaluate the model and it
15:26
really depends on the problem at hand
15:28
usually by default people use either the
15:30
accuracy or the receiver operating
15:32
characteristic area under the curve
15:34
but there may be reasons in certain
15:36
applications to you to look at
15:38
precision and recall or the f1 score
15:41
in certain applications uh it's also
15:43
useful to look at the cross entropy
15:45
the cross entropy is also used as an
15:48
objective function that we optimize for
15:50
example in logistic regression or
15:54
neural network training but this is uh
15:56
getting way ahead of ourselves here
15:58
so we will cover this or these different
16:01
types also in the model evaluation
16:03
sections later on
16:04
just i'm showing you that these other
16:06
methods exist but
16:08
usually most of the time in this course
16:09
we will focus on the classification
16:11
error or accuracy
16:14
and yeah next let's to finish up this
16:17
lecture let's talk about different
16:19
machine learning
16:20
approaches and motivations why we are
16:23
interested in machine learning

##v6:

Introduction
0:00
okay so previously we talked about approaching a machine learning problem
0:05
how we would approach a problem that was um yeah first defining the problem
0:12
the it's horrible handwriting
0:19
okay so previously we were talking about how we approach a machine learning application
0:24
that was one defining the problem then collecting
0:33
or finding a good data set
0:39
then we said we would choose an algorithm or algorithm class
0:45
that we want to use to um solve this problem then we would define an optimization
0:54
metric for yeah training the model and then once we trained the model we
1:00
would have an evaluation metric
1:06
yet to evaluate the final performance of the model now we are talking briefly about
1:12
different machine learning approaches and also motivations behind
1:18
doing or using machine learning so what different people how to get out of machine learning
Machine Learning Tribes
1:26
dominguez who is a professor at the university of washington has a very nice figure here which i took
1:32
from his book the master algorithm where he categorizes the different approaches to
1:38
machine learning into five tribes so he calls these tribes the symbolists
1:45
connectionists evolutionaries bayesians and energizers so here he's trying to
1:52
categorize each tribe into a representation chosen for representing
1:57
the model an evaluation part which would be the objective
2:04
function we talked about earlier that's what we want to optimize during training and then here and
2:11
your optimization approach so how we optimize the objective
2:20
function so don't confuse the eval here with the model evaluation metric which is a
2:27
little bit different so the metric like we said before that we optimized during training doesn't necessarily have to be the same
2:33
that we use to evaluate the final outcome the final model
2:39
so here let's just maybe have a look at one of these examples for example for the connectionists pedo
2:45
dominguez classifies the or defines the representation as neural networks so
2:52
that's the model for modeling the problem then the objective function would be optimizing the squared
2:59
error of course this is just one example it could also be the cross entropy
3:05
and then the algorithm or optimization approach would be using gradient descent
3:10
in new networks we usually use something called back propagation but it's based on gradient descent and yeah this is how
3:18
one type of machine learning would view the problem using a new network model that is trained to optimize the squared
3:24
error during training using the gradient descent approach and then evolutionaries would be using a
3:32
genetic search as an optimization approach and optimizing the fitness
3:38
and the representation of the problem or the model that would be the genetic programs
3:44
or in a bayesian view these models would be graphical models
3:51
and we use probabilistic inference for the posterior maximizing posterior
3:56
probability for example so many different approaches to machine learning and i thought this might be a
4:01
very nice overview slide of course each category only contains one example
4:08
um not it's not an exhaustive list of all the examples and models and representations for each category
Statistical Modelling the Two Cultures
4:16
so another interesting viewpoint is provided by leo bryman who was a very influential
4:22
statistician who developed very important algorithms such as decision trees and random
4:27
forests which we will cover later in this course and if you have time i really recommend
4:33
reading this paper it's called statistical modeling the two cultures it's an it's not a requirement
4:38
for this course to read the whole paper but i think it will open up some interesting
4:43
insights into the relationship between statistics and machine learning so he made the statement that there are
4:51
two goals in analyzing the data one goal is prediction and one goal is information
4:57
for example if you have a scenario like here where you have some observation or feature
5:04
and some response variable or target as we call it in machine learning
5:11
the one goal would be to predict what the target or response
5:16
is here for um future input variables so
5:21
if we have a model that we fit to the training data then at some point we want to make new
5:27
predictions we have features that we observe from new data examples for example if you think back
5:33
of the email spam classification example we fit the model on the training set but at
5:38
some point we really want to use the model on real data so if we have a new email coming into our email inbox
5:44
we want to classify that as well the other one the other motivation is obtaining
5:50
information so to extract some information about how nature is associating the response
5:56
variables to the input variables so here this is more about understanding on the relationship between x and y
6:03
and you don't necessarily have to understand this relationship or what's
6:09
called nature here perfectly in order to do predictions so the goals sometimes overlap so sometimes
6:16
of course it's beneficial if you understand why a model is predicting certain outputs or what the relationship
6:22
is between x and y well it's not always a requirement for
6:27
example if i have a highly accurate spam filter i have a spam filter that correctly
6:33
classifies spam email all the time 100 accuracy then i
6:38
don't really care about um you know what the relationship is or what makes a spam email as long as the
6:45
algorithm performs well the decision uh could be complex i mean it could depend on many
6:51
different input features um highly complicated um model would associate a very yeah
6:57
complicated relationship there but it's not necessarily important to understand this if it
7:04
performs well all of the time but there are of course very um important
7:10
applications where it is important to understand what the model is doing but in any case here i just wanted to um
7:17
say what leo bryman said there can be two different goals in analyzing the data
7:34
yeah so in the statistical modeling culture or approach
7:41
what we have is we have a given relationship where we have we said before this box was called
7:47
nature where there is a relationship between x and y that's some natural phenomenon for example and we
7:53
want to model that in statistical modeling we would make an assumption for example there's a linear relationship between
7:59
x and y and then we would use a linear regression model to model this we can use that either to make
8:04
predictions but also you have to make assumptions and get information about
8:09
the mapping between x and y or the relationship between x and y so that would be the approach that we
8:17
would make in statistical modeling in machine learning we don't necessarily
8:22
have to make assumptions about x and y and the underlying model there are certain types of algorithms
8:29
that are just black boxes so um leo bryman calls this the algorithmic
8:37
culture so he says the analysis in this culture considers the inside of the box
8:44
complex and unknown so nature here is in reality often so complicated then
8:51
we yeah it can't always make assumption also so we just consider that as a unknown function we don't really um
8:59
have to think hard about it and the approach is to find the function f of x that was our
9:05
hypothesis x earlier which is an algorithm that operates on
9:10
x to predict the responses y the their black box looks like this so
9:17
instead of assuming that nature behaves like a certain model
9:23
we just treat this as unknown and use an algorithm for example decision trees on your networks um that
9:30
we fit on the training data and then we use it to make predictions on why we don't really need to
9:35
understand the relationship between x and y we we just care about the predictions so this is a different approach to yeah
9:42
statistical modelling that's the algorithmic approach and this is essentially machine learning most of the time
Extreme Algorithmic Approach
9:48
so this would be a fun example of a problem that was solved without understanding
9:53
actually the problem so um
10:00
so this is a fun example here of a very extreme algorithmic approach like
10:07
solving the problem without actually understanding it and it also shows that it's not always
10:12
necessary to understand the problem um so i'm not sure if you've seen that before and if you have an idea what that is
10:19
so this is an evolved antenna that was designed by evolutionary algorithms and this antenna
10:25
here was used on a nasa spacecraft so they used evolutionary algorithms to design an
10:31
antenna with the best possible reception basically and it turned out that the algorithm found that this
10:37
kind of antenna although it looks super weird or yeah performs very well and this is
10:43
we don't know why this antenna performs well but actually it just performs well and this is um enough here to
10:50
use it on another spacecraft so it's not always important to understand what makes an antenna getting a better
10:56
reception but of course if you have further insights into the problem you can maybe even design better antenna but
11:01
yeah this is just a example of an extreme approach where we consider the model as a black box and
11:09
let it do its thing and get an outcome that actually performs very well in practice
Black Boxes and interpretability
11:14
regarding black boxes and interpretability some models are harder to explain or
11:19
interpret and we usually call them black boxes and some models are easier
11:26
to interpret and these are usually i mean interpretability is usually desirable but there's usually a trade-off simpler
11:33
models are easier to understand but they usually don't give you a great performance
11:39
then on the other side more complicated models may give you a better performance but they are harder
11:44
to interpret and the different levels of that and different sweet spots and later in this course we will see
11:50
many examples of that where we have a deep decision tree that performs very well except that it may
11:57
overfit but it is then very hard to interpret compared to a simpler shorter decision tree the
12:02
shorter decision tree would have the problem that the predictions are not as accurate so there's really the dilemma sometimes
12:09
between interpreting the model and the model performance and i think also it doesn't really help
12:15
if you have a highly let's say well-performing model but
12:21
sometimes it screws up in an important application that's not good but on the other hand if you have a very
12:27
simple model that you can understand but it never predicts something very well then also understanding the prediction is not very
12:34
useful because you maybe don't end up using the model in practice because it's just not performing well enough
12:40
regarding black boxes and interpretability george box our department's founder he said the
12:47
following all models are wrong but some are useful so that's maybe also something to always
12:53
keep in mind so another view on the different
13:00
motivations for studying machine learning could be that engineers
13:05
focus sometimes more on solving actual problems using machine learning as part of a
13:11
solution to a problem that could be self-driving cars where machine learning plays an important role
13:17
so solutions to real world problems for example
13:29
whereas some mathematicians computer scientists and statisticians are more interested in developing
13:35
machine learning theory like understanding machine learning on a more fundamental level
13:42
of course i'm generalizing here doesn't mean that no engineer would care about ml theory and it also doesn't
13:49
mean that no computer scientist statistician or mathematician would um solve real-world problems so i'm just
13:55
trying to group these different types of motivations roughly by yeah a kind of department here so and
14:03
some neuroscientists study machine learning because they're very interested in understanding how the human brain works
14:10
and also um trying to develop algorithms that mimic the human brain
14:15
that could motivate the understanding of the human brain but also it can help to improve algorithms if you
14:21
use the human brain as a template for example so here that's more like um
14:28
i would say more like a biological motivation
14:36
okay so we are so in case you were already wondering we talked about
14:42
machine learning but i many times mention the terms ai and deep learning so what's the relationship
14:47
between those so originally i mentioned that earlier machine learning emerged as a subfield
14:53
of ai so we described machine learning earlier as algorithms that learn models or representations or rules
15:01
automatically from data and examples that was the principle behind machine learning
15:07
then deep learning emerged as a subfield of machine learning relatively recently like a little bit
15:14
more than a decade ago and this is a field that focuses on multi-layer neural networks
15:20
so multi-layer neural networks have been around for a long time but deep learning it also goes a little bit beyond just
15:26
multi-layer networks but also focuses on certain tricks to make the learning more efficient
15:32
however in a way deep learning is just a rebranding of the term neural networks so this is not covered in or deep
15:38
learning is not covered in this course this is a topic of statistics um four five three which i
15:44
usually teach in the spring semester so ai i draw that i drew that circle
15:51
here as an intersection between machine learning and ai and not machine learning is a subfield
15:57
of ai because i think nowadays we have a lot of machine learning applications that are not
16:03
necessarily ai systems so i define ai systems as a non-biological system that is
16:08
intelligent through rules so systems that can be able to perform
16:14
certain tasks that humans are usually good at for example driving like self-driving cars or
16:21
playing chess and things like that but also image recognition recognizing handwritten digits from images
16:27
i would call that ai systems whereas machine learning i mean if you think back of the iris
16:35
example where we saw an example classifying different flower species based on simple measurements of the
16:41
petal lengths and widths if we use a simple k nearest neighbor algorithm
16:46
which we will talk about next lecture i would call that a pattern recognizer but i
16:52
wouldn't necessarily call that an ai system it's i think it's a little bit too simple to call that an ai
16:57
system in any case there are many approaches to ai that are not machine
17:03
learning so you can also design an ai system by having human experts hand coding the
17:09
rules it can be tedious but it can result in very highly efficient ai systems
17:14
so machine learning is not necessary for ai so that is why also i drew machine
17:19
learning and i as intersections because not all of machine learning is ai and there are also many forms of ai that
17:25
don't use machine learning i realized this introduction is already
Tools
17:32
very long but i want to briefly just um finish up with some topics uh now here regarding with the
17:38
tools that we are going to use you probably already know that we will be using python in this course
17:45
so here's just a quick overview of the tools we are going to use for or in python because python is a very
17:52
powerful language it's like a general purpose language you can do a lot of things in python but it's not known for being an
17:59
efficient language in a way that if you just use vanilla python then it may be too slow for certain types of
18:04
applications which is why the scientific community developed many libraries on top of it that not only make it more convenient
18:10
for scientific computing but also way more efficient so here i just want to show you a brief
18:17
overview of the different tools that exist and that we maybe use or will be using in
18:22
this class this picture is based on a now five-year-old
18:28
um keynote by jake fenderblast but it's still very accurate this is really the core
18:33
ecosystem in python for scientific computing we also sometimes call that the
18:39
size stack so the stack for scientific computing and let me highlight some of these
18:46
models that we will be using in this class and tell you what they are about so python is the programming language
18:51
itself then there's something called ipython which is an interactive interpreter so it's just a way it's a
18:58
little bit more convenient to use python through ipython which is providing you some nice
19:03
coloring in the terminal and stuff like that i will show it to you actually um next week and on top of
19:10
ipython there is the jupiter notebook which is just um if you have used r markdown or rstudio it's kind of
19:16
like that it's just like a program where you can execute python and add notations so these are not really python
19:23
libraries in a way for scientific computing they are more like um like environments
19:30
that make certain things more convenient now however there is numpy
19:37
numpy is one of the most important python libraries it's a linear algebra library
19:46
there are some additional nice functions in there but fundamentally it's like a array and linear algebra library and
19:52
they implement algorithms very efficiently using fortran and c code under the hood so even if you
19:58
call the function in python or do a computation python it's very fast because it uses fortran and c code under the hood
20:04
however it's as convenient as python because you actually execute python functions but we'll see
20:10
that in more detail also when we talk about numpy next week so i'll give you some examples and show
20:16
you how to use numpy so scipy is extending numpy there are
20:22
some scientific functions in scipy so i would say this is like an advanced
20:32
a scientific library so it has some more specialized um functions that are
20:39
not in numpy let's call it advanced scientific computing something like that
20:46
there is matplotlib which is a library for plotting putting data
20:53
and there is pandas let me use a different color pandas which is i would call that maybe
21:01
a data frame library that's maybe a good description um it's similar if you have used r it's um
21:08
providing what our data frames are basically providing and some more things
21:14
so it's usually the go to function for reading and writing data also and yeah also working with data frames
21:20
it's not always um or we don't always use that in machine learning but for certain types
21:25
of the workflow it makes things easier so for example for data pre-processing for collecting data
21:31
and cleaning up data pannas can be very convenient there are
21:36
there are other libraries here but we won't be using them in this course so the ones that i highlighted here are the main
21:42
libraries oh wait i forgot one very important one and that is um scikit-learn this is of course our
21:48
machine learning library so that is the main machine learning library that we will be using here
21:54
um also you notice that in this plot or in this graphic uh jake venaplus drew
22:00
these lines here so these divider lines it also tells us a little bit about the level of how the libraries are related
22:06
so at the core there's python and let's say numpy is built on top of python
22:13
scipy in turn is built on top of numpy and scikit-learn
22:19
is essentially built on top of scipy and numpy so scipy makes heavy use of cipher and
22:25
numpy and in that way also usually libraries in the scientific
22:31
python ecosystem they benefit each other they are all interoperable so you can usually export
22:38
back and forth between numpy and pandas nowadays i could learn also um
22:44
accepts inputs from pandas and we can also pandas uses or some headboard lib for
22:49
their own visualization tools and so forth the matpot lib works with numpy they're all connected with each
22:56
other so the ones that i circled um numpy scipy
23:01
madboot lip pandas and scikit-learn will be the ones that i will show you next week and that we will be using that
23:07
course and we were also using this course jupyter notebooks because they make teaching and um yeah tutorials writing
23:15
providing you with material more convenient because i can write some text in there but then at the same time we can also
23:21
have code in there and we will also be using jupyter notebooks for the homework where i will give you
23:26
some example code that is let's say unfinished i will give you some instructions maybe some figures and you will then uh
23:32
yeah write your code in in the homework uh the homework code in the jupyter notebook
23:38
and then you can also add your results add some explanations and so forth so it's a very convenient environment
23:43
here also for this class
Spam
23:51
we are almost at the end of the lecture some more additions i wanted to make so we talked about spam
23:58
classification earlier so in the context of
24:04
emails so you are probably wondering what is why do we call spam email spam it's actually inspired
24:10
by this food which is a food that was made i think like uh during the second world war or
24:17
something to have some food that can be easily preserved it's still very popular in hawaii um i
24:24
saw that a couple of times there i don't know why it's still so popular i think it's probably delicious but maybe not the most healthy
24:30
food anyways um the reason uh why spam email is called spam is that the monty python
24:38
group that's like a comedy group from like many many years ago was a little bit before my time but they
24:44
performed certain sketches about spam many many times so i guess it became
24:50
annoying at some point and then when there was a time when email was invented and to pick a name for
24:56
these uh kind of unsolicited electronic messages they just picked the name spam for it
25:02
because it was inspired by this annoying yeah referencing of spam in the sketches
25:09
uh how is this related to python now because i just talked about python actually uh it all comes back full
25:15
circle because python itself is inspired by monty python so that's
25:21
the sketch group so even though python has a snake as a logo originally python the name came from
25:28
this monty python comedy group so yeah i also have this from wikipedia
25:33
python's name is derived from the british comedy group monty python whom python creator guido van rossum
25:39
enjoyed enjoyed while developing the language so here we go so there's actually a direct relationship between
25:47
monty python and python and spam and monty python so it all goes back to
25:52
monty python anyways um okay so lastly just to wrap up some of
ML Terminology
25:58
the terms we covered today let me briefly recap the ml terminology that we
26:03
talked about the hypothesis is a certain function that we believe or hope
26:09
is similar to the true function the target function that we want to model so when we think back of our setup so we
26:17
have some input feature x some function f
26:22
and then some output y and f is let's say the label providing
26:28
function some function that actually yeah provided us with a label so it could be even a human
26:34
um assigning spam and non-spam emails and our machine learning algorithm wants to learn or
26:40
should learn a model that can provide the same mapping well so in the email spam classification
26:47
example approximating the spam and non-spam label assignment that the human would do
26:53
so we would have a model that we call that h hypothesis in
26:59
machine learning that would do the same mapping or approximate this mapping so in a way
27:04
the hypothesis is an approximation of this target function and traditionally people say or call
27:12
this the hypothesis nowadays it's more i would say common just to use the term model they're kind of
27:19
interchangeable in other sciences also hypothesis means something very different so it can be
27:25
even confusing to use the term hypothesis i think so for example i may have a
27:31
pharmaceutical drug and i may have the hypothesis that there's no significant difference
27:37
between a control group and a treatment group who takes the drug so that is a
27:42
different type of hypothesis that has nothing to do with machine learning for example so yeah just the bottom line is
27:49
hypothesis and model are kind of interchangeable and they are both the thing that we want to approximate
27:55
so the learning algorithm is the algorithm that learns the model from the data set
28:02
so i have provided you here with a little more detail just to summarize what we talked about in this
28:08
lecture so here in this slide i'm pretty detailed it's just more you for your personal reference
28:13
i don't want to read that all out loud and a classifier would be a special case
28:20
of a model so the learning algorithm is used on the training set to produce the model
28:26
and if the data set happens to be classification data set where we have
28:32
class labels for y for example the spam
28:37
and not spam example that would be a classification case so we would call that specific model a classifier
28:46
yeah but this is just a brief recap and some reference for you like to clarify some of the terms we
28:53
covered today so in this course i try to structure it
Course Structure
28:58
into seven parts we have the introduction which was partly covered today so next lecture
29:06
will be the introduction to k nearest neighbors like the first supervised learning
29:11
algorithm that we will cover in this course just to give you a taste of machine learning and a machine learning
29:17
application so how a machine learning algorithm works and then we will cover computational
29:22
foundations we'll talk a little bit more about numpy how to use numpy in scikit-learn the
29:28
machine learning library but of course like i mentioned earlier it would be highly recommended if you
29:33
have not used python yet to really look or work through some of the resources that i provide you here in
29:39
this first week i will add that to the piazza page also to the canvas page so after we cover the
29:46
computational foundations we will go back to machine learning and talk about tree based model methods and
29:53
models this will also include model ensembles like um random forests and boosting
29:59
algorithms after that we will talk about model evaluation
30:05
so we will spend a lot of time discussing how we properly evaluate
30:10
machine learning models because it's a very important topic and um it's kind of fundamental to know
30:16
how we evaluate a machine learning model before we can set it loose in the real world so i think that's a very important topic that we should pay close attention
30:23
to then we will talk a little bit about dimensionality reduction and unsupervised learning including
30:29
clustering after that i hope we still have time then to talk more about bayesian
30:34
learning this will be the last part of the core lectures here in this course and then lastly you will be giving the
30:42
presentation so i will provide you again more with more detail about the class projects later
30:47
i talked a little bit about this in the beginning but i will send around more resources also so that will be then the
30:55
time or the last few lectures or weeks last two weeks where you will be giving
31:00
your presentations about your awesome class projects
31:06
yeah also here it's the same thing just in more detail the next lecture will be the introduction to
31:12
supervised learning and kenya's neighbors then in part two we will talk about python
31:18
python scientific computing stack like numpy and then data processing machining with psychic
31:24
learn so that's just part one and two in more detail here
Reading assignments
31:29
so lastly some reading assignments so i really recommend reading the first chapter of the python
31:36
machine learning book it's very short but it's like a i would say maybe more accessible
31:41
introduction than the course notes it's a little bit shorter i highly recommend you to read the
31:46
course notes though which summarize what i just talked about so i was just writing down what i
31:51
had in my slides in in more detail also maybe more clearly at some points another helpful book it's
31:58
a freely available online um it's elements of justice uh elements of statistical learning it's not
32:04
required that you read that but it's uh i would say a little bit more formal than the python machine learning book or
32:10
actually way more formal so if you prefer that style i recommend reading elements of statistical learning
32:16
the first chapter and optionally if you like i recommend leo bryman's paper
32:23
that i referenced earlier in this lecture it's very nice accessible paper you don't need much
32:29
background knowledge for understanding what he's talking about uh yeah but again this is not a requirement
32:34
it's just an optional reading assignment for you so maybe call this optional
32:41
and this optional of course to some degree this is also optional
32:47
it's just for you it can help you but i don't i won't ask you any questions about this chapter
32:53
for example in the exam so you don't really have to read it it's just for your own benefits if you like all right so
32:58
that's it for week one next week we will lecture one
33:03
in the next lecture we will talk about k nearest neighbor algorithms

##v7:

0:00
yeah hi everyone and welcome back i hope
0:03
you had a very nice
0:04
first week so just to briefly recap
0:07
what happened so we covered lecture one
0:10
the introduction to machine learning
0:12
and in the office ask the most common
0:14
question was basically about the project
0:16
the class project
0:18
i will make a separate announcement
0:19
about that but uh yeah one thing i can
0:22
already tell you is that i enabled a
0:23
function on piazza
0:25
that you can use to find team members
0:28
but i will again share that in a
0:30
separate announcement
0:33
so today in lecture two we'll mainly
0:35
talk about
0:37
the k nearest neighbor algorithm it's a
0:40
kind of a classic machine learning
0:41
algorithm but it's still very useful
0:44
and i would say that is maybe the nicest
0:46
most
0:47
gentle introduction to machine learning
0:49
in in terms of using the first machine
0:51
learning algorithm and taking a closer
0:53
look
0:54
at how machine learning algorithms work
0:57
so also
0:58
while it is maybe not the most popular
1:00
algorithm anymore i would say
1:02
i would really still recommend it highly
1:04
to include it in your
1:06
projects so if you work on a project
1:09
where you want to
1:09
classify certain things or even let's
1:12
say predict continuous outputs
1:14
i would always start with k nearest
1:16
neighbors as a
1:18
performance benchmark so that could be a
1:20
benchmark in terms of
1:22
prediction accuracy but also a benchmark
1:25
in terms of computational efficiency
1:27
so speaking of which along with
1:30
introducing how k nearest neighbor works
1:33
we will also briefly talk a little bit
1:34
about big o the big o notation
1:37
which is a very common way of looking at
1:41
the efficiency of different algorithms
1:42
it's
1:43
kind of very computer sciencey but still
1:46
i think it's useful in this context to
1:48
talk a little bit about
1:49
big o notation and analyzing algorithm
1:51
efficiency
1:52
that's something i think that is also
1:54
useful not only for machine learning but
1:56
yeah like uh programming in general
2:00
yeah and um at the end of this lecture
2:02
then uh
2:03
since i also mentioned computational
2:05
aspects after introducing the concepts
2:08
of
2:09
k n i will also then show you some
2:11
examples in python how we can
2:14
use k n and python of course this is
2:16
just a very brief
2:17
overview some parts may be confusing but
2:20
again in the next lecture
2:22
in lecture three i will talk more about
2:24
python how to install it and
2:26
also about uh the main libraries we will
2:29
be using like
2:30
numpy and scikit-learn okay so then
2:32
let's get started
Outline
2:37
so in lecture two we are going to talk
2:39
about nearest neighbor methods
2:41
this includes aspects about nearest
2:43
neighbor methods in general
2:45
but also more specifically the k nearest
2:47
neighbor
2:48
algorithms for example k nearest
2:50
neighbors for classification or
2:52
regression
Structure
2:54
to make this lecture a little bit more
2:55
approachable i structured it
2:57
into six parts so first we
3:01
will take a look at some applications of
3:03
nearest neighbor methods
3:04
and also just a basic one nearest
3:07
neighbor method
3:08
then i will show you the decision
3:11
boundary of the nearest neighbor method
3:13
to get a better understanding of how it
3:15
works
3:16
after we talked about the nearest
3:18
neighbor method in general
3:20
i will introduce the k-nearest neighbor
3:22
methods for example
3:24
k-nearest neighbor classifiers and after
3:27
i mean this is a very simple
3:28
concept after we went over this we will
3:31
dive into a more
3:32
like computer sciencey aspect of this
3:34
lecture
3:35
and look at the big o uh runtime
3:38
complexity of k-nearest neighbor
3:40
algorithms
3:41
it's like a computer science topic that
3:44
deals with analyzing of
3:46
analyzing how efficient an algorithm is
3:49
after part 4 i will show you then some
3:52
ideas and tricks to improve
3:55
k nearest naval algorithms so this whole
3:59
part one to five is rather conceptual
4:02
it kind of kind of introduces the idea
4:04
behind k nearest neighbors
4:06
and after we finished these parts in the
4:09
end i will also show you
4:11
how you can use k nearest neighbors in
4:14
python
4:14
so that is also maybe for some of you
4:17
the most fun part
4:18
but of course first concepts and then
4:21
the application because otherwise
4:23
um showing you the application first it
4:25
would be kind of like
4:26
some magic stuff going on so first let's
4:29
talk about the concepts
4:30
and then about the application yeah but
Applications
4:33
in a certain way
4:34
applications can also be quite
4:36
motivating
4:37
for introducing a certain topic so i
4:40
picked some
4:41
example applications of k-nearest
4:42
neighbor methods
4:44
in practice so here i found a research
Research Article
4:47
article entitled
4:48
automated web usage data mining and
4:51
recommendation system using
4:53
the k-nearest neighbor classification
4:55
method so here
4:57
the researchers deal with web usage data
5:00
mining
5:02
and more specifically this would be a
5:04
case of a recommender system
5:06
so kenya's neighbors are still very
5:08
commonly used for building recommender
5:10
systems
5:11
and here what they say is basically they
5:13
trained the k
5:15
nearest neighbor classifier to be used
5:18
online and in real time to identify
5:20
clients
5:22
or visitor click stream data
5:25
matching it to a particular user group
5:27
and recommend a tailored browsing option
5:30
that meet the need of the specific user
5:32
at a particular time
5:33
so it's um you can think of it as a
5:36
recommendation system
5:37
recommend recommending certain i would
5:40
say i don't know links or websites and
5:41
so forth
5:43
based on the past or present browsing
5:45
behavior
Biometrics
5:48
yet traditionally k nearest neighbor
5:50
methods have also been
5:52
used extensively in the field of
5:54
biometrics that includes like
5:56
face recognition or fingerprint analysis
5:59
and so forth
6:00
um nowadays it's maybe more common to do
6:03
biometric research using deep learning
6:05
but
6:05
kenya's neighbor algorithms are still
6:08
very commonly used in
6:09
established algorithms that are employed
6:11
in industry
6:13
so here's a little bit of an older paper
6:16
demonstrating the use of
6:17
nearest neighbor classification for
6:20
image data
6:21
so here this is just an example of
6:25
face image data set and here's the mnist
6:27
data set
6:28
more specifically this paper was not
6:32
just about the application of k-nearest
6:33
neighbors it was about
6:35
um distance metric learning so learning
6:38
a distance metric
6:39
for the k-nearest neighbor method we
6:41
will talk more about distance
6:43
metrics also in this lecture only very
6:45
briefly
6:46
for instance um the my harlem nova's
6:49
distance uh
6:50
was yeah learned here we will also
6:53
briefly mention
6:54
uh the mahada nova's distance and how
6:56
it's related to the euclidean distance
6:57
measure
6:59
may be notable is that they achieved a
7:01
test error rate of one point three
7:03
percent
7:04
on mnist hand written digits so
7:07
it's just uh yeah interesting because we
7:09
talked about mnist in the past in the
7:11
last lecture
7:12
and this is a relatively classic image
7:16
classification data set where the task
7:17
was to recognize handwritten digits
7:19
i think it was like 50 000 training data
7:22
points in this data set
7:25
so here is another interesting
7:26
application of k nearest neighbors
7:29
so here it's not k nearest neighbor
7:31
classification but
7:32
k nearest neighbor regression the
7:35
title of this paper was remaining useful
7:38
life estimation of
7:40
lithium-ion cells based on k-nearest
7:42
neighbor regression
7:43
with differential evolution optimization
7:46
so here they estimated
7:48
how many life cycles are left in a
7:52
lithium ion battery using k nearest
7:55
neighbor
7:55
regression yeah lastly one of my
7:59
applications of k nearest neighbors in a
8:01
recent on research collaboration earlier
8:03
this year
8:04
so this paper was entitled machine
8:05
learning to identify
8:07
flexibility signatures of class a gpcr
8:11
inhibition gpcr these are proteins um
8:15
a special type of membrane protein it's
8:17
called
8:18
um well it's a g protein
8:23
coupled receptor sits in the membrane
8:25
it's a relatively important
8:27
receptor throughout the animal kingdom
8:31
and of course in humans it's one of the
8:32
most
8:34
or biggest drug targets in humans it's
8:35
involved in many many different
8:37
processes in the body
8:39
so in any case so here we basically used
8:41
um
8:42
k nearest neighbors together with
8:43
feature selection to pinpoint
8:45
um certain regions in the protein
8:49
that are involved in certain activity
8:53
or in active and inactive states of that
8:55
protein because they're usually
8:57
some small ligands small molecules
8:59
binding to that protein
9:01
and they can either activate or inhibit
9:04
the protein receptor so we try to learn
9:09
what distinguishes basically active and
9:10
inactive proteins
9:12
so the inactive and active states
9:15
and um basically also looking at the
9:18
flexibility transitions
9:20
that are triggered by biologically
9:23
active ligands
9:24
so here we also used k nearest neighbor
9:26
classifiers
9:28
yeah after such a top-down look at the
9:31
k-nearest neighbor method
9:32
let us now take a bottom-up approach and
9:35
talk about the
One NN Method
9:36
one nearest neighbor method before we
9:39
dive more into
9:40
k-nearest neighbors and how it works so
9:43
the one nearest neighbor method
9:45
is a very simple method it's a special
9:48
case of k nearest neighbors
9:50
so it's um k nearest neighbors
9:57
with k equals one it's just a special
10:01
case of k nearest neighbors
10:03
so how does the k-nearest neighbor
10:05
method work
10:06
let's say if we want to use it for
10:08
making predictions
10:10
so here i'm showing you a simple data
10:13
set a toy data set
10:14
consisting of two features so we have a
10:16
feature x1 and a feature x2
10:20
and the training data set consists of
10:23
five data points one two three
10:25
four five so given this data set of
10:28
these blue dots
10:29
now assume we have a new data point we
10:32
have
10:33
this data point this question mark and
10:35
we want to predict
10:37
a target value for this question mark so
10:39
how do we do that
10:42
so to make this a little bit more
10:43
concrete for the target value for now
10:46
think of it as a classification problem
10:48
so we have
10:49
two classes class zero and class one
10:53
um so i took the five data points here
10:57
i showed you in the previous slide and
10:59
just mark them with appropriate class
11:01
label
11:02
so the triangles here are class 1
11:06
and the squares are class 0. so
11:10
what would be the class label for the
11:12
question mark point
11:14
in the one nearest neighbor method as
11:15
the name suggests
11:17
we found we find the most similar data
11:20
point
11:20
to our query point here in the training
11:23
set
11:24
so for the question mark point this is a
11:27
new data point this is
11:28
you can think of it as new data point
11:33
or new example that we want to
11:40
classify
11:43
so what is its label we want to find
11:47
want to find
11:51
the label which is either
11:54
a triangle or the square class
11:57
class 0 or class 1. and in order to do
12:01
that we look at the most similar data
12:02
point in the training set
12:04
and then look at what the label of this
12:07
training data set point is
12:10
so in this case the most similar data
12:13
point using a euclidean distance measure
12:15
would be this point here the square so
12:18
it's the closest point to the question
12:20
mark
12:20
so what we would do now is we predict
12:23
that this
12:24
question mark belongs to class
12:28
0 and that is how the nearest neighbor
12:30
or the first
12:32
simple case of a nearest neighbor method
12:34
works it's k nearest neighbor with k
12:36
equals 1. so we find the one closest
12:39
data point
12:42
so to talk about the nearest neighbor
12:44
method in a more i would say structured
12:46
way
12:47
let's break it down into a training and
12:50
a prediction step so remember
12:52
from lecture one we usually have a
12:53
training and a prediction
12:56
phase we sometimes also call the
12:58
prediction phase
12:59
inference so how um does the training
13:03
step for k-nearest neighbors or the one
13:05
nearest neighbor method looks like
13:09
so the nearest neighbor methods are also
13:12
called
13:13
lazy oops lazy
13:16
or lazy
13:20
we often say the nearest neighbor
13:22
classifier is a lazy learner
13:24
because there's not really a big
13:27
training step here
13:28
the training step is simply remembering
13:31
or memorizing the training data set
13:33
so if we have a training data set in d
13:35
here and with the data points
13:38
um with uh the data points here where x
13:41
is the feature vector
13:43
and y is the label
13:46
or target value so these are the
13:49
features
13:50
so it's a feature vector it could be one
13:53
or more features in the previous
13:55
slide where we had oops
13:58
where we had this setup we had two
14:00
features
14:03
[Music]
14:06
and i is the index over the data points
14:09
in the training set so in this case we
14:10
have
14:12
i equals 1 to n we have up to n
14:15
data points in the training set and the
14:18
training
14:18
step is simply remembering these data
14:20
points there's not really much we have
14:22
to do here in
14:23
the training it's just storing storing
14:26
the data in a sense
Prediction Step
14:29
then in the prediction step there are a
14:31
few more steps
14:33
so the prediction phase of the k-nearest
14:36
neighbor or
14:36
nearest neighbor methods is a little bit
14:38
more involved so that's where
14:41
nearest neighbor does all its work in a
14:43
sense
14:44
so again given the training data set
14:47
of size n the task in
14:50
prediction is to predict the label
14:54
of a new data point let's call this new
14:56
data point
14:57
xq so we have the features x
15:00
q you can think of q stands just for
15:04
query data point it's just a new data
15:06
point
15:08
we want to find its label so we want to
15:10
know what
15:11
it's um y label is the predicted y label
15:15
so we use then the nearest neighbor
15:18
model
15:19
f to make the prediction on this on
15:22
these features
15:23
and the algorithm is as follows so we
15:26
start
15:28
by setting it up with the closest point
15:31
so we want to find the nearest neighbor
15:32
so in the beginning we don't have a
15:34
closest point because
15:35
yeah we we just started it's our initial
15:37
condition
15:38
and then we set an additional parameter
15:41
here
15:42
a closest distance so that would be the
15:46
distance to the closest point or the
15:49
distance corresponding to this closest
15:50
point here
15:51
and we set this to infinity here
15:54
and then for every
15:58
data point in the training set so we are
15:59
iterating from
16:01
of we iterating from one over to n so we
16:04
have
16:05
again n data points in the training set
16:08
what we do is we compute the current
16:11
distance
16:12
the current distance means here the
16:14
distance d
16:16
some arbitrary distance measure we can
16:18
choose the distance
16:20
d between the current
16:23
training set point so this is a
16:26
training set point
16:32
and this one here oh i've written this
16:35
over here is the query point
16:37
so we compute the distance between each
16:40
training data point and the query data
16:42
point gray data point is uh the one
16:44
where
16:44
for which we want to get the class label
16:46
or target value
16:48
and given this distance now after we
16:52
computed this
16:52
we check it or we compare it to the
16:55
closest distance
16:57
so in the first round because we start
17:00
out with infinity
17:01
the first point we will encounter will
17:04
be
17:05
the closest point but then of course
17:07
while we iterate we may
17:08
find another more closer point
17:11
so if the current distance if we find
17:15
that the distance of the current point
17:17
we are currently looking
17:18
at is smaller than the closest distance
17:21
we found previously
17:23
we update this variable closest distance
17:27
with the current distance
17:29
and then also we save the closest point
17:32
so the closest point is the one that
17:34
corresponds to this closest distance
17:36
so it's this closest point that
17:40
we used in this distance computation
17:44
yeah and then we return the closest
17:46
point so the prediction
17:48
so this is uh the algorithm for finding
17:50
the closest point
17:52
and the prediction would be returning
17:55
the class label corresponding to this
17:56
closest point
17:57
because um let's say i find that
18:01
the closest point here is the point
18:05
13 in my data set so that would be let's
18:08
say my
18:10
my closest point would be 13
18:13
where we of course are interested in in
18:15
the label so what we would do is we
18:16
would also have to look up
18:18
the label of the closest point
18:22
and this is the prediction this is the f
18:24
closest point
18:25
the label corresponding to the closest
18:27
point and we have the label because this
18:29
data point is of course
18:30
the data point 13 is in the training set
18:33
yeah and that is
18:34
essentially the main idea behind the one
18:38
nearest neighbor method that's the
18:39
prediction step
Distance Measure
18:42
so regarding the distance measure in the
18:45
previous slide i just showed you
18:47
an arbitrary distance measure that i
18:48
call the d
18:50
commonly or most frequently what people
18:53
use
18:54
is the euclidean distance so if you have
18:56
continuous features
18:57
you don't have any particular preference
19:00
people usually start out using a
19:02
euclidean distance measure
19:04
but there are many many other different
19:05
choices i will list some of these
19:07
choices later
19:09
but yeah one one aspect to mention here
19:12
is if you use the euclidean
19:13
measure it's kind of important to make
19:16
sure
19:16
that the features are all on a
19:18
comparable scale that
19:20
um each feature weighs in equally
19:24
because if you scale one feature more
19:25
than the other
19:27
then this feature will of course um
19:30
dominate the distance computation so if
19:32
i have
19:33
two features like x1 and x2
19:37
and let's say i um put a point here
19:41
in the center and this feature goes from
19:45
one to ten and this feature goes from
19:49
one to 100 of course
19:54
if i have a data point i want to compare
19:56
it if i compare
19:57
these two data points to each other so
20:00
if i make the comparison between these
20:01
data points
20:02
then feature x2 will be much more
20:05
important
20:06
than feature x1 because you can see
20:09
the axis here for x2 this axis
20:13
is much larger the values are much
20:15
larger so they will dominate in this
20:16
distance computation
20:18
so if you want to make a fair comparison
20:20
then of course
20:21
uh it's important to have the features
20:23
on the same scale
20:24
but um not it's not always also a
20:27
requirement to have the features on the
20:29
same scale there may be a reason
20:30
why you want to weigh a feature more
20:32
heavily in this case you can also
20:35
intentionally
20:36
scale a certain feature but of course we
20:38
will talk briefly about this later
20:40
this is a hyper parameter it's like a
20:43
decision
20:43
you can make but you don't have to make
20:46
okay but before i get too distracted by
20:48
already talking about hyper parameters
20:50
here
20:51
let me wrap up this first video and in
Outro
20:54
the
20:54
next video we will take a closer look at
20:57
the nearest neighbor decision boundary

##v8:

0:01
yeah so in this second video we are
0:03
going to take a look at
0:04
the decision boundary of the nearest
0:07
neighbor algorithm or model
0:09
in particular we will take a look at the
0:11
one nearest neighbor
0:12
classifier so here i'm showing you a
0:16
data set consisting of two features
0:18
x1 and x2 and again the reason why we
0:22
use the two-dimensional data set here
0:24
for illustration purposes
0:25
is that humans can't visualize data sets
0:28
in
0:28
more than three dimensions usually so it
0:31
it is just easier to work with such a
0:34
simple toy data set so we can
0:36
visualize certain things and draw
0:38
certain things
0:39
so in this data set again we have five
0:41
data points the blue dots here
0:43
and let's just focus in on a and b here
0:47
and we are particularly interested in
0:49
the decision boundary between
0:51
a and b the points a and b so if you fit
0:54
a one
0:55
[Music]
0:56
nearest neighbor
1:00
model given the data set
1:04
what would the decision boundary between
1:06
a and b look like
1:07
so with decision boundary i mean
1:11
a line or a boundary here that divides
1:15
between a and b so if you have a new
1:17
data point
1:18
and it lies on this decision boundary it
1:20
would be equidistant from
1:22
a and b so maybe take a moment pause
1:25
this
1:26
video now and yeah think about what the
1:28
decision boundary would look like
1:32
okay so the decision boundary for a and
1:35
b here or the decision mark between a
1:37
and b
1:37
would look like this it would be
1:41
drawn here using a clean euclidean
1:44
distance
1:45
metric so any point that lies
1:49
here on this line dividing a and b
1:52
really at any point on this red line
1:54
is equidistant from
1:57
oops equidistant from a and b
2:00
so the distance between
2:05
on the line and a and b is basically the
2:08
same
2:09
everywhere on that line so if we would
2:11
go have a let's say a new data point
2:13
here
2:13
that we want to classify it lies here
2:16
it's the same distance from
2:19
a s from b everywhere on this red line
A and C
2:25
okay we are going to repeat this
2:26
exercise now
2:28
but now we are going to focus on a and c
2:32
so what would the decision boundary for
2:34
a and c look like
2:36
again it would be a line perpendicular
2:38
to a and c
2:39
such that every point on the line is
2:41
equidistant
2:42
from a and c so we would draw that
2:46
approximately like
2:48
this this would be the decision boundary
2:50
for a and c
2:52
all right next we have c and d the
2:54
decision boundary for
2:56
c and d here that would be
2:59
this line and so forth and the reason
C and D
3:03
why i was doing it is
3:04
if we assemble all these decision
3:07
boundaries for all the points
3:09
in the data set or the pairs of points
3:11
in the data set
3:12
we would get the decision boundary of
3:14
the one nearest neighbor classifier
3:17
so here in the bottom right corner we
3:20
have the decision boundary for the
3:22
one nearest neighbor classifier and if
3:24
you look at this diagram
3:26
um you've probably seen something like
3:27
this before and this is called
3:29
also voronoi diagram
3:35
or voronoi
3:38
tessellation
3:43
so we're basically dividing up the data
3:45
set such that
3:48
these lines are for each pair of points
3:52
the lines where each point on the line
3:54
is equidistant
3:55
to the two points on left and right
3:59
or perpendicular to this line for
4:01
example
4:03
this purple one is this one here
4:08
this one and so forth um yeah and
4:11
this would be how we construct a
4:14
decision boundary for one
4:15
nearest neighbor classifier but yeah of
Class labels
4:18
course we are not done yet in the
4:20
previous slide i just showed you the
4:21
decision regions
4:23
given a data set now let's consider the
4:26
actual class labels so before
4:28
i didn't show you any class labels so
4:30
every point was just
4:32
a dot here now consider the same data
4:34
set with
4:35
class labels again the triangles here
4:39
are class 1 and the squares are
4:43
class 0 so these are our class
4:46
labels and i've oops
4:50
i have um drawn them here on the left
4:52
side let's focus in on the left side for
4:54
now
4:54
so this is the same voronoi tessellation
4:57
that i showed you in the previous slide
4:59
except now i'm showing you also the
5:01
class label symbols here
5:04
how do we actually get from that voronoi
5:06
tessellation to the decision
5:08
region that the one nearest neighbor
5:10
algorithm would use
5:12
to make a classification that's
5:14
relatively straightforward
5:16
we would just take the union of those
5:19
regions that belong
5:21
to the same class label so for example
5:24
if we consider
5:25
this red triangle here we know
5:27
everything
5:28
that is um here enclosed by these lines
5:33
is the region that is closest to this
5:36
triangle
5:37
if i go over here this region here
5:40
this is the region the whole region here
5:42
is the one that is closest
5:44
to this this triangle here so we can
5:46
also fill this out as red
5:48
oops i'm sorry so everything here
5:52
on this side would be closest to the
5:54
triangle in the center
5:55
and then everything here is closest to
5:59
this triangle in the center so we can
6:00
also fill that out by red in red
6:03
now if we have this whole thing here in
6:04
red this is the decision region for all
6:07
the red
6:07
triangles it's just the union because we
6:09
know
6:10
for each one for this one for this one
6:13
and for this one
6:14
the triangle or eight triangle is
6:17
closest to any data point that falls in
6:19
here
6:20
so what i mean is if we have a data
6:22
point here it will be closest to this
6:23
triangle here in the center and so forth
6:26
so the whole region here on top is red
6:28
that's the union of all the
6:30
red decision regions and similarly
6:34
every data point that falls here in this
6:36
region will be closest to this blue
6:38
square so we can fill this out
6:40
in in blue and every point that falls
6:43
here
6:44
will be closest to this square here so
6:46
we can
6:48
sorry we can fill this out
6:52
in blue here as well and then when we do
6:55
that and
6:56
we just think of the blue regions now
6:58
instead of the voronoi tessellation
7:01
what we get is the decision boundary of
7:03
the one nearest neighbor classifier
7:05
it's basically shown here on the right
7:07
hand side
7:09
that is the decision boundary or
7:12
decision regions
7:13
these are the decision regions of our
7:16
one nearest neighbor classifier
Simple test
7:19
yeah so to test your understanding let
7:21
me ask you a
7:22
simple question let's suppose we have
7:25
our data set with the five dots
7:27
and i'm asking you which point is the
7:30
closest
7:31
to the question mark point so maybe
7:34
pause the video for like
7:36
a few moments and think about this
7:37
before i give you the answer
7:40
so if you have done that if you pause
7:42
the video and thought about it maybe you
7:44
would have realized there's one
7:45
missing component that i didn't mention
7:48
so in order to answer the question which
7:50
point is the closest a b
7:51
c d or e you would have to know
7:55
how the distance measure is defined
7:58
because
7:59
yeah it really depends on how we measure
8:01
closeness or
8:02
similarity or distance so i'll just
8:05
give you an example of what i mean
8:09
so what i'm doing here is i'm showing
8:11
you
8:12
the euclidean distance
8:17
of radius one for this point so let's
8:20
just suppose this is a radius of one
8:22
here
8:22
this um dotted circle
8:25
euclidean distance of one unit
8:29
[Music]
8:30
around this question mark point and if
8:33
we use or if we draw this
8:35
consider this euclidean distance here
8:38
you can see that the closest point
8:41
here would be
8:45
it would be this this one that i just
8:47
colored in a purple here
8:49
this would be closer than
8:52
than this point well let me use a
8:55
different color
8:56
so this distance here is closer than
8:59
the distances i'm drawing here in green
9:02
i hope you can
9:03
see that now if i would use a different
9:06
distance measure though for example the
9:08
manhattan distance
9:11
the manhattan distance is also called
9:13
taxicab
9:14
distance so using this distance measure
9:17
you can see now
9:18
that there's a different point that is
9:20
closer now and this point would be this
9:23
one that i'm coloring in green now so in
9:25
purple
9:26
we find that this point this purple
9:28
point here is the closest one
9:31
and using the manhattan distance
9:34
we find that this green dot would be the
9:37
closest one
9:38
so what is the correct answer and which
9:40
one is depend uh the closest point
9:41
it really depends on the distance
9:43
measure i mean there are different types
9:45
of problems where you care about
9:46
different distance measures
9:48
and it's up to you to define closeness
9:50
or similarity
9:51
usually we would use something like the
9:54
euclidean or manhattan distance but
9:55
there are also many other types of
9:57
distances that we may use
Continuous distance measures
10:01
yeah so here i have a list of the most
10:03
common continuous distance measures
10:05
so continuous in terms of the features
10:07
that we work with
10:09
one common distance measure of course is
10:12
the euclidean distance
10:13
you're probably already familiar with
10:14
that one and the manhattan distinction
10:17
distance which is very similar to the
10:18
euclidean distance but
10:20
uses um the absolute difference between
10:23
two values
10:24
rather than the squared distance like in
10:26
the euclidean
10:27
distance measure just to make this
10:29
comparison between manhattan and
10:31
euclidean distance more clear
10:33
let's consider the minkowski distance
10:36
the minkowski distance is a
10:37
generalization of the euclidean and the
10:40
manhattan distance
10:41
and here's the definition on the right
10:44
hand side
10:45
of the minkowski distance so what we can
10:47
see here is we have
10:49
two data points um data point a and b so
10:51
it could be two training examples
10:54
and then we compute the difference
10:56
between those two
10:57
and take the absolute value here so the
11:00
absolute difference between the two
11:02
and we do that for each feature j to m
11:05
so m is the total number of features in
11:07
our data set
11:08
i just realized i forgot an index here
11:10
it should be
11:12
xj and x j here because we iterate over
11:15
the features
11:17
um and there's one parameter here p so
11:20
if we set
11:21
p equals one that would be the manhattan
11:24
distance
11:24
so if we set p equals one the
11:28
p would go away here right because it's
11:30
um to the power of one
11:31
and then one over one is one so we can
11:33
also cancel this one here
11:35
and then you can see the manhattan
11:36
distance is um simply
11:39
the sum of the absolute differences
11:42
the euclidean distance is the special
11:44
case where we have p
11:45
equals 2. so let me sorry
11:48
let me erase i didn't want to re-erase
11:52
everything but
11:53
okay let me redo this one so i wanted to
11:56
show you the p here again in the
11:57
equation
11:59
if we set p equals 2 for the euclidean
12:01
distance
12:02
we will have a 2 here a squared
12:06
term and 1 over 2 which is a square root
12:10
so let's remove this one and just write
12:12
it like
12:14
like this is maybe more clear it's a
12:16
square root so in the euclidean distance
12:18
we have
12:19
the squared difference so we still have
12:22
these bars here but they don't do
12:23
anything because we square anyways
12:25
so we have the squared difference
12:26
between two feature values sum them up
12:29
and then take the square root to have
12:30
the original unit back
12:33
yeah and that's how the euclidean and
12:35
manhattan distances are related
12:37
usually i mean in practice it doesn't
12:40
always make a big difference which one
12:42
you use but like you've seen in the
12:43
previous slide it can make a difference
12:45
so which one to use it really depends on
12:48
the problem
12:49
in practice you can also consider the
12:51
distance measure unless you have some
12:52
domain knowledge you can consider the
12:54
distance measure as a hyper parameter
12:56
something to experiment with
12:58
and to see which one let's say gives you
12:59
better performance if you apply it in
13:02
on a real world data set another
13:05
distance measure is the malachanovis
13:07
mahalanobis distance so the mahalanobis
13:10
distance is a distance that considers
13:13
oh yeah the distribution of the features
13:15
so
13:16
in previous slides i mentioned that if
13:19
we work with
13:20
nurse neighbor methods it's important
13:22
yet to consider our feature scales
13:25
so sometimes or usually often we want to
13:28
make sure that our features are on the
13:30
same scale
13:30
to allow fair comparisons because
13:33
otherwise one scale or one feature will
13:35
dominate
13:36
in the distance computation like
13:39
euclidean and manhattan distance
13:41
the mahada nova's distance takes into
13:42
consideration the distribution of the
13:44
data for each feature so
13:46
you can think of it as a distance that
13:48
considers the
13:51
distance of a data point to its
13:53
distribution in terms of standard
13:54
deviations
13:56
um yeah we won't go into too much detail
13:58
there's one special case where mahalo
14:00
was an euclidean distance um
14:02
are similar and that is if the
14:04
covariance matrix
14:06
is um identity matrix so for example
14:09
if if i have unit variance so i have a
14:12
covariance matrix with ones in the
14:14
diagonals
14:15
and this is a coherence matrix of the
14:17
features so x1
14:18
x2 x3 in this case x1 x
14:21
2 x 3 and they are
14:25
all uncorrelated so covariance is
14:28
0 um for all the features they're all
14:31
unrelated
14:32
and uh the very they have all unit
14:34
variants in that case
14:35
the euclidean and mahalanobis distances
14:37
would be exactly the same
14:39
but yeah we won't go into too much more
14:40
detail about the mahalanobis distance in
14:42
this
14:43
class here the last distance measure
14:47
here on this list
14:48
of course there are dots. there are many
14:50
many more but the last i would say
14:52
relatively relevant one is the cosine
14:56
similarity
14:57
so what's the cosine similarity it's
15:00
considering
15:01
basically the angle between two features
15:05
so the how can i explain this maybe
15:07
think of
15:08
the dot product so if you recall the dot
15:11
product
15:12
let's um for simplicity use the vector a
15:17
and the vector b and this t is the
15:19
transpose
15:20
so a refers to this
15:24
x a for one dimension
15:28
oh sorry for all dimensions um and the b
15:31
is the x b it's just
15:35
a little bit too much it's just a little
15:38
bit too much to write so we will just
15:40
use
15:40
a and b here so if we write the dot
15:42
product between
15:44
a and b to between two vectors we can
15:46
also write it
15:47
if you recall from linear algebra like
15:49
this so we have the magnitude of a
15:51
which is a scalar times the magnitude of
15:54
b which is also a scalar
15:56
times the cosine of the angle between
15:59
the two vectors
16:02
now the cosine distance is you can think
16:04
of it as the normalized
16:06
dot product normalized by the
16:09
length of the vectors because if i want
16:12
to
16:13
get the cosine here what i do is i
16:15
divide by
16:16
a times or magnitude a times magnitude b
16:19
so what i get is a transpose b
16:23
times or divided by a times
16:27
b times cosine
16:32
theta so that is my
16:36
oh sorry equals cosine theta this is my
16:39
cosine
16:39
similarity measure when is that useful
16:43
um yes suppose we have a vector a
16:47
document vector representing
16:49
a document and now
16:52
using for example the euclidean distance
16:54
between two identical documents we will
16:56
find
16:56
the distance is zero um we will find for
16:59
example that the cosine similarity is
17:02
one it's like maximized but now consider
17:05
we duplicate each sentence
17:09
in the document so we just create
17:11
duplicate
17:12
sentences if we the more sentences we
17:15
add between the two documents
17:17
and we measure the distance between the
17:19
documents using the euclidean distance
17:21
we'll find the more sentences we
17:23
duplicate the more
17:25
dissimilar the two documents will become
17:29
however if we use something like the
17:30
cosine similarity which
17:32
measures the angle between the vectors
17:34
the angle is not really
17:36
that much affected by adding more
17:38
similar words because
17:40
the vectors or the words are sorry the
17:42
documents will still remain similar
17:44
because it's just duplicating content
17:46
so using the cosine similarity we'll
17:48
still find that
17:49
we have two very similar documents here
17:52
whereas with the euclidean distance
17:54
with every duplicated sentence we will
17:56
probably find that the documents
17:58
become more and more different so that's
18:01
maybe one
18:01
motivation for using cosine similarity
Discrete distance measures
18:06
so now here's a list of the discrete
18:09
distance measures the most common ones
18:10
that come to my mind
18:12
so one common discrete distance measure
18:15
is the
18:15
hamming distance and the hamming
18:18
distance just looking at it
18:19
it looks very similar to the minkowski
18:22
distance or
18:23
particularly the manhattan distance so
18:26
we also have
18:28
an absolute term here sum over
18:32
the m features so the only big
18:34
difference between this one and the
18:35
manhattan distance is
18:37
the data input is usually binary feature
18:40
vectors so usually we have
18:42
vectors that look like this so machine
18:45
learning binary
18:46
the term binary usually refers to values
18:48
0 and 1.
18:50
so these would be binary vectors because
18:52
they only consist of
18:53
values of zeros and ones but of course
18:55
it's
18:56
it's kind of the manhattan distance so
18:59
if we have two vectors let's call them a
19:00
and b that look like
19:05
this the only difference between the two
19:07
vectors here
19:09
is this one so in that way the manhattan
19:11
this uh sorry them in
19:12
hatton or hamming distance would be two
19:15
right so because
19:16
zero minus zero is zero one minus one is
19:19
zero
19:20
zero and zero zero here we have
19:23
absolute value of one another absolute
19:26
difference of one
19:28
zero zero so in the sum
19:31
is one one plus
19:35
one which is two so we would have a
19:37
hamming distance of two
19:39
another common similarity measure
19:42
measure for discrete
19:44
feature vectors um is the jaccard
19:47
similarity or
19:49
tanimoto similarity the word telemoto
19:52
similarity is often used in
19:53
computational biology
19:55
it refers to the same thing as the
19:57
jaccard similarity it was just
19:59
defined or rediscovered by a different
20:02
person named
20:02
tenimoto so which is why in computation
20:05
biology it's
20:06
more often called the motor similarity
20:08
whereas
20:09
in data mining computer science and so
20:11
forth and
20:12
machine learning it's more often known
20:14
as the
20:15
jaccard similarity how does the jaccard
20:19
similarity work
20:21
so let's uh look at the equation here so
20:23
what we have here is
20:25
um an intersection term
20:29
and a union term here i'm just writing
20:32
it out in more
20:33
verbose terms so what we have here is um
20:38
two sets a set a and b so
20:40
[Music]
20:42
again we have vectors but we um consider
20:45
them
20:45
as sets here so just to give you maybe a
20:49
more concrete example because it gets
20:50
really abstract here
20:52
so let's say we have the feature vector
20:55
consisting of the values one two
20:58
three four five six
21:01
something like that um and then the
21:04
other one would be
21:07
um let's call them five six seven
21:10
eight nine ten so we probably should use
21:14
commas otherwise
21:16
it's not clear because we have a
21:19
number 10 year not one and zero okay so
21:22
we have these two feature vectors oops
21:25
um and b and
21:29
let's construct them now as sets let's
21:32
call them capital a
21:34
so again one two three
21:37
four five six but the order doesn't
21:40
matter
21:42
here
21:44
5 6
21:47
7 8 9
21:51
10 and what we would do is to compute
21:56
the intersection we would first consider
21:59
what are the ones in common so in order
22:02
to compute this denominator term we
22:03
would
22:04
find that 5 6 here
22:08
is in common so the intersection vector
22:12
a
22:15
b that would be uh sorry the
22:16
intersection set
22:18
that would be 5 6 and the length of the
22:22
set here
22:22
this would be length 2 right
22:26
um okay so now let's consider
22:31
uh the denominator what's the length of
22:33
set a
22:34
these are six values it's um
22:38
let's do it like this length of a is
22:42
six the length of b is one two three
22:46
it's also six
22:53
so we have 12 as the length here
22:57
the combined length so this term is
23:02
12 and then this intersection term is
23:04
again
23:05
the two so 12 minus 2 equals
23:08
10. so the jacquard similarity between
23:10
the two vectors
23:12
here would be 2 over
23:15
10 which is 0.2
23:20
so put it point two we could also say
23:23
some people use the word jakarta
23:25
distance so we can also say
23:27
it's a jacquard distance of 0.8 so the
23:30
jaccard distance
23:35
it's just the similarity or one minus
23:38
the similarity sorry
23:41
so it happens all the time sorry
23:46
yeah somehow my ipad is super sensitive
23:48
if i touch it in the wrong way it
23:50
advances to the next slide but yeah also
23:52
this is all i wanted to say about this
23:54
slide here really
24:00
yeah so for this video on distance
24:03
measures and distance
24:04
metrics one big takeaway is
24:08
also that feature scaling is important
24:10
for most of these
24:12
so for example recap the euclidean
24:15
distance measure that we talked about
24:17
on the left hand side i'm showing you an
24:18
example where the axes are on the same
24:21
scale
24:22
so between oops between 0
24:25
and 5 here on both on the x1 and the x2
24:29
x's
24:30
on the right hand side here i rescaled
24:34
the x1 feature however i kept
24:38
the dots at the same position just for
24:41
adding a visual effect so i just
24:46
use the same dots the same layout of the
24:48
dots but i
24:49
just use a different axis and you can
24:51
see now how the euclidean distance
24:53
measure would look like when i
24:57
if i expand the
25:01
x1 feature so before data point b
25:05
was the closest one to the question mark
25:07
now with this rescaled
25:10
measure here with a rescaled feature
25:13
now c is the closest one right because
25:16
um b is now much farther away because
25:19
it's now
25:20
yeah 10 uh sorry two times farther away
25:23
than before because i rescale the x one
25:25
axis by the factor of two all right so
25:28
yeah that was a lecture on
25:31
one year's neighbors and some feature
25:34
measures
25:35
so next we will talk about the k nearest
25:38
neighbors method

##v9:

0:00
yeah i just want to make a quick
0:02
addendum i think in the previous video i
0:04
just said
0:05
um distance metrics not all of the
0:08
distance measures we discussed in the
0:10
previous slides are metrics
0:12
or proper metrics for example the cosine
0:15
similarity
0:16
is not a proper metric because it
0:18
doesn't satisfy the
0:19
triangle inequality which if you
0:22
remember
0:23
maybe from other courses is
0:26
defined as follows so the distance
0:28
between two data points
0:30
and c um is smaller equal to the
0:33
distance between
0:35
a and should be b i think plus
0:39
d on b and c right because
0:42
um b and c is like this so where we have
0:46
three data points let's say a b
0:49
and c on some number line anyways um
0:52
just
0:53
an addendum that the cosine similarity
0:56
is not a proper metric but
0:57
still super useful in practice in
0:59
certain contexts
1:00
so in this video i'm going to cover the
1:03
k-nearest neighbors
1:05
approach the k-nearest neighbor model
1:08
before we
1:08
mainly talked about the one nearest
1:10
neighbor model however
1:12
there's not that much to say about k
1:14
nearest neighbors because
1:16
it's just a generalization of the one
1:18
year's neighbor method
1:19
so this will be a relatively short video
Example
1:24
so here i'm showing you an example of a
1:27
k-nearest neighbors
1:28
model and again we have our two favorite
1:31
features x1 and x2
1:33
arbitrary features and the toy data set
1:35
here so just have it easy to visualize
1:38
and like so often we want to classify a
1:40
data point
1:41
so in this case it's the question mark
1:43
here in the center again
1:45
and what we do is we consider
1:50
these data points in this radius here
1:51
let's say using a euclidean
1:53
distance measure so if i would consider
1:55
these neighboring points here
1:57
to make a prediction about the question
1:59
mark in the center
2:01
what would be the value of k in this k
2:04
nearest neighbors approach
2:05
maybe pause the video for a few moments
2:07
and think
2:08
about what k could be here i think that
2:11
should be relatively
2:13
intuitive to guess right now so yeah k
2:16
is 5 here so this is a 5
2:19
nearest neighbors model i'm considering
2:22
the five
2:23
closest data points to the data point i
2:25
want to classify
2:27
and here i should mention also we have
2:29
three different classes we have these
2:32
these crosses here we have these circles
2:35
here and we have these triangles here
2:37
so what we do is we take a look at all
2:40
the
2:41
data points in this or the five closest
2:43
data points and we look at
2:44
the counts of each class so we see in
2:47
this case we have
2:49
one two three triangles one circle
2:53
and one cross so that means this
2:56
triangle is the majority we have three
2:58
triangles
2:59
and the regular k nearest neighbors
3:02
approach
3:03
uses a majority vote to do the
3:05
classification so in this case the
3:07
predicted class label can you guess what
3:09
it is
3:09
yes it is a triangle
3:14
yeah so i just said in k nearest
3:16
neighbors we use the majority vote to
3:19
assign the class label
3:21
uh you let us be a little bit nitpicky
3:23
about the term majority vote now for a
3:25
second
3:26
so a majority board is usually if we
3:29
have
3:30
two different classes and we look at the
3:33
one that is in the majority that means
3:34
more than 50 percent
3:36
so in this case the majority vote would
3:39
be
3:39
the square so in this case a here this
3:42
would be the
3:43
square symbol here it would be the
3:45
majority vote another term for that
3:48
here in this case is plurality vote i
3:50
just see
3:51
there's a typo i wrote pure reality but
3:54
it should be
3:56
plurality and here
3:59
too oops
4:03
plurality so
4:06
the polarity uh vote in this case would
4:08
also be the square
4:11
um in the bottom example in example b
4:13
here
4:14
however we don't have a majority vote
4:16
because there's
4:17
if we have three classes here there's
4:19
not necessarily anything that has
4:21
more than 50 percent so for example if
4:24
we would have
4:25
one circle one square in the
4:28
remainder would be these green diamonds
4:32
then the green diamond would be the plur
4:34
the majority vote because we would have
4:36
more than
4:37
half of the data points as diamonds
4:40
but here in this case there is no symbol
4:44
so the square the circle and the diamond
4:47
none of those reaches more than 50
4:49
percent so we don't
4:51
have a majority here if we are strict
4:53
with the words
4:54
in this case we actually have a
4:56
plurality so the plurality means
4:58
the data point that occurs most often
5:03
in in this data set here
5:07
so in this case it would be the diamond
5:09
so but
5:10
usually you know in practice we are not
5:12
that picky with these words we just say
5:14
majority
5:16
i think in britain it's also called the
5:20
relative the plurality is also known as
5:22
the relative majority
5:24
or in certain countries so let's say
5:26
british english has the word relative
5:28
majority which means in
5:29
american english plurality
5:32
so we don't need to be super picky in
5:34
this class we will just use
5:36
majority to mean the
5:39
label the class label that occurs most
5:41
often so in that sense we say
5:43
in k nearest neighbors we pick the
5:46
data point or sorry the class label that
5:49
occurs
5:50
most often among the neighbors so and we
5:53
call that the majority vote
5:56
maybe also related to this slide now
5:57
that i see that one question you may
6:00
have is
6:01
what happens if there is a tie so for
6:03
example
6:04
we consider
6:07
three nearest neighbor algorithm say we
6:10
have our three nearest neighbors
6:12
there's a triangle square and a circle
6:15
and we want to classify this data point
6:16
and there are
6:18
other data points around it but here in
6:20
this
6:21
radius there are only these um three
6:23
data points and each one has a different
6:25
cluster what we what do we do in this
6:27
scenario so it really depends on how
6:30
it's implemented in software
6:32
but usually there's no really no good
6:34
way to
6:36
pick one data point over the other we
6:38
would just
6:39
pick one label at random so it's not a
6:41
good thing to do but that's how it works
6:44
in most software packages
6:45
usually in software packages also you
6:48
have
6:49
integer class labels let's say 0 1
6:52
2 and so forth and usually the software
6:55
if there's a tie would pick the one
6:57
with a lower class label index
7:00
there are certain modifications of
7:02
k-nearest neighbors i will talk a little
7:04
bit about this
7:05
later in a later video that consider
7:08
the distance though so if you have
7:11
these five nearest neighbors you would
7:13
still even though you found the
7:15
neighbors you would still
7:16
consider the distance to the center
7:18
point here so for example
7:20
one of these three might be closer to
7:22
the center than in one of the other ones
7:24
so you would pick the class label that
7:26
is corresponding to the training data
7:29
point that is closest to the center
7:31
but yeah i'm going into too much detail
7:32
here at this point i think
7:34
just what i wanted to say here on the
7:36
slide is technically
7:38
we have a plurality vote in k nearest
7:40
neighbors but we
7:41
can just call it majority vote it's just
7:43
fine i think
7:44
among us we know everyone knows what we
7:46
mean by that
Definition of majority vote
7:49
yeah if you would like to have a little
7:50
bit more formal the definition of the
7:52
majority vote
7:53
here i've written it down in more
7:55
mathematical
7:56
terms so consider we have a
8:00
subset d sub k which is
8:03
the subset of the k nearest neighbor so
8:06
if we have
8:07
k equals 5 these would be the five
8:09
nearest neighbors here
8:10
of course d sub k is a subset of the
8:12
whole training set
8:14
now the majority vote part this is this
8:17
part here
8:18
is as follows so there's a lot of stuff
8:20
going on in this arcmax function
8:22
so let's just um untangle it from maybe
8:26
from right to left
8:28
so this part here this is the prediction
8:32
the returned let's call it the returned
8:38
returned label
8:41
and y is a possible class label
8:45
so both f of x
8:48
and y are both
8:51
class labels in the previous slide we
8:55
used class values or class labeled
8:58
square
8:58
oh sorry triangle square circle
9:01
now let's assume we have actual integers
9:04
like 1
9:05
2 3 up to t
9:08
so that is here on one of the possible
9:10
class labels
9:13
and um this delta function here
9:16
it's kind of the opposite of zero one
9:19
loss
9:20
it assigns a value 1 if
9:23
a equals b so that means if this value
9:26
here
9:26
equals the f of x it returns a 1
9:29
otherwise a 0.
9:30
now what we do here is we compare
9:36
in a way uh we search for the class
9:41
label
9:41
that maximizes the function arguments
9:45
here
9:46
um sorry we search for the function
9:49
argument that maximizes
9:51
this sum here so if i have my neighbors
9:54
my five neighbors let's say i have
9:58
among my neighbors the class labels
10:01
1 1 two
10:05
three one
10:08
or five yeah so let's say i have five
10:10
neighbors like that
10:13
um and also note that we have the sum
10:16
here
10:16
so i sum over the five neighbors and see
10:19
which one gives me the best or the most
10:23
let's say the most um
10:26
the highest the largest sum so i can put
10:29
any value here for y
10:31
but if i don't put a value here that
10:34
matches my neighbors
10:36
then i will get a 0 right
10:39
so if i put a 1 here
10:42
let's say let's do this concretely we
10:44
start with y equals one
10:46
and i compute the delta here for this
10:48
part um
10:52
so for this part so i get first
10:56
one right get a one because a equals b
10:59
i get another one here i get a zero
11:02
because
11:03
one doesn't equal two here i get a zero
11:08
and here i get a one and the sum
11:12
the sum of that is equals equals
11:15
three so if
11:18
we would put a one as our predicted
11:21
class label
11:23
or if we would put a one here we would
11:26
get a three
11:28
if we put a two here instead of
11:31
so we put a two here instead of the one
11:33
for y
11:34
what we would get is we could get a
11:36
result of one right because there's only
11:38
one two
11:38
it's the only one that matches here in
11:40
this part if i put a
11:44
3 here for y if i put y equals
11:47
3 the sum would also be only a 1 because
11:50
there's only one 3 here
11:51
so it's only one matching this y here
11:54
so i can just again try out all these
11:56
different values
11:58
and i will find that one maximizes the
12:00
sum here
12:01
so the arc max so the argument that
12:04
maximizes this function here
12:06
the arc max would be y
12:09
equals one and this would be then the
12:12
the prediction by the k
12:13
nearest neighbors on the for the query
12:16
point q
12:16
so this again sorry the f i said um it's
12:19
the prediction is more like the return
12:20
label
12:21
for this data point so the prediction is
12:24
the return label
12:25
this is here on the left hand side this
12:27
h is the prediction
12:29
so the arc max is just a way of
12:32
let's say a convoluted way of writing
12:34
the majority vote finding the most
12:36
common class label
12:38
and you probably in other statistics
12:39
classes just refer to this as
12:41
the mode so what is the most frequent
12:43
data point
12:45
in our case we are interested in the
12:46
class label so i was writing f of x but
12:48
really these are
12:50
our y is our class neighbors i wasn't
12:52
writing y
12:53
because then it can be confused with
12:54
this y here
12:57
okay i hope i didn't confuse you so it's
12:59
just
13:00
maybe a more formal way of writing the
13:02
majority vote
Regression
13:05
yeah we can also use k n for regression
13:08
analysis
13:10
for regression analysis that's actually
13:12
a bit simpler to write
13:14
it's usually just the average so the
13:17
regular
13:18
k n algorithm for regression is just
13:21
averaging the continuous target values
13:23
for the k
13:24
nearest neighbors so again we have a
13:26
data set d
13:27
sub k um the prediction
13:30
h so h is the
13:34
prediction of knn
13:38
so this is just the average over all the
13:40
k nearest neighbors so
13:42
k nearest neighbors i'm just averaging
13:44
over the target value so again
13:46
these are my whys the target values of
13:49
the training data points here in this
13:50
case the k nearest
13:52
neighbor training data points
13:56
yeah that is basically it for this video
13:58
i think it was a bit shorter than the
14:00
previous videos
14:01
the next video will be again a little
14:03
bit more interesting i think this will
14:04
be
14:05
a short video on big o analysis like
14:08
analyzing the runtime complexity of k
14:11
nearest neighbors

##v10:

0:00
yeah now it's about time to talk about big o and k nearest neighbors run time complexity
0:07
so big o is a notation or concept in computer science that is used to
0:12
analyze the efficiency of algorithms so usually that refers to the runtime
0:17
complexity in terms of the execution speed but then also um
0:23
with a focus on how it behaves asymptotically if we have a very large data set sometimes big o notation is
0:29
also used to analyze the memory efficiency so how much memory is required
0:36
so if you think back of what i showed you in the very beginning of lecture two the training step of
0:42
k-nearest neighbor is simply saving the training data set and that itself can be very expensive so
0:50
saving the training data set can require a large amount of ram so computer memory or if we keep it on
0:58
the hard drive um yeah hard drive storage space hard drive storage space space has been come
1:04
has become cheaper over time but yeah depending on how we implement the k-nearest neighbor
1:09
algorithm it may require that we hold all the data points in in memory and if we have a large data set
1:16
let's say millions of images then this can be quite a limiting factor
1:21
but right now let's more focus on a runtime complexity that means how fast k n is in the
1:29
prediction step so first for those who have not heard
Big O notation
1:35
about it let's briefly introduce big o or big o notation so here i'm just listing uh several
1:44
functions that uh are used for
1:49
basically describing how efficient an algorithm is so we could also maybe extend this list and call this
1:56
column notation and then we have a big o of 1 of
2:02
log n and so forth and we usually use these functions here
2:07
to denote the the complexity or the runtime of other functions so these
2:13
are the common ones that are usually used in the context of big o um i will show you a concrete
2:20
example how to find out the runtime complexity of certain functions in a few moments
2:26
but yeah i will also on canvas if you have not heard about big o before post some reading material and some
2:33
introductory reading material about big o there's also something called big theta and big omega so they are related
2:39
concepts so maybe it would not hurt to read about this in a i would say more detailed tutorial
2:45
because in this class we don't focus that much on computer science it's just that we use big o here
2:51
right now to understand the k nearest neighbor algorithm so in this table i'm sorting also
2:59
the functions from lowest runtime complexity to highest
3:08
runtime complexity so that means uh yeah the the higher up the function
3:14
is on the list the better the faster it would execute for example
3:19
so what we have is just to maybe briefly go over it we have a constant one so constant means no matter how big my
3:26
data set is um this function would never become more expensive if n increases so
3:35
we we usually look at the case where n approaches infinity
3:40
so if this grows really really large let's say infinitely large how would my function behave a constant
3:46
function wouldn't be affected by that at all so it would execute at the same or in
3:51
the same manner and that is the ideal case scenario so functions like that that are that fast
3:58
and not affected by the number of data points let's say in machine learning that would be awesome but of course it's
4:05
usually not realistic logarithmic is also pretty good still
4:11
linear is also still pretty good but of course not good as good as logarithmic
4:16
then we have log linear growth it it's a bit slower than linear but again not bad uh where
4:23
it becomes bad or what people kind of start consider as
4:28
not ideal is everything let's say starting with quadratic or beyond so
4:35
quadratic cubic or higher level polynomial complexity and especially exponential complexity
4:41
that's usually considered very bad and in this case it's not ideal to use such algorithms
4:47
for very large data sets yet to get a more visual impression of
Runtime complexity
4:52
how the runtime complexity looks like as a function of n i made a plot here so
4:57
on the x axis that's n the size of the data set
5:03
and f of n is basically the complexity of the algorithm so basically what happens if i plug in n
5:09
into into the function here so as you can see uh if we are at the very low end here
5:16
around two it doesn't really matter which algorithm we use it's about the same uh runtime so we can also
5:22
maybe um yeah consider this as a time that it takes to run the algorithm
5:29
not just only the output of the function but really like a runtime so the higher the worse and
5:35
the lower the better of course so we can see as we increase n certain functions become increasingly
5:43
increasingly bad it's hard to see how well the quadratic one is doing
5:50
because we are really here at a very small level still and um also we have a large
5:57
scale so this scale is not really zoomed in into this area here so it's kind of hard to see
6:02
how really how very expensive the quadratic already is but what we can see is that something
6:09
like cubic becomes really bad really fast and then especially this um
6:15
exponential one it is like exploding very soon even with small numbers so usually we want to
6:20
really avoid exponential growth in machine learning in terms of the data set size
6:30
so to explain a little bit more about how we get from a certain let's say function to the big
6:35
o notation of that function i'm providing an example here so this is
6:41
a simple function a credit quadratic function and this would
6:46
basically reduce to a big o complexity of x squared so quadratic the reason is
6:53
that we usually only look at the dominant term so the dominant term is the one that grows
6:59
the fastest in this case it would be um this term here because uh and like
7:06
we've seen in the previous slide comparison to this term the growth of this one and this one is really natural
7:13
so these are so small that let's say they're so small if we go to n infinity that we can just ignore them
7:19
and then also it doesn't really matter whether we have 14 times x squared or just x
7:27
squared when we go um with n really large it's it'll be both really large numbers so
7:32
usually we also would drop this and just focus on on the
7:38
um x here so that is how we would get the big o notation of this function so let's
7:44
take a look at a different function now yeah so like you saw in the previous
Scaling factors
7:51
slide scaling factors are usually dropped when we do the or when we derive
7:56
the big o notation so in the for this example might be useful if you pause the video for now and um just
8:03
maybe try to solve it yourself and then i will give you the solution in three seconds
8:09
yes so again like in the previous slide the solution would be um or we would be focusing on the
8:15
dominant terms so we would be dropping this term here and this factor here just focus on the x
8:23
so we have x log and then again this is negative if we go from x
8:31
or we if we consider x to be infinitely large whereas x grows infinitely large so in
8:38
this case what we would have here what would remain is x
8:43
log x so again yeah dropping the non-dominant terms
8:49
focusing on the dominant terms here and that would be log linear growth in that case
Natural logarithm
8:56
oh yeah so one additional note i wrote x log x
9:03
and not x log 2 x so i have the natural
9:09
logarithm instead of the logarithm with basis 2. and it's because it doesn't really matter which one we use
9:16
so we um we don't really distinguish between different logarithms we usually just use the natural logarithm and
9:24
yeah why is that i mean if you think about transforming the base of a logarithm for
9:29
example if i go from log 2 to let's say
9:35
the log of base is 10 or the block with base is 10. how i would write that is simply log
9:42
10 of x divided by log 10 should be 2 right so i could express
9:49
it like as follows and then you can see if i just rewrite this as um 1 over
9:58
look 10 2 times
10:03
look 10 x you can see the x is inside here so here in this term
10:10
there is no x really involved so it's just a scaling factor so we can just drop this scaling factor
10:16
and now i have log 10 of x here so um for the big o
10:21
notation but of course i can do that with any basis so i can also use the natural
10:27
logarithm so i can just drop the 10 here so we have a natural logarithm now some people write the natural logarithm
10:34
also as ln but in this class we will just use log for the natural logarithm which is
10:39
more common so i can also do this and then the big o notation for this function
10:47
here would be x log x right so in that case we don't have to worry about the basis of the
10:53
logarithm you can just simply ignore that as well yeah instead of
Python matrix multiplication
11:00
giving you another boring symbolic function i thought i would give you a python function here to explain
11:07
um big o notation or just to show you an example a concrete example of applying big o
11:12
notation to a computational algorithm so here i implemented matrix
11:17
multiplication a function for matrix multiplication between two matrices a and b
11:23
and this is a very inefficient way to do a matrix multiplication in python and i was just doing this
11:28
intentionally because next lecture i'm going to show you a more efficient way of doing
11:34
that the point here really is not the efficiency of this matrix multiplication it's more about just having a function
11:40
so that we can look at the big o complexity or the runtime complexity of this function
11:48
so let's maybe walk through this function step by step so what am i doing here so again the
11:54
inputs to this function are these two matrices um a and b so i'm actually calling it
11:59
here so um i'm calling the matrix function multiplication function here so the
12:05
inputs are a and b the two matrices and there will be an output matrix
12:11
c so c that's what's getting returned here as my output matrix so i'm just setting it up in the
12:18
beginning so that we have a matrix of zeros and then we populate the matrix with the
12:24
values so as you may know if we multiply two matrices
12:29
and we have let's say matrix um m times p let's let's just use the concrete numbers
12:36
we have a matrix a with dimensions um two times three
12:44
and then the second matrix is three times two right so three rows one
12:52
two oops one two three two columns so the output dimension would be
12:59
output dimension would be two times two right
13:08
so this would be my output dimension so i'm just setting it up here so here
13:16
sorry here in this block i'm setting up my output matrix it will be
13:21
then a matrix of 2 times 2 because here i'm doing this
13:28
i'm iterating i'm putting a 0 for each row in
13:33
length a so because i'm using a python list here the length of a is 2 because um this
13:39
list has two sub lists so each row is a sublist sub list one sub is two
13:46
so this will be giving me a list of two
13:52
and then for each column i will um do the same thing here for
13:57
each column in b so again this will evaluate to two so i will have a two by two matrix
14:03
this looks a little bit complicated this is called list oops
14:11
i hate it when it happens list comprehension
14:17
this is called list comprehension okay so but the focus is not really here on
14:22
creating the output it's um it's important but we can see
14:30
that here we have two for loops whereas here we have three for loops so the
14:36
majority of the time in this function will be spent will be spent here right so not
14:44
in not in here so let's see how we carry out the actual matrix multiplication so what i'm
14:51
doing here is for each row
14:56
in my matrix a so i'm iterating first over the rows so
15:02
i'm starting with the first row and then let's say for the first row which is
15:07
one two three right for the first row then i'm going through
15:14
the columns in b so the columns in b um these and these
15:22
so now let's say we consider the first column 5 6 7
15:30
so that's where we are right now we have this first row in this first column and
15:36
then i'm saying for each column in a
15:43
so i'm now iterating through columns here
15:48
so we are let's say still in the first iteration we're entering over columns
15:54
i'm adding the existing value in c we start with the value 0 right so that would be
16:00
the value 0 and then we multiply between the first column
16:09
and the first value so the first column here and the first value in my um in this
16:16
column here so i'm basically updating it like this right so i'm multiplying one times five
16:24
and then i'm putting one times five here to update the first value
16:34
so next we would uh look at the lower end or the deepest for loop to complete the
16:40
deepest for loop first so which is this one so again we
16:45
we said we iterate over call a which is um the position in um the column
16:52
position in in this row here in the first row still and
16:57
we use that call a here and here sorry here and here so we use that
17:03
before to compute one times five and then update the position zero now
17:09
what we do is um i should maybe say no the value here would be five
17:14
after the first update now what we do is we advance one more position but again
17:21
because we use it here and here we also advance this position here so
17:28
we are at six now so the second update would be one times six which is six and we add
17:35
this addition here we added to the previous result again so this should be updated now and should
17:41
be 11 and so forth and we would yeah complete this um and then after we completed this for loop
17:47
with a third number here we would um go back completing this for
17:53
loop and so forth so once we've done that we would get the
17:58
this this following result here and if you have not followed exactly how this python function works
18:04
don't worry so much about it that's not the point of this slide the point of the slide is really the
18:09
runtime complexity so we would try to um find what are the expensive parts here that
18:17
depend on the input size so in this case what we have is we have
18:24
three for loops so these are the expensive for loops
18:30
of course we also have some for loops here but there are only two nested follow-ups so the really the expensive part is is
18:36
going to happen here so if we think of matrices in this case
18:42
let's say in case of quadratic matrices like a quadratic shape
18:48
what we can see here is that we are iterating over the rows
18:55
and over the columns and again over the columns of that row so in that
19:00
case um if we consider n the number of rows and the number of columns of this matrix
19:06
because there are three four loops what we would find is that the runtime complexity of this function is n cubed and as we've
19:13
seen earlier in the plot n cubed that's actually a pretty expensive algorithm so in practice we
19:19
would never use such an algorithm here in practice there way more efficient way to do a matrix multiplication in python
Runtime complexity of Knearest neighbors
19:28
yeah so now the more interesting question what is the runtime complexity
19:33
of the k-nearest neighbor algorithm so if you think of the brute force search
19:40
that we introduced in the beginning for the one nearest neighbor search we are searching for k near
19:48
neighbors so we we want to carry out the search k times so we search
19:54
for k neighbors and in the brute force search if we use
20:01
the naive approach that we covered at the beginning of this lecture in the first video we are looking at each
20:07
training example so we have k neighbor neighbors and we check
20:14
each training example to do the distance computation
20:22
and the training data set let's say we call that n we have n training examples so that
20:28
depends on n so if we have 100 training examples we have to do
20:34
100 um distance computations
20:39
against the query points and if we want to use k numbers if you want to find k n neighbors and we use a naive approach we
20:45
have to repeat this process on k times but they are more efficient way of doing that but in the most simple case we would be
20:53
k times searching for the neighbor in the n sized training set
21:01
and then another factor is if you think back of the euclidean distance the distance depends on all the
21:07
dimensions so if we have a euclidean distance with a sum over
21:15
where all the distances between let's say some query point and some um data point in the training
21:22
set so this is for one data point let's
21:28
let's call this i the i training point in the data set we would have
21:34
of course n times these computations so if i have the euclidean distance like that
21:41
this would depend on the dimensions so if we have m dimensions we would have the distance
21:49
computation depending on m the number of dimensions so if i would then
21:55
consider that i would have k times n times
22:02
m that's my runtime complexity of a naive application of k nearest neighbors of
22:08
course um k is usually very small we usually use something like 5 or 3 5 7 10 something like that
22:16
so in that case maybe you can ignore that okay here and for m i mean usually also we have
22:25
very large training sets and lower dimensions so usually we have n it's much bigger than
22:31
m so in that case we maybe can also drop the m here
22:36
and in that case what remains is um runtime complexity of n as the size of
22:41
the training set and that would be for the most naive implementation of the k nearest neighbor algorithm
Making Knearest neighbors more efficient
22:48
let us briefly think about how we can make k nearest neighbor algorithms more
22:53
efficient so maybe also that's a good point here to pause the video
22:59
and to brainstorm a little bit and think about possible ways for making k-nearest neighbors more
23:04
efficient and maybe you can even take an hour half an hour go for a walk and think about it and
23:10
come back later and continue this video it's one of the advantage of having an online
23:15
video compared to in-person classes and after yeah after you've done that we
23:21
will talk about some of the possible ways so i'm intentionally leaving this part
23:28
this slide blank now and in the following slides i will show you again the naive
23:33
k nearest neighbor implementation then i will show you one little trick and in the following video i will show
23:39
you some more tricks and maybe uh if you thought about potential ways your way may be different from what
23:46
other people tried and that would be then an excellent class project or maybe even research
23:51
project so here is one naive way um how we can
Knearest neighbor search
23:58
implement the k nearest neighbor search so i just call that naif sorry if
24:04
nearest neighbor search um there are of course many different ways we can do that but that's on the i would say most simple one i can
24:11
think of i call this variant a i will show you in a next slide another idea i had for implementing k
24:18
nearest neighbors so what's going on here so first i will start with the data set
24:24
dk so this is um we start with an empty data set so this
24:30
will be the data set holding our k nearest neighbors and then we implement the while loop we
24:36
say while the size of the set of the set decay here
24:41
is smaller than k then continue doing something and that is finding a new neighbor that we can add
24:48
to the set so how do we find the neighbor this is similar to what i've shown you in the very first
24:54
video of lecture two so we start out by setting the closest distance to infinity and then
25:00
we iterate over the training set for all the data points that we have not considered yet so for
25:07
the symbol here means for all i data points that are not contained in the set
25:14
decay so what i do then is i compute the current distance between
25:20
my query data point that's the point i want to classify and the ith data point in the training
25:26
set so the is data point is what we are entering or iterating over so we have n data points in the training
25:31
set like always and then we say if the current distance is smaller than the closest
25:37
distance we start with infinity then we keep that point so we consider it as
25:43
a closest point so after each loop here let me use a different color
25:49
after each loop over the training set we will find one neighbor that we
25:56
haven't found before so by each loop we increase the size of decay until
26:01
it reaches size k so what we have is we have k times a for loop
26:10
over the n training data points so what would be the big o complexity of
26:16
this maybe pause the video and think a little bit about this
26:23
yeah i hope this was pretty straightforward so this would be k n because we look for
26:30
k near neighbors in the n sized data set that's one way of implementing k nearest
26:36
neighbors here i thought about a different way for
Variant B
26:44
implementing k nearest neighbors i call that variant b it's basically doing the same thing we did in the
26:49
previous slide backwards so i start with a subset dk which is the
26:55
whole training set and again while the length of the k is not equal to k
27:02
we do continue doing something but instead of drawing decay like in the previous one in the previous line
27:08
slide we said if dk is smaller than k now i say if dk is greater than k
27:16
so what i'm doing now is i'm eliminating data points from this um set decay until
27:22
i reach my desired number of neighbors so this because we eliminate we start
27:28
with the largest distance setting it to 0 because we want to
27:34
find the point that is the farthest away from our query point and remove that
27:39
so we set the largest distance to zero and then again for each data point in the training set
27:45
um but also again we only consider the ones that are not already con contained in in the subset here oh sorry
27:51
in this case we are considering only the ones that are contained in the subset because this is what we want to
27:57
eliminate we don't want to consider points that we already eliminated in the previous round so for all the data points in the
28:04
subset i compute again the current distance so we compute the current distance
28:10
if the current distance is larger than the largest distance in the first iteration this will be of
28:15
course true because the largest distance will be likely larger than zero otherwise
28:21
it would be exactly the query point if that's true if we find a point that
28:27
is larger away than the largest distance we already have then we save that point
28:33
and then we remove it from decay and we remove points until the size
28:43
of decay matches k so i have a greater sign here so if this is
28:50
true so if k sorry if the length of decay if we want to find let's say
28:56
five neighbors and the size of dk oops size of decay is
29:04
six then we would still meet this criterion here and then execute the last while loop and
29:09
in the last while loop again we remove one more data point so after this while loop
29:15
d k will also be size five and then we can stop so what is the time
29:20
complexity of this variant b so what do you think
29:27
yeah so in this case since we go backward we start with n training data points and then we
29:33
eliminate right so we have n minus k and then because we have a for loop
29:41
we have a for loop for each
29:46
neighbor that or for each data point that we remove from our decay list so it should be times n so what would be
29:54
the time complexity of this approach that would be then n minus k i should put this in
30:00
parentheses times n so which one is more efficient
30:06
variant a or b because that depends on the size
30:13
of um k so if we have a large k uh compared to n then of course um
30:20
variant b would be more efficient than a but in all likelihood n
30:26
is much much larger than k so that case i would say um variant a is more efficient
Priority Queue
30:34
yeah another idea i had is using a priority queue that can help us speeding up k-nearest
30:40
neighbor implementations so in the previous two slides variant a and variant b kind of suffered from the problem that
30:47
we checked the training data set repeatedly which can be wasteful i think
30:53
so we could for example use a priority queue um and kind of keep track of our nearest
30:58
neighbors as we check the data set so we don't have to check it k times because here in the previous
31:04
slide we basically selected one neighbor um when let's say variant a we selected one
31:10
neighbor and then once we selected it we started all over again and did the same check over all n
31:17
minus 1 data points to find the second neighbor
31:22
so what we could do is we could initiate a priority queue so for example if we are interested in
31:30
k equals five neighbors we could um take the first let's say or just
31:36
randomly five data points in the training set and initialize a priority queue
31:42
for example let's say we call it the data point x 5 x i don't know x
31:50
13 x 4 and let's let's change this to k equals
31:55
3 so i don't have to write that much um let's say we found these five
32:00
uh three random points and we can keep track of them as we check our training
32:06
set so when we iterate over our training set we check for each data point in the training set
32:13
is it closer than this one if yes then we replace this point here
32:19
with the point in the training set if no we check this one and say okay is this
32:25
point closer to my query point than this given training point if yes again
32:32
we swap it otherwise we move on to the next one and we say if this data point is closer
32:39
to the current training point um then we swap this one with the current training data
32:46
point otherwise we we continue up to the next training point so in that way
32:52
um we only have one sweep through the training set we don't do the
32:58
n checks multiple times right so that way um that can help us speeding up the k nearest neighbor
33:04
search and yeah for this priority queue we can use a data structure also for example a
33:10
heap data structure to make this more efficient and then this would eventually come down to
33:15
something like um log k times n so we again have at least one
33:24
time we really have to sweep over the whole training set but we don't have to do it we don't have to do a full
33:29
sweep again in the next round for the k nearest neighbors so i just set um heap data structure
33:39
so what is the heap data structure you don't really have to know this for this class really this is like a
33:45
computer science concept a data structure in computer science i will post a link on canvas for further
33:52
reading if you're interested but really you don't have to know what a you don't have to know what a heap is
33:57
for this class here but no if you're interested let me just quickly tell you what a heap is
34:02
so it's just a data structure for organizing a data set or an array and it allows us
34:09
to find certain points more efficiently so let me uh draw a binary heap so it's
34:16
kind of like a decision tree let's consider a try data set let me
34:22
just pick some random numbers i don't know 1 8 6 5
34:28
9 7 so let's say i have an array like this i would organize it into a heap data
34:35
structure by starting first i would basically construct the initial heap so
34:42
i would go put the first element at the root and then it's a binary data structure so
34:48
what i would do is i would take the second two elements put them here eight six
34:54
you can put the larger one to the left for example but usually we go just how the data or array is organized
35:02
then i have a five and nine so i start always on the left side i'll just put the five
35:07
here the nine here and the seven the remaining one
35:12
here because this is like an unorganized heap so we would then in the next step um yeah sort this array
35:20
so how that works is for example i could all put all the largest values on top and for that i
35:27
would do several swaps so i would for example swap these two numbers so six and the seven so after swapping
35:34
them i will have the seven here and the six here
35:41
um and then i can use a different color i can swap these
35:46
two and in one swoop um because nine is greater than eight and eight is greater than one so i can
35:52
also swap these two here so in one step how that would look like after a swap i would
35:57
have the nine here the
36:02
one here right and the eight here
36:11
and then of course i can swap the one and the eight right so let me cancel or
36:18
remove this so you can see what we currently have and then the last step i because eight is greater than one i would swap
36:25
these two so in the end i would then have
36:31
the one down here the eight up here so the cleaned up
36:37
version of the heap would be nine eight five
36:44
right here one seven six
36:52
and this one allows me for example more efficiently to look up certain values more
36:58
efficiency efficiently so if i want to find the largest value i would stop at a root node
37:04
and then you can go through the seep basically and find the largest value always basically um to
37:11
the left so large uh the larger one is to the left so here in this case the eight and then
37:16
here the right side is the seven and then for each root node i have again like an organization where the larger
37:22
value is to the left and the smaller value is to the right and i just see um since we're interested
37:27
in similarity and distance it would actually be more useful to have a heap
37:32
that is organized such that the smallest values are on top so what i was just
37:38
drawing is a max heap you can also draw a min heap that would actually be more useful
37:44
for nearest neighbor search with a priority queue but again this is like a detail you don't have to worry about in this class
37:50
i was just briefly going over the concept over of a heap i can just post some tutorial
37:57
if you're interested in learning more about it but again you don't have to really understand how a heap works
38:05
so next um in the next video i will make this a separate video i will show you some more tricks for making k-nearest neighbors more
38:11
efficient so the priority queue is like a nice idea but the priority queue is also not super
38:18
efficient compared to some other tricks that people usually use in practice

##v11:

0:00
In this video, we are now going to talk about how we can improve the
0:04
K nearest neighbors algorithm using certain modifications, and also
0:09
considering certain hyper-parameters.
0:13
So in the previous video, we talked about a priority queue, which is.
0:20
Basically a data structure that we use to make seniors neighbors more efficient.
0:25
So use the priority queue to avoid searching the whole training set every
0:30
time when we looked for a new neighbor.
0:32
So here another way to make.
0:35
The performance of the computation performance of Kenya's neighbors,
0:38
more efficient it's using space, partitioning data structures.
0:45
The heap was technically also space partitioning data structure,
0:51
data structures, to speed up the sweep over the training, examples themselves.
0:57
So in that way, we maybe can avoid making a distance computation for every.
1:03
Training data set point.
1:05
If we can divide the data set upfront into a space petitioning data structure.
1:11
So for example, one simple technique for doing that would be packeting.
1:18
So again, this is something that we do upfront.
1:20
Now.
1:21
The priority queue is something we would run at, um, the, uh, prediction time.
1:26
But we are talking now about data structures.
1:29
During training.
1:35
So in that way, um, can you hear us neighbors won't be as lazy as before, so
1:40
it's not just storing the data points.
1:42
It's also, yeah.
1:44
Petitioning the dataset during training.
1:47
So in bucketing, for example, if we have, again, our simple data
1:51
set with two features, X one and X two, we could think of a way.
1:56
Of dividing the data set into sub sets on two buckets.
2:01
So we can make, for example, equally sized buckets, maybe like this, and if
2:08
we know the location or the features for each bucket, so the feature measurements,
2:13
the boundaries for each market, then we can avoid searching the whole
2:17
training set for every query point.
2:19
So for example, if a query point.
2:22
Located here.
2:24
It would maybe make sense to only search points within this pocket.
2:29
I wouldn't have to search points that are, let's say over here.
2:32
Right?
2:33
So that way it can actually eliminate all.
2:36
These data points here in my training set.
2:38
If I'm interested in the question Mark, for example.
2:41
So in that way, that is one way we can make the search more efficient.
2:47
There are more sophisticated ways of doing that.
2:50
One is for example, called K D tree just makes also relatively similar,
2:58
um, Hyper cubes, similar to bucketing.
3:02
It will look a little bit different.
3:03
It will look a little bit like this, where we divided up like, like this.
3:09
Hmm.
3:09
And this is a very efficient, um, approach for dealing with it and substructure.
3:14
Uh, we don't go well, we don't need to go into too much detail about Katie trees.
3:18
That's really a computer science topic.
3:20
We don't need to know all the details about all the data structures here.
3:24
It's just like I'm here about the main concept that we can.
3:28
Petitioned a search space here.
3:30
Another one that is very common is so-called ball tree.
3:36
It's more like, um, an algorithm for making spiritual lockets.
3:41
Instead of these hyper cubes, we make hyper spheres to divide the dataset
3:45
and which one to use really depends.
3:46
So if we have a large number of features, the ball tree would be, for example, for
3:50
example, we preferred over a KD tree.
3:54
Um, There is a tool that we will be using in this class pretty heavily.
3:58
It's called psychic learn machine learning library.
4:04
And this library has a setting for the cane, nearest neighbor classifier.
4:08
It's called.
4:09
So you don't have to memorize this.
4:10
It's called algorithm.
4:14
And in the algorithm setting for the Kenya neighbor classifier, there
4:18
are different options you can set.
4:20
By default, it's set to auto.
4:23
And that means that the tool, the machine learning tool, but automatically based
4:29
on your training set to decide which one to use, which space petitioning
4:33
algorithm to use, you can override the setting by providing options
4:37
like, um, KD tree or wall tree manually, but usually there's no need.
4:45
They will.
4:46
I mean, the algorithm has been written in a way that they will
4:48
automatically choose the one that is most efficient for given training set.
4:54
There's also an option called brute, which is basically a brute force search.
4:58
And this brute force approach would be the naive, keen years neighbor implementation
5:03
that we talked about earlier.
5:05
The, what we call it, the variant a I already know in the previous
5:10
video, another approach to making.
5:14
Kenya stable is more efficient.
5:16
It's using dimensionality reduction.
5:19
So dimensionality reduction, um, comes into flavors.
5:22
There is a feature extraction it's usually involving the like involving linear
5:31
transformations of features or nonlinear transformation of features, squishing
5:35
them onto a lower dimension of space.
5:37
We'll talk way more about that later in this course.
5:40
And another flavor is a feature.
5:43
Selection.
5:45
So for example, again, the main differences, if I have, let's say
5:49
three features X one X, two X, three feature extraction may combine them
5:54
in a way that we have a new feature, that one, and that two, for example,
5:58
or just that one and feature selection would take one of these features.
6:03
So it doesn't make a new feature.
6:05
It doesn't combine these features or transforms these features.
6:08
It's just selecting one, for example, we may select X one, the next three.
6:13
So in that way we just reduced.
6:15
It's the number of features that we use.
6:17
And why does it make Kenya neighbor more efficient?
6:20
It's because we have a cheaper distance computation, right?
6:24
If you think of the Euclidean distance, if you have fewer
6:26
features, we have fewer things.
6:29
To compute in the Euclidean distance.
6:31
So that might be another way to make seniors neighbors slightly more efficient.
6:37
And there's also something called the curse of dimensionality.
6:45
And this is usually a big problem in machine learning.
6:48
When we have a large number of dimensions, um, there's a problem,
6:52
usually that the generalization performance, that means how well.
6:56
The algorithm will perform a new data.
6:59
Um, so with the cross of the dementia right here, that means the more
7:02
features we have, usually the worse, the generalization performance becomes,
7:07
and that is usually due to over-fitting.
7:09
So, because in a high dementia space, everything is.
7:12
Pretty far away compared to a lower dimensional space.
7:15
I have a more concrete example with some numbers about that in the cost notes,
7:21
but again, we don't need to go into too much detail here in the lecture notes.
7:25
So I recommend any ways that you read the cost notes, where I give an example
7:29
for the course of dimensional team.
7:34
Yeah.
7:34
We can also improve the computational performance of
7:36
Kenya's neighbors by editing or.
7:40
Pruning.
7:40
So pruning or editing simply means that we are editing out or removing data points
7:46
from the training set, but we remove them in such a way that they won't the
7:51
decision boundary, if they are removed.
7:54
And to show you an example of what that means.
7:57
Have a look at these plots here.
8:01
So on the left hand side, where I'm showing you is a plot, a
8:04
scatter plot again with two feature axes X one and X two.
8:08
And I have two classes, these circles and these diamonds.
8:14
And you can see, for example, if we would have a new data point somewhere,
8:18
let's say located on this end here, and we want to classify that.
8:23
Uh, and we would consider the nearest neighbors assume for this purpose,
8:27
we have a continuous neighborhood model with K equals three or larger.
8:31
What would happen is we would find, for example, these, uh, three neighbors here.
8:37
And even though we have the diamond here, it will never really do
8:40
anything because per majority vote, we also have these two circles here.
8:45
Right?
8:45
So in that way, really, this is kind of.
8:48
Not necessary to have it here because it will never really change the decision
8:52
boundary because we always consider three neighbors and there will always
8:56
be two circles in the neighborhood here.
8:58
So what we can do is we can just get rid of this point here so we can remove this.
9:04
And similarly, we can also remove this point at the no one left corner.
9:08
So what happens then basically is that we.
9:12
If we have any point here in this region as shown on the right, these
9:16
will still be classified the same way as if, um, these diamonds were included.
9:21
So there's just a way we can make the computation more efficient
9:25
because we have fewer comparisons for your distance computations.
9:29
So when we look for the caners neighbors and the cost level, A concept that is
9:35
somewhat related to the editing and pruning earth creating prototypes.
9:40
So with that, I mean, replacing a dense region of training data
9:44
points with a single data point.
9:47
So for example, if I have a data set like this again, I have my two
9:51
features X one and X two, and I have a lot of data points over here.
9:55
The training set
10:00
really dense region.
10:01
And again, I have a, maybe a redone region here.
10:07
So these are two classes, two different classes, the red and the green ones.
10:11
Can we just use colors?
10:12
What I can do is I can replace these points.
10:17
Buy bigger points.
10:18
So if I have a K nearest neighbor model with cake was three, and I don't really
10:24
have to have all these points around here, because if I have a new data point
10:28
that falls in here somewhere, I don't really have to have all these points here.
10:33
Right.
10:33
So what I can do is I can replace them by a few number of prototypes.
10:38
So I can, um, get rid of these points for example, and put some,
10:45
oops, some bigger points here.
10:47
Let's call them the prototype points, something like that.
10:54
And even though I have these points way, fewer points than before I would
11:00
still get the same classification.
11:02
Right.
11:02
Because if a point is over here where the question Mark is.
11:05
If I consider the three nearest neighbors, let's say this would be, these ones would
11:10
be still the circle class, that red.here.
11:14
And similarly, I could also replace on the right hand side, these green
11:17
dots by field prototypes, or we don't have to have all of them around.
11:21
And again, by having fear training examples, I will speed up the
11:25
computation of course, because I have fewer comparisons to make.
11:31
Another aspect next to having this algorithm running more
11:34
quickly in a prediction task.
11:37
Another advantage of having these prototypes is also that it
11:40
will require less storage space.
11:42
So it's also space advantage that we don't need to have a large, let's
11:46
say a storage space requirement.
11:48
Now, if we have a data set of billions of data points, we can maybe reduce
11:52
it to thousands of data points and can save up on a lot of storage space.
11:59
Now another topic is improving the predictive performance.
12:03
Before we talked about the computation performance, making it run faster.
12:07
What about making it perform better?
12:09
Having a better.
12:11
A better prediction, accuracy.
12:16
It's also an important consideration in practice, of course, because we not only
12:20
care about having a fast algorithm, but also a hot and very accurate algorithm.
12:24
Otherwise it wouldn't be useful in practice.
12:26
Usually your machine learning algorithms come with a lot of settings, lots of
12:32
options that we can choose when we.
12:34
Run these algorithms and these options are also called hyper parameters because
12:39
they're not really parameters that we fit.
12:42
So they are not really extracted from the training data.
12:46
The, these are so called hyper parameters.
12:48
Hybridized are, you can think of them as tuning options or.
12:58
I agree with them settings.
13:06
This is usually something that I grow them.
13:08
Doesn't learn by itself.
13:10
It's something you, as the user would play around with and then see
13:14
if it can make the algorithm perform better than with another setting.
13:18
We will.
13:19
Talk a lot about this in the model evaluation lectures, that
13:23
we will see how we can do that properly without over fitting.
13:26
But for now, let's just consider we have different options and by these,
13:31
uh, or using these options and setting different values for these options, we
13:35
can also make a better can end model a better, can you just name a model?
13:42
So, yeah.
13:43
What are these different options?
13:44
So there's of course the value of K the number of cane years, neighbors
13:49
to consider there's of course, no solution to every type of data set, but
13:54
usually you would try different values.
13:56
For example, three, five, seven.
14:00
10 15, 20 and so forth.
14:03
And see what from speller, uh, as a rule of thumb, the larger case, the
14:08
smoother, the decision boundary will be, and the smaller, the case of constant
14:12
noise yet the decision boundary will be.
14:14
If you have a binary data set, it would make sense to use
14:18
values like cake what's three.
14:20
Okay.
14:21
I have like all the values because if a binary data said this
14:23
way, you will never get a tie.
14:25
If you use, for example, um, cake was to, okay.
14:29
Cause for you can get a tight where you have, let's say two labeled for.
14:34
Class zero and two labels for class one.
14:37
And then it's basically a random decision, which prediction you make.
14:41
And I don't like randomness if it can be avoided.
14:43
So I would usually choose the odd numbers.
14:46
I have a binary classification data set.
14:50
Another hyper parameter that we talked about earlier in lecture, two
14:54
was the scale of the feature exists.
14:57
Sometimes it's desired to have features on the different Xs, because then
15:02
we can maybe incorporate some domain knowledge and say one feature is way
15:06
more important than another feature.
15:07
So we can also.
15:09
Affect the decision boundary by scaling this feature.
15:13
So that's also one hyper parameter, unless though you have some domain
15:17
knowledge or some specific reason to change the feature exists.
15:21
I wouldn't touch them.
15:22
It's more like, um, usually I would just make sure they are on
15:26
the same scale, but then you can maybe, um, experiment with tweaking.
15:31
These exist a little bit.
15:35
Another I have a writer would be the distance measure.
15:38
So we talked about choosing different distance measures, like the Euclidean
15:42
distance, the Manhattan distance, and so forth, or the core sign similarity.
15:46
So in a way, these options are also available and depending on the
15:51
problem at hand, one distance metric may perform better than the other.
15:57
Lastly, we can also introduce a weighting Trump in the distance measure
16:01
computation, and it is somewhat related to scaling the feature Xs, but sometimes
16:06
it's just more elegant to yeah.
16:09
At this weighting Trump in the feature distance computation.
16:15
Yeah.
16:15
So in this video, I'm showing you the decision regions of three
16:19
different Kenya, Neva models and four different values of QI.
16:24
So my question would be, can you guess which key value corresponds to which plot?
16:30
Again, we have two features X one and X two, and we have two classes.
16:35
It's a binary problem.
16:37
So we have these squares and the triangles.
16:40
So maybe take a few moments to think about it.
16:43
Um, yeah.
16:44
Which K value corresponds to which plot?
16:48
So, yeah, if you paid attention to the previous slide, what I said is
16:51
that usually the smaller case, the noisier, the decision boundary is
16:57
so in this way, we would have the noisy I want here cake what's one.
17:01
You can see that in particular, if we look at on certain examples,
17:04
you can see there's a boundary around these individual points.
17:07
So that can only be on cake what's one, right?
17:10
Cause if we have cake what's three.
17:14
We wouldn't observe something like that for cake what's three, for
17:17
example, we see that this point here it's, again, the same point.
17:22
It doesn't really influence the decision boundary anymore because there are
17:24
always two or more triangles around it.
17:27
And then again, this is I'm coming back to the editing or pruning.
17:32
Um, slide that I talked about earlier.
17:34
Sometimes it makes sense just to remove data points because they don't really
17:37
influence the decision monetary and anyway, and it's just a waste of time
17:41
to include them in the training set.
17:43
So here, this would be actually corresponding to.
17:47
Okay.
17:47
Quartz three.
17:48
And the smoothest decision Monterey would be this one cake with seven.
17:51
So you can see, for example, here are these two on triangles influence
17:55
the decision Monterey because, uh, for K cause three, these two ones
18:00
outweigh the square next to it.
18:02
But here it's not true because we have a lot of squares around this region.
18:07
So these two triangles don't really do anything anymore.
18:12
So, yeah, we can also do the feature waiting via the Euclidean distance.
18:16
So recall the Euclidean distance as would be this whole thing here.
18:20
We can also insert a weight WJ here.
18:24
If we have all the weights equal to one, that would be like the
18:27
regular Euclidean distance, or it can also include a, a weight here.
18:32
So for example, if I have we, uh, w J.
18:38
To the, so the second feature, if I said that to two, this
18:41
would be equal to scaling the second feature by effect of two.
18:47
So it's in that sense, equivalent to feature scaling.
18:50
So we don't really has to modify the distance measure.
18:53
We can also scale the features upfront.
18:56
It's just a different way of doing it and here at the bottom, and
18:58
just show you how you can do that more efficiently using get adopt
19:02
product, um, on doing linear algebra.
19:07
So what I'm, what I'm showing you here is, um, so this part should be equivalent to
19:14
computing the regular Euclidean distance.
19:16
So for example, we would subtract the two vectors.
19:19
So vector a and B are the feature vectors corresponding
19:22
to training, examples and beam.
19:25
Um, maybe let's, let's do a spontaneous example.
19:28
If I have.
19:30
A vector a let's say one, two, three, and the vector B.
19:36
So XP just right before space reasons.
19:40
Um, it's just a two, three, four, then a minus B would be sequence
19:48
minus one, minus one minus one.
19:51
Right.
19:52
And, um, the.
19:54
Transports C transports C.
19:56
That would be minus one times minus one, plus, sorry.
20:04
Minus one.
20:05
Minus one is a one plus again, minus one times management is again
20:09
one plus minus one times minus one, a second one, which is three.
20:15
So see transports C is three and then the square root would be squared of three.
20:22
Um, we can then insert the weight that we had up here using
20:26
a matrix, a diagonal matrix.
20:29
So in the stack of a matrix, why do we have space here in this stack of a matrix?
20:33
I would put the weights three one w two w three.
20:38
If I have a three dimensional vector in the diagonal.
20:42
And then I can express this more efficiently because linear algebra
20:47
computations and Python are just more efficient than writing a followup
20:50
because the sum symbol would usually translate to a followup in Python and
20:55
next lecture, we will see how we can use non-paid to do the dot products.
20:59
So maybe just to compute the, uh, or complete the computation
21:02
here, if I have my w and it's just used values, don't know one, two.
21:08
Three here for these weights.
21:11
I would first, I mean, I can do it either way, right?
21:14
Can compute this first or this first.
21:16
It doesn't matter, but let's just compute this one first.
21:19
Um, so what we do is, uh, we compute C transports w C minus
21:25
one, minus one, minus one.
21:27
So minus one times one plus minus one times zero plus minus one times zero.
21:34
That should be.
21:36
Um, minus one.
21:38
Right?
21:39
So let me write this down here.
21:43
Oops.
21:44
Minus one.
21:45
And then for the second row, zero times, minus one, two times, minus one, zero
21:52
times minus one, that is minus two.
21:56
Um, for the third one, zero times minus one, plus zero times minus
21:59
one plus three times minus one.
22:01
That should be minus three.
22:03
Right?
22:04
So this is our vector C transports w and then we multiply it by the rector C again.
22:11
So minus one times, minus one is one.
22:14
Let me put it you're on the top.
22:17
Um, plus minus two.
22:21
Times minus one that's two plus minus three times minus one is three.
22:28
So the results six that's the result of C transposed w um, times,
22:35
sorry, C transports w with a dot product C that is this value.
22:44
And if I would take the square root, this would be.
22:48
Square root of six.
22:51
So yeah, there's just a more efficient way than let's say using this.
22:54
Um, some, but if that didn't make any sense, don't worry about it.
22:58
Uh, we will talk more about nonPareil in algebra, in the next
23:01
lecture and why that is faster.
23:03
Let's just, yeah.
23:04
Rambling here on how we can do the feature weighting more efficiently
23:08
compared to using the followup in Python.
23:13
Yeah, just a quick clarification.
23:15
I didn't want to interrupt my own train of thought here on this example, but I
23:19
just noticed while I was writing this, that, that so square root missing.
23:22
So if we want to have the.
23:24
Feature weighted Euclidean distance.
23:26
We would have a square root there without the square root.
23:29
We have that feature weighted squared, Euclidean distance, and practice.
23:34
It doesn't really make a difference, but whether we use squared or the
23:38
regular Euclidean distance, but yet just to make this example consistent
23:43
with what we have above here, we have to have a square root here.
23:49
Yeah.
23:49
Another flavor of Canaan is the distance weighted Keenan.
23:54
How does that work?
23:56
I hope you remember this equation here.
23:58
This is the mode.
24:00
It's just a fancy way of writing the mode.
24:02
And this is for determining the class table during predictions.
24:06
So basically the majority vote and yeah, here, this is why we brought it
24:11
in a fancy vape in the previous slide.
24:13
Cause we can then also insert the weight here now that compared to the feature
24:18
weighted Euclidean distance, right.
24:19
This wait is not for the feature, but for the training example, I, so what does
24:24
it do maybe to give you a more intuitive example, uh, then this equation here
24:30
consider we have a data point that we want to classify, and then we have the, let's
24:36
say five nearest neighbors around it.
24:38
Say we have this triangle here, this triangle here, and
24:43
this triangle here, and then.
24:45
Two circles very close by.
24:48
So these would be my five nearest neighbors that I would consider for the
24:52
majority vote using a regular normal cane.
24:56
N what we would assign here as the class ever would be the triangle, right?
25:00
Because we have three triangles and only two circles.
25:03
However, if we use the distance weighted on Canaan, we may
25:06
even prefer these circles here.
25:09
Right?
25:10
Because, um, what we do is we weight the distance.
25:13
So with a mean of the distance between each training data point
25:21
and the actual query data point, and we can have a different weight for
25:26
how heavily we weight the distance.
25:29
There's a common way to do that.
25:30
It's like the, um, Square to sincere one over the square to distance between
25:37
the query data point quantity here, it's the data points you in the center
25:42
and the given training data point.
25:44
But yet again, this is just an arbitrary hyper parameter.
25:47
There may be different options you could consider practice.
25:50
Sometimes people also add a small value here.
25:53
Let's call it Epsilon.
25:54
I don't know, like some very small value, like zero point.
25:59
Zero zero zero zero five zero zero zero one.
26:03
For example, um, just some small value to avoid a zero division error.
26:09
If we have a data point.
26:11
That is exactly the same.
26:12
Of course, this again, depends on manufacturers also depends on what
26:17
we choose as the distance matrix.
26:20
A metric.
26:20
So we can use also the Euclidean distance metric.
26:22
If we use the Ukrainian descent metric to find the care nearest neighbors,
26:26
which would be the most intuitive way.
26:28
But again, this is another hyper parameter.
26:30
We are really free to choose any distance metric that we would like to use.
26:35
So yeah, there are many, many have brightest when we talk
26:37
about Ken years neighbors.
26:40
Okay.
26:40
So, um, that's it about improving, uh, Kenya's neighbors?
26:46
Um, And yeah, next lecture.
26:49
We will talk about Ken years, neighbors in Python.

##v12:

0:00
Yeah. After talking about Kenya's neighbors in great detail. Yeah. Let us finally get to the fun part of the selection.
0:06
Sure. K nearest neighbors in Python. So what I'm going to show you is, uh, Cody example, I made, um, you
0:14
know, implementing Kenya's neighbors, using the psychic learn library. Not all of it may make sense at this point, the next lecture, we
0:21
will talk more about Python and num PI also about psycho turn. So right now this is maybe more like a teaser.
0:28
I will go. Through some of the concepts already, but if you feel that's a little bit
0:33
too complicated at this point, you can also watch the video later after we discussed non-pay and some of the psychic learn basics, but I thought maybe it's
0:42
a good opportunity here to give you a top down view of how these tools work.
0:48
So I will go to this website here, um, and donut also the code examples from here.
0:57
So, yeah, that's the website. So we have a right now in kind of more interactive session and instead
1:03
of doing the slides, so I set up a GitHub repository for this class. And the reason why I like uploading things to GitHub is because it's
1:12
also like a real world, um, tool. So I just see, I should fix this line, issue, this, everything on one nine.
1:20
Okay. It doesn't matter now. I don't want to get distracted now, but yeah. Um, GitHub is a tool that.
1:26
Most machine learning researchers use in practice. So it's kind of good to become familiar with it because many
1:31
people upload the code there if they write papers and things like that. And I also heard that a lot of companies nowadays, they ask for your GitHub profile
1:41
when you send in your CV or resume. So, yeah, it doesn't hurt to build a portfolio and get up at some point,
1:48
maybe even uploading your class projects and this semester, if you have some cool projects that you want to share.
1:55
So it's always a good idea to share it because yeah, my recruiters may want to take a look at this at some point.
2:02
Yeah. If you want to donut things from GitHub, if you go to a repository like this repository here, you can click on this green button here and there should be
2:11
a donut zip link, and it will download the whole repository as a zip file.
2:16
Now, like I said before, I will be updating this repository. And if you don't want to read down what the whole repository,
2:23
every time you can also clone it. So. What that means is we make a copy of the guitar repository on our
2:31
hard drive or on our computer. And then we can update it later on in this course.
2:37
So I will also show you how that works. So instead of downloading the zip file, I will copy this link here,
2:43
and then I will go to my terminal. So on windows that might maybe a little bit different. I honestly don't know exactly how to do that on windows.
2:51
So I'm on a Mac here, but also the same concepts would apply on Linux. I think there may be good tutorials for windows and the TA can also
3:00
help you with that because the TA is also one of my research students and he's also using windows.
3:08
So I will first go to my desktop because it's just a temporary setup here.
3:14
Um, and then I type good cologne and paste this link that's downloading the content
3:24
may take awhile.
3:34
So after it, download it. Um, we have this folder here now on the desktop, and if I open it, it's
3:39
basically a copy of the getup repository. Uh, and there are some additional files or an additional folder.
3:47
That's the docket folder. It just contains the basic GIP, get history, get lock files, and so forth.
3:54
So this is, um, this good folder is basically what makes it a good repository. And then once I've done that and, um, I navigate into this folder,
4:04
I can in future update it by. Doing good pool, for example, right now it's up to date because I just don't
4:09
know that it, but let's say next week you want to get the latest update. You can just type good pull in.
4:15
It will only download the changes that want redone or the whole folder.
4:22
Now to show you the code examples, I will make a copy of that because I don't want to modify it because if I would modify it here and then I would type a
4:32
good pool, what will happen next time? Is that, um, Yeah, it will get maybe some conflicts of, because we changed
4:39
something and it does match the version that it's pulling anymore and so forth. So I'm making a separate copy on my desktop here, and then I'm navigating
4:49
into this folder and we will be using.
4:54
Oh, sorry. It was the wrong one. I have a coat folder or somewhere else on my computer.
4:59
So I'm now in this folder and there are two files. Um, uh, I P Y N B file, which is a Python notebook file.
5:09
It's called Jupiter notebook nowadays. Back in the day it was called IPython notebook and there's a text
5:15
file, a CSV file to pre precise. And this contains the Iris dataset.
5:21
I know not everyone is excited about the Iris dataset, but I think for the first example code example, I wanted to pick a very, very easy data set because then we
5:31
can focus more on the tools rather than. Understanding the data and the Iris data set is something
5:37
I introduced the next one. So in that way, we don't have to spend too much time on exploring
5:43
a new data set because that's just like a data set we covered before. And here we can now focus more on the tools, the machine
5:50
learning tools and the code. So I will start Jupiter notebook.
5:55
I use actually Jupiter lab, which is a flavor. Of Jupiter notebook. It's like a newer tool that is a little bit more fancy than
6:03
the regular Jupiter notebook. Yeah. So let me start it here.
6:10
It will open up in my browser by default, and then I can open it here.
6:17
Now, let me clear, let me clear these outputs here on.
6:32
So that I can execute them step by step and go through them step by step. So it's not overwhelming.
6:37
So you will see the results while I execute them. And again, in the next lecture, I will talk more about Jupiter
6:43
notebook or Jupiter lab, and we'll show you how you can set it up. I actually ever maybe also share some documentation on the guitar repository.
6:51
Cause sometimes it's just easier to have it in text because then you can follow it. Step by step and copy and paste the commands and click the links and so forth.
7:00
So usually what I like to use in my Jupiter notebooks is, um, an extension called watermark.
7:06
And it's an extension I made a long time ago and it's just listing versions of certain software packages.
7:15
The reason why I'm doing that is it shows me what versions of the certain packages I used the next time I execute that notebook.
7:23
So if I get some different results, I can maybe say, Oh, my version is no different than before, for example.
7:28
And that may explain why the results are different, or if someone has a buck or something, if you have your homework and there's something not right, maybe
7:36
it helps seeing what packages you used. And then it's. Probably basically based on the package version you used it, there's a buck
7:43
and then we can make recommendations what to update and so forth. So let me execute the sale.
7:51
It will show you yeah. Your Python version. I'm currently still on Python 3.7.
7:57
I recommend Python 3.7, 3.8 for this class thing, Python 3.9 will be released soon.
8:04
It doesn't really matter whether it's 3.7 or 3.8, either way. It should be fine.
8:10
Um, yeah, learn again. We will talk more about installing these in the next lecture.
8:18
So if you want you install any package, just, um, from here from the
8:23
Jupiter notebook, you can copy this command too installed watermarks.
8:29
If you execute that it will install watermark using PIP. That's the, uh, Python package installer.
8:36
Um, and. There's another way to do that. It's Conda. I personally use condom.
8:42
It's like another Python distribution that has also it's it's better at managing a
8:48
Python environment for Sri data science nowadays it's less important than it. Once was nowadays using PIP is also pretty good, but back in the day, it
8:57
was trickier for certain packages. So condom makes certain things more easy and it also checks compatibility between.
9:05
Certain packages. So some packages require some other packages, and then there can be conflicts that this version number is required for one package.
9:13
And another package likes another version of this software and Conda usually finds the common denominator and makes it work pretty nicely.
9:21
So we can also install it like that. If you would hit enter. Um, one thing I want to mention here is the Y is it just means yes.
9:31
So, and the channel, what that means is, um, There's a certain base channel
9:39
where Conda packages are located. However, watermark is more like, um, project I developed and that is not
9:46
important enough to include it of cost and the basic condo installation or condo pitch, um, repository.
9:52
So there's a community, um, maintained. Repository of conduct packages, it's called kind of forge.
9:59
And usually I would even say they are tested even better than the regular Connor packages because of the kind of watch community has a lot of, um, tools
10:08
for checking that these libraries work on different computers and so forth. So it's just saying install watermark from this channel, from the kind of
10:16
watch channel anyways, that's not good distracted by installations.
10:22
So after we. Just check that everything looks okay, that we have kind of up to date software here.
10:28
Um, I'm in parking now, some packages that I will be using in this notebook.
10:33
And so these are my basic packages. We almost always need these packages. Like penises for data frames, non-payers for linear algebra and the race and
10:43
Metro tip is for visualizing data like a plotting data, doing that ups.
10:51
Next we will be lauding the Iris dataset from the CSV file. So first I'm using this head command to just take a look at the seasons we file.
11:01
It usually looks like that. So the head on command here is a Linux or Unix command or program that will
11:09
show us the first lines of a data file. So in this case, it will show us the first 10 lines.
11:14
It gives us an idea of how the CSV file looks like.
11:19
So you can see that as a headline, it contains the column, headers, the column names, there's an ID, sepal length sepal with column and so forth.
11:29
And the last column is the class level, the species. And then we have, um, yeah, the values here each again, each
11:37
training example is one role. So. These four values here, separated by a comma are the features.
11:44
And the last column is the class level so that I would do, um, tail. There's also a tail.
11:50
It shows me the bottom of this data set. So year we have Britannica and in general, we have 50, the tours are flowers,
12:00
um, 50, whereas the color flowers. And after that 50 Organica flowers.
12:07
Now we are going to launch the data, set into pandas into a penthouse data frame.
12:12
There's a read CSV function. Yeah. It has a lot of options, but for this file, we don't need to use any of these options.
12:20
So this is, um, how the file looks like when I, what the data frame looks like after a lot of the text file, the CC file, it's a
12:27
camaraderie, a comma separated file. Comma, a CSV stands for comma separated values, but essentially it's a text file
12:34
where each column is separated by a comma. So that's how it looks like.
12:39
Oh, the tail command is similar to when I type tail up here, it's showing the last few lines here in, um, in pen as the tail command shows last
12:49
five lines, but I can also show, let's say the last 10 lines if I wanted to.
12:55
Alright. Um, yeah, that is just usually a good, good way to just double
13:00
check that everything looks okay. So in machine learning, we usually use.
13:07
Non-paid erase instead of data frames. However, recently, psychic learn also started to support data frames.
13:13
So we could technically use data frames too. But I personally, it's just maybe because I'm traditional, I like to use
13:21
a student, my non-paid erase, which is maybe more of the classic approach. And if you use this, um, so let me go one step back.
13:30
If I use. This comment here, I will extract certain columns from the data set.
13:35
So yeah, we'll only extract the putter length column and the Patel width column, which are this column in this column.
13:43
And I'm just doing that first to just demonstrate how you can extract columns.
13:48
And second, to make the data set a little bit easier for our first machine learning example here. So if I do that, I will only get these two columns here.
13:58
Um, yeah, and the values will give me the data frame version of that. Sorry, the array version.
14:05
It will be now in . So this is known non-pay array looks
14:10
at it more bare bones now. So you can think of it also as a matrix, um, and by M matrix, where N is the number
14:18
of training examples, and M is the number of features in this case, it would be.
14:25
One of the 15 training examples and two features.
14:34
So the shape command will confirm, or basically what I just said, the shape
14:39
command is showing me the number of dimensions and each, uh, you had the
14:44
number of entries in each dimension.
14:50
I should execute this first. So it shows me. It's actually the same.
14:57
It shows me that this data frame, sorry, this array consists of two Xs or two dimensions.
15:05
The first dimension is the one on the left here, and this is the second dimension. So the first dimension has 150 entries and the second dimension has two entries.
15:14
So that it's the, like the, the metrics, the NBM. It's the one I have 50 times two matrix in this case.
15:23
So you can, if you wanted to, you can also just get the number of dimensions like this on oops, no end them.
15:33
I think so it's the number of dimensions, but usually I never do that because
15:38
then I can usually count one, two here. So it's kind of overkill to execute the end command to get an idea of the dataset.
15:46
So here, this also gives me an idea of. How many values are, how many entries are in each dimension and I'm pay, we
15:52
call these dimensions axes like, um,
16:02
so yeah, with numb pipe, um, we can also do indexing like, um, with Python, however, we can have an index for every, um, dimension.
16:12
So next lecture, we'll talk more about how that works in. In detail in non-pay let, just briefly here, this gives me
16:19
the first fi first five rows. It's basically the same as writing this Rose zero to five.
16:25
Note that in contrast to our, you probably have worked with are a lot in statistics in contrast to our, uh, Python starts at zero with the index.
16:35
So this will give me the first five rows. And if I have the colon here without any venues, it means all of them.
16:42
So that will give me all columns in this case, two columns. So yeah, essentially printing out the first five rows of my array just
16:54
to visualize it or just to double check how it, that it looks okay. Basically.
17:04
Yeah. Another traditional aspect of machine learning and Python is to have class abled as integers, instead of strengths.
17:12
Nowadays, I think also psychic learn naturally supports strings as class labels, but yeah, and because I'm traditional,
17:20
I'm also doing it the old way. I'm converting the strings into.
17:26
Inter just for the class neighborhoods. And that has the advantage. If you are using tools on that are somewhat compatible
17:33
for, with psychotherapy. So a lot of people develop algorithms that work with psychic learn.
17:38
Not all of them are so strict and allow you to use basically strengths.
17:43
Um, so they don't really ensure that everything is totally compatible. It's always, I think, a good idea to use integers because that.
17:51
Should always work. So what I'm doing here now is I am using the pandas data frame with
18:00
the map function to convert all the string class labels into integers.
18:05
So I will be using a zero instead of Iris Tozer, and I will use the
18:10
one instead of Iris Rosa color. And I was, uh, I will use a two instead of Iris beginning count.
18:18
Yeah. So this whole thing is the Python dictionary and there's a map function, the
18:24
map functions like a programming concept, um, it exists in different languages.
18:29
Um, you may also know that from our or different languages, I'm just mapping one thing to another thing.
18:36
So, and this is essentially my mapping dictionary. So, um, what I'm going to do now is, um, I'm applying something to the species
18:43
column, the species Calamus, Maya. Class, they would come just to show you how it looks like.
18:48
Again, it's just my class tables here. So I was the Tozer until I was the beginning and I'm going to replace
18:56
them and the map function will take. So if it sees basically, uh, Irish, the tour side, we'll take
19:02
this string and convert to a zero. And if it sees Iris vertical, I were converted to one and so forth.
19:09
This is what we want to basically. So after I executed this command, um, what we can see here is that we have
19:18
a new column it's called class level. So I was, uh, assigning a new column to this data frame.
19:26
I call it class level, and this is. Basically the converted version of the species column.
19:32
So let's just see what happens if I just executed like this. So you can see now, can we use the values because if I don't use the
19:41
values, that will be as series and that has this index here on the left, which is maybe a little bit misleading here.
19:48
So this is my array. And you can see basically that is consisting of the converted values.
19:55
So if I don't do that, I will have my strengths here in my array.
20:02
So what I was doing, basically I was on, but I was assigning this array to a new column just for reference.
20:07
So the column is shown here on the very, right now. And, uh, yeah, for second learn, we also have a convention that we usually
20:16
use the letter X to refer to the data set or the features and the letter Y
20:22
to X, um, refer to the class tables. So I'm when I'm executing that, or this comment, it will assign these values to
20:31
a variable Y um, here, this is just the ten first values, but we can take a look at all of them because they're small.
20:37
So you can see, these are my. Um, 150 training. Examples can just maybe make sure that it's indeed making sense.
20:47
We should have 50 training examples for each class. So yeah, 54, zero 54, one and 54, two.
21:01
So in machine learning, we usually have a training set and a test set. Sometimes we also have additional data sets, splits like a validation
21:09
set, but we will talk more about this in the model evaluation electron. So, yeah, this point we are just, uh, dividing the data, set into a training
21:18
set for fitting the model and then a test set for evaluating its performance.
21:24
So, first now in this step four here, I'm going to show you how we.
21:30
Can do that manually. And then I will later on show you how we can do that in psychic learn so many.
21:36
Let me hide this lower part because I know it's distracting. Okay. So what we are going to do now is we are shuffling the data set
21:44
first, and then we are dividing it. Why do we shuffle it? I mean, I showed you above that, um, the class table it's on sorted.
21:53
So when we look at why again, we see that, um, the first half of the data set.
21:59
Would be approximately here. We can actually show it like this. It should be 75. Right?
22:05
So these would be by first half, this would be my second half. So if I would divide, if I would say the first 75 data points are my
22:15
training set or let's say the first 100 training, examples of my training set and the last, um, 50 examples.
22:26
Oh, my test set. What will happen is that the model during training only sees
22:31
the two classes zero and one. And then during testing, she is an entirely new class class two, and that
22:37
will, of course not work because, um, we, we usually assume that a training set has
22:42
the same distribution as the test set. So, what we will do is we will shuffle the data set first.
22:49
So how do you shuffle something? I mean, there are many, many different ways. I personally I'm like doing it this way, realize that different
22:57
ways, but if I would do it manually, I would first create. On index array that has the same length as Y.
23:05
So I just I'll just show you how that looks like. So it's just an array from zero to 149.
23:13
Okay. And that's right here and then I will shuffle it. So I'm using from non-pay this random state object.
23:22
Uh, there's also a different way you can do that. It's um, I'm PI random.
23:28
Seed. I think that can also set a random seed and the random seed guarantees that you
23:34
get the same results every time you set the random seed and execute an operation.
23:41
And I think, uh, it's not really necessary always, but most of the time I prefer that because it gives me like consistent results.
23:50
If I want to. Double check my results. I make a tweak, something in my pipeline.
23:56
I want to make sure that, um, I don't have any kind of randomness that changes when I execute my code again.
24:02
So that way I can make it reproducible. Or if I give you my code, you will get the same exact same
24:08
results I get, which is I think. Nice. So, um, let me execute this.
24:14
It will, first of all, uh, initialize this random. R and D object.
24:19
It's a random state object. And then I will call the permutation function, which will just shuffle around these index indices.
24:27
So you can see they are shuffling. Now. Now, when I execute this again, we'll always create the same shuffling.
24:36
If I wouldn't use a. Random state or random seed. You can see it changes every time.
24:43
And now if, then for example, I get a certain result. I will give the notebook to you and say, yeah, here you can play around with that.
24:48
You will get probably totally different results than I did. But if you use a random seed, the same random C that I used, you
24:55
will always get the same results. We don't have to use one, two, three, it's just arbitrary. We can use also our favorite number 42, if you know, Hitchhiker's guide
25:03
through the galaxy, that's like a common programming joke anyways. Um, So, yeah, I just do one, two, three here.
25:09
And for arbitrary reasons, it has the, you can also actually, um, use a random seat.
25:15
Manually like this, but sometimes, um, when we make more complicated pipelines,
25:21
especially when I work on my, in deep learning stuff, I have a separate, random state for different parts of my code, and I like to keep them separate.
25:29
And if you, if you set the random seed like this, it's, um, effecting all the code globally, which I sometimes don't want, but you can also use non-pay
25:38
random seat instead of this one here. And I think, um, And on right now, recall what the commander's
25:49
maybe random permutation. something like that. Nope.
25:54
Sorry. Non-pay yeah, you could technically also, um, use
26:07
this approach. Nope.
26:17
So this should give you the same. Let's do the thing, this random state. I like doing it with a separate random state.
26:23
Anyways, I'm getting distracted here again. Sorry. All right. So why did we shuffle the indices and why did we just shuffle the.
26:35
Label a rate directly that is because we want to shuffle of constant feature array accordingly.
26:41
Right? So because each label corresponds to a row in our, our matrix X.
26:48
So we have to reuse the shuffled in nexus indices. So what I'm doing now is, um, if I do that, it will
26:58
shuffle around the different. Values in this array.
27:04
So for example, um, before that the Indies index zero was in the
27:11
front, it was before we had like zero one, two, three, four, five. Now, um, zero is a total different position and so forth.
27:18
So it's just shuffling around all the labels here so we can see it's now shuffled.
27:24
And the same is true. Then accordingly for my x-ray. So it will also shuffle all the rows the same way we shuffled the label so
27:34
that each, um, they will re corresponds to the right feature values here.
27:39
So the first level corresponds to this first row and so forth,
27:47
it's a lot of stuff here. Let me delete this. Okay. So, yeah, we are shuffling the data set now, and then after we shuffled it, we
27:56
can divide it into training and test it. So I was just, I'm using the first 105 examples as training
28:03
set and the remaining 45 examples. Sorry, the remaining 45 examples for, um, the tests said, so this is the
28:13
same as the writing, writing this. So in Python, we don't need to provide the number four.
28:20
The yeah. Upper bound basically.
28:25
Yeah. That's quickly double check that this makes sense. I mean that this worked it's let's just check the dimensions here.
28:34
Oops. I should execute this first. Yeah, it makes sense. One of five training examples in the training set and two features, and we
28:44
should then have 45 in the test set. And of course, when we do that with our, why should also be one of five and 45.
28:57
So that's all good. Now that was a lot of work. Of course, we can also use cycle learn to make this a little bit easier.
29:07
So psychic run also comes with the Iris dataset implemented. So we don't really have to use our CSV file.
29:14
Psychic learn has a data sets or sub module that has a lot Iris function, which contains the Iris dataset.
29:21
I'm lording it here. And it also has a train test split function, which allows us to split
29:28
the data, set into the training. And it has said, and also we can then provide our random seat here.
29:35
And say that we should shuffle it and we can specify the size of the test set.
29:41
So we say 0.3, which means, um, 30% test data. And then the remainder will be training data and 30% of 150, that should be on 45.
29:52
Right. So we should get the same size as before 105. Training data points and 45 tested appoints.
30:00
That's execute this. Yep. That looks good.
30:06
So we have one of five training, data points and 45 testing data points.
30:15
Yeah. So personally, I like to visualize my data set first before I work with it. Now, um, this is kind of a little bit late in this notebook, but yeah,
30:23
I want to do just, um, Go over some concepts before we do the visualization.
30:28
Maybe I should have moved that to the top anyways. Um, I have a. Convenience function that I implemented for myself a long time
30:36
ago, just a scatterplot matrix. You probably know that from our, I edited to, um, a library called MLX 10,
30:43
which is a personal email library that I created as a grad student back in the
30:48
day, implementing certain functions that I couldn't find anywhere else for Python.
30:54
So there's just like a library of, um, collected things I collected over the.
30:59
Over the years and that extent stands for machine learning extensions. Um, it's just because I couldn't think of a more creative name for that.
31:08
And I was just adding functions when I needed them. Um, so yeah, here I have a scatterplot matrix which will
31:16
create a scatterplot matrix. So it uses by the way, met potluck. So how that works is, um, let me explain it step by step.
31:26
Before we look at this. Well, maybe we should look at this first. So what it is showing us is, um, a scatterplot matrix containing
31:35
the histograms on the diagonal. So we have four features in the data set.
31:41
So here I'm using the whole Iris dataset, not only the two features, so it will show me a histogram for each feature here.
31:48
Uh, the sepal length, SEPA, width, petal length, and petal width. I provided the names here manually because the names are
31:56
not in this, um, non-pay race. So this is a non rate, I think.
32:03
Yep. Okay. And. We can just, I find it usually helpful just to look at the
32:10
histograms very quickly. And I can, for example, by looking at the histograms, see that sepal length and
32:15
several bits are not as useful as petal length and petal width for distinguishing between the different flower classes.
32:21
So each flower classes, one color here. Um, but I'm doing here as why I have three lines of code.
32:28
Um, is to make the color thing here, work. Um, first, um, plotting only the examples from the first class.
32:36
So class zero, I'm doing that with this indexing here. So again, um, this is, I will explain that more later in the next
32:42
lecture when we talk about non-pay, but this is called fancy indexing. So it will create a mask, a bullion ask and it has true and false values.
32:53
And then for example, if I have. Um, this array here and I apply my Boolean mask.
33:02
It will only give me the values for which in the mask. I have a true value.
33:07
Right. So it will only give me, give me this year. And these are the ones corresponding to class zero.
33:14
So that would be . So it's only this values here, and then I can do the same thing for.
33:20
One and two. Okay. So what happens here is that here I'm only plotting the torso and then here
33:28
I'm plotting a versicolor and here and plotting virginica, I'm only giving the
33:34
names, the column names to the last one. Otherwise I would have, um, a lot of column names, which I
33:40
don't need, so I would have them. It would work, but they would be overlaying each other basically.
33:45
So it's just redundant and the alpha just means transparencies. If I don't use that, um, if I use, if I just remove that,
33:54
it will be a solid color here. And if I do that for all of them, if I have a solid color for all of them,
34:00
I can see how they overlap anymore. Okay. So this is just a. Yeah, very simple scatter plot function to get a glimpse of the whole dataset.
34:11
And we can also see, not only the horizontal, horizontal, sorry, the deck not here, but we can also see.
34:17
Ah, how the scattered lots of different combinations of features look like so simple length and supply width.
34:23
They actually are not too bad if you combine them. So you can see, for example, I can separate odd these flowers here.
34:30
I should have included a legend. I forgot. But yeah. So this is, I think we're Guinea com so we can separate odd beginning code.
34:37
If we would draw a line. Like, oops. I didn't like this one. However, we can't really separate you the orange and the green ones.
34:45
However, if we look at pet her with and petal length on this is actually a good combination of features, we can actually draw a line here to separate these out.
34:53
For example, any case in practice or for this tutorial, we'll be working
34:59
only with Patel width and putter length, because I want to show you some other plots later in these pots only work with two dimensional datasets.
35:09
So you have a set up of only the two features we are looking at, or we're working with for the rest of this tutorial.
35:15
I, here I edit the legend with the labels. So here I'm also only plotting the training set, not the whole dataset.
35:26
Yeah. And that is how my train set looks like.
35:33
Yeah, like I'm saying here, in this case, it may be overkill to use the scatterplot function. We can just create a scatter plot I'm using Matt put up directly.
35:43
So if you want to use meetup metadata directly, there's a scatter function at a we'll make a scatter plot and, um, Here we use a very similar concept.
35:54
We use the fence indexing. This gives us all the examples for label zero for class zero.
35:59
And the second number here. This means the column. So the column in extreme.
36:06
So the first value before the coma is the role. And the second value is the column of this matrix, extraneous matrix.
36:14
So here I'm plotting. The role, which is petal length.
36:20
And here I am plotting it against the petal width. So I'm putting putter length against pedal width and I'm choosing a marker.
36:28
This is just a circle. And for the second one, I'm using a triangle and the third one, I'm using a square.
36:37
So here, this is I'm sorry, this is . This is and this is working together.
36:51
Yeah, this is how it looks like. If I would just use metadata. Of course, we can also use the alpha, maybe helpful.
36:57
So alpha is usually for transparency so we can use alpha, let's say 0.5.
37:12
So then we can see, for example, there was actually an overlap that we wouldn't have seen otherwise this, um, this one here
37:23
now let's get into the interesting part, the machine learning part, because all of that before was just exploratory data analysis.
37:31
So let's now get to the machine learning part. And sacred land. There are many, many different classifiers and regression models.
37:38
So here, because the lecture was about Kenya's neighbors. We are starting with Ken years, neighbors, classifier.
37:43
We could use this also Kenyans neighbors or K neighbors. Regressor so there's also.
37:50
A regressor, but because this is a classification data set, we will be
37:56
using of course the classifier, and there are lots of options and cycle learn. So for each type of machinery model, there are different options.
38:05
Um, here we are. Setting the options, neighbors three. Um, also, yes, I could learn as using an object oriented approach.
38:12
We will talk more about this. Um, when I talk about psychic learn next week. So next week I will talk a little bit more about how, how the
38:19
API behind secular and works. But yeah, in a nutshell, usually we impart a class.
38:25
So this is a class by convention in Python. We use the chemical case it's called, um, Camel oops, camel case.
38:36
Um, that is when you have these capital letters, this usually the notes, it's just a convention that this is a class, not a function.
38:42
And so, yeah, we impart this Ken years, neighbors class or K neighbors classifier,
38:48
and then we instantiate a new object. So. Class classes kind of like a cookie cutter.
38:54
And with that, we are cutting out a cookie right now in our cookies, the cane end model and the kin one model is just an empty model right now.
39:01
It's just initialized. And we say, we want to have a 10 years neighbor models model with
39:08
three neighbors, and then we fit this model to the training dataset.
39:15
By the way, if you want to know all the options on. Can I should. I think you can do it like this.
39:22
So in Jupiter analytics, you can use this question Mark, and it will show you all the different options.
39:28
So we'll explain all the options to you. So here's also the ball tree, KD tree brute force approach that
39:34
I talked about in the lecture. Yeah, lots of stuff going on here. Awesome examples.
39:39
I personally usually use the website, the secular and website, because it's nicer to read, but, um, if you are in a hurry for example, or if
39:47
you just want to briefly look up a name, I usually use the, um, this approach here using the question, Mark.
39:54
Okay. So this will, um, fit our dataset. It's also not, there is no output here, really.
40:01
I mean, the output is just the object itself. It will return Cain and model, but, um, We can also just suppress the output
40:09
like that because it's an object oriented approach and we'll fit the model in place. So there's like a side effect here.
40:16
So the model will be fitted after that call. I just see, I have a question here in this notebook and yeah, you can maybe
40:23
answer this question by using, by using this approach here and then seeing
40:32
where the distance metric is defined. I will leave that as an exercise. So I'll read through that and somewhere here I can receive it, but I want to
40:41
tell you, because it's an exercise. So maybe read through this and see what, by default, what metric
40:47
it uses about distance metric. And then you can maybe have a code, sorry, make a comment on Piazza and have a small discussion.
40:54
So let's see who gets it right first. Okay.
41:00
Now after fitting the model, we can make predictions. So for each model that has been fit to a training set,
41:06
we can use the predict method. And usually we are interested in making predictions on the tests, right?
41:12
So this is now evaluating our model. Also in practice, we pretend that test that is new data.
41:20
So why. Underscore P R E D. This contains now our predicted class table.
41:25
So this is what our model predicts. How do we know whether the predictions are good? We, yeah, we compare them to the.
41:33
The two, the true labels, right? So the true labels are why tests. So we compute how many of them are correct for that?
41:40
We can use Python so we can use a direct comparison here. It's comparing the two erase and it gives them me true and false values.
41:49
And I can then simply sum up, I can do an umpire some over
41:56
the true values and in Python. Um, yeah, it should say R.
42:03
True evaporates to one and false evaluates to zero.
42:08
So here, the sum will compute the number of. True value is basically, so it will give us a count of how many are correct.
42:17
So 43 are correct, and two are incorrect.
42:24
All right. So doing that, um, so here, Oh, I see. I wrote it like this it's the same, so we can also write it
42:30
like this it's the same thing. So now in order to find out the accuracy, we have to divide by
42:35
the total number of examples. And the total number of examples is the length.
42:41
Of the array. So if you recall shape, looks like that. There's this, uh, it's a Topal.
42:46
So there's this calmer. I use the zero to get riddled Tacoma here, and this gives me the proportion
42:53
of data points that are correct. And then I multiply it by 100 to get the accuracy in percent.
42:59
So I'm doing that here. And I see, okay, has a 95.5, 6% accuracy, by the way, I'm using an F string here.
43:09
And that is a feature that has been added to Python. Recently. I honestly forgot it was either Python 3.6 or 3.7.
43:17
So if this doesn't work, you may have an old version of Python. So you may want to consider updating Python.
43:25
But yeah, if you can't or don't want to update path and you can also use, um, the older approach on this classic way of making strings personally,
43:34
I grew up doing this and I'm also like a CNC plus plus programmer. And this is like a very common.
43:42
Way of formatting strings. Um, so in that way, I'm, I may sometimes using my code also this old approach.
43:51
There's nothing wrong with it. I just like F strings because you can do cool things with that you can
43:56
do, for example, um, I don't know. You can have, uh, you can have something like, I know one class too.
44:06
He quilts and then you can actually have a computation right here. Um, oops, forgot the quotation.
44:13
Mark here can have, um, uh, thingy right here instead of having a separate
44:22
results here, a variable, and then, well, you could, you could actually.
44:27
Do it like, um, this too, but oops. See that you have to have extra parentheses.
44:35
So with F strings, if you have a lot of stuff going on, so if you have another thing and another number you have to add, or you have to keep adding these numbers
44:44
here and then it gets kind of complicated. You have to see, okay, what is going here? And what is going here.
44:50
If you have like, Let's say 10 numbers or something like that. If you have these F strengths, it's just simpler because you can put
44:56
the numbers here in directly, right? So you can have also variable names. So if I have a bar that variable name here, it's they call it an bar.
45:05
Some thing
45:11
I can put the variable here and it should work.
45:17
So I can't mix and match things, but, uh, something like that.
45:25
Um, so I kind of personally like these, uh, F strings, but it's not a big deal not to use them.
45:31
So again, sorry, I'm getting distracted here. Uh, what's more important than F strings though is, um, in second round,
45:37
there's also a score function and form classification algorithms by default
45:42
score will also compute the accuracy. I think for regression models that confused the computes, the R square
45:48
coefficient of determination. So here though. Bye cause we have a classification model. It will also compute the accuracy.
45:55
Yeah. Manually multiply it by 100. And by the way, um, this one here is just to, um, limit the numbers of.
46:03
Uh, the numbers after the December point, if I remove that, it will give me the full position, which is sometimes, maybe a bit too much.
46:11
Right. So if I remove that thing here, you can see also it's the same results.
46:19
So squat provides our computes, the accuracy. So we don't have to do that manually every time, but this was just to
46:25
illustrate how accuracy is computed. Lastly to wrap up this probably already long lecture.
46:30
I didn't check the time, but we are probably already like, I don't know, 20 minutes, half an hour or something. So the last thing, uh, another convenience function I have here, and this is also
46:39
more for, um, I would say educational purposes is a decision region plot,
46:45
and this is why we only work with two features here in this, um, in this notebook because we can make a nice.
46:54
Right here. This is a harder decision region. Look like for the training set.
47:01
And the decision region's father tests, it should look the same, right? So it should be the same, our decision regions.
47:08
Because again, during testing, it's using the training set, however you can.
47:13
So the data points overlaid here are a little bit different, so you can see these other test data points, and these are the training data points.
47:21
So it looks like to me, if I look at that, it gets all of these blue ones, right? There's the tools or flowers I have.
47:28
I can see in the training set, it gets these two triangles right here. So it's fitting it very well.
47:33
So this green one is, um, Maybe not, uh, fit it very well.
47:38
Cause it's like a three nearest neighbor model. If we would use a one year stable model, let's maybe just quickly do that.
47:44
Um, let's use a one nearest neighbor model.
47:50
You can see it. We'll get all of them.
47:56
Correct. But then the problem is. Over fitting. Right? Cause now we make mistakes on the tests.
48:03
So there was also the problem that we had earlier or what you saw before I re executed the plot above.
48:09
Um, it was fitting maybe these triangles so closely and here on the training test set, there are two circles.
48:14
And with these feature values, so here it would make these two misclassifications.
48:21
So if I look at it, no, I think that all fitting, maybe even worse or not really. So it's the same.
48:26
So we also get these. Two data points, right? Because we can see on that. These are tricky because they just, um, I mean the training set it's maybe
48:35
not the greatest training set because here on these are hard to distinguish
48:40
just based on the training set. So, if we look at our plot here, these are probably these points here, but yeah, that
48:49
is also easy to look at because we have a two dimensional data set in real life. We usually have very high dimensional data sets.
48:56
So we would not be able to look at these on these plots here, but let me
49:01
go back and maybe let's just compute it.
49:07
So the tests had arrow is. 95%. It doesn't matter. We saw whether we use one or three nearest neighbors, so we can also
49:16
compute training, set accuracy.
49:25
And that should give me a higher accuracy, I think. Yeah, 1980 here we get more.
49:30
Right. So in that way, it's slightly overfitting. So the model is slightly overfitting the training set.
49:36
Yeah, you can maybe also, uh, by yourself, experiment with other values for K maybe cake what's five or seven and see how that affects the decision boundary.
49:45
But now let me wrap up this video because it's getting too long. Uh, yeah. And the next lecture, we will talk a little bit about Python.
49:53
I. Already evaluated. The survey that I sent around, most people seem to have used Python, but I think
49:58
it still doesn't hurt to just maybe at least show you how you can install it. And I also posted some exercises on Piazza that you can do to kind of familiarize
50:07
yourself a little bit with Python. Okay. It's so I will see you back next lecture.

##v13:

0:00
Hi everyone.
0:01
I hope you had a good week so far catching up with a kin in lectures.
0:05
So there was this one more lecture that we had on improving Canaan and
0:09
then the one lecture on implementing kin and in Python using psychic learn.
0:15
So.
0:16
I decided to make another video.
0:17
I was reviewing your quiz, uh, the intro to getting to know you quiz, which I
0:23
really appreciate that you all answered.
0:25
So I really liked reading about your experience.
0:29
So I can also a little bit tailor the cost we experienced, and it seemed
0:33
like most of you, all of you have a programming background or had taken a
0:39
programming class before, which I think is very useful for taking this class.
0:44
But I would say only half of you have a solid experience with Python.
0:49
So before we start scientific computing with Python next week, and also looking
0:54
into psychic, learn a little bit more, I thought it might be helpful for
0:58
those who are, let's say a little bit more new to Python to give you some
1:03
help with setting it up so that next lecture will go more smoothly for you.
1:09
Yeah.
1:09
And also as a fun fact, I was reading through your,
1:13
um, favorite hobbies section.
1:15
Um, like I mentioned, I like cross country skiing in winter and running in summer,
1:20
and I really, really like hiking also.
1:22
And I try to spend as much time as possible in summer, outside
1:26
in nature if time allows.
1:29
However, there are often many rainy days and there are also
1:32
long winters in, uh, Medicine.
1:34
So similar to some of you, right?
1:36
Also like video games.
1:37
And also there was at least one student who mentioned the Zelda series.
1:42
And I think I didn't even miss one single entry in the major
1:46
series of this gaming series.
1:48
So that's something I really like to do on a, during Christmas when it's really
1:52
snowy outside, you can't go outside.
1:54
And, um, let's say you had a very busy, stressful, productive day.
1:59
It's kind of a nice thing at the end of the day to relax a little bit anyways.
2:02
Um, Let's get picked to the lecture.
2:05
So like I promised, um, this lecture will be an optional lecture.
2:09
If you have a strong Python experience or you already have some Python set up
2:14
on your computer, it's not necessary that you watch the following three videos.
2:18
It's really more for the students who, uh, we have not worked
2:22
with Python on their computer.
2:24
So in that way, I can maybe give you some motivation, but also
2:28
some, um, Advice how I use Python.
2:32
Of course, the way I use Python is maybe not the way you want to use Python.
2:37
I'm just giving you some examples here from my experience.
2:42
So then also after this lecture, next week, we will
2:44
have the first real homework.
2:46
So I had like these small quizzes.
2:49
However, these were more like self assessment quizzes to see
2:52
whether you follow the lecture.
2:54
However, it's really better understand how certain concepts
2:58
explained in the lecture work.
2:59
Right.
3:00
It's very helpful to implement them.
3:02
So I will prepare a homework for next week where you will be toying around and
3:06
implementing a Kenya's neighbor algorithm.
3:09
And part of it will require you that you write your own code,
3:12
not only using psychic learn.
3:14
So in that way, it would be helpful for you to help yourself
3:18
to set up Python this week.
3:20
And the next week I will.
3:21
Tell you about non-pay and a little bit about the scientific
3:24
computing libraries, which you will then use for implementing Cain.
3:28
And, but don't worry.
3:29
This is not a very hard homework.
3:31
It's the first homework, right?
3:32
So it's more about.
3:34
Helping you to understand the kin and nature.
3:37
And after we'd done that, then we will go back to some more
3:40
conceptual machine learning aspects.
3:43
So before we start, just to give you a, again, like a short overview
3:47
of where we are in this course.
3:49
So we covered the introduction the first week, and we are currently
3:53
in the second week, I'm talking about the computational foundations.
3:57
So the introduction was like just a simple intro to ML and the K
4:03
and N and after awhile potential foundations, we will go back to more
4:08
like core machine learning topics.
4:10
However, for these core machine learning topics, I have homeworks in mind
4:14
that I want to make, where I will ask you to use some of the computational
4:19
aspects that you learn about in part two, to implement some of these ideas
4:23
and concepts here, which is why.
4:26
No computation foundations come so early in this class so that you can use them
4:30
to really toy around with these ideas.
4:34
Yeah.
4:34
And in particular, and part two, this lecture is this lecture on
4:39
using Python and this is optional.
4:41
So you don't have to watch it.
4:43
If you have Python all set up, if you have a new version of Python, 3.7 or.
4:51
3.8, if you have something like Python two, um, that's a very old version
4:55
of Python and you may want to watch this video to just get an idea of how
4:59
you can set up the recent version.
5:01
And also there will be a tool required, um, can use either Jupiter notebook.
5:08
Or Jupiter lab.
5:10
So we will be using these for the homework.
5:15
If you have no idea what that is, um, you can watch the
5:20
third video of lecture three.
5:21
The first two videos are very basic.
5:23
And the third way you will, I will give you some idea, uh,
5:27
how you can install Jupiter lab.
5:31
Yeah, this will be a rather unusual lecture because it
5:34
will be more interactive.
5:36
So I'm not going to use slides this time, but rather type
5:39
here in some basic text file.
5:41
So I'm just going to type some basic keywords just to help us yeah.
5:46
Seeing where we are in this lecture.
5:48
So the lecture Electra extra three will be.
5:50
Primarily about using Python and I will start by giving an
5:55
introduction to Python, and then I will show you how we can set up.
6:01
Python.
6:02
Like I will show that on my own computer because I have a Mac.
6:06
I don't have a windows computer, unfortunately,
6:07
where I can test this windows.
6:09
However, if you have any questions about that, our TA in this course,
6:14
uh, has a T uh, has a windows.
6:17
So he will be happy to help you with any windows related questions.
6:20
But I think it may still be useful to go over the basic concepts on
6:25
let's say my Mac computer, even though you have a windows computer.
6:29
Yeah.
6:29
And like I said, in the beginning, you don't have to, to be an
6:32
expert programmer to use Python.
6:35
Um, of course in certain applications, you may want to be an expert
6:38
programmer, software engineer, computer scientist, and so forth.
6:41
But for this class, we are just using Python for machine learning
6:44
and, um, I think it is already sufficient to learn some of the
6:49
basics in order to follow this course.
6:51
You don't have to know everything about Python.
6:53
I mean, even I used who used Python, like for 10 years or so.
6:58
I don't know everything about Python and I also don't need to because I'm more like,
7:02
um, researcher, I don't, uh, yeah, I'm not a software engineer, at least not yet.
7:06
So in that way, Uh, we are just focusing on some basics of Python, but
7:12
yeah, before I go on and on about that again, um, let me just get started
7:17
by talking about Python itself.
7:20
Yeah.
7:20
So Python is an interpreted and, um, dynamic programming language.
7:30
Let me also remove maybe the setup for now because we are not in the setup right now.
7:36
We'll talk about this later.
7:38
Python is a dynamic and interpreter programming language.
7:40
And for example, another language that you may have heard of is C
7:45
or maybe even C plus plus C sharp or objective C and so forth.
7:49
And C is for example, aesthetic typed language.
7:59
Um, I can also say statically typed.
8:02
It's like a language with a static type system.
8:05
And this has some implications with regard how, how we use the language.
8:10
So.
8:12
Um, the advantage of Python is really that it's more interactive.
8:16
It's a interpreter and dynamic.
8:18
So that kind of implies it's more, somewhat more active for easier to use.
8:23
It's very similar to our, in that way.
8:26
If you.
8:27
Um, we have used are in other statistics classes and I'm 99% sure that you have it.
8:33
It's very similar to our, in that way.
8:34
And very, very different from C although C is used to implement
8:38
Python, but yeah, C, C would be something you would use if you have to
8:42
implement something very efficiently.
8:44
One disadvantage of Python being interpreted and dynamic
8:47
is that it's relatively slow, but also machine learning.
8:50
We don't really have to worry about it that much, because as we will see in
8:54
the next lecture next year, for most of the scientific programming libraries
8:58
or computing libraries will be using C or Fortran code under the hood.
9:04
So Fortren is another statically typed language on that was very popular in,
9:09
I don't know, in science, like 50 years ago or something it's still very popular
9:13
because it's still unused under the hood, but it's just more work to write.
9:18
Um, code in C and Fortran, and it's also more work to kind of run the stuff.
9:24
So if we run some computations, that will be way more work.
9:27
If we want to just get some quick results to do that in C on Fortran,
9:31
which is why Python is quite convenient.
9:34
And it's also an all purpose programming language.
9:38
So with that, I mean, we can do all kinds of stuff.
9:41
I mean, I know people who use Python for the web, um, frameworks,
9:45
um, just a top of my head.
9:47
I think Instagram, Dropbox and stuff are implemented in Python.
9:51
They're many, many people using Python, very extensively
9:54
for various different things.
9:56
I think even YouTube, but I maybe they've changed it.
9:58
I don't know.
9:59
I don't know the details anymore of what people are doing at these
10:03
companies, but back in the day, at least a YouTube, I think was also
10:07
based on Python for some time, but I don't want to say anything wrong here.
10:10
So don't take that at least the sentence with a grain of salt.
10:16
But yeah, before I go on talking about interpreted and dynamic languages, um, And
10:22
statistically statically typed languages.
10:24
Maybe let me show you an example.
10:26
I will just maybe code a simple example in C first, and then I'll
10:31
show you how, how much work that is.
10:34
And then I will do the same thing in Python.
10:36
So then you will maybe appreciate why we're using interpreted and
10:39
dynamic language in this class.
10:44
Yeah.
10:44
So the program that I'm going to write as maybe something very simple, like printing
10:49
a string, like ABC equals C and then maybe a plus two equals intrusive three.
10:58
So there's something the program has to evaluate.
11:00
And so it should be a three, but I want tell the program, I will just try to
11:03
program to do this simple computation.
11:08
So I will use my favorite text editor for doing that visual studio code.
11:14
It's right now my favorite text editor, but of course I
11:18
switched text editors a lot.
11:19
Um, anyways, I will talk more about that also.
11:22
I think later in this lecture, let me just write the quick C program that does
11:28
like the, a plus B plus C equals C and the one plus two equals hopefully three.
11:36
Let's call that example let's see, or something.
11:41
So we'll just call that example.seek and first and see we have to yeah.
11:49
Use a header file.
11:51
Usually it has some basic functions.
11:56
It's just a header file here.
11:58
And then I would write my main program.
12:01
So, um, see, we usually have a main program.
12:05
It's kind of funny because when I learned Python, uh, in my undergrad studies,
12:10
Also our professor us was mainly a C programmer and we always had to write
12:14
a main part of function in Python.
12:16
So later on when I took a C plus Pascal class, I kind of learned
12:21
where that loss coming from anyways.
12:23
So in statically typed languages, we have to declare our variables.
12:28
So I would have, for example, in results.
12:30
So that's an integer that is then storing the results later
12:34
of my one plus two calculation.
12:38
What else do I need?
12:39
I need a character victim.
12:40
So I call that maybe word.
12:42
It's just an array, character Ray.
12:45
So characters for the characters and the naturals here.
12:48
It's because we want to print this one.
12:52
I just see, I think I just need a five here.
12:55
Right?
12:56
So that's what I want to print here.
13:00
A plus B C and then I have my result.
13:06
That is the result for my computation that I'm caring about.
13:10
I have a one plus two, right.
13:13
And not really.
13:14
That is why it's certainly tapped.
13:16
I first have to declare the variable.
13:17
I have to declare the variable result, which is an integer variable,
13:22
because this will be an integer.
13:24
And then this is for another thing I will do.
13:27
I think I need a semicolon here too.
13:28
Right?
13:31
And here too.
13:32
And now let me print the character victim.
13:40
It's like some very arcane stuff.
13:42
I'm typing here.
13:44
Oops.
13:48
But we can use the same stuff in Python, actually.
13:50
So this is like this typical string formatting format.
13:53
So we have the stance of our string and, um, this backslash and
13:59
it's like a new line character.
14:01
So we are printing first hour or thing here.
14:05
And then what we are doing, we are just maybe printing the result and then we're
14:09
done, um, let's call or let's print F and just the result without anything.
14:16
I always forget the semi-colons because you don't have to do them in Python or R.
14:20
And so I I'm a bit rusty on my C programming here, and then it's
14:25
finally returned zero, which is also another convention in C.
14:32
So now all we have to do is we have to save the file and then
14:36
we can hopefully execute it.
14:39
Let's save it.
14:41
But yeah, executing it.
14:42
It's not so simple because it's a statically typed language.
14:45
We have to compile it.
14:47
It's like an extra step.
14:49
So I can't just run the school.
14:51
I can't just go to my terminal.
14:54
Um, Let's go to the desktop where I saved my example.
14:59
Seafarer I can't just run my example C5 because well, um, okay.
15:04
It also show some weird permission issue, but it's not like, um,
15:08
file a program that I can run yet.
15:11
So what I have to do is I have to compile it first.
15:13
So it's an extra step that we have to do, so we have to compile
15:17
it and we will call the program.
15:21
Uh, maybe just example for simplicity.
15:23
So we'll compile, compile this, uh, example C file to the program example.
15:30
Let's do that here.
15:32
Okay.
15:32
It's doing some fun stuff here.
15:34
Uh, forgot SIM in common.
15:39
So the compilers are throwing an arrow here.
15:43
It's competitive again.
15:44
Um, there's some warnings, but I think it should be fine.
15:47
So again, um, we're, we're still compiling it, so it has compiled.
15:51
And now we have a program called examples, so you can sit here on the right side.
15:57
Maybe you should make that a bit bigger.
15:59
Um, so this program.
16:04
That, uh, we just have compiled and we have just compiled.
16:09
We can execute that right now in the terminal and we get a segmentation fault.
16:16
And I think this is because I use the character vector of six and a
16:23
five and I should have used six.
16:25
I think that's why.
16:28
Let me just try this again.
16:29
Yeah.
16:29
See, that's like a lot of hassle, so we have to compile it again and Nope.
16:36
I am still giving a segmentation fault.
16:39
I think that's maybe because I didn't do the proper string formatting here
16:49
or at least yeah.
16:50
The print command.
16:52
That's let's try this one.
16:56
Yeah, you can also see doing that life is a little bit weird.
16:59
Um, yeah, that works perfectly now.
17:04
So yeah, I successfully printed a string and printed the number three.
17:10
I carrying out the computation here and you can see, I mean,
17:14
just based on my workflow here, that this is a lot of work, right.
17:18
So maybe we can just use Python to do something simple, like that
17:23
way more conveniently for that.
17:27
I don't even need to set up some script and ComPilot.
17:31
I can just use my interactive interpreter.
17:35
So I'll also show you how you can set it up in a later video.
17:38
But for example, will just enter my interactive Python.
17:42
Session here.
17:43
And I can just, um, yeah, I don't even have to declare variable here.
17:48
I can just type it and it will know that result is an integer because I'm adding
17:55
to introduce here so I can just show the results here or I can also use sprint.
17:59
It's not even necessarily in the interpretor.
18:04
And then similarly, if I want to get my string, I can just type a plus B
18:11
equals C and I can just print works.
18:17
I'll just execute word.
18:18
I'm also know that our way there are a lot of different ways to print something
18:23
in Python, the string formatting.
18:25
I can use the same thing I used in C like doing it like this.
18:39
And also, instead of running this in our interpreter, we can write a Python script.
18:45
This is usually useful if we develop more complicated code or if we want
18:51
to share our code and stuff like that.
18:53
So they can also write a script file, example pain.
19:00
And I can, um, just do the same thing I did in, oops.
19:05
It's giving me advice here.
19:07
That's cool.
19:07
Right?
19:08
Uh, anyways, um, Works, let's call it a plus B equals C and
19:18
then printing just the result.
19:21
And you can see it's making suggestions or suggestions here while I type.
19:27
So visual studio code is actually pretty handy for Python programming
19:30
because of all the additional help here in case we need it.
19:37
And then once I've done that, I can just run the script by.
19:43
Calling Python sample and it will run that and we don't have to compile anything.
19:51
We can just safe and then run it this other way.
19:56
You can just run it to here.
19:57
I think it should.
19:58
Oops.
19:59
Yeah, it should also run it here.
20:01
Usually I'm traditional.
20:02
I just use my terminal for that, but you can also just do it, a visual studio code.
20:06
It's maybe easier.
20:08
One disadvantage though, when you're running Python code, is
20:13
that things are evaluated at runtime except like syntax, arrows.
20:18
Let me show you what I mean, if I have something like if some condition
20:23
and then I have something like on text equals I don't ABC class
20:29
one, two, three, and then else.
20:33
Text equals a, B, C plus let's say, I don't know.
20:39
Something like that.
20:42
Oops.
20:42
I am not sure what button I pressed here.
20:47
Okay.
20:47
So if I have something like that, uh, I should, maybe I should,
20:53
um, the, find the condition.
20:59
Mm, let's say false.
21:03
So if conditions false, it will execute this one first.
21:08
Let's quickly do that.
21:11
Okay.
21:11
Ed works because there is no issue here.
21:14
However, this part here is kind of illegal in Python.
21:18
You cannot just add a number or interject with string.
21:22
If you wanted to add this, you would have to do this.
21:26
Oops.
21:27
I'm sometimes pressing the wrong button here.
21:32
Right?
21:32
So you would have to do this and.
21:36
This one is not.
21:37
Okay.
21:38
So Python is not telling us about it though.
21:41
It's executing the code anyways.
21:43
However, this can cause issues.
21:46
If you have very complicated code, let's say you are Instagram and you
21:50
implemented some very complicated API and there's some rare case.
21:56
Where are some else conditional.
21:58
If condition gets triggered, it's very rare.
22:01
Maybe it only happens once a month or something.
22:04
So if you'd apply that code, we'll likely not know that
22:07
there's maybe a potential error.
22:09
Yeah.
22:09
However, if some user uploads a certain thing and it triggers certain condition,
22:14
then it may cause an error and then it's pretty late because then the
22:17
user gets annoyed and stuff like that.
22:19
So that's one disadvantage of Python.
22:21
So, um, This one is only executed or evaporated if it's executed.
22:27
So if this condition is true, then this would be executed that
22:31
if condition will be executed.
22:33
So if I do this, now we get a type error.
22:36
Here can only concatenate string, not integer string.
22:40
So yeah, that is a little bit annoying.
22:42
Right.
22:42
But yeah, that's one downside of Python.
22:44
However, we get all the convenience that things gets executed without a compiler.
22:50
All right.
22:51
So enough about compilers and stuff.
22:54
Let's talk about how we can set up Python.

##v14:

0:02
Yeah.
0:02
So in this second video, we are going to talk about the setup,
0:06
how we can install Python.
0:08
In the first video, we talked about the introduction or we talked about.
0:12
Interpreted and dynamic, uh, programming languages and see that
0:16
CS aesthetically type language and Python is dynamic interpreted.
0:20
Now let's talk about setting up a Python.
0:24
Yeah.
0:24
And please watch the video before you install anything on your computer.
0:28
What should at least one time and, uh, don't install anything on your computer
0:32
while you're watching the video, because I will tell you about different
0:36
approaches for installing Python and.
0:39
At the end, you will have maybe the full picture of all the options.
0:42
And then you can just choose the option that is best.
0:44
But if you install things while you're watching the video for
0:47
the first time, you may install something you will regret later on.
0:51
Right?
0:52
Well, I just have some extra work, so maybe just be patient and watch the video
0:55
first, and then you can install things.
0:58
So in general, you want to check.
1:00
So maybe before you do anything, whether you already have an up to date Python
1:05
version installed on your phone, Peter on a Mac or Linux computer, you can.
1:10
Um, type which Python, and it should show you what, uh, where Python is installed.
1:19
And also what version thing you have to do, um, this in order to find all
1:25
the details in windows, I think you can use the ware command and then
1:31
you can see where Python installed is installed and stuff like that.
1:36
And in general, mech traditionally came with a very old version of Python,
1:41
Python two, and we are not going to use Python two for this cause.
1:46
So if you have anything that shows Python two, then I highly recommend you
1:51
to update this because Python two will likely not be compatible with most of the
1:57
code that we will be using in that class.
1:59
Actually, since the beginning of this year, the Python community.
2:04
Stopped supporting Python two or 2.7.
2:07
So.
2:09
It's really highly recommended that you upgrade Python.
2:12
And ideally, I just see, I have Python 3.7, ideally maybe install 3.8.
2:18
There's a 3.9 version, which is currently in development.
2:21
So I wouldn't install that one yet, but 3.8 3.7 should be fine.
2:26
Um, in the process of this video or the next video, I will probably
2:30
also upgrade my Python here to 3.8.
2:33
I just see it's still 3.7.
2:37
And let me maybe show you the official way of installing Python first.
2:43
So the official way is by going to python.org and then
2:48
downloads should be like this.
2:51
Um, we all check that art personally.
2:54
I usually don't use this installation way.
2:58
So if we go to the web browser, just entering this one here, um, you will.
3:05
See, this is the main Python website and I think it automatically
3:09
detects which operating system you're on based on your browser.
3:12
Um, yeah, that's also a bit creepy because it's like all
3:14
the privacy stuff is anyways.
3:16
Um, it knows that I'm on macro S by the way, uh, macro S should be spelled.
3:22
Oh S um, 10, I think 10 something that's like make Apple thing.
3:26
That's the data to spell it like this, but it doesn't really matter here.
3:30
And I don't want to get distracted anyways.
3:32
I, um, you can go here and then download it and install it.
3:36
However, I usually recommend installing it a different way,
3:41
which I will show you shortly.
3:44
So I personally, um, we don't need that.
3:48
I personally install Python using Anaconda or well specifically mini
3:54
Conda, which was a leaner version of an icon and icon that comes with a lot of.
4:00
Libraries which are useful, but we are not using all of them and they can maybe use
4:06
too much storage space on your computer.
4:08
So I usually use mini Conda, which is just a package installer
4:13
and Python distribution.
4:14
It does not come with any libraries.
4:17
So I usually prefer that it's a little bit leaner, but it also requires more work.
4:22
Um, cause we have to install it, pick it just manually.
4:26
You like, I just set an icon, a mini corner.
4:28
These are.
4:30
Python distributions
4:38
and, uh, package managers.
4:42
Why do I recommend that?
4:45
It's just like, uh, something I had a very positive experience with in the last five,
4:49
six, seven years, and a lot of the members of the Python scientific computing.
4:55
Community is also using an acronym mini Kona, because the
4:58
package manager is very nice.
5:00
So what it does is for example, it will manage multiple packages
5:05
for you and making sure that all the required versions I installed.
5:09
So for example, if you update num PI, it will also make sure that
5:14
, which is connected to it will be.
5:16
Um, updated and stuff like that, it will kind of see, or if, if you have
5:20
a installation and require a certain number of the installation and it will
5:26
updating one package, we'll also maybe make sure that the other packages updated.
5:30
But also if you install packages that will get you the versions that are best suited.
5:36
So the newest version is best suited for your operating system and so forth.
5:40
So there's a lot of, um, yeah, making sure that everything works well together.
5:46
Stuff happening under the hood.
5:48
So in that way, I find using conduct very convenient.
5:51
It will make your life most of the time easier.
5:54
However, using just a regular Python should also be fine.
5:59
But yeah, personally, it's just my preference using an icon and mini MineCon.
6:05
It's also free.
6:06
So there's not really anything bad about it.
6:09
I wanted to show you how we can install it.
6:11
Let me also just remove my current installation.
6:16
So if you install mini Conda, it will create a folder in your directory and
6:22
it will contain all your Python stuff.
6:25
Um, there will be different environments like, um, I have a
6:29
Python 2.73538, um, environment.
6:35
It's if I want to test.
6:37
Different software.
6:38
Um, want to test how certain code works on old Python versions?
6:42
I can activate this environment or this environment and just test it.
6:47
So, yeah, I have my 3.8 environment here.
6:50
I have an environment, um, my book, which I worked on, I wanted to make sure that
6:55
it's, um, tested in a blank environment.
6:59
So I also have an environment for a small code for my book,
7:02
testing it and stuff like that.
7:03
So it's very nice.
7:04
This, if you move it out here, It is basically like uninstalled.
7:07
I can also move it to my trash and then it's uninstalled there's no, no, no stuff
7:12
left on my operating system, which is, I think a very clean way of installing it.
7:17
So the website for downloading mini Kona.
7:20
It's um, I've written this down here in front of me.
7:24
Um, it should be docs dot, contact.io/english version
7:31
latest, and then mini condo HTML.
7:37
So if we go to that website,
7:46
We get the different installer options and you can see there's also some for windows.
7:53
We are on a Mac.
7:54
So, uh, I usually use the bash installer.
7:59
So I click on that one.
8:01
Download it.
8:06
So means it's a shell script, a bash shell script nowadays, I think, uh, since
8:14
the recent update, what am I on here?
8:16
Um, that is good to do Catalina.
8:22
So in Catalina here, um, I think they use a Z shell by default.
8:25
It's not the best shell, but I think it's still works.
8:29
So I can, uh, go to my desktop where I downloaded it by default, everything
8:33
downloads on my desktop, on my computer.
8:35
So I have my mini corner thing here.
8:37
Make me bigger here.
8:40
I can then execute midnight mini conduct.
8:42
And then, um, ahead through the steps.
8:45
So click enter.
8:47
Yeah, no, the license agreement, because I installed it many times.
8:51
All right, so I can scroll through this one.
8:54
Oops.
8:54
It too much.
8:56
I accept the license agreement and then it will ask me where
9:02
it wants to be installed.
9:04
I like it to be in my main home directory, so we'll just hit
9:08
enter and then it's installing.
9:23
Yeah.
9:24
And initializing conduct is also usually a good idea.
9:27
So we'll also hit yes here and that's it.
9:32
So I have conduct installed.
9:34
I can then double check that my default Python version is no.
9:40
The Python in my mini Conor directory.
9:42
And I can open Python like this and it should show me 3.8.
9:47
If you recall, before that it was like 3.7 something.
9:51
Right.
9:51
So I successfully updated my Python here.
9:56
Yeah, what's also nice about Anaconda or mini Kona is that, uh, it helps us
10:02
with managing different environments.
10:04
So unless you use Python for many other things, you can just ignore virtual
10:09
environments for this class, but it may be useful for one or the other.
10:13
If you're working on multiple projects to have a yeah.
10:18
The statistics for five one on yeah.
10:21
Environment.
10:22
There's by the way, another tool for virtual environments, it's
10:25
called a virtual ENF, which is also, it's just an alternative it's.
10:30
Um, if you go to virtual ENF paper or not in the English version, stable,
10:42
if you go to this link here, then you will find about a different.
10:48
Environment manager that many, many, many people use and recommend.
10:53
However, personally, I like to use the Cano one.
10:57
So for example, I can create a new virtual environment just for this class.
11:02
I can do it like this conduct, create your environment, and
11:06
then I can give it any name.
11:08
I will just call it statistics of four, five, four, five one, and this
11:15
will create a new virtual environment.
11:20
And then I can activate the environment via Corning it by its
11:27
name, Conda, sorry, Conda activate.
11:30
And then the environment here, and this will have activated
11:34
my virtual environment.
11:36
And then I can also.
11:39
Deactivate it, this is usually helpful if you are working, um, with various
11:47
conduct packages in different projects, but if you just use Python for this
11:52
class and nothing else, and you don't have to have different package versions
11:55
of different libraries, then it's fine to not use special environments.
12:00
Yeah.
12:00
And how can we then install different packages?
12:03
So one package, for example, that we will need for that class for this
12:07
class, next lecture is numb pipe.
12:12
So what you can do is you can use the PIP installer to PIP install, numb pain.
12:19
However, if you are using conduit, I recommend using the condor installer.
12:26
Using is just fine, but I usually only use that if a package is not available in
12:31
conduct because yeah, the condom packages, they are usually a little bit more,
12:36
um, I would say tested better tested.
12:38
So, um, the conduct community, there's also a Conda, um, forge community.
12:43
They have some recipes to making sure that the packages work well on your computer.
12:48
And, um, historically for certain packages, it makes
12:52
it easier to install them.
12:54
But to be honest, nowadays, there's only a very little difference, but since we are
12:58
using the conduct package manager, anyway, let's just use conifer, installing it.
13:03
Conda install lumpy.
13:19
So, if we would have wanted to, we could have installed a different version.
13:24
So if there's some certain version requirement, that's maybe not
13:28
the older newest version we could have also installed Conda install.
13:33
Let's say num PI 1.15.
13:37
We don't want to do this right now, but, um, let's just say you have a
13:41
software and you want to make sure your software works for both, um, Python.
13:47
Uh, non-pay 1.15 users and, um, num PI.
13:51
1.1, nine users.
13:54
So in that way, how I would do is I would use or create an environment that's a
13:59
con a create new environment and call it.
14:02
I don't know.
14:02
I'm PI one five, create an environment, a condor activate num
14:10
PI one five, and then Conda install.
14:14
Um, num PI equals 1.15.
14:30
and then you should see if you open Python and impart non-pay
14:41
version should be.
14:45
The 1.15 version here.
14:48
And then if I are conduct the activate my environment, I think it has maybe even
14:56
downward Python because it's not a 3.79 because it's a very old non-paid version
15:00
that is maybe not supported in 3.8.
15:03
So if I cannot be activated, I'm now in my normal Python thingy
15:08
here, and then this should be the.
15:12
Uh, 1.19 version.
15:21
Yep.
15:21
You can see this is the other version.
15:24
So I can, for example, if I want to run code in my other
15:27
environment, I can just activate this environment and then I will have.
15:36
My other version.
15:37
And then I can switch again by the activating this environment.
15:41
And that way I can make multiple environments to test my code
15:45
in different package versions.
15:47
And usually for this class, it will not be required.
15:50
I'm just mentioning it as one cool thing about condom.
15:54
Yeah.
15:55
And later on, you may want to update certain packages.
15:59
So you can also use kind of updating Petra packages.
16:03
It's usually Conda update.
16:06
Let's say non-pay to tell me, Oh, it's actually updating something.
16:12
Thought it was already up to date.
16:13
Okay.
16:13
Fair enough.
16:16
But anyways, yeah, Conda update something.
16:18
It will.
16:19
Update packages.
16:21
And, um, similarly, so if you want to use PIP and PIP, um, updating a
16:27
sort of a different, so you would type PIP, um, num PI upgrade.
16:33
I think if you install it by a PIP, The last thing for this video is
16:39
maybe showing you how to install packages that are not in condos.
16:43
So for example, one of the packages we are going to use in this class for
16:47
certain things is the MLX extent package.
16:50
So the con Kona install and an extent command will likely not work unless
16:54
they have done something on it recently.
17:00
No, you can see it's not working.
17:02
It's not finding ML extent.
17:05
So if that's the case, I usually recommend checking out kind of forge.
17:10
So there's a channel called Conda forge, and this is a community, um, developed
17:18
approach or a repository that contains.
17:22
Libraries supported by the wider conduct community and kind of watch packages are
17:28
usually very well tested and very well supported on different operating systems.
17:33
So I really recommend using of forge over PIP, for example, personally, um,
17:39
I'm the developer of eminent extent.
17:41
For example, I usually upload my library to PI, which is the Python package index.
17:48
And once it's there, it can be installed by a PIP.
17:52
However, then I also upload it to kind of forge and they run a whole bunch of
17:56
different scripts, making sure it works on windows, making sure it works on
18:00
Linux and Meco S on different versions.
18:02
It's way more comprehensive than what I do before I upload it to PIP.
18:06
So usually that version is on very well trusted and really
18:12
robust and should work basically.
18:14
So I usually really like couldn't afford.
18:17
Let's install.
18:18
Yeah.
18:19
I'm an extent.
18:30
So yeah, you can see, it's also installing some of the requirements of
18:34
Penda Smith put lip and other stuff.
18:37
Um, so yeah, what's nice about that is we probably won't have
18:40
to install them by hand later on.
18:45
Okay, but I think, yeah, that's all I wanted to say about installing Python.
18:49
I personally recommend Conda.
18:51
However, I realized some people may prefer just installing Python from
18:57
here from the main Python website.
18:59
Um, either way is fine.
19:02
I'm just telling you what I am doing and you don't have to do everything I'm doing.
19:07
I'm just.
19:08
Telling you, uh, yeah, my experience and hopefully this is useful
19:12
to you and wasn't too boring.
19:14
And in the next video, I will tell you about a year running Python code.
19:18
What I use for running my code.

##v15:

0:00
Yeah. So in this third and last video of lecture three, I'm going to show you how
0:05
to run Python code running Python code. And by that I don't mean to introduce you to all the concepts of Python, but
0:13
rather I will talk about the different ways we can execute Python code.
0:19
And most importantly, I will talk about Jupiter notebook, which is a certain file format and also program form.
0:26
Python code that you will be using for the homework. The first homework assignment will be sent out next week.
0:33
I am currently preparing that and it will be likely about implementing a cane, nearest neighbor classifier, and you have to make the homework most convenient.
0:43
So that you can write a text, have some equations run code, and also have plots in one document.
0:49
I will ask you to do that in a Jupiter notebook, and I will show you in this video, how to set it up.
0:55
If you have not worked with Jupiter notebooks yet, but for now, let's take this step by step.
1:01
I will show you first the easiest way to run Python code.
1:06
So I would say the easiest way is using the interpreter or some people also call it the ripple.
1:15
So interpreter or rapport.
1:21
So, yeah, rebel is a weird name. It stands for REIT evil.
1:28
Print loop. And that simply means that we are executing Python interactively, and we can do that.
1:34
For example, if we go to our terminal, wait, let me do that nacho here.
1:40
Um, my opening Python, and then we can now go, go ahead and execute our code.
1:46
Yeah. The reason why we call it interactive is that it gets evaluated immediately.
1:52
So that means if I have write down an expression in my interpreter and I hit enter, we can see the results immediately.
1:59
So let me show you what I mean. So if I type print, let's say one plus two, it will already
2:07
show me the result immediately. I don't have to compile anything or.
2:12
Run a script or so forth. And this is what I mentioned also in the first video and the same goes also for more complicated things that say a followup.
2:20
So for example, if I loop over the values on zero to five, oops, I forgot
2:30
an influx in wrench indentation. So if we print the values zero to five, they get printed immediately.
2:40
As soon as I. Finished my full loop. So the dots here, these are line continuation characters.
2:47
So that just means that, um, the line or the command ends here.
2:53
And then after I press enter here, it will execute. Yeah. My coach here.
2:59
Yeah in practice, we rarely need to do that kind of interactive computing.
3:04
So personally, I would maybe do that sometimes if I have to quickly compute some site in a way use Python sometimes as my calculator.
3:12
For example, if I want to know the sum of some numbers, I would just type on one,
3:17
two, three, four, something like that. So I would just use that for my convenience instead of using a
3:24
pocket calculator, I go to my Python. Interactive interpreter. And that's how I execute code.
3:30
But personally I would never use the interpreter for more complicated code because it's easy to lose sight of what computation we are doing.
3:39
If we make, for example, some typos and you see then, um, That we have
3:45
some Arabic, my sister's in between. And even if we fix them, they're still there. And then sometimes if we want to read what we have done, like 10 minutes ago, for
3:53
example, it becomes tedious to scroll back and find the commands that we executed. So personally, when I write more.
4:00
Complicated code. I would do that either in a Python script or in a Jupiter notebook. And I will also show you when to use which and how they work, the Jupiter notebooks.
4:10
But before we get to that, let me show you an alternative, um,
4:15
interactive Python interpreter. It's called So let me quit this one.
4:22
So I think if I type, I Python here, it will not work because remember
4:28
last video, I just installed mini condo and I didn't install anything except ML extent non-pay and so forth.
4:35
So let me try that. No, it doesn't work. So I, Python is an interactive interpreter that I really like and.
4:42
Jupiter notebooks, for example, they were back in the day called I Python notebooks because they were all built on top of . So it's still Jupiter notebooks, as far as I
4:52
know, rely on IP Python, which is a very nice alternative interpreter that has
4:57
some additional features and especially the so called magic, um, functions.
5:06
But let me go ahead and install I Python so that I can show it to you. And by the way, um, if you want to visit the IPython website, you can go
5:15
think it should be IP it's under arc. Oops. Let me see if that works.
5:24
Yeah. So the I Python website is here. If you want to learn more about I Python, they have also
5:30
documentation here and so forth. See a lot of that is also mentioning Jupiter.
5:36
Anyways, let's install IPython because I prefer condom. I use Conda for installing IPython condo install Python.
6:02
Now after installing I Python, we should be able to start it from the command line.
6:09
Yes that worked and you can already see it's a little bit more colorful. Right? So if I do the same thing I did before can see it has nice Syntex color, which
6:18
is relatively nice and helpful for writing some more complicated code.
6:23
So let's just do the same thing, but it, before four I in range five, you can see, it looks a little bit nicer.
6:35
It's also nice. It has this history function, so you can go back and edit it, which the normal interpreter doesn't allow you.
6:41
So it's more easy to modify some code. We can, for example, just go in here and at one, without having
6:48
to rerun everything or I'll retype everything, um, and so forth.
6:54
So that way already the editing or modifying code in Python is easier than
6:59
using the regular IPython interpreter. So one killer feature of I Python, I would say is the question, Mark symbol.
7:09
So in Python, we can get help by using the help function so I can type help some, which was nice.
7:17
But yeah, the IPython interpreter has a nicer, shorter way. You can just type.
7:22
Um, some question Mark, and it gives you this, I think more readable version of this it's especially useful.
7:29
If we have more complicated documentation strengths, this is maybe a very simple one, Larry like that.
7:34
And with that, um, so there's not only the question Mark, but a whole bunch of useful features and these features are called magic commands.
7:43
These usually start with this percent sign. I will only show you one particular one for now, and that's the time it.
7:52
Magic command. I really liked that one because it helps you to very efficiently and quickly compared different emblem code implementation to see which one
8:00
is more efficient to show you what I mean, let me implement two functions for reversing strings, and then we'll take a look, which one is faster.
8:10
So function one, let's call that reverse string one because I'm not very creative.
8:17
Uh, just to my string here and. For this function, I will just use the joint function or method
8:29
together with reversed my strength. That's one way for reversing a string.
8:37
And the second way, the second function we'll call that reverse string too.
8:51
And for this one I will be using, um, just indexing.
9:00
I will talk more about indexing next lecture when we talk about non-pay. But, um, yeah, so these two columns mean, um, basically, so the first
9:09
column is the beginning and end. So if we don't specify in a beginning and end, it will take the first
9:15
and the last position and the minus one, we'll flip it around. So it will start at the end and go to the beginning.
9:23
So we will reverse the string this way. So just to make sure that this actually works.
9:29
Let us test our function with just some arbitrary string.
9:34
Hello world. Reverse string one.
9:42
That works right. If we read it from. Here to here. It's successfully reversed.
9:48
Let's try one other function.
9:55
Alright, same results. That's great. Um, now we can use the time at function to find out which one is more efficient.
10:02
This seems a little bit silly because it's a very simple function here and we're just reversing a string. Okay. But for real world application, when you implement code like scientific
10:11
code for scientific computing, it's sometimes really matters how efficient your implementation is. And then it becomes really useful to compare different
10:18
functions so I can call time it.
10:24
And then the name of my string function or reverse string function.
10:29
And then also with an argument that's just a, and when I execute it, it will do a benchmark.
10:38
So you can see it runs in 370 nanoseconds plus minus 10 nanoseconds per loop.
10:45
So it's running on 1 million loop. So it's executing the function 1 million times to get in good
10:53
idea of how efficient it is. And it, uh, it repeats that seven times and then computes the average.
11:01
So each run. Consists of 1 million repetitions and then doing, after doing that seven times,
11:10
this is the mean, plus minus the standard deviation, you can actually control
11:15
the number of runs and, uh, Loops by. I think the argument is minus N for the number of loops.
11:23
And, uh, the other one is minus R for the number of runs. I have to double check by default.
11:29
It may vary based on your function. So they do some automatic guessing of how many times to run it so
11:35
that it runs in a reasonable time. So we are just using the default arguments here. Let's do that now for function.
11:41
Number two.
11:47
All right.
11:56
Yeah, we can see the second function is three times faster.
12:01
Approximately you can see. It's now 130 nanoseconds.
12:07
It's like one third of the time. Of course we are only doing that for a very short string. We can also do that for super long string.
12:14
So maybe just for fun, let's do it. Just do something arbitrary here and repeat our string maybe thousand times.
12:26
Let's do 10,000. So we'll have this very, very large string. And then we do the same thing again.
12:37
Okay. Again, it's just, um, why I should've used to be here. Sorry.
12:53
All right. That makes more sense. Um, so it's now 1.3, three milliseconds before it was 371 nanoseconds of
13:02
course, it's way slower because. A string is way longer here. And also you can see it only runs 1000 loops for now because otherwise
13:10
it would take too long and it's doing some automatic guessing that we don't have to wait forever. Um, let's do that for the second string or second string function.
13:27
Yeah. So based on these results, now we can see. That the second function is magnitudes faster.
13:34
Cause it's now about 30 microseconds. And, um, here we had 1.3, three milliseconds, which
13:41
was 1,330 microseconds.
13:47
So 1,300 versus 30 it's approximately 40 times faster running the second function.
13:54
I mean the point was not really a, which function is. Faster, but yeah, we learned about this nice time at function and
14:02
why, um, why I Python notebook. I had Python.
14:07
The interpreters are very nice and has some extra benefits that the normal Python ripple doesn't have.
14:15
Yeah. The second way we can execute code is using Python scripts. That's what I showed you already in the first video.
14:21
So we can. Make a file. Um, let's save that on my desktop.
14:27
Call it my script of pain and then we can write some code for I in range five print.
14:39
I, then I go to my. Terminal and execute that.
14:50
So that's the second way that we can use to run Python code.
14:55
I, um, why just see, it says linter flake a is not installed.
15:01
I think it was just due to the fact that I just uninstalled Python yesterday. Right.
15:06
If you remember. So, um, let's install that. Using condom and a linter in Jupiter, sorry.
15:16
In a visual studio code is really nice for making sure that your coat has a good style.
15:22
For example, if I write some function with some function argument let's to do it like
15:31
this, and it just prints out that then you have a nothing really special here.
15:39
What it will do is it will highlight issues like style issues. It's like with the English language, if you have a comma
15:45
mistake, it's kind of not. Terrible. People can still read your text, but it doesn't look so nice if you have like
15:52
spelling errors and stuff like that. And the same is true for Python code. So there are certain guidelines.
15:58
They are actually explained in a document called pep eight and, uh,
16:03
linter the flake eight, eight helps you with make writing cleaner code.
16:08
For example, I can hover over here and it says, um, That there are some issues, for example, no new line at the end of the file.
16:17
So if I do a new line, then this will be resolved. Undefined name a so yeah, we can't.
16:23
So it's also not only helping us with typing errors, it's also helping us with basic code problems because we haven't defined A's.
16:31
We should have written some string here, right. Because it's an undefined variable and here what's the problem.
16:38
Um, Expected to blink lines after class or function. So we have to add another line here, and then this is much nicer.
16:47
This is the more professional way to write Python code. And it will also highlight, for example, it's.
16:52
If I put a white space here, it will say unexpected spaces around keyword
16:57
it's, uh, the code will still run, but it's just good style to do it like that. So by the way, also with the spacing, for example, if I have a
17:04
variable and I do do it like this here, The white space is expected.
17:14
So here are the white spaces expected. If I would remove it, likewise, it would complain missing my space because
17:20
here it's a mathematical operation. So we have a white space also for the variable assignment.
17:26
So usually for variable assignment, we use a white space. However, inside.
17:32
A function when we define the parameters. Also, if you provide a function argument, uh, for a parameter,
17:40
we don't use white spaces. It's just the Python convention. But yeah, if you're not familiar and you have a flake eight here installed, it will
17:48
complain about it if it's not working. And which I think is a nice feature, also visual studio code.
17:54
Yeah. So the last tool I want to show you is Jupiter notebook and Jupiter lab.
18:00
Actually, I'm only going to show you Jupiter lab. So Jupiter lab app, it's a program that.
18:08
Runs Jupiter notebooks. So they are Jupiter notebooks, which is a file format.
18:14
And the files are abbreviated. I P Y N B, that's just a convention in Python.
18:21
And that comes from the fact that they were back in the day called I Python notebooks.
18:26
And it's a little bit confusing, but there's also a program called Jupiter notebook.
18:32
So Jupiter notebooks can be opened in an application. So this is a. Application, and this is a file.
18:42
The file can be opened in the Jupiter notebook application, but it can also be opened in the Jupiter lab application.
18:47
And Jupiter lab is just a little bit newer than Jupiter notebook. It's newer than this one.
18:52
And it's, it looks a little bit nicer and has some more convenience features, which is why nowadays I recommend using Jupiter lab instead
19:00
of the previous Jupiter notebook. And I will show you how we can do that.
19:06
So far that let's go to the terminal. Once you have Jupiter. Notebook installed.
19:13
You should be able to call it Jupiter lab. However, remember I just installed my mini con not from scratch,
19:21
so it should not work right now. Yep. It's complaining. So we would have to install it first.
19:27
So let's go to the Jupiter lab website should be on Jupiter lab.
19:32
Do I read the docs? Don't I, Oh, I think so. Let's try that one.
19:41
Oops. Yep. And here I would just look for the installation here and
19:50
usually they recommend yeah, they use kind of watch still. So let's copy that command here.
19:57
So you can also install my PIP if you like. Um, but yeah, since I'm using condoms, I will install it using condom.
20:23
Yeah. So now after installing it, we can open it from the terminal Jupiter lap and it will
20:31
open in our default browser by default. So, yeah, it will make a new browser view here and here on the left
20:41
hand side, we have a navigation that is just our file system. So I go to desktop and I can make a new notebook by just
20:49
clicking on notebook here. And it's currently called untitled.
20:54
You can see, it was just created here on the right. Can rename that and let's call that just my notebook.
21:05
And yeah, this notebook, um, is something. Recall, because you can write Mark down here.
21:11
You can execute code. You can have plots here. Uh, what else you can have LayTec in here.
21:17
So let me just maybe show you something to begin with. So I can, for example, choose Mark Don and Mark.
21:23
Don is a, if you have not heard about it, maybe search for it on the web. It's a very easy to learn language, which has some convenience functions.
21:30
For example, I can type, um, had our one and a two.
21:37
And a three and then some text. So this will be converted to a header, which is bigger than
21:44
a regular text, for example. And, um, this is the biggest headache, the second biggest header, the
21:49
third biggest header and so forth. And you can also have some quote text, so it should also make it Mark on then,
21:59
or, um, I can have, I can modify it here. It's maybe easier I can have Italax.
22:08
Um, both fund can have links very easily. For example, Jupiter lab website.
22:16
I can. Create links for other people to follow links like that.
22:22
Yeah. Lots of nice, easy things to format a text in markdown.
22:28
And what's also nice is allowing us to have equations latex equations here.
22:33
For example, if I write something I, what should I write to them? Maybe the weighted sum Z let's call it some I over N.
22:52
Um, maybe just something simple, something like this.
23:01
So you can see it's formatted as LayTec equation here, which is also very nice. So if you, um, if you, oops, if you've write some code and you want to explain.
23:15
Certain things using mathematics, you can just also have directly the later can hear, which is sometimes very convenient for note taking.
23:25
Yeah. Another thing you can do is you ha can have plots here. So for that, I think I have not installed so another thing is about.
23:34
Jupiter lab or Jupiter notebook is that you can use the exclamation Mark to execute terminal commands.
23:41
So instead of going to my terminal and running Conda install matplotlib I can do that directly here using that exclamation Mark.
23:50
So we'll see if I don't use it. I will be an error, right? Oh, it's actually working.
23:56
Okay. I don't even need to do that. Usually there was an exclamation Mark required for that.
24:05
So, what does it say here? Oh, I actually made a type one. I should have written that plot lip.
24:14
Yeah. It's a little bit hard for me to type here when I have my desk at an unusual high to make the microphone work.
24:21
So I have to maybe find a better solution so I can type better in not make so many titles.
24:27
Okay. Let's see what it did. Alright. It's installed. Matt put lip.
24:34
So let's restart the session. Cause it recommends us to do that. Uh, we don't need this money anymore.
24:42
So now there's also a certain. Way for Jupiter lab to have plots in line.
24:48
So what we do is met plot lip in line, then plots will be shown in the notebook.
24:53
They have some different options, like a metadata notebook and so forth, but you should believe this is the one that works on most computers.
25:00
And then for example, we can import MedPro lip. Pay it promotes pot.
25:07
It's also important I'm paying. We will discuss what that is in the next, um, lecture and extra for, I just want to
25:14
briefly show you how we, uh, how nice it is to show plots in the Jupiter that pier.
25:20
Okay. Let's just use some values on.
25:26
Or maybe let's, uh,
25:33
just some random values
25:38
and then we can plot histogram.
25:47
And you can see everything is nice in the browser here, so I can then also annotated and so forth.
26:02
So yeah, it's I really like that. It's um, having everything in one notebook. So of course it's a very trivial example here.
26:09
Just some random stuff. However, when you work on real code later, it's sometimes very helpful to visualize
26:17
your results and using Jupiter lab. It's very nice to have code notes, plots everything in one place.
26:25
So the last question for today might be when should you use Jupiter lab and when should you write scripts?
26:33
So it's a tricky question. Personally. I use visual studio code.
26:38
So Python scripts to develop functions or code in Python that is, let's say, code of a package or code that I'm planning to reuse.
26:47
And I use Jupiter lab. Yeah, just like a notebook to do some. Analysis or to take notes and to explore and stuff like that.
26:55
But I also find it super helpful for writing documentation, maybe to show you what I mean by that.
27:02
Let me give you a concrete example. So I mentioned before that I'm working on this ML extent library for Python.
27:10
So for ML extent, um, I have, for example, my code repository, uh, this is
27:17
just a Python package and then I have. The coat here, for example. So let me open the file.
27:24
Um, this is an implementation of an ensemble vote classifier. And we'll talk more about this later in this course, and this is just the
27:32
implementation of this classifier. Um, so there's a lot of code and this is something I would
27:37
write in visual studio code. Right. But then if I use the ensemble board classifier for some analysis, then what
27:47
I would do is I would use a Jupiter lab environment or a Jupiter notebook.
27:52
So for example, um, in this context I have documentation here.
27:59
So, um, if I go to docs, Sources is a little bit complicated how I set it up,
28:06
but yeah, I've write my documentation in Jupiter notebook or Jupiter lab.
28:12
So for the classify and some of what classifier I would have. Um, I would have this failure, this I Python notebook file.
28:20
So you're maybe wondering what's going on with the MD files. It's a markdown file. Um, you don't have to do that.
28:26
I'm just doing that. I'm converting the Jupiter notebooks to Mark down because, um, I have a website for M and extent.
28:35
So for example, here on this website, I have an HTML version of the markdown.
28:43
So basically the. I Python notebook gets converted to Macedon and the McDon gets converged HTML.
28:52
And that's what you see here, but there's a lot of warnings going on.
29:00
I should maybe improve that in future. So, but yeah, there are some, just some documentation for how to use the methods.
29:08
So you can see I'm using some, uh, LayTec here. Um, by the way, there's some weird issue in Safari that it
29:15
doesn't really show LayTec nice. Right now we could automate in Firefox to make it look nicer, but that's
29:21
kind of right now not necessary. Um, and yeah, so I have some LayTec here, some explanations,
29:30
then I have my code examples. And also some plots, and this is all based on the Jupiter notebook.
29:38
So I have it right here, so I can go here and actually open it to show it to you.
29:57
Okay. So what's the Jupiter notebook. And yeah, so this is basically my Jupiter notebook, so I can go here and
30:04
then execute it and I can modify it. There's a typo. I can just go here and edit it and stuff like that.
30:10
And what's nice about writing, stuff like that. And the Jupiter notebook, like also the code and everything is that I can, uh, if
30:19
I make an update, just rerun everything. So if I go there. And change, make some changes to the code here.
30:27
I could then go to the Jupiter notebook and it's importing, um, an extent
30:34
or the function for an extent here. So I can make an update and then rerun everything, restart
30:40
Colonel and run all cells, and then it will execute everything. And I can then simply double check if everything still works.
30:48
If my, maybe my own. Fix your maybe is broken some documentation.
30:56
I can then see if some of the cells fail so you can see it's currently executing this part and so forth.
31:02
Of course I have also unit tests, but that's way beyond scope for right now. I'm just yet trying to tell you how I use Jupiter notebooks and how I use.
31:11
Uh, visual studio code and Python scripts. So I wish I could show you the homework right now, but it's not finalized yet.
31:17
I will share with you next week. And also right now this week should be more about setting
31:23
up your Python environment. So making sure you can run Jupiter notebook or Jupiter lab, and then
31:30
next week I will go over numb pipe. And for expanding non-pay we'll also use a Jupiter notebook.
31:35
And then I will explain how we do machine learning with psychic, learn the machine learning library.
31:40
And then we will also get back to the conceptual lectures, like decision trees and talk about more machine learning algorithms.
31:49
So this week was a little bit more technical next week. We'll talk about the tools that we will be using for machine learning.
31:56
And then we will go back to concepts.

##v16:

0:02
Yeah. Hi and welcome back everyone. I hope you had a good week and set up your Python environment last
0:07
week, because today it will be. Pretty irrelevant. We will be using your Python environment pretty heavily.
0:13
So today I will be talking about scientific computing and Python for that. I will be mainly discussing the non-pay library, which is
0:21
an array computing library. And then in the next lecture, lecture five, I will be talking
0:26
about psychic learn, which is a machine learning library for Python. So why are we doing that?
0:32
Why are we spending so much time on computing? I really think it's helpful to have a.
0:37
Tool like Python, where you can toy around with certain ideas and algorithms
0:42
that we learn about in this course. So after these two lectures, after the num pay and the sacred learn lecture, we will be getting back to the concepts and discuss certain
0:51
concepts around machine learning. So we will start by decision trees and sambal methods, and then talk about model evaluation.
0:58
And it will be very helpful to have a tool like Python, where we can try out these things in practice.
1:05
All right. So with that, let me then get started. So this week I also don't have any lecture slides.
1:11
I will using a Jupiter notebook to show you some of the ideas, because then I can also show you the actual code and the code output, and you can
1:19
have the Jupiter notebook afterwards. Um, actually I will make it available now, before you.
1:25
Watch the video so that you can actually execute it onsite. And also I encourage you while you're watching the video.
1:31
I'm pausing the video once in a while, and then also toying around with some of the code that I'm showing you.
1:37
Um, I think that really helps yeah. Deepening your understanding of certain concepts. Okay.
1:42
But with that, I think before I make this introduction belong, other than the lecture itself, let me get started.
1:53
Yeah, before we start, I should again, mention that this Jupiter notebook is also on get hub.
1:58
So if you go to our classes, get up repository here. Um, it's under lecture four and then this I Python notebook
2:07
file or Jupiter notebook file. So if you click on it, you can also view it and yeah, you can also then download it from GitHub.
2:15
I will. Also include this link on canvas, so you don't have to search for it, but yeah, you can maybe just don't know the whole GitHub repository, or if
2:23
you recall how to clone a separate pository, you can just update your, get up repository by a pole, get to pool.
2:32
And yeah. So that is where you can find the notebook. Something else I wanted to say is, yeah, this first.
2:40
The lecture will be about nonpayment. And you can also find more information about an empire on the
2:45
main non-pay website, because the notebook that I created here is just a very basic introduction.
2:52
So if you want to learn more later, you can also consult the official documentation here, which has all the necessary details.
3:01
And there's also a learning page. So here the non-paid community compiled.
3:08
A lot of tutorials from a beginner tutorials to more advanced
3:13
tutorials, which is something you may want to check out later. But for this class, it will not be required.
3:19
I don't think we will cover anything that really goes beyond the basics that I created here.
3:25
Also, if you're interested and find a buck or something like this here, this is the official num PI getup repository, but I would only recommend to file
3:34
a buck for example, or contribute a feature if it's really a buck. And you made sure that no one else filed it yet because you can see
3:42
the 1,900 issues you're on get up. So, uh, yeah.
3:48
Pay an unpaid community is very busy to not add more to their work, please, before you submit an issue, make sure that it's really an issue.
3:56
So you can also, if you have some issues you can search here for these types of issues.
4:01
Anyways, um, the num PI project is an open source project. Also, there are many people contributing to it, mostly scientific researchers
4:10
and people doing scientific computing computing at various companies. So 1,200 contributors right now.
4:18
And what's also interesting to see us, the Cote breakdown of this repository. So you can see the majority of code is in Python, as you would expect,
4:26
but some of the code is also in C and C plus plus and Fortran. And that is because non-pay is using those primary C under the hood.
4:36
To make it more efficient. And that is why it's so attractive for Python users, because it is way
4:42
more efficient using Python scientific computing compared to the basic Python, um, methods are implemented, basic functions implemented in Python.
4:53
Okay. So let me switch one more time to this. Main notebook here. And then I will briefly tell you what this, uh, video, the first
5:01
video will be about and what will be covered in the next videos. So I recently discovered this very nice plugin for Jupiter lab to just before
5:10
we go through this list, it's called a Jupiter talk and Jupiter leper talk,
5:15
uh, talk sense for table of contents. So, if you want to install that and you can go to the GitHub
5:21
repository and they have some instructions for installing it here. Um, so yeah, you can install it and then after you install it, you will have such
5:29
a nice button here, which gives you a table of contents for the whole notebook. So using this table of contents, just to briefly tell you what we are going
5:37
to cover in this first video, we are just covering the basics of non-pay.
5:42
So that means, uh, introduce what non-pay is a gift, some little motivation of
5:48
high non-pay school, and then introduce end dimensional, erase like the basic data structure implemented by non-pay.
5:54
And then in the upcoming videos, we will talk more about array, construction, and indexing, and then also some array math and the so-called universal functions.
6:05
After that, we will talk a little bit more about. Broadcasting, which was a really cool feature in non-pay.
6:11
And then also some advanced indexing, which is usually called fancy indexing.
6:17
Yeah, but they are small. They are random number generators, ways for reshaping number hurries.
6:23
Uh, non-payers sorry. And, uh, non-paid comparison operators like creating selection, masks and so forth.
6:30
And then just briefly about linear algebra with non-pay after we've covered all the non-pay stuff.
6:35
I also want to give you a brief introduction into MedPro clip. I won't be talking much about CIP because CyPass is the library.
6:42
That implement some algorithms on top of non-pay algorithms that are commonly used in scientific computing.
6:49
For example, the two norm that we covered in the cane and lecture would be a function implemented in SIPO.
6:56
However, CIBA you can think of it more as a collection of tools. So we don't have to learn anything specific about there.
7:02
If we need it. I can tell you what we have to import from now, from Nampa, sorry, from CIBA.
7:08
And then we can use it. We don't have to really memorize the whole library. Any case. And then I will lastly show you some med plot lip submit plot lip
7:17
is a library for plotting graphs. All right.
7:22
So that is just the overview. Um, it's hopefully not getting too long in terms of time.
7:28
It looks like it's a lot, but I think we get through this pretty efficiently.
7:33
Yeah. So let me hide my table of contents and focus on the main notebook now.
7:39
So like always, I start by importing the watermark library. So watermark is a library that I developed just for showing package
7:47
versions, because personally I find it very helpful to see what libraries are used the last time I executed a notebook.
7:54
So by that I can make sure. That, uh, I execute the notebook with the same libraries. If I need to, to reproduce some code, I can also see whether our
8:02
libraries are outdated or not. So if you don't have watermark installed, uh, this is what you
8:09
can execute to install watermark. And then once it's installed, we can check the versions of the libraries here.
8:15
So non-pay site by Metro flip that, uh, these are the main libraries for this notebook and yeah, uh, I will be using non-pay PI 1.1 9.1.
8:26
I also recommend that you have a recent version of num PI. It doesn't have to be 1.19. It could be non-pay.
8:32
1.8 or something like that. It's actually, I'm 19, not one nine.
8:37
So in many, uh, open source projects, people count, um, The versions as follows.
8:45
So the last number is usually a Pecha origin. That means a while. Let me start on the left hand side.
8:51
The left number is the major version. So this is num PI version one. And then this is the secondary version.
8:57
It's like, if you, this is like for defining the main API. And once the API is stable, there may be some enhancements and stuff like that.
9:05
And that will be usually the second version number. And this whole numbering scheme is also called semantic.
9:12
Versioning in any case. So this would be non-paid version one.
9:17
Uh, one 19, two pre precise and the number after the second dot, it's just a patch version.
9:24
So when people release, um, numbers that are greater than one here, it usually means a pitch.
9:29
So here, for example, this would be, uh, Python three Python three versus baseline two is a big difference, a big API difference.
9:37
And then over the course of the development of Python three, there were a new versions developed, like the edit, for example, the F
9:43
strings I talked about and so forth. So this is like for adding major features, but they don't
9:48
change the API fundamentally. And this is like for pitching, if there's a buck, but you don't want
9:54
to make a new version of Python. I mean, it's the same version you just want to. Patch the buck. Then you add this number after the second December point, any case.
10:04
So yeah, if you have not installed pine Cipla, you can install it using this command with conduct and.
10:11
If you do that, and these numbers are still not matching, you can update your condo.
10:17
Sorry. so sometimes this will not do anything if you have it already installed,
10:24
but it may be a old version. So you may have to run the updates to get the most recent version. So, yeah, I just want to say, make sure you have recent versions here and
10:34
then you shouldn't have any problems executing the code from this notebook. Okay, but that was just the setup.
10:41
Let's get started with the main parts.
10:49
Yeah. I have a lot of text here on how I want to just read it out loud. I just want to briefly give you an introduction, like what
10:56
non-pay is and what it is about. So non-pay is a rate library. So it's mainly for computing with computational arrays and array.
11:06
You can think of it as like a 10 saw. It's actually a data structure for representing a tensor.
11:12
There are other libraries like TensorFlow and PI torch. They call that. Tensile right away, although in technical trumps attend.
11:19
So it's more like a mathematical object and an array is the data structure representing this mathematical object.
11:27
And, uh, the non-pay array is basically the same thing as a patriarch or TensorFlow tensor.
11:34
Um, non-pay itself was created long time ago in 2005, by merging and numeric,
11:41
which were two computing libraries. Developed approximately in the 1990s, I think, um, num numeric came first,
11:49
like in the 1990s, a number Ray was a reimplementation of numeric and then they diverge a little bit, but had different features.
11:56
And then at some point they were merged. I think it was primary by Travis Oliphant who was on big, uh, yeah.
12:03
Uh, contributor. A still is a very big contributor to them. Non-pay and the NYPA and unpaid ecosystem, and many other libraries
12:11
nowadays are built on top of non-pay actually, I don't know. I mean, there are probably not many libraries anyone would know that
12:18
are not built on top of non-pay. So the most notable ones are CyPass.
12:23
I could learn Penders and so forth. So they are all built on top of non-pay and specifically they use the num PI
12:30
array format, which, um, Uh, I mentioned before, like the multidimensional
12:35
erase and uh non-pay and, um, these, we sometimes call them also end
12:41
dimensional array and the short version, the data type would be in DRA, which stands for and dimensional array.
12:48
And like I mentioned before, when I showed you the getup repository, um, Non-pay
12:54
has mainly implemented using C code. So Python acts as a glue language around the C code.
13:02
And that is what makes non-pay so efficient. So non-pay is way more efficient than let's say, using Python lists because
13:10
non-pay uses contiguous blocks of memory. Uh, with that, I mean, with memory, I mean a random access memory.
13:17
That's the computer memory. And that allows some things like caching, like, uh, the CPU has like
13:23
a T to cash and it can buffer certain values in the, um, in the cash and
13:28
make the Xs much, much, much faster. So in a Python list, everything in a Python list is, um, A pointer to a memory
13:37
location where the object is stored. The advantage of having a Python nest is it allows us to mix different types.
13:44
So we can have a string type and integer number of float and so forth everything in the same list.
13:50
However accessing it is relatively small slow. Of course, if you would execute Python code you as a human would
13:57
notice, it looks super fast, but in scientific computing, if you do a lot of computations, this would be super slow and a major bottleneck.
14:04
And a num PI it has the downside. Yeah. Everything has to have the same size in an array.
14:11
So you can only have interjects or only floats or only strings you can Mitch match them in the same array.
14:17
However, the advantage is if you have only data types of the same type in the array, that means, you know, the size of that array.
14:26
So if you have. Let's say 64 bit integers in that array and yeah, eight 64 buddies
14:33
to just, you know, the size of the array is eight times 64. And also you only need to store the first memory address the memory
14:41
address of the first element, because, um, you can get the other memory
14:47
addresses by simple arithmetic. So, um, you can just count so you can say.
14:52
No, let's say the first memory addresses at position 16. And the second one would be at 24 because it's 16 plus eight
15:01
if with an eight, a bit array. So I was just assuming eight bits right now. Anyway, so, uh, It's an advantage for computational purposes to
15:09
have everything at the same type. It may be an inconvenience when we work with certain data sets.
15:15
However, not that this is in practice, also not a big problem because in practice we can also use num PI when we process, sorry.
15:22
Penn does when we process the data and then we can later convert it to a non Tyree for very fast computing.
15:35
I, another thing I wanted to say is besides being more efficient, one other advantage that I really like about non-pay is that it allows us
15:42
to implement code more elegantly and makes it also more readable. So that's mainly the linear algebra operations that we will see later.
15:53
Um, yeah. And also coincidentally, there was just a paper about Nampa released after all these years, uh, the community finally wrote a review paper.
16:02
So that was in, uh, I was last week. So it was published in nature and it's called a re programming with non-pay.
16:10
So here's the figure from that paper that again, highlights that, uh, non-pay is really like the foundation of the Python ecosystem or so you
16:19
basically have even foundational libraries built on top of non-pay. So pay, raise, come at the very bottom.
16:24
And then on top of it, you have. MedPro clip the plotting library we'll be talking about and scientific algorithms
16:30
that all use the non-player race. And then you have techniques specific libraries, such as psychic learn the machine learning library that we will talking about.
16:37
There's cost there's pandas and stats, models, statistics, library, and so forth.
16:44
And they're also domain specific and application specific tools. So everything like you can see here is kind of built on top of is
16:51
probably the most influential or most important, um, Python library.
16:56
For example, just recently, um, when the first black hole was discovered, I mean, the pictures were taken also non-pay was involved in and so forth.
17:06
All right. Yeah. But before we get started with a bottom up approach where I will
17:12
show you the different things in non-pay, I wanted to give you a brief motivation why non-pay school.
17:20
So, um, what I did here is I just provided a very simple computation computing, a dot product.
17:29
So I'm not sure why this is missing. It doesn't matter. So this dot product here between two vectors between a vector X and w can also
17:37
be expressed by, uh, some, uh, basically, uh, some over these products here.
17:42
So you have X, X, one times. W one plus X, two times W2 and so forth.
17:49
So you can express the dot product also as a son. So yeah, it was just spelling it out. That's the long way to write this.
17:57
And every time you see a summon Python, sorry, every time you see some, you
18:02
can convert to a followup in Python. So somehow I would cut it up. I would use the followup for example.
18:08
So this would be the naive way of implementing the stock product. I would write it in Python.
18:14
So assume I have two lists. One list is a and one is the speed. So one, two, three, and four, five, six.
18:21
So the computation here in this function would be one times four plus two times five plus three times six, which I think should add up to 32.
18:32
So if I would execute this, let's check. Yeah, it's a 32. So this would be the naive way of computing, a doc product
18:39
in Python using a list. So, uh, using lists here and then the, for loop iterating over the elements in
18:46
the list, and then adding them to this, um, output value, which we then returned. That's our 32.
18:52
So recall the time at function from last lecture. So I'm using here the time at function to time how efficient this function is.
19:01
On two larger rates. So we have to erase with 1000 elements each. So let's execute that too.
19:12
Yeah, that takes awhile, but shouldn't take that long either. We go. Okay. So yeah, that is executed in 96 microseconds or
19:20
let's say 100 microseconds. Now I have the same thing in a non pay.
19:27
So here it's the dot product in non-pay. I can write it like this here.
19:33
It's a nonprofit function, but you can also call a method directly on Henry. Doesn't matter.
19:38
It's the same. And this should give us the same computation again, a dot product. Um, it's like a linear algebra vector dot product is one times four plus two
19:48
P two times five plus three times six. So it should also be 32. And just to double check, it generates the same results.
19:56
And now let's time how fast this dot product is Nampa. And then we can compare it to the Python implementation,
20:06
you know,
20:12
Okay. I finished, um, yeah, this one runs in 1.6 microseconds 1.06.
20:18
So it's about 100 times faster than our Python implementation, which I think is pretty impressive.
20:27
Yeah. And if you recall from the Ken and lecture, I showed you a way you can compute matrix multiplication using just Python for loops.
20:35
So we had these two nested Python, four loops. So after watching lecture, four might be interesting.
20:41
If you could try to benchmark the matrix multiplication in Python that I implemented in the Cain and lecture and compare it.
20:49
To using a non pay for the dot product. So a non PI, there's also a dot function that the same dot function
20:56
can also compute a matrix modification as we will see later, I think it was in a later video, but also show you some, uh, linear algebra stuff.
21:06
I think I had it in 4.9. So after watching these videos, Would it be cool if you on Piazza,
21:12
could pose the benchmark okay. Between the, uh, Citrix multiplication of Python and non-pay cause I
21:18
think it will be magnitudes faster. This one, that that product was 100 times faster for the vector product.
21:23
But I think for matrix medication might be thousand or 10,000 times faster. Okay.
21:28
So that was hopefully some motivation showing you why non-pay school. I mean, it's faster, like you've seen here, but also
21:36
this one is way more concise. Of course then this one. Right? So if you have a lot of code, it can actually improve the readability.
21:43
Oh, one thing I should maybe mention is. So in our newer versions of Python, I always forget the CA made this
21:50
notebook and also forget about it. A new version of Python. You can use the at symbol here, and this will also act like
21:57
the.so at and.is the same. So in non-pay, so the non-pay dot is the same as the at symbol.
22:07
So if I replace this by the, at this would also work. Yep. See, so it's another cool feature of Python or non-pay you can make
22:15
it even more concise, although it's maybe arguable, if this is looks
22:20
nicer than this, I don't know. But anyways, let's talk about end dimensional, erase.
22:28
Yeah. Like I mentioned before, a num PI array is somewhat similar to a Python list,
22:33
except it has the fixed size and it can have only elements of the same type.
22:38
And, um, but in contrast to a list, a non-pay array can have multiple dimensions.
22:45
So a regular Python is just one dimension. Uh, if you approached, uh, if you paid attention to the previous
22:51
section, have you seen that? We used a one dimensional race, but let's just do it again.
22:58
So let's do a list. Oops.
23:05
And then, um, this would be a one dimensional list. So it would correspond to one dimensional array.
23:11
So this would be, can also say this is a vector. If we work in the context of a linear algebra application, we also just
23:17
call this back to instead of array. It's a one dimensional Ray. Um, yeah, we can make two dimensional, erase a two dimensional array.
23:25
You can think of it actually as a list of list. So we have a list that contains two supply lists, and that would
23:31
be a two dimensional array. And, and yeah, this is, uh, corresponding to this two dimensional array and,
23:42
um, So the array has two Xs because of the two dimensional array and Python
23:49
starts at zero indexing and conscious to R so we always con from zero. So the non-pay, there's a concept called XL.
23:56
So the first X's X is zero corresponds to the first dimension
24:02
and, uh, X is number one. So this is the second excess because we started counting at zero.
24:08
So the second ex-US corresponds to the second dimension of the array. So the second dimension, if you think of a matrix in a matrix, we have, usually
24:19
we refer to matrix by rows times columns. Right. So if we, um, write the dimensions of the matrix, um, look like,
24:30
so, so we would write it like. This for a matrix of type real, the type and dimensions
24:39
we would write it like this. Um, let's say N times M dimensional.
24:46
So this would be, um, I think it should be math. BB always confuse these two.
24:54
So, um, it's would be N rows and M columns and similar in a non PI.
25:01
We have. Uh, X is zero for the rows. So one, two rows and X one for the column.
25:08
So one, two, three columns. So this would be a two by three matrix.
25:16
Yeah. And then, uh, I will talk more about indexing later, but if we want to,
25:21
let's say quickly demonstrate what the X's are for, if you're doing indexing everything before the comma refers to the first exes and everything after
25:30
the calmer refers to the second Xs. So, um, this one would refer to the first exes because it's at the first position.
25:39
So maybe let's choose. Some, uh, it's fine. So let's say we have one here and the first excess would be zero.
25:47
We would be looking for, uh, index one in this first excess would be zero one.
25:54
So we are in the second row because we started indexing zero. And then we look at the second number.
26:00
The second number would be indexing over X as number one. So we count zero one, two.
26:07
So this one should actually. Oh, return the value six.
26:13
Yup. So there was just a quick demonstration of, uh, you know, what the X's mean
26:19
basically, but what, we'll talk more about indexing with a square record later on. So it was maybe a little bit too early to introduce it here.
26:31
Yeah, Nampa in first, the type automatically from Python. So I'm upon construction.
26:38
So before we had an integer rain, So by default, if we converted it to this array to D this one here, this will be automatically also 64
26:48
integer array because in Python, uh, most of most people, I think nowadays use a 64 bit computer.
26:56
So you also have a 64 bit Python installation or operating system also. So this one should be also.
27:02
So if you use a 64 bit machine, this should also be ready for the 64 bit.
27:07
Oh, Ray into generate I have, or you can con convert it. So, um, it was a reason converting it directly to a float here, but you
27:15
can, um, you could convert it into. Uh, integer 32 array.
27:21
For example, you can do, uh, as type non-pay int 32, and this should
27:26
be a 32 bit interjectory, and you can also convert to other data pipes like from integer to float.
27:32
So you can use this floated data type. You can do a 32, you can also do a 64 and convert into other types,
27:41
and you can do the conversion by using this Ester type command here. Yeah.
27:46
Why is that useful? Uh, it's not necessarily useful here, but if we work in learning, that's the
27:53
other class, I'm teaching statistics four or five three, where we use PI torch. We usually work with 32 bit erase or 10 source and pay torch because,
28:03
um, just work better with 32 bits. That's more efficient. Basically it uses less storage, but one downside is you lose a position.
28:13
So by that, what I mean is if you have, let's say an, a number, like,
28:18
I dunno, let's say one point or one, so it was already too much.
28:27
So if you have this number here, this is a 64 bit float.
28:33
So you get this, uh, precision here. Um, but if you convert it to a, let's say 16 bit array, you
28:45
will lose a lot of position. I mean, it will use less storage. So you will use only 16, but instead of 64, but, but, um,
28:52
you will use a lot of positions. So if I execute that, you should only see one point because it doesn't have the precision to show so many points after the decimal point.
29:02
Yeah. See, so you would have to remove a lot of these so that this would work, but
29:07
if you have more, it gets basically cut because it uses less starch. So it can not represent the same number of precision.
29:14
So in scientific computing, I highly recommend that you use 64.
29:20
Bit integers, however, in deep learning. And there's a lot of randomness and stochasticity and stuff like that.
29:26
So a position doesn't matter that much. So 32 is also fine and some research started working on 16 bit algorithms
29:33
that work well with six in bed, but here in this class, yeah, please use 64 bit integers or 64 bit floats.
29:46
Okay. Somehow my Jupiter notebook is stuttering. Sometimes I click and nothing happens.
29:52
I don't know what's going on here anyways. Um, and dim. So, yeah. And then, uh, this is showing us the number of dimensions.
29:59
So recall we had a two by three. Two by three array.
30:05
So that two dimensions, X is zero and X is one. So this should return a two because we have two dimensions.
30:11
So if we have a big array, lots of numbers, and, um, this command may become handy, especially if we have like a three or four dimensional
30:19
array, it's sometimes hard to see. So this is just a quick way of accessing the number of dimensions.
30:24
However, I actually rarely use that command. I usually almost always use touch shape.
30:31
So that shape is giving you the shape of the array. So you can get two types of information.
30:36
So if you do something like this length of that shape, this would correspond to NDM.
30:41
Basically it would be the same as dim. Um, and here, if you could just do it like this, it gives you more
30:48
information because it tells you how many elements are in each. Dimension or excess.
30:54
So this tells me that two elements in my first dimension. So that two rows, one, two and three rows, sorry, three columns.
31:04
Cause they're three elements in my second dimension. So one, two, three. So I usually almost always use shape.
31:11
And if I actually, um, Neat. The number of dimensions for something I always use for some
31:17
reason, length shape is just a habit. I never really think about ending, but it's there.
31:22
If you need it, it's probably more efficient to call in them than this one. Alright. So yeah, that was, I don't know stuff about introducing non-pay in the next,
31:33
um, Videos, I will make a short cut here. And in the next video, we'll talk about an unpaid array,
31:39
construction and array indexing.

##v17:

0:00
Yeah.
0:01
So in the second video, I want to briefly talk about non-pay
0:04
array, construction, and indexing.
0:07
So array, construction routines are some building routines or functions that I
0:12
find useful for constructing a race.
0:15
And that is sometimes useful.
0:16
If you want a place holder array that you want to fill out with
0:20
certain values later, for example.
0:22
So let's show you what I mean.
0:25
So using the ones function, we will create an array consisting of only the numbers.
0:30
One could look like this and note that this is the, uh, defining the shape.
0:37
And, um, the shape is here three by three.
0:39
I can also make it three by four, and then it will be a three by
0:43
four matrix consisting of once.
0:45
There are many other types of arguments you can provide.
0:48
For example, a D type you can set it to, um, Integer into a 64 or
0:53
interject by default is the same.
0:55
If you have a 64 bit machine.
0:57
So it will be an integer array of ones and so forth.
1:03
And the same is true for the zeros.
1:06
So always remember if you want to find out more information about these functions,
1:11
you can type in them, pay once in the help function so you can call help on this one.
1:17
It will give you some information here.
1:20
Personally, if I'm already in a Jupiter lab notebook or I Python
1:25
interactive shell, I use, should we use the question Mark, which is oops.
1:30
Once it was just, you should be faster and it also gives you the nice color here.
1:34
Usually it's easier to read this way, I think.
1:38
Um, yeah, there's more information here.
1:40
So that shape, for example, the D type.
1:43
But before it will be the float 64.
1:46
And, um, there's also something called odder.
1:50
There's something called a, um, column or row order.
1:53
And it has something to do with affect how things are laid out in memory.
1:59
So C stands for C code.
2:01
So in, um, C code, it's using the row major style, um, in memory.
2:10
And if you choose F.
2:14
We'll do a Fortran style layout and you don't really have to think or
2:17
worry about it and practice it won't change the results or anything.
2:22
If you do have a computation, it's just how the, these are stored in memory.
2:26
And this would make it more efficient.
2:27
If you couple your non-paid code with.
2:29
C code or, and code in certain applications.
2:32
But, uh, in this class you won't have to worry about things like that.
2:35
It's just an additional tool in, uh, software engineers toolbox
2:39
to make non-payers fast with both C and Fortran code anyway.
2:43
So it wasn't really too much detail.
2:45
Alright.
2:47
Yeah.
2:47
Maybe why these betas placeholders are useful.
2:50
I mean, even though let's say you have a, you want an array that consists
2:54
of all the values should be all 99.
2:58
So each value should be 99.
3:00
Uh, how you would create it.
3:01
You can still use the zeros function, for example, uh, you can do zeros.
3:05
Plus 99, for example, it will create your, your array.
3:09
So these, uh, pretty efficient, I would say, uh, ways of
3:13
creating a race correctly.
3:14
Um, I usually use either ones or zeros.
3:16
It doesn't really matter.
3:18
Sometimes it depends on what I'm trying to do.
3:20
I use either or, but we will see examples of that later.
3:23
Just wanted to mention that these exist.
3:25
There's also one called empty, which makes a completely empty array.
3:29
So we will talk more about this data in this class when it's useful, but,
3:32
um, MTS wish we had a bit faster, cause it doesn't fill the array.
3:37
It just creates an empty array.
3:39
Uh, it doesn't fill it with memory, uh, values in the memory, but um, usually in
3:44
all applications, we don't have to matter.
3:46
Uh, we don't have to worry about these little details the way it will just
3:50
put some arbitrary values in here.
3:53
Um, some arbitrary menus from memory.
3:55
So years just coincidence 99, but, um, Could be some, you
4:00
see some arbitrary values.
4:02
So if you use empty, uh, don't pay attention to the extra value is
4:06
just treated as an empty array.
4:07
It's just using some method, the fastest method possible to create an empty
4:11
array, basically without boring, it goes inside, but yet actually that's maybe
4:16
too much information for this class.
4:19
So there's also the I function, which was, I think like a nice
4:22
pan on the identity matrix.
4:24
So this will create an identity matrix.
4:29
Um, a three by three matrix can also create a diagonal matrix consisting
4:36
of the values three or three by three matrix consisting of the values.
4:40
Three let's maybe use a different number here because this would be I, okay.
4:44
Sorry.
4:44
These are the values along the diagonal.
4:46
See, I already forgot what these mean.
4:49
Such would be one, two, three, so we can create agonal matrices like that.
4:56
And this is usually something we rarely have to do.
4:59
What's more useful though, is talking about the, a range function.
5:04
So the age range function will create, um, non-pay array starting at the first
5:10
value and stopping at the second value.
5:13
And this will be a half open interval.
5:15
So this will be the start value and it will be up to the
5:18
10, but not including the 10.
5:19
So let's create this object so you can see it's doing four,
5:23
five, six, seven, eight, nine.
5:25
Can also do this with integers.
5:30
And you can also just omit the stopping position.
5:33
So it will Kia create the values zero.
5:36
So sorry.
5:37
So if you only use one value, it will be actually the stopping position.
5:40
So, um, if you only use one variable, zero one, two, three, four.
5:46
So, and this is similar to using a Python range object, right?
5:52
So.
5:53
Actually nowadays we are nowadays, it's a generator.
5:55
So we have to, if we want to show it how it looks like call us done it.
5:59
So, but this will be a Python list and this will be a non pirate.
6:02
So it's kind of equivalent in that way.
6:05
You can also include a step.
6:08
So this means basically I'm skipping three second venue in this case, it will.
6:14
Um, so for instance, here, it will then, um, skip all the even values.
6:20
Uh, yeah, so one, three, five, seven, nine.
6:23
So it will start at one and then all, um, all the second value, uh, will be
6:29
every second video will be included then.
6:32
Okay.
6:34
And yeah, the, a wrench function is essentially what you know,
6:36
from Python, um, as the range function, but range can't do floats.
6:42
Right?
6:43
Oops.
6:45
So we can't do.
6:47
This ranch, however we could, if we wanted to do it with InterGest.
6:55
So this would be the integer equivalent.
6:59
Yeah.
7:00
One very useful function is the Lin space function.
7:03
So a range.
7:05
Creates numbers in a certain interval.
7:08
And you have to say specify what the interval is by default it's one.
7:13
So it's incrementing it by one.
7:15
I have a, um, maybe it wasn't quite clear here, so we can actually
7:20
increment it by very small values.
7:22
We can increment it by very small interval.
7:25
It's like 0.1 here.
7:27
So in this way, we're using a range.
7:29
We specify the interval range.
7:32
A related function is the Lin space function.
7:35
And this will create an interval with a certain number of values.
7:39
So here we specify the starting point and the ending point.
7:43
And then we say, how many values we want in this interval?
7:46
So again, here we specify the entire wall width, and here we specify the.
7:53
Taught a certain bin width.
7:54
And here we specify the total number of values in that interval.
7:58
So here should be five values.
8:00
So you can see it starts at zero entered one and there
8:03
will be five values in total.
8:04
So zero one, two, sorry, one, two, three, four, five.
8:08
And, um, I can then also let's say create 10 values and so forth.
8:12
Um, and it, I mean, it works with arbitrary.
8:15
In tablets, I can use mental health, let's say five to 15 or something like that.
8:20
It will create values between 10 values between five and 15.
8:26
And yeah, these values are evenly spaced.
8:30
So I could, for example, going here, enter a six and then we will have six
8:34
to 15, which are exactly 10 numbers.
8:36
Right?
8:37
So in this case, they will also, you can easily see, they will be evenly spaced.
8:43
Okay.
8:44
So yeah, what's useful to remember is the age range function for creating
8:49
inter volts with a specified.
8:51
Bin width and the Lin space function for creating a certain number
8:55
of values in a certain interval.
8:57
And then, yeah, also the basic array creation functions
9:01
like, uh, zeros and ones.
9:04
And I'm not asking these things on the exam, by the way, I don't ask
9:06
you to create an array in the exam.
9:08
Uh, at least I don't plan to, um, but it's useful to know that for the
9:14
homework and your project and so forth.
9:16
So let's talk about, uh, re indexing.
9:21
And now I will talk about fancy indexing in a later video.
9:25
So this is just the indexing basics.
9:28
So the very basic way of indexing and non-payers later, I will talk about
9:32
a concept called fancy indexing.
9:35
So far one, I mentioned array, the indexing works similar to a Python list.
9:40
So if I have a Python list, that's called us LST and we put
9:44
the videos on two, three in here.
9:46
If I want to retrieve the first value, I.
9:50
Use the spare records, right?
9:52
So it's the one and this is the video too, and this is the venue three and
9:58
the same way we can do this, an empire race of a one dimensional non-pay rate.
10:02
We use the square brackets to retrieve these numbers.
10:05
Um, What's also useful is the slicing.
10:08
We can also do that in a Python list so we can execute it like
10:11
this and it slices the list.
10:14
Same way we can slice.
10:16
And , um, not that it's the same for Python lists and Ampyra is we
10:21
don't have to write the first index.
10:23
If we started zero.
10:24
If I do something like this, I would include the one because I want
10:29
to start at the second position.
10:31
Have if I want to start at the beginning.
10:33
This one.
10:35
And this one does is exactly the same.
10:40
Um, next.
10:43
If I have a two dimensional array, what's different from Python lists.
10:47
So we have a two dimensional Ray sort of a one dimensional.
10:50
We can use this comma notation.
10:52
So the first position refers to the index or the first dimension.
10:57
And the second one refers to the index over the second dimension.
11:00
It's maybe.
11:01
Easier to see in this figure.
11:03
So with this first value, we are indexing over the first dimension,
11:07
which is the excess zero.
11:08
So we access either the first row or second row.
11:11
And with the second number we index over the second dimension.
11:14
So we go by first row, sorry, first column, second column, third column.
11:20
So in that way, this one would give us the first value because
11:23
it's the first row, first column.
11:26
And.
11:28
If I do this one, for example.
11:30
So let me just execute to show you that this is actually correct.
11:33
So it gives me the one here.
11:34
So this one would give me the number two, because it's still the first row, but
11:40
now it's the second column and so forth.
11:44
Um, we can get the lower right with minus one minus one.
11:48
So this should return the six.
11:50
And this is because minus one means the last element.
11:53
So here, if I do minus one, this would return.
11:57
The number three, because it's the last element.
12:00
So it's the same as typing too.
12:03
However, if we wait, why is it useful to use the minus?
12:05
If we have a very big array, it can be inconvenient to count.
12:08
So we would have on two, three, four, five, six, seven.
12:11
So if we want to have the last value, we don't have to really memorize what
12:14
the length of the race we can just have minus one, it gives us the last value.
12:18
And then again, you can do also the same thing.
12:20
Minus two would be the second last, in this case.
12:23
Uh, this is the last one and this is the second last one.
12:26
So it should return to here and so forth.
12:30
Um, yeah, it's just another example.
12:33
That's returning the four here, cause it's a first role.
12:37
And, um, actually this should return to five.
12:41
I'm not sure why I put the image around here.
12:46
Sorry.
12:47
I was confused.
12:47
So, um, this should return that.
12:52
Two because it's the first row in the second column, I was not
12:55
a one, one would return the five.
12:57
I don't know what I did here anyways.
13:01
Um, we can also return an entire row.
13:05
So, if we omit the second, if we do this or this, it will
13:10
give us the entire first row.
13:12
I think this should also work and we can also type this or three
13:16
ways gives us the same results.
13:19
Um, so this one, uh, the column basically means all, so we want all values.
13:25
So if I do something like this, it will give us all the values in the array.
13:31
And this one, uh, basically too, because, uh, we are omitting the second one.
13:36
So if we admit something, then it automatically means this one here.
13:40
So for example, if I want the first column, I can do the zero here.
13:46
So it's one for one for second column.
13:49
It's two, five, right?
13:52
Going over the second column and so forth.
13:54
If I only want the first row.
13:57
Um, I can, uh, do it like this.
14:02
So it's one, two, three, because we admitted the second one and so forth.
14:06
So we are here just shortcut, um, uh, sorry, some meditation
14:10
entire first column.
14:11
So that's what I did before.
14:13
And we can also slice in the second dimension, like we
14:16
sliced in the first dimension.
14:17
So I can, for example, say I'm the first.
14:23
Two rows and the first column, second column.
14:27
So this would give me the two five, because we go over the first two rows.
14:33
We only have two rows.
14:35
Um, maybe this is not the best example because you only have two rows.
14:40
And then we go out for the first column.
14:41
So let's maybe do the first row and the last two columns so we can,
14:46
um, do one, two, so we can type.
14:52
One three, because the last value is not included.
14:54
It's similar to the age range.
14:56
When we have a range three, it will only give us zero one and two.
15:02
So in this way, the three is not included, so it will end up at two.
15:06
So this gives us, um, for the first, uh, the row and the second position.
15:14
Cause we started indexing zero.
15:15
So we'll give a go here.
15:17
And then the last two columns are these two here.
15:20
This why it's five, six.
15:25
Yeah.
15:25
And that's returning the first element in an upper left corner.
15:29
I'm not sure why I put it here again.
15:31
Um, alright.
15:32
So that was the basic index thing.
15:35
So, um, I recommend you to toy around with us.
15:39
Um, it's not super, um, complicated.
15:41
Once you get the hang of it.
15:42
You just, um, think of this first dimension here.
15:46
As the Rose, if you have a two dimensional array and the second dimension is
15:50
the columns, and then you can specify which rows and columns you want.
15:54
And that's all you need to know about indexing for now.
15:57
But later on, I will show you some tricks called fancy indexing.
16:03
All right.
16:03
In the next video, I'm going to show you some non-paid array,
16:05
math and universal functions.

##v18:

0:00
Yeah.
0:00
After spending so much time on creating a race and indexing
0:04
individual values in an array.
0:06
Let us finally get to a more interesting topic and talk about non-pay array,
0:10
math and universal functions.
0:13
Universal functions.
0:15
That's a, actually not too long, but programmers like to abbreviate things.
0:19
So non-pay, it's called a Ufuk.
0:22
So you Frank as a short form.
0:24
A short form of universal function.
0:26
And, um, a universal function is a really cool concept because it
0:31
makes working with Nampa erase way more efficient and convenient.
0:36
And that is by enabling a concept called vectorization.
0:40
So vectorization means that we are calling, uh, operation a
0:46
mathematical or arithmetic operation on sequence, less like objects.
0:50
So.
0:52
For example, uh, think of it like this.
0:55
We have one operation that we want to execute on all values in an array.
1:00
And, uh, let's say this, um, operation is just mathematical addition.
1:06
We want to add a number to every element in an array.
1:10
So if I want to add the first value to the array, I can call an
1:14
additional function in my program.
1:17
And if I want to add again, the same number to the second
1:19
video, I can do the same thing.
1:21
However, if I want to add the number to the second value, I don't have
1:26
to really wait until the first edition on the first number finishes.
1:30
I can actually do that at the same time, like computing that in parallel,
1:34
because there's no dependency between.
1:37
The elements in the array.
1:38
So in that way, it would be wasteful to use a Python for loop to add
1:43
these numbers, to the array.
1:44
There's a way called vectorization where we can actually call the
1:48
same, same operation on parallel in parallel on the whole vector or array.
1:53
And, um, yeah, I will show you how that works in Nampa.
1:56
It's actually pretty intuitive, but I thought it's kind of
1:59
useful to talk about it.
2:00
So you kind of get an idea of what's happening under the hood in Nampa
2:04
when you're calling certain functions.
2:06
So.
2:08
Um, also after watching this video, I highly recommend you to check
2:12
out the official documentation for the complete list of all the
2:16
Euphonix implemented in non-pay.
2:18
Cause there are more than 60 you funks right now.
2:21
And we will not talk about all of them.
2:24
Actually, we will maybe only talk about a handful of them.
2:27
Um, but it might be useful for you later to scroll through through
2:30
this list and see what's available.
2:32
And you may.
2:34
We need that in a future project.
2:35
For example, of course you don't have to memorize any of that.
2:39
It's more about like, I'm just seeing what's out there and then maybe in
2:43
a future project, you think, okay, I make a, I may have to compute,
2:48
I dunno, the arc 10, for example.
2:50
And then, you know, okay, this actually exists.
2:52
The non peso can use this.
2:53
Ufuk here.
2:55
Um, anyways, so let's get back to, um, Let's get back to some examples here.
3:02
Um, actually to give you an example, Of and non-pay, uh,
3:07
I thought it's maybe easiest to talk about element wise addition.
3:11
So consider this hypothetical weird scenario that we have right
3:16
now, where we have a list of lists or a two dimensional array.
3:21
Let's say this is our two D array implemented in just Python.
3:26
It's a list of lists.
3:27
If we wanted to add the number one to each element.
3:30
So if we wanted to.
3:32
Add one to each element and the array already exists.
3:37
How do we do that?
3:39
So how we can do that is by using followups.
3:42
Right?
3:43
It's actually the only way we can do that, I mean, there may be other way
3:46
waste, but this is like the natural way we would do that in Python.
3:50
So we would iterate first over the lists in this.
3:55
List of lists and then it's rate or by each element in the list
3:58
and then at the number one to it.
4:00
So we would have actually two followups and let's just check if this works.
4:06
Okay.
4:06
This seems to work.
4:07
Actually.
4:08
I just see, I executed this notebook before that.
4:13
That's what makes this so I can see the results before we talk about it.
4:19
Okay.
4:20
So you can see it's successfully incremented each value by.
4:24
One.
4:25
So before we had one, two, three, now we have two, three, four, and so forth.
4:28
However, if you recall from the Cain and lecture, this is a very, very inefficient
4:33
way of incrementing each value by one, because we have two followups, which means
4:38
we have a big hole of in squared, right?
4:41
So this is super inefficient.
4:43
And if you may ask, okay, can we just do this more efficiently?
4:45
Can we just do it as T plus one?
4:48
Does does that one work?
4:50
No, unfortunately in Python this would throw an error.
4:53
So I think there is no, really, no much more efficient way than
4:57
using this followup approach.
5:00
Of course.
5:01
Yeah.
5:01
We can use list comprehensions and you may notice in future notebooks and I
5:05
think also already in the Canaan notebook, I shared last week that I'm a big fan
5:09
of list comprehensions and Python.
5:11
And by the way, I also should not list comprehensions are.
5:15
I would say a little bit weird.
5:17
It's just, I'm writing this thing here in a more compact form, so
5:20
you don't really have to use them.
5:22
Um, you can also just use regular Python followups.
5:26
I don't know.
5:26
I, for some reason they were newly introduced back then maybe half a
5:31
decade ago or something like that.
5:32
And I'm always like, huh, that's a new function Python.
5:34
I'm really excited to use that.
5:36
And then I just used, started using that very extensively.
5:40
Sometimes I just use this comprehensions because I like
5:42
them, but I realized they can be.
5:44
And fusing, so I may actually use or should use more followups.
5:50
Um, and also if you see list comments that don't make sense, just let
5:53
me know on Piazza or something.
5:54
And I am happy to explain it to you just using regular followups in any case.
5:59
So this, uh, this comprehension would actually do the same thing
6:02
as these two nested followups.
6:03
So this would be slightly more efficient.
6:05
You can maybe time this by other time at command and see that
6:09
this is maybe a little bit more efficient, but not by much.
6:13
And you can see it's doing the same thing.
6:15
However, it's not a, so the reason why it's not that much more efficient is, is
6:19
that we still have two followups here.
6:22
Right?
6:22
So it's kind of a little improvement, but still two
6:25
followups at speak off and squared.
6:28
So it's sort of very inefficient approach doing that.
6:31
So in an efficient approach might be using UFA.
6:36
Mmm.
6:37
You folks would do the vectorization that I talked about earlier
6:42
at the start of this video.
6:43
So vectorization means that we can compute the additional, this element of
6:49
the element one at the same time on each value and the num PI uh, certain functions
6:56
are supporting this way, the funk, the, um, Universal function operation.
7:02
And one of them is non-paid dot add.
7:04
So non-paid dot add would add the number one to this array and to be precise,
7:11
this would be called a binary you funk.
7:15
So let me write the cm binary.
7:17
You funk and you know, the reason why it's called binary, you Frank,
7:21
is because this function takes two arguments and binary two values.
7:24
You know, like this is just like a way of calling this a binary.
7:28
You funk.
7:28
There are you funks that are you Neri?
7:31
Um, so there's only one thing that goes into this.
7:35
Here.
7:36
For example, if you think of exponentiation, uh, if you compute
7:39
the power of an element, it's just one, let's say just a square
7:43
root square root would be a union.
7:44
Sorry.
7:45
Um, this would be a urinary function because we only have one value.
7:50
Binary is if we have.
7:52
Two arguments here, any case let's not just get distracted by
7:55
the Trump binary in unitary here.
7:57
So here, this is the additional operation and I'm PI and it will add
8:02
the value one to the whole, um, array.
8:05
So it will do that at the same time.
8:08
So it doesn't have to have a heaven.
8:09
It doesn't have to be a loop basically.
8:12
So let's call it.
8:13
And, um, again, you can try the time at function.
8:17
You will find that this is way much faster than using the followups in Python.
8:25
And awesome.
8:26
Uh, know that there's a concept called operator overloading
8:31
here, operator overloading.
8:32
So what that means is that certain symbols on our keyboard or in the code,
8:39
certain symbols, like plus minus, uh, division multiplication, um, this,
8:45
uh, power off and stuff like that are.
8:49
Overloaded.
8:50
That means if I have to, let's say Python into just like one, well, one plus two,
8:58
then this will perform a Python addition.
9:03
However, if the left side here is an array, this will
9:07
perform the num pay edition.
9:09
So under the hood, this will actually do the non-pay edition here.
9:14
So in that way, Uh, this is called an operator overloading because we
9:17
don't really have to call a nonpaid or at, we don't have to do, uh, this.
9:25
Oops.
9:28
This, we can just call it like this and it will automatically
9:32
use dot add under the hood.
9:34
I have done have a good example of like I'm showing it to you.
9:37
You would have to dig into the source code to see that this is actually the case.
9:41
And which would probably take me five or 10 minutes not to go to
9:44
the code, but I can maybe, uh, if you are really interested in that,
9:49
just post on Piazza, I can just show you the source code in non-pay that
9:52
is doing this operator overloading.
9:54
If you don't trust me that this is actually doing a nonpaid ad.
9:59
Okay.
10:00
So yeah, here I have the non ed.
10:02
Yeah.
10:02
Another common one would be computing, the pole, raising
10:07
each element to the power of two.
10:09
So squaring each element.
10:11
So it's another Ufuk and this would be a unitary UFOs.
10:21
Yeah, like I said, there are many you fangs implemented in non-pay.
10:26
If you go back to the website at the top that I showed you, you can
10:30
check the whole list of your funds.
10:32
Now let's get to a more interesting case of a U funk that
10:37
is involving the reduce method.
10:41
So the reduce operation, what it does, it's applying an
10:46
operation along an excess.
10:48
So by default, that applies to the first excess X is zero.
10:54
And, um, I just introduced to you the PI dot add function.
10:59
So if we combine it with this, uh, reduce Europe's, I moved it around.
11:04
If we combined with us reduce here, what will happen is it
11:07
will compute the column sums.
11:09
So if we have an array, that's step one, step back and just call 'em.
11:15
No, it's actually fine.
11:16
Sorry.
11:17
So let's consider this example.
11:19
So we are computing, the com sums.
11:22
So what happens here is we will roll over the first excess,
11:29
which is the excess zero.
11:32
So what it means that it will, it will use the add function.
11:38
Um, like this, it will roll over.
11:40
Thanks to this, reduce here over this excess.
11:43
It's hard to do it with my mouse, but it will roll over one and
11:47
four at these two numbers and then reduce them to one number.
11:52
So the term reduces maybe at a bit weird.
11:55
Um, but you can think of it as combining numbers, multiple numbers
11:59
into one single number, or we can actually do that also form.
12:03
An arbitrary number of values.
12:05
That's a five, seven, eight here.
12:08
The sort of, I said nine.
12:09
Um, this would also work, so it will still roll over.
12:13
These exits basically saw, reduces.
12:18
Combining two values or more than two values, everything that
12:22
is contained in this excess.
12:24
So in this excess, um, we are, so we are talking about the zero excess.
12:29
It's rolling.
12:31
So what I mean is rolling over the first exes exes zero.
12:40
So.
12:42
It's running over this and then combining these elements.
12:45
So if we wanted to compute the column sums, we can do this.
12:49
And similarly, we can roll over the second excess so we can do
12:53
one, two, three, this would be six.
12:56
Right?
12:57
And, uh, so we would have one plus two plus three, we would.
13:01
Then squish them.
13:02
So reduce them to one thing.
13:05
And I'm on, this would be six and four, five, six.
13:07
This is nine plus six.
13:09
So it should be 15.
13:10
So that will be six and 15 if we execute that one.
13:14
So yeah.
13:15
So the reduced function, it will.
13:19
Tell us about which excess we want to do a certain operation.
13:24
However, this is kind of unnecessarily the boast.
13:27
I'm just explaining the concept behind the reduce.
13:31
And you may have heard about the term map, reduce.
13:36
Or Hadoop Hadoop.
13:37
Is she an open source implementation of map reduce, which is a concept
13:43
that wasn't developed at Google and the MapReduce algorithm.
13:48
It's kind of mapping an operation to multiple compute nodes.
13:52
And then there's at the end one compute node that combines the results that the
13:58
other compute nodes computed basically.
14:01
So, um, Yeah, that is maybe a lot, but you can think of it like this.
14:06
So you can think of it, like you said to the operation, uh, one plus
14:10
four to compute to the computation node or compute node number one.
14:18
And, um, the operation two plus five to the compute node two, and
14:26
then the operation three point.
14:29
Six to the compute, not number three
14:37
and yeah, and this will be then reduced to the individual values.
14:42
So some will be reduced to the five.
14:46
Seven and nine.
14:47
So in that way, we do certain things in parallel.
14:50
We don't have to wait until one plus four is finished until we compute 2.5
14:55
and 3.6 or three plus six and so forth.
14:58
And yeah, and that is one advantage of the youth fund.
15:00
We don't have to wait until this computation finishes
15:03
before we compute this value.
15:05
Of course we are not having a compute node when we compute things.
15:08
And non-paid because it's all.
15:09
Operating a computer.
15:11
However, there's another library called a desk.
15:15
It kind of supports the num PI API also, and this is capable of scaling up
15:20
computations across multiple computers.
15:24
Okay.
15:26
Um, yeah, of course we can do things not conveniently.
15:29
So we don't always have to call ad dot redos, which can,
15:33
can kind of become verbose.
15:35
And like I said, programmers, don't like repository.
15:39
So there's of course a convenience function it's just called the sun.
15:42
So it's actually doing exactly what we've done above.
15:45
So we can call this one to compute the column sums.
15:49
This is equivalent to Aqua.
15:52
First case here.
15:54
So this case, so we didn't write ecstasy zero, but it just the is zero by default.
16:01
So this is, would be equivalent.
16:03
Um, the reason why I'm mentioning this is, um, if we don't provide
16:06
an access argument, it will compute the sum of the whole array.
16:15
Anyways.
16:15
So this will do the same as at reduce with no argument with a
16:20
default argument excess to zero.
16:22
And like I said, it's, I'm rolling over the extra.
16:25
So it's like rolling over this excess, the excess zero, the rows,
16:30
and then compute these venues.
16:31
And here again, it's going with X equals one over the columns.
16:38
So, yeah, like I said, this would compute some of the whole array,
16:42
so he wanted to compute the rows.
16:45
Some, we would do this.
16:55
Yeah.
16:56
And like I mentioned before, there are many other youth funds out there.
16:59
Here.
16:59
I listed some of the most better than once I think.
17:02
So these are the ones we will be probably using a lot in this class.
17:06
So it might be useful to go over these and what they are.
17:10
Um, yeah, I'm just looking through these, I think maybe one word of caution
17:14
regarding our style deviation and variance here is that these bulk computer
17:20
population variance, incentivation not the sample variance and standard deviation.
17:25
Um, yeah.
17:25
As a statistics students, uh, student, this may be a little bit confusing,
17:28
probably because most tools out there compute the sample variance by default.
17:34
So what I mean is this doesn't compute or include pestles correction term.
17:39
So let's maybe take the standard patient as an example to show you what I mean.
17:44
So if we have the standardization, um, let me write this down.
17:48
Square root, right?
17:49
Um, so fraction here.
17:52
One N
17:56
yeah.
17:56
Life writing and coding while speaking is not really my strength.
18:02
Uh, am I forgetting something?
18:04
I think this should be squared, right?
18:09
Let me check
18:13
looks good.
18:13
Right?
18:14
So yeah, this should be the standard deviation, the regular
18:16
one, the population one.
18:18
And let's maybe code one example.
18:21
I don't know some fenders.
18:22
He values here.
18:23
One, two, three, four, and C num PI.
18:28
What that results to should be get 1.1, one, not it's just.
18:36
To see what's going on implement this ourself.
18:38
It's take this, um, function here.
18:41
So what we have is we have to compute the mean first, right?
18:44
So the mean would be some for every value.
18:49
So yeah, I'm using a list comprehension.
18:50
Um, I four I in a, I call it a and then yeah, this would be my mean all
18:59
divided by the length by N so major.
19:03
Makes it more clear.
19:07
So we can run it like this, and now let's compute the values on, yes.
19:13
Sorry.
19:13
I have to maybe stop talking for a second because I can't
19:16
really talk while I'm writing.
19:40
Yes, square root is in Python.
19:43
You can also write it.
19:44
Why in general is over one half, right?
19:49
What am I forgetting here?
19:51
Yeah.
19:55
Some over, oops, something's weird here.
20:05
Alright.
20:05
This is I think, over in.
20:09
All right.
20:10
Yeah, there we go.
20:11
So this gives us the same result and yeah, we can see
20:14
that we didn't have correction.
20:16
If we wanted to have vessels correction.
20:19
I have to do a minus one here.
20:20
Right?
20:21
So this would be Bessel correction.
20:23
And in non-pay there's a paramount are called degrees of freedom or
20:28
sorry, Delta degrees of freedom.
20:30
So it would be D D or F and by default it's set to zero.
20:34
So no data degrees of freedom and here data degrees of freedom
20:38
would be yeah, the Delta.
20:41
So the Delta means difference.
20:43
Um, so we have a difference of one, right?
20:46
So we, cause we have N minus one, we have N minus one degrees of freedom.
20:51
So this basically stands for the minus one here.
20:55
So this would give us Besler correction, Trump.
20:58
Yeah, it was just like a kind of little tangent here.
21:02
I just wanted to explain to you.
21:04
Um, that this variance incentivation, and then PI won't by default
21:08
user, the sample variance.
21:10
And by the way, in machine learning, it doesn't matter.
21:12
Anyway, the only cases where we are using scientification variances for
21:16
normalizing or standardizing variables, and that really doesn't matter whether
21:20
it's Bessel, correction included or not, and so forth, um, sort act sort and
21:26
soft argument arc max, I think we will.
21:28
We'll discuss that later about maybe if you are curious, um, site is just sorting.
21:33
An array of values.
21:35
If we have an array, say I'm paying Murray five, seven, one
21:44
three, something like that.
21:46
We call them pilots, SART eight.
21:49
This will give us the sorted array and ArcSight will give us.
21:55
The indices that we can use to Saudi Arabia.
21:58
So it will give us the index position.
22:00
So this would be an exposition zero one, two and three, and it will then be, um,
22:08
one, uh, and this would be three, right?
22:14
This would be zero.
22:16
And this would be one, sorry, this would have been two.
22:21
Okay.
22:21
Two, three.
22:24
Zero one non-pay arc sort.
22:29
So this gives us basically the two, three zero one, um, the
22:33
sorting on order of the indices.
22:35
So I can actually use that one to sort my rate if I wanted to.
22:40
So.
22:41
This is actually useful if we want to shuffle to a race in
22:44
unison and stuff like that.
22:46
I think I showed you how to shuffle in the rain unison using that
22:50
approach in the Ken and nature.
22:51
But I kind of forgot what I exactly did this kind of a week ago.
22:55
And yeah, I think that's, that's at least how I would do it.
22:59
If I would start to erase newness and I would use the arts art, um, and then
23:03
similarly, uh, Non-paid dot max and our ArcaMax work behave similarly.
23:12
So max would be for finding the highest value in an array.
23:16
So here, for example, this would return six and the, if I do an arc max
23:22
non-paid or arc mix, it will give me the index position of the highest value.
23:26
So zero one, this should be returning a one.
23:29
And then I could get the highest value if I wanted to, by doing the article mix aim.
23:36
Well, I can just save that as index and then do it like this.
23:40
It's usually useful.
23:41
If you have to erase or more, oops.
23:43
Um, to erase a more and you want to look up or they belong together and you
23:48
want to look up the highest value or the value corresponding to the highest value.
23:53
In another way, just spontaneously.
23:55
One case that comes to mind is eigenvalues.
23:57
If you do an icon decomposition, And you'll find one to find, um,
24:02
in an array of eigenvectors the highest, the eigenvector that
24:05
corresponds to the highest eigenvalue.
24:07
So you can use non-pay arc max to find the highest eigenvalue
24:11
in the eigenvalue array.
24:13
And then you can use that index to look up the highest eigenvector in the
24:17
corresponding Ang victory and so forth.
24:20
But yeah, these are I'm rambling on here.
24:22
I noticed I should maybe stop this video cause we will have another video
24:26
about non-paid broadcasting because this will be another very important topic.
24:31
That's actually one of the, I would say most fundamental topics
24:35
in non-pay one of the cool, oops.
24:38
It's jumping around to you.
24:39
And one of the.
24:40
Cool features a non-pay, which will allow us to do certain
24:44
things way more efficiently.
24:45
And this can also cause some confusion in the context of linear algebra.
24:50
So, but yeah, I don't want to take away of this right now.
24:53
We will cover this in the next video.

##v19:

0:00
ja in das video we're going to discuss
0:02
broadcasting widget konzept related to
0:06
victory station war das casting the
0:08
previous action concept victoria station
0:11
and you fonds in dabei broadcasting ist
0:15
just something that happens behind the
0:18
curtain of magic in the background sowie
0:43
geformtes operation what happens
1:09
mein mandant ist das city-kino lineare
1:33
algebra notations in lineare
1:35
vatikanisches skelett effekte wie kostet
1:37
der menschen von manchester city war
1:40
welle welt kommentar operationen lineare
1:45
afa numbers to do you speak simplicity
1:49
jetzt dass man bei dawn of the warrior
1:53
bord wie gesagt die terz hasler in der
1:56
backgroundsängerin regler linie war
2:03
however mit max aber live walk on wien
2:06
entwicklers dass man hier mit markus in
2:09
creating the second base hast du denkst
2:14
einer postprint ja von hier nach review
2:21
of paper planes auszukommen happens ist
2:28
für comeback tour the matrix switch km/h
2:34
in linearer brothers wird oft kostet
2:37
operation hat in computer science and
2:40
learning in maschinen und jetzt kommen
2:43
to record review sexy thing that is
2:48
impossible project hier 11 ingrid video
3:04
sharing konzept so here waiting to der
3:13
menschen railway construction
3:16
contractors metrics
3:20
sowohl hätten ist rettet extreme works
3:22
by creating the simplicity der menschen
3:25
hier recall the way back to execute the
3:37
fine art antiques sondern mit wie die
3:47
fanszene des box everything rektor der
3:53
menschen und metrics and you tube
3:55
broadcasting jetzt wechselt creating the
3:57
simplicity menschen hier in etting goes
4:00
to get you but that's it for this video
4:06
der nächste video world rocketman
4:17
concept cars when you know you want to
4:34
be

##v20:

0:00
Unknown: Yeah, in this fifth video, we are going to talk
0:02
about indexing again. However, unlike the first video where we
0:06
talked about indexing, we will be talking about advanced
0:09
indexing now, so we will introduce some topics like
0:13
memory views and creating memory copies and so forth, which I
0:17
think is very important practice because that avoids all knowing
0:21
about it avoids making mistakes, like accidentally overwriting
0:26
certain array values when it's not intended that you do that.
0:30
So um, yeah, I think this is maybe one of the most important
0:33
videos about NumPy. Because it really helps avoiding unwanted
0:39
bugs and weird behavior in NumPy.
0:42
So yeah, let's get started.
Memory Views
0:45
Yes, so in the previous section, like I'm writing here is one
0:49
aspect of what it is that we created, so called views of
0:52
NumPy arrays in memory. So when we were using the regular the
0:56
basic indexing, we were creating views, not copies of arrays. And
1:02
this can be sometimes a little bit dangerous, because we can
1:06
accidentally overwrite values if we're not aware of it. So
1:09
consider the simple example here, where I have an array, or
1:13
two dimensional array, two rows, three columns. And just for my
1:18
convenience, I am assigning a new variable here I am assigning
1:23
the first row to this first row variable, let me just do this in
1:27
a separate step here. Easier to explain it this way. So first
1:35
row will be the vector, or one dimensional array 123. Now, and
1:41
yeah, so we just assigned this one to this variable. However,
1:45
in contrast to certain other parts of Python and how they
1:49
behave, this created a view onto this array. So what that means
1:53
is that this is actually not its own object, this is just a link
2:00
to this original part in the array. So if I now execute
2:07
executes this row here, which means adding the number 99. to
2:14
everybody in this variable here, what will happen is it will
2:18
overwrite the original value as well. So let's take a look what
2:22
I mean by that, we execute this, execute this now you can see an
2:26
array. So what happens is, first row will be all incremented by
2:33
99, but airy as well. So we not only modified the values in this
2:40
variable here, but we also modify it to the first row in
2:43
the original array. So that is kind of like a hint that what we
2:48
were working with is just a view onto this onto these values in
2:54
memory. It's not like its own object. And not knowing about
2:58
this can be a bit dangerous, because you can see, it may be
3:02
easy to override certain values if we work with, let's say, the
3:06
rain. But in the meantime, for convenience, we create a
3:09
variable which is just on the first row or some other value in
3:12
that array. And we maybe want to increment it as a type of
3:16
counter or something like that, we may do that. And then by
3:20
accident, we forget that this also modifies the original
3:23
array, and then we get into trouble if we want to use the
3:25
original array for some computations later on. On the
3:30
other hand, though, this is also incredibly useful, because it
3:33
really helps us saving memory, so we don't make unnecessary
3:37
copies if we don't need them.
3:41
Um,
3:43
yeah, well, I think explain that later. I hear there's, um,
3:46
before we get to that, there's also a way we can manually
3:49
create a copy when we need it. But let us briefly just stick
3:54
with this example. So I mentioned that if we do use the
4:01
symbol, a simple indexing with an integer here, then this will
4:05
create a memory view and slicing will also create a memory view.
4:09
So we can slice or use a slicing operation. And this will also
4:14
create a memory view that will even happen if we use let's say
4:17
something or let's say let's do it like that. So, this will then
4:23
also create a memory view. So, every time we use a slicing
4:26
operation, similar to using an integer as indexing on the that
4:32
you it will always create a memory view. And the same
4:35
applies to columns here. So column slicing. So here we are
4:40
just using all the rows and we use an integer for the columns.
4:44
So this will also create a memory view. Similarly, if I did
4:47
say one two, the last column stood two to three, this will
4:51
also be a slicing operation now and this will similar to to
4:55
create memory view So yeah, the takeaway here is that slicing
5:02
creates use. However, if we wanted to, we can create copies.
5:09
So that's what I'm demonstrating here. So we can create a copy of
5:14
an array by all values in an array by just calling copy. So
5:18
in this case, I'm creating a copy of the second row, I can
5:22
also just do the first row. But I mean, why not? It's maybe less
5:26
confusing to compare to switching between rows. So now,
5:31
this one will be unmodified. See, so we use copy. So this
5:37
one, first row will be modified. So this will be incremented by
5:40
99, like before, but the original array will be
5:44
unaffected. Now this memory view concept applied to using integer
5:52
indexing commands, and using slicing. However, there's a
Fancy Indexing
5:56
concept in NumPy. It's called fancy indexing, where fancy
6:01
indexing creates copies of an array, not views. And, um, yeah,
6:05
this can be maybe a little bit confusing, because it's not the
6:09
indexing by itself, that creates views. It's just the integer
6:13
indexing and the slicing that creates views. And the fancy
6:16
indexing creates copies. So what is fancy indexing. So fancy
6:23
indexing it's a fancy name for a relatively simple concept. It's
6:28
just using multiple integer integer index indices. So why
6:34
it's called fancy indexing, I think it's because something you
6:37
can't do in Python. So let's say I have a regular Python outside
6:41
NumPy. So if I have a list like that, in Python,
6:46
I can do slicing.
6:49
So I can do, let's say, two to five, that will work. And I can
6:55
just use a simple integer here. But I can't do anything like
7:00
let's say, returning two values that say I want the first value
7:03
and the third value, that doesn't work. So many, I can
7:08
also think there's a slight rotation, this one will also not
7:13
work if I use brackets inside. So in Python and regular Python
7:17
lists, this type of indexing is not supported. So if I want the
7:20
value zero, so the first value at the first position, position
7:25
index zero, and the position index two, which would be the
7:29
third number, this doesn't work. However, NumPy allows us to do
7:33
that. So here, so if this was a NumPy array, let's just do this
7:38
NumPy array, this would actually work now. So this would be
7:44
called fancy indexing, because it's something that
7:50
sorry,
7:52
something that Python would not allow us to do. So this is
7:56
called fancy indexing. So we use this one is, or two numbers,
8:01
it's a list of two numbers, which will be indexing,
8:05
referring to the next zero, and two, so the first and third
8:09
number. And so many, if we have a two dimensional array, we can
8:13
also use the same fancy indexing way for the columns. So we can
8:20
use this month to return the first column and the third
8:23
column. However, note that fancy indexing will return a copy of
Copying
8:30
the array, not a view, which we can demonstrate by again, adding
8:35
our favorite number 99 to the array after fence indexing. So
8:39
here, we will create a copy. So recall, zero and two will be
8:43
returning the first and third column. And you can see they are
8:47
not modified. So I mean, this copy will be modified. But the
8:57
original array won't be modified the origin race that one,
9:01
because fancy indexing creates a copy. And it may be a little bit
9:07
weird why NumPy is doing that. And it's related to efficiency
9:12
reasons. Recall from the introduction to NumPy. In the
9:15
first video, I talked about caching and things like that. So
9:20
if you have a slice, you can easily Yeah, cache some values
9:26
of the array. In memory. It's kind of a efficiency thing. Or
9:30
However, with a fancy indexing this right now no implementation
9:34
to cache these values into a single array. So you can maybe
9:38
think of it like that. If I have an array, where I do a slicing
9:43
like that, I can just take out this one as a view. However, if
9:49
I have a fancy indexing, where I may have the first value in the
9:52
last value, I would have to create a new array right because
9:56
I can't just by slicing take out this one. This doesn't work. I
9:59
would have To go in there and modify this one if I want fancy
10:02
indexing with the first and third element, and this one
10:05
would be a new array because it this is not contained in this
10:09
one here. So in that way, on the fence indexing and the copying
10:14
or making a copy of the array, it's just a consequence of how
10:18
are we work with the array, we don't take out a chunk here, we
10:22
really take out individual values with fancy indexing and
10:25
then patching them together. Of course, I mean, you can do
10:28
something like that, where you have all three columns, which
10:33
will be exactly copying the whole array, basically, right?
10:37
However, I'm still because it's kind of like a syntax thing.
10:43
fence indexing, by default is just behaving differently the
10:46
way it's implemented, it's not auto guessing, it's not going in
10:49
there and saying, Oh, you want column 012. Coincidentally, this
10:55
is all the columns in the array. So I could actually do slicing
10:58
and self defense indexing. So NumPy is not doing that it's
11:01
kind of if it's fancy indexing, it's regarding a sense indexing,
11:05
and perhaps always the same as doing the copy. And in that way,
11:09
the only things you really have to remember is slicing an
11:13
integer based indexing will create memory views. And fancy
11:18
indexing will create copies of the array is the last example
11:24
related to the fancy indexing on that I used above. So above, I
11:30
returned the first two columns.
11:33
Sorry, the first and third column. And here I'm returning
11:36
third and the first column, so I'm kind of reversing it, which
11:39
is another cool thing about fancy indexing. So it allows you
11:44
to shuffle things. So here, I'm shuffling this array here. So I
11:49
can then also, I mean, this is again, a copy, just call it CP,
11:53
and then CP plus 99. And then
12:00
I can just do plus equals the same thing.
12:04
And then if I generate return a rate, it's unaffected, it's
12:07
still creating this copy. The aspect that I wanted to show you
12:12
here is
12:13
that we can rearrange.
12:17
The order of the columns tool with fancy indexing can be
12:21
useful sometimes if we want particular columns, and we want
12:24
to shuffle the order of the columns. Another thing that we
12:29
often do in practice, or at least I will show you some
12:32
examples during the class when we implement machine learning
12:35
algorithms is using Boolean masks. So Boolean masks, yeah,
12:41
just masks of containing true and false values in Python, true
12:46
and false remember, are called Boolean, Boolean. So these are
12:50
the type of data type Boolean. So I think if you do type this,
12:55
it should actually show you bool or something. So it's a boolean
13:00
data type. And we can use masks to find certain values in an
13:05
array, and then use the mask to select values from an array. So
13:09
for example, I can create a mask and say, greater than three
13:14
here. So it will return a mask that has the same shape as this
13:19
original array. But all the values corresponding to which
13:24
are greater than three will have a true value. And all the values
13:28
smaller or equal to three will have a false value. So it will
13:31
look like this. So we'll have false false false, true, true
13:34
true. And then I can actually use that mask to select values.
13:38
So I may have a secondary, I mean, this is a very simple
13:41
example. So I don't have a second array. But you may have a
13:44
corresponding array, and then you can select using this mask.
13:47
So it can use this true true true, false false false mask to
13:50
select actually these values. So it's basically a two step
13:53
process to select individual values from an array. And this
13:58
will also create a copy. It's similar to fancy indexing. It's
14:02
just a special case of fancy indexing. Yeah, what's cool also
14:07
about these masks and selection operations, is that you can
14:12
chain them. So you can use a logical or, or a logical end to
14:17
chain them together. So in this case, I will create a mask that
14:24
will be values greater than three in the array, and the
14:29
values will be divisible by two. So it will be actually arm but
14:33
it's greater than three. So I only would consider these and
14:36
then divisible by two would be then this one, right? And this
14:40
one said return four and six. So this will be of course, just the
14:45
mask and then I can use the mask to select the various four and
14:49
six. And yeah, that is what I wanted to say about fancy
14:54
indexing memory views and memory copies. Yes. Remember, fence
14:59
indexing? returned copies of the array. And integer based
15:03
indexing and slicing will create memory views. Both are useful.
15:07
It's just a matter of knowing which does what and then you
15:11
will be actually fine when you use NumPy in practice

##v21:

0:00
Unknown: So in this video, we are briefly going to cover
0:02
random number generators in NumPy. I will not talk about all
0:06
the different ways we can generate random numbers in
0:08
NumPy. However, the focus is more on understanding random
0:12
number generators and getting an idea why they are useful in
0:16
practice. So maybe let's start with a simple example. So let's
0:21
just draw a random number one random sample. Let's first
0:28
import NumPy. And then there's this random module in NumPy,
0:34
which contains a lot of different functions for drawing
0:36
random numbers. Here's a nice overview. It's an older
0:40
documentation, but I couldn't find the equivalent in a newer
0:43
documentation that has such a nice list of different things.
0:49
For example, using random dot Rand which draw random samples
0:55
from a uniform random uniform distribution, given a certain
0:59
shape, so if we provide two and three here, it will generate a
1:04
two by three dimensional array with random numbers from a
1:08
random uniform distribution. There are also other ones here,
1:14
for example, the random function random random, which contains
1:20
random floats in the open half open interval between zero and
1:23
one, and so forth. So there are many different types of
1:25
functions you can use. Also, you can draw random samples from
1:29
different distributions here. For example, there's one way
1:32
using the random dot RAND function to draw samples from a
1:39
standard normal distribution is also another one, I think, you
1:42
know, right here. Same thing. Also, on your drawing samples
1:47
from a random normal distribution. If you want to
1:49
draw samples from a normal distribution, you don't want to
1:52
rescale it manually, you can just directly use the normal
1:57
function here, which gives you the mean, standard deviation and
2:01
the size thing it should be the second deviation could be the
2:03
variance, but I think this is the standard deviation. Yeah.
2:08
Okay. So let's draw, using a simple approach a random sample
2:15
using rent and, and we will just draw a random sample of 10
2:19
values. Yeah, this is nice. However, as you can see, if I
2:27
execute it, again, these numbers will change, which is useful in
2:30
practice in many applications. But in machine learning, if we
2:34
want to, for example, generate random numbers for shuffling. Or
2:38
if we want to just shuffle an array, and we implement some
2:42
functions to test our implementation. Sometimes we
2:45
want to always get the same results. And that guarantees us
2:49
to have a reproducible code, which means that if we send our
2:53
code and our example execution of that code to another person,
2:58
the other person who would run your code would get exactly the
3:01
same results. And this is often very useful in certain
3:05
situations where you have reviewers to submit the paper
3:09
and they run your code. And ideally, they should get the
3:12
same number as you get right. So if everyone gets different
3:15
numbers every time you execute it, then it's kind of hard to
3:18
tell what's going on. So in order to do that, to guarantee
3:22
that you always get the same results, you can set a random
3:26
seed at the top of your notebook, for example. So this
3:30
is not a numbers totally arbitrary. It's just some
3:33
number. And here now, when I execute this, I get these three
3:39
values. For example, After setting the random seed, if I
3:41
execute it again, it will always be the same three values, right?
3:47
However, if I draw another sample here, this will of
3:52
course, be different. Because it's still a random sample. It's
3:56
just like, if you execute the code over again, it will be the
4:00
same numbers drawn from the random uniform distribution.
4:06
Yes, so why and when is that useful? If you think back of our
4:10
KNN notebook, from lecture three, I showed you how to
4:15
shuffle an array. And that for example, it would be useful to
4:18
set a random number seed. So every time we split the data
4:22
set, it's the same split. So if someone wants to compare or
4:26
method, the can method with a different cane and method, it
4:30
would always generate the same split of the data set if we use
4:33
the same random seed before we shuffle it. Or maybe just to
4:37
give you an intuitive example here to let's consider a simple
4:42
let's say can n implementation. So if we have
4:49
k n KNN
4:52
classifier, some neighbors I think um, Second run, let's just
5:01
say we want to test it. For some reason, we want to implement a
5:05
test. We don't want to test it on some random data and we
5:11
generate labels. Let's say we have 50. examples from Class
5:18
Zero,
5:19
and
5:22
50, an example from class one. So it's just a quick way of
5:27
creating a label array. Random labels, I mean, the labels are
5:30
not random, but we will associate random values to that.
5:35
So we can then for example, write a sample. So NumPy, sorry,
5:42
in second run, our convention is usually we use y for the class
5:46
labels and x for the features. So we have, let's say, 100
5:52
training examples, corresponding to or labeled here, and then two
5:57
features. So this will be random data. And then let's say we can
6:03
fit on can use neighbor classifier
6:14
can fit right, explain. And then let's say we have our scoring
6:21
function was like computing the accuracy. So we get an accuracy
6:26
of 66%. Now if we do that, again, our accuracy goes up to
6:31
68. So this kind of fluctuating, so if we want to stabilize that,
6:37
we would, of course, have to use our random seed, we would insert
6:42
that, usually at the top of our notebook or code. So this would
6:45
be the top of our notebook, it would be going right here,
6:49
before we use the random function. So it will always be
6:53
the same value. No. Now we can, for example, let's say we
6:56
develop a unit test, I'm just showing a very simplified
6:59
example, we can include a test like this. And then this should
7:05
always pass until maybe I change my random number generator, and
7:09
this doesn't work anymore. Or if I draw, so this would work. And
7:12
then I draw another random sample, because the second
7:15
random sample is different. This is not true anymore. So that
7:20
will give us an error. And the same. So this is a very true
7:24
example. But the same issue exists. If we shuffle our data
7:28
set, for example, using the train test, split method in
7:35
psychic learn that I introduced in the K nearest neighbor
7:38
method, notebook. But yeah, let's not get into too much
7:41
detail about k nearest neighbors. This was just an
7:43
example showing you how not random number seed and random
7:49
number generator works. Personally, I always prefer to
7:55
use a random state object in NumPy. This is an object that
8:01
are its own random number generator, because usually when
8:06
I write code, I have different positions where I use
8:10
randomness. And this allows me a little bit more fine grained
8:14
control over where I want my randomness. So if I have a very
8:18
long code example, let's say I want my randomness, because I
8:21
want to collect a sample of something, this random, large
8:26
random sample, and I only want the shuffling of the training
8:30
set to be fixed. But every time let's say I execute my code, I
8:33
want different results. So in that case, I would only set the
8:39
NumPy random seed for the specific part in my code, for
8:44
example, that train test split. So I would, for example, when I
8:49
draw random in the indices to shuffle the race, I would only
8:51
use that there. And this random state allows me to do that. So
8:55
if I use this one, it won't, I will show you maybe here, it
9:00
won't affect anything we do with NumPy random dot random. So if I
9:07
set this random seed here, it will every time still generated
9:13
different numbers. So this one is not affected by this object,
9:19
because if we want to use this random number generator, we
9:22
would have to use it directly. So here we are calling a NumPy
9:27
function. So the function is rent which is contained in the
9:30
NumPy random module. And here we are initializing an object from
9:37
the random state class. And then we are calling a method rent on
9:42
this object. So we are calling it here. So every time I'm
9:46
executing this, I will get the same results. And this is the
9:50
same as doing NumPy random dot
9:55
seats.
9:57
So it's the same thing. You can also see numbers match. However,
10:02
I can have multiple of these objects in particular, I can
10:05
have infinitely many of these. And I can use them at different
10:09
places in my code. So this one gives me almost the same
10:12
results. But then if I call it twice, of course, it will also,
10:16
the second result will be different from the first result,
10:19
right. So this will always give me the same results, but this
10:22
one will be different from this one. Here, this is usually how I
10:28
prefer using a random state in my code. However, there's also a
10:32
new version of that. So this is because I'm old school, back
10:36
then there was only random state. However, nowadays, the
10:39
NumPy community recommends the new random generator. So if you
10:45
like, you can read more about that here. For this class for
10:48
our class, it's not necessary. I'm actually I kind of even
10:53
prefer the old one, because it generates results, similar to
10:59
using a function. However, yeah, I should probably recommend
11:04
using the new random generator, in your projects, if you like. I
11:08
think the improvement is just the way they generate random
11:11
numbers. So the algorithm that is used for generating random
11:14
numbers, in practice for simple applications, you won't notice a
11:17
difference, because in our case, it doesn't really matter how the
11:22
random numbers are generated. For us, it's more important that
11:26
we get consistency, and reproducible code. And this is
11:29
more due to setting a random seed. In any case, this one will
11:37
give different numbers than, let's say calling this one. So
11:41
be aware of that it's not like a one to one mapping like this to
11:45
this one will generate different values. And it's just using a
11:48
different method for generating these pseudo random or random
11:51
numbers. So in code, number generators are not truly random.
11:56
They are usually pseudo random. But yeah, that would be a very
11:59
long video to explain that here at this point, all you need to
12:02
know is there are different methods for generating random
12:05
numbers. It doesn't really matter which one you use,
12:08
especially not for this class. The only thing that matters is
12:11
having a random seed. So for example, if you submit homework
12:15
and you get certain results, and I execute the homework to check
12:18
if your results are correct, for example, it would be great if I
12:21
get the same results as you get right. So in that way, what's
12:24
more important here is setting a random seed. Okay, so but that
12:28
is all I wanted to say about random number generators that
12:31
are not super important, like what type of random number
12:35
generator you use. But using a random seed is important.

##v22:

0:01
Unknown: Yeah, we are finally getting towards the end of the
0:03
NumPy stuff, I'm slowly running out of topics, there are only
0:06
three videos left. However, this is an important one, it's about
0:10
reshaping NumPy arrays. And this is specifically useful if we
0:14
want to get our data into the right shape. This could be for
0:17
example, four. Yeah, reshaping a matrix into a vector, a vector
0:24
and a matrix. So I talked about that briefly. And the
0:28
introduction of this class, and the very first lecture, where I
0:33
talked about m NIST. So let's just assume,
0:37
for simplicity, you have
0:39
this array 28 by 28. So oops.
0:46
And this 28 by 28 array, it's an image basically, so there should
0:50
be different pixel values. But just for simplicity, just
0:53
assume, each one year so this from pixel values, we have this
0:57
28 by 28. image. And on Yes, so the problem with that would be
1:03
that we can't have a 28 by 28 matrix as a feature vector,
1:10
because you learned, classify, since I could learn they can and
1:13
they assume a feature vector, not a matrix for features. So
1:17
what we can do is we can reshape that into
1:22
vector that should be several 84 elements, right? So we 28 times
1:28
28, should be some are 84 elements. So we could reshape
1:33
this one
1:35
into
1:37
784 element vector. So this would be one long vector, and
1:43
then we can give it as a feature vector to Kane. And so each
1:47
training example would be one image, and each training example
1:50
would have 784 features. For example, there's a simpler way
1:56
using this approach. But I will show you briefly why that works.
2:01
And how that works, I don't want to get ahead of myself here. So
2:05
I'm here, let's start with a simple example, where we have a
2:10
very simple toy data set instead of thinking of images. So this
2:14
toy data set is 123456. It's a vector. And we can reshape that
2:19
into
2:22
a two by three matrix here. Note that
2:26
these numbers have to be correct. So this product here
2:30
has to sum up to the number of elements, the length of the
2:32
array, we can't just do some, something like three and three,
2:36
because there are no nine elements on the sixth element.
2:39
So this would throw an error. So you have to get the dimensions,
2:43
right, you can do three and two. And you could even do one, six,
2:48
so this would not this has no two arm brackets. So this would
2:53
be six columns. Before it's just one dimensional vector. Now,
2:57
it's a two dimensional vector,
3:00
or a sorry, our 2d array, it would be a matrix, it would be
3:03
basically a column vector. And we can also do the same way
3:07
making a row vector and so forth.
3:09
But let's get back to this one here.
3:14
So also, if we do the reshape, what happens is that we will
3:18
create a memory view. So it will not create a new array, it will
3:22
create a view on through that array. And it's related to what
3:25
you learned in the previous videos when I talked about using
3:29
slicing operations and indexing for creating memory views. So
3:34
there's a function in NumPy. That also allows us to double
3:38
check that, but I think the NumPy developers state that this
3:41
is not 100% accurate, it's most of the time accurate, but maybe
3:47
wrong. So it's called maisha memory and not just chair
3:51
memory. So but yeah, this is one at least piece of evidence that
3:54
these
3:56
share memory. So the view, the reshaped one and original one.
4:04
Yeah, getting back to the minus one here. So there's one little
4:08
convenience function and pi, which is, I think, pretty handy
4:11
in many applications. It's that it will guess the last Xs, so
4:16
it's kind of related to the degrees of freedom
4:20
when you compute things in statistics, so you can for
4:25
example, if you know you have six elements, and you put it to
4:28
here, you know, this can only be three, right? So there's no way
4:32
this could be a two on there's no way it can be a four, because
4:35
two times four doesn't match up to six, right? So there's only
4:38
one way you can have that and it's the three here. So minus
4:42
one will also create exactly the same one here and minus one,
4:47
two, same way. This will be replaced by as three, because
4:52
there's only one way or one number that we can put here.
4:55
That's the three to get six elements. So you can think of
4:59
this
5:00
As a placeholder, so here, the minus one acts as a placeholder.
5:05
But please don't confuse that with, let's say the minus one in
5:09
indexing. So minus one in indexing, it's not a placeholder
5:13
that's returning the last element. But in reshaping minus
5:17
one is like a placeholder. It's just helping, basically, the
5:21
method to guess what dimension it is.
5:26
Because it would also work if we have multiple dimensions. So if
5:28
we have one to minus one, so the minus one would be again,
5:34
three here, because this one would just be an empty
5:37
dimension. So it is, it works with an arbitrary number of
5:41
dimensions.
5:47
Yeah, and we can also use reshape, I showed you that in
5:50
the very beginning to flatten an array. So if we have an array
5:54
like this, we can call reshape to flatten it. So shape and
5:59
reshape what goes in here is basically the same, it's the
6:02
number of elements on each axis. And if we aren't, so it's a
6:08
comma separated stuff here. So if we only have one value, this
6:12
means only we have one axis. And given that we, for example, here
6:16
have six elements, there's actually only one way we can
6:20
have one axis, and that is by putting a six here. So putting a
6:23
six here, is again, also the same as minus one. However, in
6:27
practice, just typing minus one is way more convenient, because
6:29
then we don't have to memorize
6:32
the number was or the size. So we could also, if we want to
6:36
write some general purpose code that should work on any array.
6:40
We could also write on this.
6:45
Well, I think I'm sorry, it should be NumPy dot print, can
6:50
also write like this, where this should give us remember
6:55
correctly.
6:57
The product of what's in there.
7:01
Try that first. Yeah, so it could also write it like that
7:06
same way. But
7:08
yeah, I think there's no argument against that this is
7:11
just nicer, simpler and faster to write.
7:16
Or I should also say there are different ways to concatenate,
7:20
sorry, to flatten an array. So this is one way to do it. And
7:25
this will create a memory view, there is another function that
7:28
is called flatten, that will also flatten an array. And
7:33
there's also a function that is called rebel.
7:41
That's also flattening array. I think this one will create a
7:45
memory view similar to this one. And this one will create a copy.
7:50
But yeah, that is maybe a good question for you to find out. So
7:54
maybe I will make that a quiz question. So that would be a
7:57
good Yeah, good question for you to find out. I will make this a
8:00
little self assessment quiz for this week as a question to find
8:05
out which one is creating the copy and which one is the memory
8:07
view.
8:10
Last thing about reshaping. Last point is also we can concatenate
8:15
arrays, so we can combine different arrays. So here, I'm
8:19
just sticking along the first axis. So if we have an array
8:25
like that, there's only one axis, right? So this is like
8:28
just a column vector. So we'll just append it, it's basically
8:33
the same. If you think of Python lists, it's the same as doing
8:39
this basically.
8:44
Another way, you can use that as um, if you have two x's. So this
8:51
would be a case where we have two x's. So this is basically
8:56
two dimensional. Now I
9:00
can show it to you here, it's sometimes hard to overlook
9:03
because we, it's not that easy to see that we have that. So we
9:06
have basically
9:08
three columns, or three value, sorry, three, three rows, three
9:14
columns.
9:17
And then we can
9:20
use concatenate with Xs zero to stack along with first x's. So I
9:26
think what it will do is it will just
9:30
stack another one below here. Let me check. Yeah, so sorry,
9:37
that's Yeah, so I Oh, sorry, I already had two. So if I have
9:41
the original one, it will just create the one that I just said
9:44
two rows. And then
9:48
what we can also do is we can stick a stick by the columns. So
9:52
this will be basically similar to this one. But to be honest, I
9:57
always forget which one is doing which
10:00
So in practice, I would just always
10:03
double check and make sure this is actually doing what I want to
10:07
do. So I have not two rows and three columns. So instead of
10:11
having the basically one row and three columns, now I have two
10:14
rows and three columns. And here I have
10:18
six columns basically.
10:20
So yeah, what I always tend to forget these things as well. So
10:24
usually in practice, I always double check things just to make
10:27
sure it's doing what I wanted to do. All right, next we will talk
10:31
about NumPy comparison operators and masks. We briefly talked
10:35
about masks before, but they are another cool set of features
10:39
that are useful in connection with comparison operators and
10:42
masks which I will cover in the next video.

##v23:

0:00
Unknown: Yes, in NumPy comparison operators and
0:02
selection masks are so much fun. Let's do another video on it. So
0:06
previously, we already introduced masks and comparison
0:09
operators. However, I wanted to show you some additional tricks
0:13
that you can use when working with these.
0:17
So here, let's start with a simple example, we have a NumPy
0:21
array 1234, just to keep it simple. And then we can define
0:24
the masks mask for selecting values. And this mask will be a
0:29
Boolean array.
0:31
So that's something we've seen before. And it will be true for
0:35
all values in the array are all positions in the array that
0:39
match the condition that the values are bigger than two. So
0:43
the mask array will always be the same size or shape as the
0:47
original array. However, the true values are the positions
0:51
where this condition is true. And the other ones are the one
0:55
where the condition is false. And then we can use the mask to
0:59
select values from the array.
1:02
Again, when we have the mask in Python, there's a way for
1:07
example that we can come up, the notion of basically,
1:12
the number one and the rule of true are the same thing. So if
1:15
we convert
1:17
true value to an integer, it will be
1:21
a one and false is zero. And this is why we can do things
1:26
like um, let's say on some condition,
1:32
one equals two. So if this condition is true, I can say if
1:36
condition.
1:39
Print, this is true. So this is something that works in Python,
1:46
it's kind of like the same thing as writing
1:51
this, however, in Python, it's best practice to just avoid
1:55
equals true. So and similarly, you can
1:59
write this one if not condition. So this might mean basically,
2:04
um, this whole thing means the same as if condition equals
2:11
false.
2:19
Yeah, and the same thing would apply if we put a zero here. So
2:22
if
2:24
not conditionals will also print this statement, because this is
2:28
the same as false.
2:32
And
2:34
this is the same as
2:37
true. So because of the relationship between Boolean
2:41
values and integer values one and zero, we can actually count
2:45
the elements
2:47
in an array that match a certain condition using the sum
2:50
operator. So here, for example, we have all the values that are
2:57
greater than two. So in this case, that to true values. And
3:00
if we have a large array, of course, we cannot really look at
3:03
it and count it by hand, it would be too much work, right.
3:05
So we can use the sum operator, and this will give us on the sum
3:10
of this mask here. So this way, it will count the values that
3:15
are true.
3:16
And then similarly, you can get the values that are negative by
3:22
just the shape minus the sum, right? So this would be better
3:26
use words, faults, then a more values.
3:32
Yeah.
3:38
We could also technically arm just to go back because I just
3:41
see the next example here, we could technically also, if we
3:45
wanted to compute the number of negative values, we can also use
3:47
the NumPy invert function. So again, if we have the mask,
3:54
this will give us the
3:57
Actually, let's extend this to
4:00
more values, then this will
4:05
return a three for the positive matches.
4:10
And then if I want to the negative matches, which are a
4:13
number the number two now because we have two faults, and
4:16
three truths, if I want to count the number of falses, I can also
4:20
use NumPy invert, where NumPy invert, will
4:27
invert these values here and so false will become true and true
4:30
when it comes faults can see that here. So I can count the
4:33
number of negative values by calling invert first. Why is
4:39
that useful?
4:43
So let's assume we have a case where we have our array here,
4:50
and we want these values to be let's say, the value one and
4:55
this value Mary's to be the value zero like binarized in
4:59
this array
5:00
So we could do is we can say on
5:04
all the values in the array
5:07
that are greater than two.
5:10
And we, let's call that, let's do the mask first, actually,
5:14
let's do mask one, all the various greater than two and a
5:17
mask two for all the values that are not greater than two, which
5:21
would be then mask, invert, I'm
5:25
sorry, NumPy, invert mask one, and then we can set the values
5:31
to one, and
5:37
oops.
5:43
Okay, so this should be than a binarized array. So we binarized
5:47
our array here.
5:51
Um, yeah, hold on, this can be a lot of typing work, right, so we
5:54
would have to type that all out. a simpler way doing that is
5:58
using the NumPy. Where function. So NumPy, where function works
6:03
as follows. It's basically doing what we've done here above, it
6:07
checks the condition. And for all the values where the
6:10
condition is true, it assigns this value, the first value, and
6:14
for all the values where the condition is false, it will
6:17
assign this value. So this one will also then do the same
6:20
binarization.
6:22
And I just see another way
6:25
of doing the NumPy invert is just using this tilde symbol,
6:30
it's the same as
6:32
doing invert. So
6:35
if we have our mask, say mask one, I call NumPy. Invert,
6:44
this is the same, much of it works actually outside
6:48
the indexing, this, this would be the same as doing mask. One,
6:52
it does, actually. So this is just a operator overloading of
6:56
the NumPy invert function here. So we can also do this one
7:00
instead of this one. But personally, I just use NumPy,
7:04
where if I only have two decisions here, if I have
7:08
something like greater than two, I want to assign it to one,
7:11
otherwise zero, I would just use NumPy. Where, because there's
7:14
just one line of code where this one, or this one is a little bit
7:18
more involved.
7:20
Okay, so um, with that,
7:23
operator, there are also other types of operators that come in
7:27
handy in practice. So the common ones, I think these are actually
7:31
all of them. And, or XOR, and not, so this is the NOT
7:37
operator.
7:40
And what's nice in NumPy, is we can combine them. So we can say
7:43
for example, all the values are that are greater than three, or
7:48
are smaller than two. So let's extend that.
7:52
So
7:54
it will then select all the values greater than three, which
7:57
are four and five, right? And smaller than two, it's only the
8:02
month. So what it should return is 145. Right?
8:05
So it's not sorry, it's just a mask. But if we would apply the
8:08
mask, it would be 145.
8:12
And then we can also do the same thing with a knot. So that in
8:15
that case would be the
8:18
would be the two and three.
8:23
And then yeah, we can also use for example, the end operator so
8:27
we can say all the values. Let's say they are that are greater
8:32
than three and divisible by two. So that would be only the number
8:37
four
8:38
should when return the number four Oh, sorry. She wanted to
8:41
use the end here.
8:44
and so forth. And yeah, this is all the nice things about
8:48
Boolean masks and selection masks and operators, logical
8:52
operators and NumPy. I think this is super cool and helpful
8:56
in practice if we manipulate data sets and so forth, and we
8:59
will be using that quite a lot later when we are implementing
9:02
certain decision tree rules and the homeworks and stuff like
9:06
that. But yeah, that is all I wanted to say here. In the next
9:09
video we will be covering some basic linear algebra concepts
9:12
and NumPy

##v24:

0:00
So in this video, I want to talk about some linear algebra basics
0:04
in context of NumPy. We won't be using linear algebra heavily in
0:09
this class, except of course, for basics like vector dot
0:12
products and matrix multiplication and so forth.
0:15
Because like I discussed previously, it allows us to
0:18
implement code more efficiently and more concisely if we use
0:21
basic linear algebra notation. So here, we can think of a one
0:26
dimensional array as a row vector. Actually, we can also
0:33
define it as follows. So that would be in a row vector, I
0:38
always confuse the terms row vector and column vector. So row
0:42
vector is naturally a vector consists of one row, and has
0:47
multiple elements. And similarly, we can create a
0:51
column vector by reshaping this run, right, so then we will have
0:56
a one column and multiple elements. So would be column
1:01
vector representation. Also, just notice, I don't even need
1:04
these square brackets here.
1:08
And also, instead of
1:10
reshaping the vector here, and self reshaping our row vector,
1:19
like this, instead of reshaping this, we can also just add a new
1:24
axis using NP or NumPy, new x's, which will do the same thing.
1:32
Um, I think row Victor is something weird here right now.
1:36
Yeah, see, I redefined it here above. So let's go back, okay,
1:43
row vector, and then this one is basically the same as the
1:46
reshaping it. Okay, um, instead of using NumPy, new Xs to create
1:53
an additional access, so this is adding an additional access, I
1:56
can actually do this two times, then we will get a 3d tensor.
2:05
And I could also, if I wanted to edit at the beginning, and so
2:10
forth. So we'll create additional dimensions with this
2:14
new axis here, and you can see now it's a one by three by one
2:21
by one tensor. That's a rank, three tensor, four dimensional
2:26
tensor. And,
2:30
yeah, instead of using new x's, we can
2:33
also just use none. So it doesn't really matter which one
2:37
you use, it's just maybe a matter of preference, you can
2:39
also use none, it will also create the new x's. So just to
2:45
keep a long story short, are the three approaches I just showed
2:47
you, the reshape the NumPy new axis and the nun, all basically
2:52
creating the same result that we added an additional axis if we
2:55
wanted to. Yeah, that was just how we get one vector into
3:02
another vector dimension. Here we have some basic linear
3:07
algebra notation, or matrix multiplication. So recall, when
3:11
we do matrix multiplication, it's actually just like
3:15
computing multiple dot products. So I would first compute the dot
3:18
product between the vector 123 and 123. Here, the output would
3:23
be 14. And then for the bottom here, I have 456, and 123. So
3:28
there's another dot product, and the result is 32. So matrix
3:32
multiplication would be NumPy. One way would be using metal. So
3:37
we can do that. Oops, matrix defines. Now it's defined, we
3:43
can also do matrix. So also, I should note, this is actually
3:48
not a linear algebra operation, right? Because in linear
3:50
algebra, we can't multiply matrices and vectors. However,
3:55
we can think of the column vector as a matrix, right, we
3:58
can think of it as a three by one dimensional matrix. So
4:05
because we can just multiply a matrix in the vector linear
4:07
algebra, but we can multiply two matrices. So this kind of vector
4:11
really is a matrix, it's a three by one matrix. So this is why
4:16
this is a better operation. However, NumPy is a little bit
4:19
more forgiving than, let's say regular linear algebra. Because
4:23
Also remember, we were able to do crazy things like adding just
4:27
a value to it. Whereas in real linear algebra, we would have to
4:33
do it something like this, let's say reshape two by three. So
4:39
this would be a regular correct linear algebra thing to do. We
4:42
add two matrices, but we can just add a value to a matrix.
4:47
However, linear algebra is a bit more forgiving, because this
4:50
allows us to write certain certain things more efficiently
4:52
and briefly
4:54
and similarly.
4:56
Met NumPy allows us with met model With metamodel to also
5:01
multiply a row vector, which doesn't have the correct
5:06
dimensions, right, it's not three by one, it's just three
5:09
elements. But this one would still work. And but not that the
5:14
output dimension is different here, right here. So here we
5:17
have to buy one vector. So let's double check, it should be two
5:23
by one, right? Because we multiply on two and three. So
5:30
two times three dimensional matrix, multiplied with three by
5:36
one dimensional matrix, dot u.
5:40
This should give us oops,
5:45
two by one, right, because we have the two and two here, at
5:50
two and the one here, here, this one will give us just a one
5:56
dimensional output, because this is also one dimension, so you
5:59
have to be a bit careful what the shape of your output is, it
6:02
depends on whether this is a three by one vector, or just a
6:06
one dimensional vector array.
6:09
Okay, um,
6:11
yeah, this is a dot product is simple dot product dot product
6:14
between two vectors. And, in NumPy, we can also use NumPy dot
6:21
dot. And actually, everyone, me included recommends using the
6:25
dot function over metamod, because in most machines, it's
6:30
implemented more efficiently. So NumPy dot will give you the same
6:37
results. And also, like I mentioned before, it's actually
6:40
used to be more convenient to just use row vector at loops
6:48
through vector to do it.
6:50
So this is a shortcut, an operator overloading for NumPy,
6:53
dot dot. And of course, we can also do that with our matrix. So
6:57
this would be the matrix multiplication. But this one,
7:01
again, is using dot for the matrix multiplication. So note,
7:05
that dot really does the same thing as MathML. Where dot means
7:10
either dot product, if it's two vectors, or matrix
7:13
multiplication, if it's a matrix and a vector or two matrices.
7:21
Yeah, here, just different combinations. And so it's really
7:24
just the same as metal. Just out of curiosity, one should be
7:29
faster than the other, but it I think, depends on the machine.
7:34
But yeah, in practice, people usually recommend the dot, not
7:37
the metal. You can see actually, in this case, metal is faster.
7:46
But yeah, that I would say remains the recommended approach
7:52
speed is kind of the same actually. Now, the transport
7:59
operation, transport really is just like an linear algebra, the
8:03
transpose, it's transposing a matrix, right, can think of it
8:07
as flipping this over.
8:11
Yeah, it's been a lot of time making this figure I hope you
8:13
like it.
8:15
Okay, so then we have now two matrices where the dimensions
8:18
match. So before our matrix was two by three, the transpose of
8:23
the matrix matrix would be then three by two. If we multiply
8:26
those two, this would give us three by three, sorry, two by
8:32
two matrix. So again, we compute matrix multiplication by
8:38
thinking of dot products. So we compute the dot product, 123123,
8:42
put it up here, and then 123 with a second column 456. Let's
8:47
go here. And then 456, this vector here, multiplied by this
8:51
vector, it goes here. And then this vector times this vector
8:54
goes here. Because transport is quite verbose, so again, also
9:00
can use action just dot here, because transport is quite
9:03
verbose. We can also just use the dot t here.
9:07
It's the same as transports, but shorter.
9:15
Yeah, and also know that the matrix, so NumPy, has a matrix
9:20
type, which is a special type form two dimensional arrays,
9:26
however, it's written restricted to
9:31
two dimensions, because it's a matrix.
9:33
So in that case, no one really uses matrix and NumPy. As far as
9:37
I know, everyone uses just a normal multi dimensional arrays.
9:40
So you don't really have to pay attention to this one. But I'm
9:44
just saying it exists. But if you encountered I would say,
9:48
don't use it because no one in the NumPy community uses it and
9:52
it would be
9:52
kind of weird to use it. It's very
9:58
unusual to his matrix. The Matrix type in NumPy. However,
10:03
if you would use the matrix type and NumPy, you could use the
10:06
star or asterisk operator to do the matrix multiplication
10:10
instead of the Add symbol. Maybe back in the day it was useful
10:13
because typing NumPy dot.is tedious. But nowadays, we can
10:17
just type on, like this ad symbol. So that way it's also
10:23
simple. Whoops, we need to transpose of course. Okay.
10:29
Lastly, Sai pi. There's not much I want to say about Sai pi at
10:33
that point, because Sai pi really is a cool library. It has
10:39
a lot of additional functionality that is not
10:41
implemented in NumPy. Lots of scientific algorithms, but they
10:44
are very special purpose algorithms. So we would discuss
10:48
these particular algorithms, you know, if we need them. So if we
10:51
need a particular algorithm, I will just tell you about it and
10:54
explain you what it does. But yeah, as you can see, sy pi
10:58
really is like a collection of many, many different things.
11:00
There are some additional linear algebra things, Fourier
11:03
transforms, interpolation, optimization submodules, some
11:08
for integration as statistics, one with additional functions,
11:13
and so forth.
11:15
Of course, it's all based on NumPy. But you can think of it
11:18
as an extension to
11:19
NumPy
11:20
and lots of specialized stuff here. You don't have to memorize
11:23
any of that if we need that.
11:25
I will tell you,
11:27
all right. Okay, so that's all I wanted to say about NumPy and
11:32
also Sai pi at this point. We will be finishing up the
11:37
scientific computing in Python lecture lecture four in the next
11:42
video by discussing matplotlib the plotting library

##v25:

0:00
Finally, we're getting to the end of lecture four, it was a
0:03
very long lecture. But I hope these concepts about NumPy were
0:07
useful to you. And in the future, we will be using NumPy
0:11
in the homework for implementing machine learning algorithms. So
0:14
it's kind of important that you get the hang of it and kind of
0:17
get familiar with NumPy at this point. So lastly, the last topic
0:22
for lecture four is matplotlib, which is the plotting library
0:26
for Python. Nowadays, there are many different types of plotting
0:29
libraries for Python. However, matplotlib remains the most
0:33
widely used one. And it's also my favorite one matplotlib, the
0:38
name it's kind of inspired by Metalab. So it follows syntax
0:42
that is very similar to MATLAB. Some people like it, some people
0:46
don't like it. I personally hated MATLAB, MATLAB, when I had
0:50
to use it in grad school. However, I really like
0:53
matplotlib.
0:54
So it's,
0:57
even though you may not be a big fan of MATLAB, matplotlib is, I
1:01
think, still relatively easy to use. And it plugs in nicely with
1:06
NumPy as well. So yeah, let's get started with that. So I
1:11
should say on that, personally, also, I don't memorize all the
1:16
different special ways you can do things in MATLAB matplotlib,
1:19
because my problem is a rather low level library. That means
1:24
you cannot do a lot of things with matplotlib. But not all of
1:27
the things are very intuitive. So sometimes you have to look
1:32
things up. Because high level of customization means a high level
1:36
of options. And, of course, you can't just memorize all the
1:40
options if you don't use it every day. So personally, also,
1:43
when I happen to use matplotlib, or plotting for a while and want
1:46
to do something very specialized, I just go to the
1:49
gallery and see what I actually want to do. Um, let's say I want
1:54
to do a stem plot, I would just go here, and then look it up.
1:58
Okay, this is the stem function again. So that way, I sometimes
2:02
just click here, look at the example, copy and paste the
2:07
example and change the data that I want to plot in this example
2:11
with my data. And yeah, then I'm usually ready to go. There are
2:15
more detailed tutorials also available on matplotlib.org. So
2:19
here's a website that has different tutorials that are
2:23
more explanatory. So here's a good image tutorial, working
2:27
with images and matplotlib, and stuff like that.
2:30
So I recommend the tutorials like
2:32
for a general explanation of how things work in matplotlib. But
2:38
once you get the hang of it, usually, it's sufficient just
2:43
have to refer to the gallery to look up what type of clutter you
2:47
need, for example, grouped bar chart with labels, you look
2:50
here, how they have done that, you copy that and replace the
2:53
data with your data. And then you're usually good to go. But
2:58
of course, it's still useful to know some basics of matplotlib,
3:02
which I'm covering here. So first of all, when you work with
3:11
matplotlib, and Jupiter lab or Jupiter notebooks, you can use
3:15
this inline function here to show plots in line that means
3:19
there will be shown in the notebook. I think there are
3:22
alternative ways you can also do this, it's like a different type
3:26
of way of showing the plots in the Jupiter notebook. However,
3:30
personally, I have problems with that on certain computers. So I
3:34
kind of recommend the old way of doing it using matplotlib in
3:38
line. So this magic command will just show the plots in the
3:43
notebook itself instead of opening a new bin window with a
3:46
plot when we created. Um Yes, so let's get started and make a
3:54
simple plot here. Here I just have the linspace. Remember,
4:00
this one will be creating 100 values in the range between zero
4:04
and 10. And we are just plotting these values against NumPy dot
4:10
sine, which is the sine function. So this would be the
4:17
simplest type of plot just using PLT dot plot. So pierotti is the
4:22
plotting library within matplotlib. So matplotlib.pi
4:26
plot, we import it as purity because matplotlib has other
4:30
stuff inside like certain color maps and other things. So this
4:35
is just a sub module with the plotting functions. simplest one
4:40
is dot plot. So we just make this simple plot. We can then
4:46
date so if we made the plot we can then adjust the axis ranges.
4:51
For example, let's say I want it between two and eight. I can
4:56
specify it like so I can set the limits for the x And similarly,
5:00
I can set the limits for the y axis. For example, between zero
5:04
and point seven, five, then I can add x axis label and the y
5:10
axis label like so. And then I'm just showing the plot. So like
5:13
here in Jupiter notebook, you don't necessarily have to do it,
5:17
you can also do a semicolon here, that usually also does it,
5:21
I mean, this would also work, but you get this ugly thing
5:24
here, object returned by the plot function, so you can
5:27
suppress it by the semicolon. But I recommend just using PLT
5:32
dot show, because in some notebooks or some computers,
5:37
this approach doesn't work so well, for some reason. Okay. So
5:43
here, that's the plot with our exes limitations. Next, we're
5:50
doing the same thing. Now we're doing two curves, though a sine
5:53
curve and a cosine curve. So we can have multiple graphs in one
5:59
figure. So that's how we do it, we just make the first figure
6:03
and then we make the second finger. And you can see by
6:07
default, it also uses different colors, then, we can also
6:10
manually change the color. So for example, I can make this red
6:15
if I wanted to,
6:17
and so forth.
6:23
And another thing I did here is I added a label. So the label is
6:27
cool, because then you can add a legend. And you can also say
6:31
where you wanted lower left, upper left, upper, right, lower
6:36
right, and so forth. And the legend kind of provides labels
6:40
here in in the legend, here in the lower left corner, which is
6:46
also useful. I should say, you can actually also make a
6:53
scatterplot. So there's a scatter plot function, and
6:56
matplotlib. But you could actually also use the plot
6:59
function to make a scatter plot, just by changing the line style,
7:03
for example, can do this, you can choose no line style, oops,
7:11
I think I have to actually add the marker. So yeah, so I have
7:16
to add the map marker. So this way, by the way, by disabling
7:20
the line, and adding a marker, we can also make a scatterplot.
7:24
Some a little bit hard to see here, because
7:26
we have so many values, that's true, maybe just 10 values. So
7:32
you can more easily see that we can make a scatterplot this way
7:35
now. However, for convenience, there's also a scatter function
7:40
in matplotlib. So here, we can also use the scatter function,
7:46
which is kind of like like I said before doing this.
7:55
But of course, it's just less to type.
7:58
So we can use the scatter function here.
8:01
Bar plots, bar plots are probably one of the most
8:04
frequently used plots in certain contexts. Yeah, bar plots are
8:11
probably the most, or one of the most widely used types of plots
8:14
in certain fields. So how that works is we provide a list of,
8:20
well, let's start it this way, we have three values, or let's
8:23
use some other values in like 5785 810, or something like
8:28
that. So these will be the values that we actually are
8:33
interested in plotting. So we have a five, eight, and 10. And
8:38
then we provide, we provide
8:42
the position where we want them on the axis
8:44
like 01, and two, and that's all we need, we have the position on
8:51
the x axis where these bars should be. And then we have the
8:55
means. So the means are just some values that I want to show
8:57
here. You can also say these our Y values. And also just In
9:03
addition, I have the standard deviation shown here as aerobar.
9:06
So y arrow, that's just some robot here. Of course, there are
9:13
different other options where we can adjust the width of the box
9:17
and also rearrange them on the x axis here and stuff like that.
9:24
But I don't want to go into too much detail. If you need that. I
9:26
would say check out the library or sorry, the gallery. They
9:32
probably have some good example for doing that. For example, you
9:35
can see these are small bars, also cleaning up the x axis
9:39
here. So if you need that, I would always say consult the
9:44
gallery.
9:46
Next histograms.
9:51
So yeah, this is just a simple example of a histogram
9:56
where we have data from a random normal distribution 1000 values
10:02
with mean zero and standard deviation 20 M. So let me show
10:08
you another example. So if we just plot this, it will choose,
10:12
if we don't provide an R parameter here, it will choose
10:14
the bins for us. So you can see, these bins are different from
10:18
these, I can manually specify my bin size here. So here, I'm
10:23
specifying it to be with five. So you have a bin size of, or
10:30
bin width of five. So it's also in practice, sometimes useful to
10:38
use alpha, which makes plots transparent. And that's
10:41
especially useful if we want to plot two histograms, for
10:44
example. So if we make them transparent, you can see both
10:49
without them hiding each other. For example, if I set it to
10:54
zero, oops, sorry, I should set it to one one should be totally
10:59
visible. So here with one, you can see that they're hiding each
11:02
other. And then it's hard to tell what's going on in the blue
11:05
histogram in this region here. So practices may be useful to
11:10
set the transparency to, let's say, 50% or something.
11:21
Yeah, we can also make subplots,
11:24
that means making a panel
11:26
of figure with multiple sub panels. So as shown here, so
11:30
here we have multiple sub panels.
11:33
And I'm plotting the same values here for each.
11:39
just for simplicity. Um,
11:43
how that works is we create subplots using the subplots
11:47
function. And we'll create a figure and axes where the axes
11:52
are these different axes. And we define it to be two rows
11:57
and three columns.
11:59
So then we can iterate. So let me maybe show you the dimension
12:03
of the axes. So it's two by three. So we can iterate over
12:08
the rows to iterate over the rows and then over the columns.
12:13
And the column would be one individual X's here. We could
12:18
technically also make it simpler we can say for sub panel in x is
12:28
and then we can do say a flatten right on rebel we wrote about in
12:34
the NumPy lecture, and then we don't need to have a nested for
12:38
loop here. So we can just do sub
12:43
panel.
12:46
And also what's nice notice here, let me go back restore the
12:51
old version. What's also nice is we have a shell x and a shell y
12:59
option here. So it's not showing the redundant labels on the
13:03
other ones if these are actually showing the same data ranges. So
13:07
it means share the x axis and share the y axis if I set it to
13:10
false for example, it would duplicate this year which is in
13:15
certain context redundant so yeah, by doing that, oops, we
13:20
can avoid this redundancy.
13:27
Yeah, and I like Like I mentioned before, we can also
13:30
choose different colors for example here choosing orange you
13:33
can type blue, there are many many different types of colors I
13:37
think if you want to know or what all the colors would have
13:42
to go here or search for it and should be. So these are the
13:48
standard colors shorthands but you can also use I think, hex
13:53
values for colors and so forth. So there are many different ways
13:56
you can put in color so RGB on strings and so forth. So there
14:03
are many many different ways you can input colors maybe checking
14:08
out the tutorial may not be a bad idea at some point. However
14:13
for default purposes in this class you don't of course have
14:16
to know all of this and also with addition to choosing colors
14:23
you can also choose different markers so we can different
14:26
whoops marker styles, I think a pentagon structure circle should
14:33
be a square with triangles and so forth. So also again if you
14:40
search for maka style
14:44
loops.
14:49
You can probably also find somewhere here know, all the
14:54
different market stats. Usually I would search that in my
14:59
browser And then usually you find a website that shows you
15:04
exactly what you want. So yeah, you have the different styles.
15:11
Um, yeah. Lastly, just how we save plots.
15:16
Personally, I recommend using
15:19
PDFs for
15:20
plots. It's a vector graphic format, if you use PNG, it will
15:25
be a bitmap format.
15:26
And, um,
15:30
yeah, let me just do that, and then show you how the files look
15:33
like that we can have it. So we plotted something, and then we
15:38
save the plot. And then we show the plot. If we do it this way,
15:43
it won't actually save the plot, because this one will clear the
15:46
figure, and then the plot is gone in memory. So we've
15:49
actually have to have the plots show after we saved it
15:55
actually saved Let's save that to my desktop.
15:59
Oops.
16:03
And this one, too.
16:07
Let's call this version two, and this version one.
16:13
And
16:16
this will be the default. So now I have three files on my
16:19
desktop. Let me make this a little bit wider here. So if I
16:23
go to the first one, this is the default version. It's 14
16:29
kilobytes. Second one is at four kilobytes. And the third one is
16:38
only eight kilobytes. So the PDF is clearly smaller. Because it's
16:43
a vector graphic and a vector graphic is, you can think of it
16:46
as an instruction for making a plot rather than storing each
16:50
individual pixel value. And that is nice. If we want to have
16:54
higher resolutions, for example, in if you prepare a latech
16:57
report, it's nicer to have these vector graphics. Another type of
17:02
vector graphics, by the way is I'm using PS, or SVG files.
17:10
Apps, yeah, but
17:12
the main point is, it will have smaller file sizes, especially
17:16
for very complicated nausori for your plots, where you have a lot
17:21
of pixel values. And then also, you can later on always exported
17:28
as PNG file. So let's take a look at the first one. That's
17:31
the default one. So if I zoom in here, hope it's visible on on in
17:37
this recording with a resolution, but you will see it
17:40
becomes super pixelated here, right? So is this the default
17:43
one. Now if I open the second one with DPI 300, which is much
17:50
larger, though, in file size, you can zoom in more before you
17:55
see that it gets pixelated.
17:59
However, if I go to my PDF one
18:03
means zoom in.
18:06
So you will see it remains sharp No matter how much I zoom in,
18:10
right? Because it's not really storing individual pixel values,
18:14
it's storing instructions for creating these lines. So you can
18:18
see, maybe it's easier, you can just see what the numbers here
18:22
can see how sharp they look, compared to my other ones. So
18:27
this is the 300 DPI version. If I go here, you can see how
18:32
pixelated it becomes. And what's nice, of course, is you can
18:36
whatever tool you use by default on your computer, this is the
18:40
PDF version, you can always
18:43
export it as a PNG file.
18:47
So I can choose PNG and then I can also choose my resolution
18:50
later on. So I don't really have to do that. When I create the
18:54
port, I can do that later. If I need a PNG file. For example, if
18:57
we want to embed our figure in a web page and web browsers on I
19:01
don't think they can load PDFs within a website. So you maybe
19:04
have to have a PNG file or JPEG file, so you can create that
19:08
later. Okay, but that is all I wanted to say about matplotlib
19:16
at this point, because I don't want to make a whole two hour
19:19
video in matplotlib here. So here are some additional
19:22
resources for matplotlib. So I usually recommend, just be
19:28
familiar with the basics of how matplotlib works. And then if
19:32
you need to make a plot that is a little bit more complicated.
19:34
Just go to the gallery and check out the gallery for examples.
19:38
Okay with that, finally, we are done with the scientific
19:41
computing and Python lecture and next lecture we will talk about
19:45
machine learning with
19:46
scikit learn

##v26:

0:00
Unknown: Yeah, hi, everyone, I hope you had a good week and
0:02
work through all the NumPy material, because this week we
0:05
will be using it, we will be talking about data processing
0:08
and machine learning with scikit. Learn, I think it's
0:11
really useful to do the coding stuff like this one, in this
0:15
lecture upfront, because later in this class, we will be using
0:18
it extensively. Because I really think it's useful to learn about
0:22
concepts of machine learning, but then also try them out in
0:24
practice and use them and explore them using code
0:27
examples. Yeah, and with that, there's not that much to say for
0:30
this lecture, except you maybe saw that I uploaded homework
0:34
one, the first real big homework, which will be testing
0:37
you on stuff that we covered in earlier lectures, like
0:41
supervised learning concepts, and so forth. But it will also
0:44
test you on the code examples and NumPy and ask you to tinker
0:48
around with the K nearest neighbor algorithm to get a
0:50
better feel for how NumPy and psychic learn work.
0:55
And with that, um, yeah, there's not much to say, watch the
0:57
videos, do the homework, do the self assessment quiz afterwards,
1:01
and stuff like that. And while you're doing that, please also
1:05
don't forget to have some fun once in a while, cause Yeah, my
1:09
favorite season of the year just started fall, I really like fall
1:12
in Wisconsin, because it's finally getting colder, and the
1:15
leaves begin to change. It's really beautiful outside and
1:18
stuff like that. And I was also super excited. Last weekend, I
1:21
already went to a pumpkin patch, you can see I got some pumpkins
1:24
that need to be carved. So with that, let me get started with
1:27
the lecture. So I can then get back to my little pumpkins and
1:30
get them carved for Halloween. So yeah, let's get started.
1:36
Yeah, we already arrived in part three of the computational
1:40
foundations lectures. Just to tell you what this lecture will
1:44
be about. Here's a list of the topics we're going to cover. So
1:47
first of all, we are going to talk about reading in a data set
1:51
from a tabular text file, such as a comma separated value file,
1:55
or CSV file, which is the most common file format for
1:59
traditional machine learning artists. Then we will talk about
2:03
basic data handling like getting the data into shape for a while
2:06
machine learning algorithms and training procedures.
2:11
And then we will be talking about psychic learn machine
2:15
learning with scikit learn. But before we do, so, I wanted to
2:18
briefly recap on Python classes on object oriented programming.
2:24
I gave you some exercises to prepare yourself for Python, or
2:27
just understanding Python better. However, I think it's
2:30
just useful to briefly recap what object oriented programming
2:34
is and what Python classes are. Because the second learning API
2:38
for machine learning is heavily inspired, or is heavily relying
2:42
on object oriented programming. So in order to understand how
2:46
scikit learn works, it's kind of necessary to understand object
2:49
oriented programming.
2:52
Then, we will talk about preparing training data using
2:55
the psychic learn transformer API. And we will also talk about
2:59
defining psychic learn pipelines, which help us
3:02
chaining different operations such as, you know, preparing the
3:06
data set like data sets, scaling, normalization, and then
3:10
also dimensionality reduction,
3:13
classifier itself and so forth. So we can define a very
3:17
efficient training pipeline that connects many aspects of the
3:21
machine learning workflow together to make things more
3:24
convenient, which is one of the big strengths of Cyclone.
3:29
Also, I should mention this lecture, I decided to make
3:32
slides again. So in the last two lectures, we talked about things
3:36
using Jupiter lab. And I like Jupiter lab a lot, but I think
3:40
it's sometimes easier to explain things if I can use my pen here
3:44
or my pencil. So with this pencil here, I can just better
3:47
annotate certain code examples. So what I did for these slides
3:51
was I made screenshots from the Jupiter lab, or Jupiter
3:54
notebook, and I will annotate them in this lecture. However,
3:59
the whole code notebook is also available on GitHub. I just
4:02
uploaded it to GitHub. And I also added some explanations
4:06
there. So you can consider this this document as an optional
4:11
course notes or lecture notes document for this lecture.
4:20
Yeah, just a brief recap, where are we in this course right now.
4:23
So we
4:25
had an introduction to machine learning covered cane and were
4:29
already showed you a little bit on how scikit learn works. Then
4:33
we set up a Python learned about NumPy and scientific computing.
4:37
And now we are going to we are going to cover data processing
4:42
machine learning with scikit learn and then in the next
4:45
lecture, we will get back to core machine learning concepts
4:48
like decision trees and sambal methods and model evolution
4:52
after what So while this is the last part in the computational
4:57
foundation lecture series,
5:00
Doesn't mean that we won't be using code in the future.
5:03
However, you can consider this as like the foundation that you
5:09
can use to play around with concepts we introduce later on.
5:15
And you will also be implementing certain things as
5:18
part of the homework. So in that way, the computation foundations
5:21
are really like the tools that we will need to explore the
5:24
concepts we cover later in this class.
5:29
Here is again, the overview of the typical machine learning
5:32
workflow that we covered in lecture one, I don't want to go
5:35
over the details again, because that's what we did in lecture
5:38
one. However, I wanted to highlight the main aspects of
5:43
this pipeline. So there's the pre processing part, where we
5:48
read in a data set, split into training and test data and so
5:52
forth. And then we get to the learning part where we use this
5:55
data set
5:57
the training data set to fit a model using a machine learning
6:00
algorithm. And then later, we evaluate the model using the
6:04
test data set, and then we can use it in the real world for
6:06
making predictions. So in this note, in this lecture here, we
6:11
will be talking about the pre processing steps. And we will
6:15
also get to the learning steps. Some of it will also include the
6:19
evaluation. However, we will talk much more about that in
6:22
future lectures. So here, we will briefly talk about
6:26
evaluation. And when we discuss pipelines, and later on, we will
6:31
go back into more detail about model evolution. So the main
6:34
focus here is on pre processing and learning.
6:38
And for that, let's start at the very beginning reading in a data
6:41
set from a tabular text file, such as a CSV file. So for this
6:46
lecture, I'm using the iris data set quite heavily. Again, I know
6:50
not everyone is very excited about working with Iris flowers,
6:54
because the data set is a little bit old and not super exciting.
6:58
However, I think there's an advantage of using a simple data
7:01
set. And it's that it gets out of the way, we don't have to
7:04
spend much time thinking about the data set and can think about
7:08
the methods here, because this lecture really is more about
7:12
understanding the computational tools rather than getting
7:16
distracted by discussions of the data set. So just briefly recap
7:20
what the data set looks like. So we have 115
7:25
flowers.
7:27
And we have three classes, Iris setosa, Iris, versicolor, and
7:30
virginica. There are 50 flowers of
7:34
50 flowers from each class in this dataset. So we have 50
7:39
flowers from each and the features, we have the
7:43
measurements, so the length and width of the
7:48
CEPA, flowers and
7:52
petal flower. So we have sepal,
7:56
length
7:59
sepal
8:02
with
8:04
petal length,
8:07
and petal
8:10
width. So we have 150 times four dimensional
8:16
data set here, in plus, of course the plus the labels, and
8:23
labels.
8:25
Personally, before I start working with the data set in
8:28
Python before reading it in, I usually always use my terminal
8:32
to explore the data set, or at least take a look at how the
8:36
first lines have a data set look like and also the last line that
8:40
can be useful, just to get an overview of the data set before
8:44
we use any sophisticated tool. So we know which tools we have
8:47
to use, for example, which options we have to choose. And
8:50
this is super fast.
8:53
And you also note that in we can do that directly in Jupiter lab.
8:57
So we can use this exclamation point parameter to execute
9:02
terminal commands. So this is a terminal or shell command.
9:11
And this head on command, or it's actually a little program
9:15
in Unix and Linux. For terminal, what it does, it's
9:20
returning the first 10 lines of a data set of a file. so here we
9:25
can get an idea of how the data set looks like. So if we take a
9:28
brief look at it, we can see there is one row that specifies
9:33
the column names and so column names are known.
9:40
It's not always the case that we have the names of the columns
9:43
included in the data set. Some data sets don't include the
9:45
first row with the column names.
9:48
We can also see we have an ID column, which just enumerates
9:52
the different training examples here. And the last column is
9:57
this label column in a string
10:02
format. And then we can see there are four columns with your
10:08
floats or decimal numbers, real numbers.
10:14
And they're all comma separated, it's also important to know. So
10:18
there's something we can learn by just doing this quick head
10:21
command here to just get an idea of how the data is that look
10:24
like looks like usually also in practice, um, use tail, which
10:27
gives me the last 10 lines of the data set.
10:32
Then my favorite library for reading in the data set is
10:35
pandas. pandas is short for
10:39
Pennell, data's. So I, I've never seen that written down
10:42
somewhere. But I heard or listened to a podcast by with,
10:47
with Kenny, he was it was an interview where the podcaster
10:51
interviewed Wes McKinney, who was the original developer of
10:54
pandas. And he mentioned that he named a tool after this acronym,
10:59
panel data is okay, so pandas is a data frame library. So it
11:05
allows us to work with data frames,
11:09
can think of a data frame as a more sophisticated version of
11:13
NumPy array. But I bet that most of you have worked with R. So
11:17
you can really think of this data frame like our data frame.
11:21
But you can also have mixed column types and so forth.
11:26
So now let's use the data frame library pandas to read in our
11:30
data set into a data frame. So on this one function, when we
11:35
import pandas that is called read CSV, and the read CSV is a
11:39
very powerful function that can read in a CSV file super fast,
11:42
it's evolved over many years, and people made it really fast.
11:46
It's one of the, I would say best ways of reading in a data
11:49
set.
11:51
So here, because our file has a very nice form, so it has,
11:57
this is the form where we don't really have to pay attention to
12:01
anything like function arguments, we can just call
12:06
the function with a filename, and it will read it into a data
12:09
frame. So this will be our data frame object.
12:17
And the data frame object also has a head method, which is kind
12:20
of similar to the head method of our terminal command here are
12:25
four terminal, however, it's only giving us the first five
12:28
lines, there's a way you can get the first 10 lines, but it
12:31
doesn't really matter, we really just care about the first few
12:34
lines. So we can see that the data set is read incorrectly, if
12:38
you omit this part, if you just call the F, it will show you the
12:41
whole data file, which is also okay. However, sometimes the
12:45
data set is very large. And we don't have to see the whole
12:48
file. Here, it's more about seeing whether everything looks
12:52
okay, if it was correctly passing the file. Otherwise, if
12:56
it's not, okay, we'll get some weird output here.
12:59
So we can see here, everything went correctly, because we have
13:02
all the column names read incorrectly. And then we can
13:06
also see, it gave in an additional index column, we
13:09
could have specified here, an argument index and a score,
13:15
call. And we could have used the first index or column index for
13:20
that, and then it would have used
13:23
this ID column
13:25
for these IDs, however, doesn't really matter here. We don't
13:29
really care about the ID here. Um, yeah, and that I mean, that
13:33
looks great. So everything was written correctly. And you can
13:36
also see, you can have mixed types. So here, for example,
13:40
these are integers. I mean, you can call some functions to check
13:45
the types. However, we can already see that there's no
13:47
decimal point. So this is an integer. This is a float type,
13:51
can see the decimal point. And here, this would be an object or
13:55
string object type. And yeah, there's also similar to NumPy, a
13:59
dot shape attribute. So if you use the dot shape attribute, you
14:03
can see the dimensions of the data frame. So in this case,
14:07
it's 150 times six dimensional data frame, like 150 rows and
14:13
six columns.
14:16
Yeah, like I mentioned, there are many options for the read
14:19
CSV function.
14:21
You don't have to memorize any of that. However, if you have
14:24
problems with reading in a data set, it's worth exploring those.
14:27
For example, there's the Sep here, which stands for
14:32
separator. In our case, we are working with comma separated
14:36
files. So we put a comma here, whoops, a comma here, but it
14:39
could also be for example, slash t if we work with tip separated
14:44
files, and so forth. So it really depends on how our data
14:47
file is formatted.
14:49
Then we have, for example, in parameter for the header, so
14:54
it's automatically set to infer so it kind of guesses whether we
14:57
have a column header or not.
15:00
If that doesn't work, for example, if we have a file that
15:04
doesn't have this role here, so if this is not included, and we
15:08
have problems with reading in the data set, we can try, for
15:11
example, setting this to none. And then should usually always
15:15
work the index column I mentioned, we can set it to zero
15:18
in this case, because we have action index column, we can also
15:22
just set it to none. So it will create an index. starting at
15:26
zero, it doesn't really matter in most applications, if we
15:29
aware what the index is, but in this notebook, for example, in
15:33
this lecture, we are not going to work with index i think. So
15:38
there's also use call, which means use columns, specifying
15:42
which columns to use. I will show you an example where on how
15:47
to use that in the next slide. And there are other ones like
15:51
I'm skipping rows, how many rows to skip, and the number of rows
15:55
to read in total, and many, many other options.
16:00
Yes, so what do we do if we have a very large data set that is
16:03
exceeding our computer memory. So here's an example code that I
16:07
wrote, like, five years ago or something when I was working on
16:11
very large molecular property files. So I had a data file that
16:15
had like 100 million
16:19
lines of
16:22
molecule data. And it was like molecular
16:28
properties, like the weight of the molecule, the number of
16:31
hydrogen acceptors, and donors and things like that. And I had
16:35
a very small computer memory, I think I had a MacBook Air with
16:39
like, four gigabytes of RAM,
16:43
which was not really much. So in that way, I had like, challenges
16:47
on working with a data file, especially if I wanted to work
16:49
on my laptop. So there's a way for example, you can use the
16:55
arguments and pandas to work with large data sets.
16:59
later on. Next slide, I will show you some other ways. But
17:02
this was one way of doing it. And also note that notice there
17:05
is some iterator function that is also useful for that, I
17:08
think. So. But the way I was doing it here was
17:13
I was defining a chunk size. And the chunk size was how many
17:16
lines of the data frame or the CSV file I wanted to read in one
17:21
iteration.
17:23
And then also to make the file smaller, or the data frame
17:26
smaller, I only read in those columns that I cared about. So
17:30
that was, for example, the molecule ID. So the name of the
17:33
molecule, the partial charge of the molecule, whether it's
17:39
currently purchasable or not. So drugs, no means basically,
17:42
whether you could buy it or not.
17:44
How many hydrogen bonds except us and how many hydrogen bond
17:48
donors.
17:51
So I think Originally, the file had like 10, or more columns,
17:55
but I don't.
17:58
So I think that the file headlines, at least 10 or 15
18:02
columns, but I didn't need all of the columns. So I only
18:05
specified five I cared about. And then I was also getting the
18:09
total number of lines in the CSV file, how many rows it had. So
18:15
it was a little bit too, too large to open it, let's say in
18:18
Excel and count or let's say, flip to the last row.
18:23
So there's a way you can do that in Python, you can just iterate
18:27
over the lines like using, like opening a file, and then using
18:30
read lines or just iterating over the files, line by line.
18:35
However, that took also a long time if you have 100 million
18:38
rows. So what I did is I was just using this terminal
18:41
command, which is b c minus L. So sorry, WC means l. w means.
18:50
So WC means word count. And minus l means lion. So this will
18:55
just give you the number of lines. And then of course, the
18:57
filename, which was, let's say, my, oops, my large dot CSV file.
19:07
I could have executed that in pandas directly using this
19:11
exclamation mark thing. However, the problem with that would be
19:14
it would be printing the number of lines, however, I wanted them
19:18
assigned to a variable. So I was using this sub process module,
19:22
which is spawning off a Python sub process in, let's say, the
19:27
terminal using check output. So that is executing a terminal
19:30
command, which I put here. And then I was just splitting the
19:35
output, getting the first menu, which is basically the number of
19:38
lines. So here I was just using this terminal command to get the
19:42
number of lines very efficiently. And then I was
19:45
iteratively. Reading the CSV file, I was actually reading
19:51
this into an SQL light table but doesn't really matter here. On
19:54
let's say, I was just iteratively, processing the CSV
19:58
and in each iteration, I was doing something
20:00
With a data frame in the data with the data and data frame, so
20:03
in each iteration, I only read 100,000 lines, all of the 100
20:08
million lines. How did I do that? So I had this range
20:13
iterator here, I set it to start at zero. And then going up to n
20:21
lines, where in lines would be something around 100 million.
20:25
And I had an increment size of step size of chunk size, which
20:30
was 100,000. So if I would execute that, that would mean,
20:34
for example, the first one would give me a zero, so I equals
20:38
zero. And then in the next iteration would be i equals
20:41
999,999. And it should be i equals 199,999, and so forth.
20:53
And then in each iteration, I was specifying, of course, the
20:57
filename I cared about. I didn't care about the header.
21:02
And then I had the number of rows. So here, this is how many
21:05
rows in total, it should read. This was 100,000. And how many
21:11
rows it should skip. So that means in the first iteration, it
21:14
would read the first 100,000 rows, and the second iteration,
21:18
it would skip the first 100,000 rows.
21:22
Because in the second iteration, we would start here, and then
21:27
it would read the next 100,000, rows, and so forth. And I could
21:30
do that and to process the whole data file, even though the data
21:33
frame didn't fit in my memory. So I'm showing you that here,
21:37
because it's just a nice illustration of how we can use
21:41
these pandas function arguments for the read CSV function.
21:46
However, there are also more efficient ways of using a pandas
21:50
like deep pandas like API for large data sets that don't
21:55
necessarily fit into computer memory or are very slow to
21:59
process. So one of them is the modern project,
22:05
which is following the second pandas API very closely. So it's
22:11
kind of like a drop in replacement of pandas. So you
22:14
can just import modern pandas SPD. Instead of importing pandas
22:20
directly, of course, you have to install modern first. But if you
22:24
do that, the API will be the same as the pandas API. And last
22:29
time I checked, they cover 90% of the pandas API. And they
22:33
basically implement functions to make
22:36
pandas run faster on multiple processes. And I think also a
22:40
lot of quad processing, which means it does not all have the
22:43
data into memory, at the same time, and so forth. So this
22:47
would be one option. Another nice option is dask, which is a
22:51
very established project in the
22:55
in the Python, scientific computing community. And it also
22:59
really has a lot of options. For example, if we use a cluster of
23:02
multiple computers can set the number of workers the number of
23:05
threads per worker, how much memory to use, and stuff like
23:08
that. So three out so cool tool. If you work on a cluster, let's
23:13
say chpc cluster or something like that at all University,
23:16
then you can use dask or modern, both have a very similar API,
23:22
because they follow try to follow the pandas API.
23:27
Yeah, this was all I wanted to say at this point about reading
23:30
in data. So it was mainly about the pandas read CSV function
23:34
when we have a data set in a CSV file format. However, in
23:37
practice, you may encounter other file formats. But I don't
23:41
want to discuss all the possible file formats right now. There
23:45
would be a very long list of file formats and possible ways
23:48
files are formatted. So but I hope that this was just a very
23:52
basic introduction that gets you pretty far because nowadays, for
23:56
example, if you look at kaggle, and stuff like that, most data
23:59
files are in a CSV format. In the next lecture, we will then
24:03
discuss how we can process the data set further, once we have
24:08
it in a panda's data frame.


##v27:

0:00
Unknown: All right, so in the previous video, we talked about reading in a data set from a tabular text file. In
0:07
particular, we worked with a CSV file, so in a CSV file, and we worked to be more specific with our Iris data set. So we read an
0:16
iris data set from a CSV file, a comma separated value file into a panda's
0:23
data frame. Now in this video, we are going to talk about how we can get the
0:31
data into the right shape for machine learning with scikit learn. So we will be talking about basic data handling, using
0:37
pandas and NumPy, to get the data into the right format for machine learning. So but before we do that, let me briefly recap
Python Function
0:48
a basic concept about Python functions because it will become handy when we talk about transforming values in a panda's
0:55
data frame. So here, that is a very simple Python function, which I not very creatively called some funk. And it takes
1:04
one input argument x, and it converts this input argument into a string and concatenate it with
1:11
a fixed string, hello world. So if our input is an integer here, the integer 123, this one
1:18
gets converted to a string. So it will go
1:24
get converted to a string. So string 123, which is basically
1:30
123 is a string. And this gets concatenated with hello world, so it will yield this whole string here. And that is just an
1:38
outline of how Python function works. We have this depth here, a colon, and then a return statement. And there
1:45
could be an arbitrary number of lines, but before the return statement, for example. Now, there's also a concept called
Regular Function vs Lambda Function
1:52
lambda functions. And lambda functions is just more like a concept for lazy people
1:57
who want to save some lines of code and write a function a little bit more quickly if it's a very short function like this
2:04
function, which is super short. And if some people find this is too much work, you can do this on
2:09
one line. So you can use lambda here, lambda, in a way, acts
2:15
similarly to the definition here. So here, we are setting up this function. With one argument, you can have an
2:22
arbitrary number of arguments similar, like you can have an arbitrary number of arguments here.
2:28
And then it's exactly like this part here. So there's nothing really useful or cool about lambda functions
2:36
is just slightly shorter way of writing a function, and then you can call the function in it does the same thing, basically. So I'm showing you
2:46
this because it's very commonly used in the context of certain pandas on data transformations on columns. So recall in the
2:56
previous lecture, what we had as we read in the panda's data frame, from the iris CSV file, so we read in the iris Iris data
3:06
into a panda's data frame. So the iris data set looked like this, that we had 150 rows. So here, I'm only showing the first
3:13
five months. And we had some ID column, which is actually not important. And then we had the features. So usually, we use a
3:22
design matrix X for the features to talk about features, the feature values, and then we had our class labeled. So this is,
3:29
we usually call it y. These are class labels.
3:34
Traditionally, psychic learn and other libraries didn't handle
3:39
string variables as class labels. Well, So traditionally was better to convert them to integers. So for example,
3:47
converting setosa Iris setosa to the integer zero, Iris verzi,
3:53
color to the integer one is beginning to the integer two, and so forth. So there is no ordering here. It's just like,
4:01
I'm just using a number instead of a string. But the order really doesn't matter whether it was zero, or one or two, if we
4:07
do it consistently, it's just the way that many algorithms when they were developed, they work with integer class labels
4:15
not worth String class labels. And second learn nowadays, it
4:20
supports String class labels and most functions. So you don't really have to do this conversion. It's doing the
4:26
conversion internally. However, there are many tools that you may be using in your career later on. Where the developers
4:34
on don't have this transformation and don't particularly develop the code for handling string data. So
4:41
that way, I usually First of all, I would recommend reading the documentation on how they kind of recommend what how the
4:48
data set look looks like or should look like. But then usually most of the time, it's safer to just use integer class
4:56
labels just like more tools are compatible with that. So you are more, while you're less likely to bump into errors if you
5:04
convert your class tables into integers. So here I will briefly explain how we do that. And that goes also
5:11
back to the lambda function cost when, sometimes when people do that you often see a lambda function in connection with an
5:20
apply method called on a panda's data frame column. So, what we are going to do now
5:27
is we are going to convert this, this column here, the species column into an integer column.
5:35
So, we are referring to this species column, which is a string
5:40
column. And then we call apply, which will iterate over the
5:46
column. So it will not sorry, if I go back, let me use the color
5:52
green No. So it will start here, and then do a certain operation on this one. And then we'll go to the next do the same
6:00
operation or call the same function here and so forth. So it's just a way of calling a function all these values here.
Column-based Data Processing via Lambda Functions and ".apply"
6:06
It's not particularly fast, it's kind of almost like a for loop on on a column. Anyways, it's just very convenient to do that,
6:14
because it can be done in one line of code. So this is also why people prefer using a lambda function in this context.
6:22
However, you could also define the function by yourself, you can define a function icon, I don't know something like
6:28
transform or something. Then put some x here and then
6:34
let's say if x equals zero, then return
6:43
Oh, sorry, if x shouldn't so you want to do it the other way around. If x equals Iris,
6:49
Certosa then return
6:55
zero, else return the original x and so basically no otherwise do
7:03
nothing. We could also have else ifs in between, so this function
7:11
will only convert Iris setosa to zero and for Iris virginica, and Iris versicolor will not do anything. Or we could expand
7:19
this function, we could say, if x equals Iris atossa, return zero, else if x equals Iris versicolor, return one, else
7:30
return two. And then we will handle all the three cases. But this is just a simple illustration. So instead of
7:38
writing this function, and then putting a transform into the play method here, we can also define that all in one line
7:45
using this lambda here, there's not a really big advantage of using lambda functions, just small, concise, maybe some
7:52
people are too lazy to define the function here. And that way, you can do everything on one line.
7:58
Um, yeah, and also kind of its signals. So we're not giving this function
8:03
name, it signals that we will, in our code, never use the function again. So it's like a throwaway function. Whereas if
8:09
we define a function, we can have may indicate that we want to reuse the function at all, no, it's just more code and
8:15
maybe maybe a little bit more harder to read, because someone may be curious, is this function useful later on, and maybe not.
8:24
And then people would have to read the whole code and stuff like that, with the lambda function, maybe just a little bit shorter. But in any case, so what this function will be doing
8:33
is just converting Iris atossa labeled from the previous column
8:39
here, so when we have asuntos, that will convert these to zero, so this will become
8:45
zero. So we have all these set to zero, which you can
8:51
see here. This is one way we can convert string enabled to a traditional label. However, in practice, I don't think this is
8:59
a great idea to do that. I'm just trying to explain how lambda in the CLI work. So in case in the future, you bump
9:05
into them. If you read some code examples, and you see someone uses apply and lambda you know how it works and how you can
9:11
understand what it does. However, in practice for the class label transformation, I would rather recommend on using
Column-based Data Processing via Dictionaries and ".map"
9:18
mapping dictionary. So here it's also kind of easier to understand or read what's going on if someone asks you later,
9:26
what is the class APR zero, then you can say this is Iris setosa because it is mapped to zero so that way you also can see more
9:34
easily what the transformation is later on if you if someone asks you about it. So here, what I'm doing now is I'm defining a
9:41
mapping dictionary. I suppose I should be mapped to zero, Iris versicolor should be mapped to one and Iris virginica should be
9:50
mapped to two. However, it doesn't really matter. I could also choose a different order I could say 210 or whatever I
9:58
like. However, also A good practice is to use integer labels starting at zero. So we
10:04
would use 012. If we have more label class labels like three, and so forth, until we get all the possible class labels that
10:13
say with an possible class labeled, so you would have them all enumerated like that without gaps. Because there's also, I
10:21
mean, depends on the software. But there are also some limitations that are most tools assume that class labels start
10:27
at zero. And in that way, it's easier to avoid bugs or unwanted
10:33
behavior by encoding the class tables starting at zero and consecutively not skipping any integer. And also, if you have a
10:41
binary class table, in many textbooks, for example,
10:47
I'm teaching that in my other class, the perceptron algorithm. There are algorithms that were traditionally developed, in case
10:54
all the mathematics work for class labels minus one and one if you have a binary classification problem. However,
10:59
modern tools or modern implementations for consistency, also kind of expect you to have integer labels like zero and one
11:08
instead of minus one and one. So usually, again, I recommend reading the documentation
11:13
of a tool that you are using. But by default, if you use scikit learn or other tools that
11:18
are related to cyclotron, it's most of the time zero, and one that is expected for binary classification. Anyway, I'm
11:25
getting distracted here. So let's go back to the map function. So yeah, I'm just reading in the data set again,
11:30
just to reset it, because I already transformed it on the previous slide. So to reset it onto to the original state, I'm
11:36
just reading it in here again. And then instead of using apply, I'm using map here. So map will convert the string navels into
11:46
the integers by mapping very similarly to the play function mapping, but it finds in the species column to the
11:53
corresponding to the corresponding integer. Also, by the way, later on, if you want to get your original class
12:01
labels back, you can define a reverse on dictionary you can for example, say D, reverse or something like that. And set it
12:09
the other way around. You can say zero equals Iris setosa.
12:17
One equals Iris versicolor.
12:23
And two, equals Iris on equals one is set to Iris
12:32
righini calm and then once you have your data set transformed like that, what you
12:39
can do is you can then call the map function with a reverse dictionary, and it will then transform them back to the
12:46
original class label.
12:51
Yes, on the previous slide, I was just showing you the first five rows you could only see the on setosa flowers that were
12:58
transformed because it was it was us. Usually if you don't shuffle the data set in Iris it comes first. Just to show you
13:05
that it also yeah handle the other flowers. So you can see for the last five using the take command that it also transformed
13:12
them into the corresponding class table. So the last 50 rows are Iris virginica, Iris virginica, was classy over two.
13:23
So the last 50 rows here, I'm only showing you the last five will also transformed and correspondingly also the rows in
Accessing the Underlying Numpy Array(s) via the "values" Attribute
13:31
the middle, which were Iris versicolor. So here, I'm showing you another concept that is using the values attribute. I
13:39
think I mentioned that before we talked about pandas. So if you cannot values it will access the underlying NumPy array. So
13:47
there's a NumPy underlying this column here, the species column, and by calling values that will access the NumPy array, and also
13:53
traditional nice, I could learn and many many other machine learning tools work with NumPy arrays, not pandas dataframes
14:01
however, also nowadays, many algorithms support pandas dataframes directly, but again, for traditions sake, or just to
14:10
kind of avoid unwanted behavior. if let's say the API is not super sophisticated, or some third party tools that are not
14:18
psychic learn, I still recommend using NumPy arrays because usually it's also a little bit faster, it has a smaller memory
14:25
footprint and stuff. So yeah, here you can see how the underlying NumPy array looks like the NumPy array underlying
14:34
this panels DataFrame column. So here you can see the first 50 flowers are the iris setosa Flowers Flowers converted to
14:43
zero mean the class ever was converted to zero. Then you have the second 50
14:50
corresponding to the rosy color flowers and the last 50 lips the
14:57
last 50 here corresponding to the running average clinica Clawson converted to the class table to.
15:04
Yeah, now we have our class table array. And like I mentioned before, we usually refer to our class table array
Creating the Label Vector "y" and Design Matrix X
15:10
as why. So why is usually our class label array,
15:16
it's just a convention in Python to use the letter Y to refer to the class table, vector or
15:24
array, and we use capital X to refer to the feature. So what we
15:30
call an introductory introduction, we call design matrix. Oops.
15:39
But touch the surface of my iPad with the finger, sometimes it jumps to the next slide, which is sometimes annoying.
15:47
Yeah, sorry about that. So here at the bottom, what happens is I'm now extracting x the design matrix,
15:56
or the features that we will be using for training our machine learning algorithm at the end of this lecture. So for that, I'm
16:03
using the ilok method on pandas. So there are multiple ways we can do that, we can also take the names of the columns and put
16:11
them in there. However I prefer, I mean, not always. But here, because it's just such a small data frame. If you go here, I
16:19
could type all these names of these columns in there. But it would be for me too much work on too much typing. So and because
16:26
it's such a simple data frame, where we only have 123456
16:33
columns, we know that the columns, one to five are the feature columns, so we can just use the
16:40
ilok I lock means index location, so it goes by this
16:45
index column index. And then we can slice it. So we say all the rows that's similar to NumPy,
16:52
when we have the selection, so the first is for the rows, and the second one is for the second x's, which are the columns. So we are selecting all
17:00
rows, because we want the whole data set all the training data, examples, and then we only select columns,
17:07
columns, oops, 125, which basically correspond Like I said before, on
17:15
small, compact, might work, sorry. So which correspond to those here.
17:23
Okay, so now we have both our label array, and our x array here, I'm only showing the first
17:30
five because otherwise it wouldn't fit. So label a sorry, the feature it looks like that. So also note, um, class of
17:37
arrays are integer. So we have an integer array here. And
17:42
the features are, in this case of float values. That's also what psychic learned expect. So we have floats. So there's no
17:49
point numbers or real values.
17:55
I'll be fine. Go to the next slide. I just put a little question here. Why did I put on creating in
18:02
quotation marks here? So why did I put that in quotation marks, maybe a question for Piazza, so maybe have a discussion on that,
18:09
we can discuss that then on Piazza. Yeah, um, and the additional tool that I wanted to mention on is MLA
18:16
extent, that is a library that I created long time ago, I think, like in 2012 2013, if not earlier, and here, I put all the
18:26
stuff in that I use in my day to day data science, machine learning workflows, and that I couldn't find implemented
18:33
anywhere else at that time when I wrote them. So in a way, these are, most of the time convenience functions.
18:40
There are some machine learning algorithms that are not implemented elsewhere in Python, or they are implemented in a way
18:48
that, that I, let's say, didn't or couldn't use in my project. So it's just a library that collects different things
18:55
related to data science and machine learning, most of the stuff is compatible to second turn also. Anyways, why
19:02
mentioning this, for example, one aspect on that is kind of useful is the scatter plot matrix.
Exploratory Data Analysis (EDA)
19:09
So usually, when I work with a new data set, I make a scatter plot matrix to just take a look at it and how it looks like it's
19:17
You mean, you know that from our it's just a very useful, simple way of looking at a data set in the context of exploratory data
19:25
analysis. And how that works is as follows.
19:30
So I have now my feature array, my NumPy feature array, and then I'm creating a scatter plot matrix for only the Certosa
19:39
flowers, then only for the virginica flowers, sorry, this rosy color and then for the beginning of fall, so this
19:46
so it was a rosy color. And
19:52
we're gonna come and um, yeah, I'm using the columns here as the names for
19:59
support. Length
20:07
sepal width and then same for petal length and petal width. So I'm
20:13
just providing them here as the axes names, I'm just extracting
20:19
them from the data frame because I was too lazy to type them in here with some legend with the class tables.
20:27
So this is in the same order as this one here, basically. And it will create three scatter
20:36
plots was scatterplot matrices, overlaid with each other. The reason why they are overlaid is so that I can basically show
20:46
all the classes separately, I could also plot everything with one function call. So I can actually ignore these two here. And then it will
20:54
only make so the last two rows will only make one scatterplot. For the whole data set, if I instead of, instead of doing x,
21:02
y equals zero, so only selecting setosa floors, I could just say
21:07
x, and they will plot the complete data set, however, then everything would be in the same color. And I wouldn't be able to
21:14
see which one is the tools on which vertical line, which is organica. So if you don't have class labels, if you have a data
21:21
set, you want to take a look at it, you don't have to do it like multiple times, you can just use a single scatterplot matrix.
21:28
Anyways, talking so much about the scatterplot matrix, how it's created, let's just take a look at how it looks like. So I
21:34
couldn't unfortunately, fit it into the previous slide because there was not much space left. But this is how it would look
21:40
like. And yeah, I always find it useful to take a look at a data set before I work with it, given that it isn't a reasonable size
21:47
and not too large. So here, for example, by looking at it, I could take a look at outliers and just get an idea of how the
21:53
dataset looks like. So I can, for example, see that based on the petal length, I can already with a very simple
21:59
classification. Based on one feature, I can say if my petal length is net same, or if it's bigger than let's say if it's
22:07
smaller than 2.2 centimeters, then
22:14
then it's the blue one, which was it was so this case, you can classify this, it was with a very simple decision rule here.
22:22
For organica and Versa color, I can almost do the same thing with I don't what is it five centimeters, it's little bit
22:28
tricky. There's some overlap, so it's not quite as easy. So maybe some other additional feature column would be useful. So here,
22:35
I would have the petal width, it's kind of similar, we can use the petal width to separate between setosa, versicolor and
22:43
organica. But it's also not so clean. So maybe using both is a little bit better. So having a classifier that splits on those,
22:52
both of them. And you can also see a sepal length and sepal width are kind of less useful than petal length and petal
22:59
width because here can see there's more overlap. And of course, yes is very simple dataset. So we can take a look
23:06
at it. But you can only take a look at two features at a time. So it's not like super useful if you have a high dimensional data
23:12
set, because you would have to have a lot of features to look at in a high dimensional data set. But I still kind of like
23:18
doing that. I mean, just like looking at the data and see if there's maybe some outlier. For example, here, this mu small
23:24
outlier. Here, they're all nicely grouped together and stuff like that. So I usually find that kind of interesting to
23:31
take a look at the data set before I work with it further. Yeah, now that we have the feature array x and the class
23:37
table array, why we can divide that up into a training validation and test set. So first, we read everything into
23:46
x. But now let's divide it into a train predation and test set. So we will be using the concepts from the NumPy lecture where we
23:54
talked about the random state. So what I'm doing first is I'm creating an index array here, so I'm taking the length of x, so x
24:04
dot shape, zero will give me the length of the array, the length
Splitting a Dataset into Train, Validation, and Test Subsets
24:11
of the first index, sorry, the first Xs, so that would be the number of training example. So that's number
24:19
of rows, right? because x is
24:25
150 times four dimensional
24:30
arrays of the shape is 115 comma four, it's a tupple first values number of rows. So
24:37
the number of rows is the number of training examples.
24:45
And what we do here is we create an index array, starting at zero so the index array we created with a range will be 01234, and
24:55
so forth, and then use a random state so it's reproducible. Later on, if we want to run the code again, it will create the
25:03
same splits. When we split the data, and so on, then what we do
25:08
is, so we have the label of raid 01234, we call so on the random state the permutation method, which will
25:17
essentially shuffle the next array. So now we have a shuffled index array. The numbers here are
25:23
from zero to 150. But now it's shuffled.
25:28
So why are we shuffling that, because we can now use that to select the training set on
25:35
validation set and tested. So now we are going to use the shuffled indices to divine data center training, validation and
25:42
test subsets. So just for reference, this column here was from the previous slide, so you can just see it, again, I'm
25:52
referencing where the period indices come from. And then what I'm doing here is I'm saying 50% of the data is going to the
26:01
training, set and 15% of the data not overlapping with any of the data and 65% here goes to the validation here. So what I'm
26:11
doing is I'm multiplying point six, five with the length of the rain. So basically saying point six, five times 150. This is the
26:20
number of training examples. And this is the number of validation
26:26
examples. And then the remainder would be the number of test
26:31
examples. So we have 20%.
26:37
For test, that's the remainder. So the test size, I'm setting it here, so the length minus the
26:47
size of the training set and validation set. So the remaining 20% will be for testing. So here, I'm just getting the sizes
26:55
for each subset, can see 97 training examples 22,
27:05
validation examples and 31 test examples.
27:11
And then I'm using my permuted indices that I created on the previous slide where I had the values zero to 155 shuffled, I'm using that as
27:21
a selection mask to select the training examples from the array. But first, I'm selecting them from the permitted indices,
27:32
so I'm getting the indices of the array corresponding to the
27:37
training one, so 65% of the data of the indices, that's the 15%.
27:45
That's a 20%. So I'm just selecting here, basically. So here, I'm selecting everything up to train size, everything up
27:53
to 97. So zero to 97. And then here, it's going from 97 to 97,
28:03
plus 22, which is 129. Right, so we have 1997 to one or 29. And
28:15
then for the last one, we have 129 to the end, which is
28:21
essentially 150. So now I have my indices, and then I can
28:27
select correspondingly the training and the training examples from the feature array, and the corresponding class
28:35
tables. So here, see I'm using that or the suffered indices.
28:41
Here. I'm using these here to select from the original one, the training examples. So the features from x and the
28:50
corresponding labels. And I'm doing that also for the
28:55
validation data set and the test sets. I have a test set now. So this is my sorry, is this my train set a validation set, and
29:03
also my test set? By the way, this one came from
29:09
Sri not sure where it came from, shouldn't be here. Some something left over.
29:15
Okay. Oh, I would say a lot of steps. So we'll show you later a more convenient way of doing that. So
29:23
later, I will show you also how we can do that more conveniently in scikit learn, but I think it's kind of an important to
29:28
understand how we would manually create training sets and validation sets and test sets just using NumPy. Because in a
29:36
sense, this is also what psychic learn does under the hood. However, they provide one simple function for doing that where we
29:42
did that manually here. So kind of looking over this and reading through this is also a good exercise for your understanding.
29:48
NumPy Yeah, so this is it for this video. So we talked about converting String class tables into integer class labels. We
29:57
call talk briefly about the lambda Functions apply and map which are convenient in pandas when we do such transformations
30:07
and then we talked about how we can divide a data set into a training validation and test it. So in the next lecture we will
30:14
all in the next video, we will be talking about some basic object oriented programming concepts and Python classes
30:21
because that will be useful for understanding how psychic learn works, which we'll be also talking in this lecture.

##v28:

0:02
Unknown: Before we talk about machine learning with scikit
0:05
learn in the next lecture, let us briefly talk about object
0:08
oriented programming. That means Python classes. And that becomes
0:13
very relevant very soon when we talk about psychic learn,
0:16
because we say learns heavily based on object oriented
0:19
programming concepts. And at the end of this video, I will show
0:23
you an implementation of K nearest neighbors using the
0:27
psychic learn API are basically the approach that I could learn
0:31
uses for implementing estimators like classifiers.
0:37
So, yeah, we are going to talk about Python classes now. So to
0:41
get a better understanding of the scikit learn API, like I
0:43
just said, and that will hopefully make everything kind
0:48
of like easier to understand when we use scikit learn in the
0:50
next video.
0:54
So here, I created a very simple naive vehicle class. So the
0:59
vehicle could be a car, motorcycle,
1:05
or truck, and so forth. So just just visualize it as like some
1:12
some type of vehicle here. So we have a vehicle class. And how
1:16
classes work is that we receive the class definition here in
1:20
this line, and then indented, we have the different class
1:23
methods.
1:26
Class methods are very similar to functions. However, note that
1:30
the first argument to each class method is the mandatory self
1:34
here. So there's also concept like static methods, however, we
1:39
are just talking about regular methods here. So every method
1:43
has to have a self here as the first argument. And the self
1:49
here refers to the object itself. So you can think of a
1:52
class
1:54
as a cookie cutter
1:59
that you can use to make or cut out cookies. If you have, let's
2:03
say, this plate of dough, and you have the star shaped cookie
2:07
cutter, you can apply this cookie cutter to different
2:11
places on this dough, and this plate of dough. And then you can
2:15
get these different cookies from there. So you can, these are not
2:21
really nice cookies, but you can get
2:24
multiple cookies. So the cookie cutter itself, that would be the
2:28
class, which you can use to make what as a template to make these
2:32
different objects. So the cookies here would be objects,
2:38
basically. So objects created from this class, or sometimes
2:43
I'll say, instances of the class and stuff like that. So I'm
2:47
here, the class, you can think of it as a template for making
2:50
vehicle objects. However, let's not get ahead of ourselves here
2:54
and see how, what we have here in this vehicle class.
3:00
So the first method here is the init method. And the init method
3:05
is the so called constructor,
3:16
which will basically be executed when we create a new object. So
3:20
if we have an assignment, for example, on new
3:25
vehicle
3:27
equals that's a vehicle class.
3:31
So if we call the class to make a new vehicle object, if we do
3:36
this, then the init method gets executed. We don't have to
3:40
explicitly call, let's say, vehicle.
3:45
Class dot underscore underscore in it, this is not necessary, it
3:51
automatically gets executed once we initialize a new object.
3:57
So what do we have here in this init method, so this init
4:00
method, accepts, accepts one argument, the horsepower that's
4:06
the horsepower of the vehicle here that we have to define
4:09
because here we don't have a default value, we have to define
4:11
it. And then there is an attribute here. So the attribute
4:16
is horsepower. So we are basically assigning the argument
4:21
provided to this method to an attribute so this is an
4:25
attribute. So if we create an object, if we created this new
4:31
vehicle here,
4:33
the new vehicle
4:36
will have an attribute dot horsepower that we can
4:42
then access to look up the horsepower. So here when we
4:46
create this, there should be a number for example, 123,
4:50
something like that. And then if we access this attribute, it
4:53
would return 123 it's just a way of attaching a value or a
4:59
variable. Just to
5:00
This object. So in the self means the object itself created
5:03
from this class or self gets translated to whatever the name
5:07
of the object is when we created.
5:11
And since we are running out of space here, let me forward one
5:14
slide. So I can talk about this a little bit in more detail
5:18
where I have lived more space for annotation.
5:24
So here again, for reference, I have want to hit on the last
5:28
slide. So we can take a look at this again. And now step by
5:31
step. Here, on the right hand side is the code for
5:35
instantiating. A new object using the vehicle class, so the
5:39
vehicle class was our cookie cutter. And this is our actual
5:44
cookie that we create using the cookie cutter. So here, we call
5:48
that object call one, it's just an arbitrary name.
5:52
And we provided with the input in the init method. So if we
5:56
create, or if we call the class here to create a new object, it
6:00
will automatically execute what's in what's in the init
6:05
method. So in the constructor, so after we created the object,
6:11
this one will be available, which got executed here. So
6:16
creating this
6:18
call
6:20
the init
6:22
method, which we also call the constructor method.
6:28
And then we can use only other methods on the car object, which
6:31
I will show you in the next slide.
6:38
So here, I'm calling now the horsepower to torque method,
6:41
which is which I looked up on Wikipedia, it's just a method
6:45
implemented for converting between horsepower, it's the
6:48
measurement of all let's say, You're not fast but powerful
6:51
cars, and converting it to torque, so put some calculation
6:56
in here, and it will return the value of the torque, so it will
7:03
convert the horsepower into torque, so we have to provide
7:06
the rounds per minutes on it. So that is something we have to
7:09
provide. But internally that we use a different color here,
7:13
internally, it will use the horsepower that we defined here.
7:17
So the car remote has a horsepower attribute. So this is
7:22
an
7:24
attribute, the horsepower, it has an attribute that is
7:29
internally used here when we call the hospital to torque, and
7:33
then it uses this one. So the RPM here together with the
7:38
horsepower argument, or sorry attribute to calculate the talk.
7:44
Now, we can also define a method that modifies attributes. For
7:49
example, in the next call here, I'm calling the tune motor
7:55
method, which tunes the motor so the car after tuning, it has
8:00
twice the hospital. Amazing, right? It would be great if it
8:03
works. So simply in real life anyways. So yeah, now our car
8:07
has twice the horsepower. So it should have, instead of 123, if
8:12
you would print hospital after two motor, you would see 246.
8:18
Now for the hospital. And now I'm calling the hospital to talk
8:23
method again. So you can see now, it's different than before,
8:29
because before our car had was bought 123 here, and we tuned
8:34
the motor, so it's now 246. So it's kind of doubled
8:40
the torque.
8:43
So in this slide, I just wanted to kind of
8:46
go over the concepts behind class attributes and methods. So
8:51
there are some methods that return values. And some methods,
8:57
they don't return values, but they modify the object so that
9:02
it's important to keep in mind that cloud methods that return
9:05
values that don't modify the object, and some modify the
9:08
object. And actually, we can really, as a user, we can really
9:11
know what's going on. I mean, usually this is hidden from a
9:16
user. And we as the code developer, or the person who
9:18
writes the code, we can, of course, see that, but usually,
9:22
the users few use something like someone's or someone else's
9:25
library or code, you only see this part here on the right. And
9:28
from here from looking at that you can just see whether this
9:32
modifies the object or not. So in a way, the only way to tell
9:36
is, let's say, looking at the source code or the
9:38
documentation. However, in scikit, learn there are certain
9:41
conventions for certain methods that do modify the object. And
9:47
we will also then talk about this a little bit later.
9:52
But for now, um, there are two more methods I wanted to talk
9:55
about briefly. So there's the private method. I had
10:00
So in Python, there's a convention.
10:04
Yeah, the Python, people in the Python community say, or the as
10:07
the saying goes, it's, we are all adults here.
10:13
So we are not
10:16
restricting any access to anything in Python. So you can
10:20
do whatever you want. In Python, you can have access to
10:24
everything, everything in the Python library that you import,
10:27
however, it's on your own responsibility. So if there are
10:32
methods that the users shouldn't use, but if they want to, they
10:35
can use them, then there's a convention to add
10:39
an underscore in front. So this is a convention saying, hey,
10:42
this method is private. Don't use that method. It's useful for
10:46
developers, but not for you, the user, but you know, if you
10:50
really want he has it, go ahead and use it, it's just your own
10:53
responsibility. If something goes wrong, it's not our
10:55
intention that you use it. But please go ahead, if you like. So
10:59
that's what the underscore indicates, underscore, in the
11:02
front. And yeah, you can just call the methods, like a normal
11:06
method, even though they have underscore in front, it's just
11:09
like a convention, it's not doing anything with the code,
11:12
it's just a convention.
11:14
Now there is a slightly stronger convention, it's using double
11:19
underscore. And that is, if you have a very, very private
11:22
method, where you really want to hide that method from the user.
11:25
And you don't want that to show up. I don't know in certain
11:28
documentation aspects, and so forth. So there's this double
11:32
underscore.
11:34
And this one, again, like we said, we are all adults here,
11:39
it's possible to access the dollar underscore methods, the
11:42
very private methods, but it's a little bit more tricky to access
11:45
those. So in order to access those, we can't just call the
11:49
method like that he will get an attribute error here.
11:53
So it will tell you that, yeah, this doesn't exist. So we can't
11:57
just call it like that. That doesn't work. So but we are all
12:01
adults, here's what can we do.
12:04
So the solution to that problem is this little workaround, where
12:08
we put the name of the class here in front. And it's just
12:13
make making the x's a little bit trickier. But again, we can
12:16
access this method. So if you want to access a very, very
12:19
private method, you will have to put the class name here in front
12:23
with another leading underscore. And this way, you can also
12:26
access these very, very private methods. But in scikit, learn,
12:29
or personally, when I write code, I usually never use those,
12:33
I just use a simple underscore method. And usually that is
12:38
sufficient in most cases.
12:42
Another concept related to Python classes inheritance, so I
12:46
should have put that in the title inheritance. So you can
12:51
essentially inherit from a parent class, you can make a
12:54
child class or children classes that are inheriting from a
12:59
parent class. So for example, I can make a specialized car class
13:04
that has some additional properties.
13:07
For example, the car class or all cars from the car class have
13:12
four wheels. And I could make a separate motorbike class where
13:16
all the vehicles, all the motorbikes, basically,
13:20
inheriting from the vehicle class will only have two wheels.
13:23
So that kind of way, I can inherit all the chat properties
13:28
from the parent class, but can make them more specific for
13:32
specific objects from a child class. So here, I'm making a
13:37
child
13:40
class that inherits from the parent class here.
13:46
So it basically inherits all everything from the parent. So
13:50
what I'm doing here, in order to do that inheritance, I put the
13:53
vehicle class here, and then I'm calling this one here. So this
13:58
one will cause
14:00
the car class to execute its init method, so that the
14:04
horsepower gets initialized from the car classes init method, and
14:10
then I'm adding another attribute here, the number of
14:14
wheels, so I set it to four here. So then I can create a new
14:18
car now inheriting from the car class, but note that it still
14:23
gets the horsepower here, because there we are still using
14:25
it here. And then we are calling that in the car classes in add
14:30
method. So even though we didn't set the attribute, we didn't set
14:36
self dot horsepower.
14:41
To horsepower, it's still available because that would be
14:46
done in the parent class. And that is how it works. It's the
14:51
rest is basically the same as for the parent class.
14:57
Yet to connect all the topics we just talked about.
15:00
wrote a very simple cane and classifier that follows the
15:04
second learning API. But of course, if you would look at the
15:07
source code of the second one, it would be way more complicated
15:10
because it has all kinds of bells and whistles like the KD
15:13
tree, bolt tree implementation, and many, many tweaks, I just
15:17
wanted to make it as simple as possible so that I can fit it on
15:20
one slide and talk about it in five minutes instead of 15
15:24
minutes. So I'm here, but so the same overall concepts apply. So
15:29
my kin m classifier has an init method. And it takes all the
15:34
relevant arguments. So yeah, I only have two hyper parameters.
15:38
So here, that would be K, the number of neighbors, for
15:41
example, in second learn, it's called an end neighbors, but
15:46
doesn't really matter, I just call it K. And then I'm having a
15:49
distance function here.
15:52
And then when the init method would be called, it would set
15:58
memorize, basically assign it to an attribute the number of
16:01
neighbors, and then if I don't provide as a user, if I don't
16:04
provide a distance function, it would use its own or the default
16:07
distance function. In this case, it would be the Euclidean
16:10
distance. So note here, I'm using this underscore. So this
16:14
is a private method, I just wrote this method for the KNN
16:18
classifier to use if the user doesn't provide a distance
16:21
method, but there is no reason that the user should ever let's
16:26
execute this one. Of course, also, you can see there's a very
16:28
inefficient implementation, I think I gave you some homework
16:33
exercise to make this more efficient using NumPy. Anyways,
16:36
so here, I'm using a private method, because there's no
16:40
reason why the user should call this method I'm indicating, hey,
16:43
this is just internally used.
16:49
Yeah, and then the two public methods, a fit method, that's
16:52
the training method, and a predict method. So that's doing
16:56
the prediction once the training has completed. Now, let's take a
17:00
look at the fit method, which is basically the training
17:05
what's going on here. So as you remember, the K nearest neighbor
17:11
classifier, doesn't really do any anything during training,
17:15
because it's a lazy machine learning algorithm. It's just
17:20
saving the data set. So here, we are just creating a copy of the
17:24
features and the training labels. And we assigning them to
17:29
class attributes here.
17:32
And then also all the unique labels. Note that I'm using an
17:37
underscore here at the end. So what does that mean? No, because
17:41
I'm sorry, here. So we didn't talk about the underscore at the
17:44
end. yet. And that is a psychic learned convention.
17:49
And
17:52
usually in scikit, learn the attributes.
17:59
With a trailing underscore,
18:02
like that one,
18:06
are I'm bringing it down, because it's kind of an
18:07
important point. And usually, it's easy to forget. And in the
18:11
past my other students that was it was a very common question
18:14
and later in the class, because people forgot what the
18:18
underscore was four. So this is a convention that actually works
18:22
with a trailing underscore are available
18:28
after
18:30
calling fit.
18:34
So that means you this actually, attributes don't exist before
18:39
calling fit. And that is a way of distinguishing between
18:44
parameters that we assign or hyper riders that we assign here
18:48
in the init method. In the inner methods, we never
18:52
use, trailing underscores.
18:58
We only use these for the attributes created in fit. And
19:02
there's just a way of finding out whether a classifier was fit
19:06
or not. And these are usually things that are created during
19:11
training, for example, these copies of the training set in
19:13
this case.
19:15
Now after training, we can then call predict.
19:20
And I don't want to go over all of this. But in predict, for
19:23
example, we are calling again, a private method. And this private
19:28
method will
19:31
find the nearest neighbor. So again, this is a method that the
19:33
user doesn't have to execute. It's just internally use. All
19:38
the user has to worry about is initializing a new object. And
19:43
then doing the fit and predict basic that's all the user has to
19:46
do. And I think I have
19:50
some more slides showing this.
19:53
So yeah, actually one more slide. So here,
19:57
this is how we would use our cane and classifiers
20:00
We would initialize it with a hammer, right or three, we don't
20:03
use a distance function. So it will, by default use the
20:06
Euclidean distance function. And then we call fit using the
20:10
training set. So x train and y train. This is what we created
20:14
previously in the last video. So this is these other features.
20:19
And these are the class labels.
20:24
And then after model fitting, we can call predict here on the
20:28
validation set. And these are the predictions by the
20:30
validation set. And that is how the psychic learn API works. Of
20:35
course, this is a very simplified version. But here
20:37
what's important to remember is, there's a fit methods method,
20:41
there's a predict method. And these are available for all
20:45
classification algorithms and all regression algorithms. Most
20:49
of them also have additional methods, for example, score and
20:52
transform and stuff like that, but fit and predict are the main
20:56
ones. And then there's an arbitrary number of private
21:01
methods, but we don't have to worry or think about the private
21:03
methods. They're just there to make the application or
21:07
implementation here. To make it more efficient to make the code
21:11
in fitness a little bit smaller, till we could have actually
21:15
squeezed all of that code into this one. But it's just like
21:20
refactoring. It's easier to write code, where you have
21:24
smaller, special purpose functions, because then it's
21:26
easier to debug the code as a developer. Okay, so that was a
21:31
very short brief crash course on object oriented programming, and
21:35
Python classes and a brief glimpse into the psychic learn
21:39
API. So in the next lecture, we will start in the next video, we
21:43
will talk a little bit more about machine learning with
21:45
scikit learn

##v29:

0:02
yeah so in this relatively short video i
0:04
want to
0:05
introduce machine learning with psychic
0:06
learn you have seen psychic learn before
0:09
in the k-nearest neighbor lectures where
0:10
i was
0:11
working with the k-nearest neighbor
0:13
classifier from second learn
0:15
however here i want to take a step back
0:17
and introduce the library properly and
0:19
then
0:20
after this short video there will be a
0:22
longer video where i will go over some
0:24
of the aspects
0:25
for preparing the training data set
0:27
using psychic learn
0:28
tools that make that more convenient and
0:30
more efficient than
0:32
compared to what we have done before and
0:34
lastly
0:36
the last video then we'll again go over
0:38
some of
0:39
yeah the cool concepts in scikit-learn
0:41
where we can combine
0:43
like the pre-processing and machine
0:45
learning classifier fitting and training
0:47
and stuff like that
0:48
using scikit-learn pipelines okay but
0:50
let's
0:51
briefly talk about machine learning with
0:53
scikit-learn now so we are
0:54
right now here
0:58
yeah personally i always refer to
1:00
psychic learn as the main machine
1:02
learning library for python
1:03
and that is because it's yeah a
1:06
relatively established library
1:07
it has a very large user base it's
1:09
really nice to use and
1:11
yeah it's just a great library and as
1:13
far as i know it's also the
1:15
most widely used machine learning
1:16
library so one thing to note though is
1:19
that scikit-learn is not
1:21
not for deep learning so for deep
1:23
learning
1:25
we have other libraries and deep
1:27
learning is a separate topic
1:28
that i'm teaching in stats 453
1:32
so here we're not talking about the deep
1:35
learning capabilities it's
1:36
just a machine learning library however
1:38
it's probably one of the
1:40
best designed libraries i know so i also
1:43
usually refer to scikit-learn as a
1:46
showcase library for implementing yeah a
1:48
good
1:48
api and a good python library in general
1:51
in python
1:52
because what's really great about um
1:53
scikit-learn is that it's very
1:54
consistent
1:55
and has a very well thought out way of
1:58
using it everything is compatible to
1:59
each other
2:00
and um yeah you will rarely find any
2:03
bugs in this library and so forth
2:05
so yeah it's it's a great library um
2:08
and it's also already a relatively old
2:12
so it was initially released in 2007
2:15
it was like 13 years ago it's a long
2:17
time ago however that doesn't mean that
2:19
it's like um
2:20
dated it's still very much up to date a
2:23
lot of people are contributing it
2:24
to it so originally it started as a
2:27
summer or
2:28
google sum of code project by um david
2:32
um corner po and later on other um
2:35
contributors joined
2:37
so later on lots of people started
2:40
contributing
2:41
so i was just checking on github there
2:44
are more than
2:45
1875 contributors now for psychic learn
2:48
and it's used by almost 150
2:52
000 people so it's a huge library there
2:55
are lots of efforts that go into it and
2:57
you can really see
2:58
that based on the quality of their code
3:01
so yeah here's the link to the official
3:04
website where you find the documentation
3:06
and tutorials
3:07
and i think this is maybe yeah the one
3:10
main paper if you use that later on in
3:12
your research project
3:13
would be nice to get to cite the library
3:15
so um
3:16
that's just a common convention in
3:19
academia if you
3:20
use the software library don't forget to
3:22
cite it because people put a
3:23
lot of work into it and it would be yeah
3:25
also nice for them if you cite their
3:27
library
3:31
yeah so here is an overview of the
3:33
scikit-learn
3:34
estimator api so with estimator api i
3:38
mean
3:38
apis for regressors like regression
3:41
analysis
3:43
classes and classifiers
3:46
so we call them in scikit-learn
3:48
regressor regressors
3:50
and classifiers these are the main types
3:55
of classes for supervised learning
3:59
so this is um for supervised learning
4:02
and here this doesn't actually exist so
4:05
this is just some code
4:07
that explains the main
4:10
concepts of the estimator api that goes
4:12
back to the object oriented programming
4:15
paradigm that i explained in the last
4:17
video
4:18
so the main aspects of any classifier or
4:21
regressor
4:21
are listed here here try to abstract
4:24
that a little bit
4:25
so what you uh how the super based
4:28
estimator usually works is that you
4:29
initialize it
4:30
you're using certain hyper parameters
4:32
and the hyperwriters they get assigned
4:34
in the constructor here so this is
4:37
usually you don't see that part
4:38
you just provide the high parameters and
4:40
there's some thing going on
4:42
in the init method and that will yeah
4:44
create the object
4:46
so when you have something like uh let's
4:48
say my new classifier
4:51
and you initialize a cane
4:55
neighbors classifier
4:59
then i'm running out of space so i'm
5:02
writing this on a new line
5:03
there will be hyper parameters like n
5:04
neighbors
5:07
you can set it for example to three and
5:08
stuff like that there are usually
5:10
multiple hyperventilators that you can
5:11
set
5:12
so that is one aspect of of course the
5:14
supervised estimator api
5:16
and the hypermeters they get assigned
5:18
here in the initial initialization call
5:20
um a very important method is the fit
5:23
method
5:24
so in the fit method you you fit the
5:27
object before you can use it
5:28
so you for example after initializing it
5:30
call classifier
5:32
dot um fit on
5:36
using the features so x is the design
5:39
matrix so
5:40
these are the features so it's um and
5:43
the shape is n training examples times
5:46
uh n features
5:49
or you can also say m features so we
5:51
don't use the same letter twice
5:53
and then we have also a label array so
5:55
this is an array it also has the shape
5:57
and train so this is just a vector
5:59
basically y is a vector
6:01
and then during the fitting
6:04
um there will be certain attributes also
6:06
assigned to the estimator
6:08
again recall from the last video on the
6:10
object oriented programming paradigms
6:13
i explained that in psychic learn these
6:15
fit attributes so things that
6:17
get created during or after calling fit
6:21
are having this underscore here this
6:23
trailing underscore
6:24
so there are additional attributes
6:26
available only after fitting
6:28
and these are the ones with the trailing
6:30
underscore often you don't have to use
6:32
them
6:33
sometimes we will be using them in the
6:34
class but if you see
6:36
something like an attribute with a
6:38
training underscore it means that it is
6:40
an
6:41
attribute created during model fitting
6:44
yeah then there's the predict method
6:46
that you can use after calling
6:48
fit so you would then do classifier dot
6:51
predict and here you can have let's say
6:54
a
6:54
new um data set that has the same shape
6:58
as your train data set so the same
6:59
features
7:00
but it could be let's say new examples
7:02
that you haven't encountered during
7:04
training it could be for example the
7:05
test set
7:06
so you can do predictions then um and
7:09
there's also a score
7:10
method so the score method it depends on
7:13
whether we have a classifier or a
7:15
regressor
7:16
in the case of a classifier
7:19
the score method is just a convenience
7:21
method for computing the accuracy the
7:24
classification
7:25
accuracy and for regressors
7:28
it's computing the um are
7:32
r2 sq the r squared so the coefficient
7:36
of determination
7:37
yeah lastly there are the private
7:39
methods the ones with the leading
7:41
underscore and these are the ones
7:42
in practice you don't have to worry
7:44
about they mainly just exist
7:46
to make the implementation of the code
7:49
more efficient and more readable
7:51
related to concepts of via code
7:52
refactoring so private methods you can
7:55
kind of ignore they are usually only
7:56
used internally
7:58
and yeah that is the main outline of a
8:00
supervised estimator
8:02
where we have the fit method the predict
8:05
method
8:06
the score method and then sometimes also
8:08
additional methods but these are the
8:10
main ones
8:11
yeah just as another way of looking at
8:13
it here is a flow chart
8:14
outlining the scikit-learn estimator api
8:17
or mainly the workflow
8:19
so after initializing an estimator
8:22
we would call fit it's the first step
8:26
calling fit or using the training data
8:29
so
8:29
this one will fit fit the model
8:33
so we have then our fitted model and
8:35
then after we fitted the model
8:37
we can use the test data set or any
8:39
other new data set that has the same
8:41
features as the training data
8:43
to make predictions so then we can call
8:45
predict and we get back
8:47
the labels so that's just the main
8:49
outline of
8:50
how we can use an estimator here is an
8:53
estimator in action again
8:55
so here i'm using the k nearest
8:57
neighbors classifier from the
9:00
scikit-learn neighbors sub-module so
9:03
second learn
9:04
organizes their code into sub-modules
9:06
because otherwise it would be
9:08
kind of hard to maintain that library so
9:09
to make it a little bit more readable
9:11
so here we import the k-nearest neighbor
9:13
classifier
9:14
and then i have a convenience function
9:16
and an extend
9:17
for plotting decision regions so
9:21
what we are doing here is we are first
9:24
initializing
9:28
an estimator and then after we
9:31
initialize it we can fit it to the
9:33
training data like outlined in the
9:34
previous slide
9:36
note that i'm only using two features
9:38
here the feature
9:40
the third feature and the fourth feature
9:41
in the iris data set so this is the iris
9:43
data set by the way
9:45
and that is just for i would say
9:47
educational purposes because
9:49
you can only plot the decision regions
9:52
for two dimensions because it's just the
9:55
way
9:55
of how we visualize things because we
9:58
can't really
10:00
visualize higher dimensional um
10:04
scatter plots right so we can maybe
10:05
visualize a 3d scatter plot but
10:07
everything
10:08
beyond three dimensions would be hard to
10:10
visualize and even making a 3d plot on a
10:12
2
10:13
d slide here would be kind of
10:15
challenging for
10:16
visual purposes so here we are just
10:18
using two features just for educational
10:20
purposes in practice of course
10:22
you rarely have a data set with two
10:24
features any case so after fitting
10:28
we are calling this plot decision
10:29
regions function um to visualize that
10:32
and this is how it would look like so
10:34
here
10:35
we have a decision region plot of the k
10:37
nearest neighbor classifier
10:39
fit to the petal length
10:42
and petal width and note that the plot
10:46
decision
10:46
regions function internally would call
10:49
on predict
10:50
to make the predictions basically yeah
10:53
and what you can see here is that the
10:55
k-nearest neighbor classifier with three
10:57
neighbors um i would say gets
11:00
100 accuracy here on this training set
11:02
so it's maybe even overfitting a little
11:04
bit here
11:05
so what you can see is it can nicely
11:07
separate out
11:08
the blue squares from the triangles and
11:11
circles
11:12
so i think uh the blue squares these
11:14
were
11:15
satosa red was
11:20
rosy color and the green one was
11:24
virginica flowers so you can see
11:26
separating of organica and versicolor is
11:28
a little bit more tricky
11:30
here it's actually doing a good job with
11:33
separating or catching this one
11:35
however one might argue this is a little
11:37
bit overfitting so
11:38
it could be um if you have new flowers
11:41
that
11:41
flowers this region might be actually
11:44
veginica flowers
11:45
however we will talk more about
11:47
overfitting
11:48
in later lectures so yeah this was it a
11:52
brief introduction to second learn in
11:54
the next video we will be taking
11:56
a look at how we prepare the training
11:57
set so basically we
11:59
we will take a look at how we get x
12:01
train and wide train from the iris data
12:04
set
12:04
um including techniques like normalizing
12:07
the data and
12:09
pre-processing the data and stuff like
12:10
that so yeah and with that um
12:12
this video was just a short teaser using
12:15
second learn in the next video we will
12:16
go into a little bit more detail

##v30:

0:00
so in this video we are going to talk about preparing our training data set using utilities
0:06
from scikit-learn and we will also talk about the transformer api which is related to the
0:11
estimator api that we talked about in the previous video so the estimator api was for supervised
0:19
uh learning models such as classifiers or regression analysis models and the transformer api is more for data
0:27
transformations but it's relatively similar and we will also yeah see how that looks like later in
0:32
this video but before we talk more about it let me briefly highlight the issues with
Issues with random subsampling
0:38
random sub sampling with random sub sampling here i mean dividing a data set into two subsets so
0:45
consider the example where i have 150 iris flowers and i'm dividing it
0:50
into a training set of 100 flowers and a test set of 50 flowers
0:56
so here each histogram is showing a frequency distribution
1:01
for uh the zipper lengths however uh what kind of feature this is doesn't really matter i'm like here more curious
1:08
or interested in looking at the class label distributions so you can see um there are three colors
1:15
so the colors correspond to iris satosa organica and versicolor flowers
1:20
and you can see when i randomly divide it up the distribution changes you can see
1:27
that for example this here is relatively similar to here however the distribution here in the
1:34
test set changes so i would argue that we have now more setosa flowers in
1:42
the training set compared to other classes um rather than in the test set where we
1:49
have fears the toes are flowers compared to the other classes um so that is maybe a little bit confusing what i
1:54
just said so what i mean is here in the data set we have a 33 percent
1:59
33 percent 33 distribution of all the flower classes so there are 50 flowers
2:05
from each class so there's a 33 percent
2:10
yeah um proportion here for each flower class to be represented in the data set
2:17
now when we split it what happens is in the training set
2:22
we may have no more than thirty percent satosa flowers in the
2:28
training set compared to the other ones
2:34
so let's say it's something like 40 20 20 uh
2:40
let's say sorry 30 30 now so it's a little bit uh exaggerated of course just to bring
2:47
the point home here the distribution changes if we randomly sub sample and have a small
2:53
data set just to random effects so it's a high chance that we skew the distribution if we have a small
3:00
data set and randomly divided now so for example if we have now more
3:05
than 33 percent of the dozer flowers in our training set we will have less
3:11
than 33 percent the total flowers in our test set so the bias will be in the opposite
3:18
direction because yeah we only um have a fixed number of satosa flaws and if we proportionately
3:25
assign more the twos are flowers in the training set we will have fewer for the test set
3:30
so here the distribution may be something like twenty percent now
3:35
and forty percent and forty percent of course again this is uh exaggerated however if we
3:43
randomly sub sample what can happen is that we skew the class label distributions and if we
3:49
think of our whole data set as the population then we introduce some bias here because
3:56
one class will be let's say under represent or overrepresented in
4:01
the training set and the opposite way it will be then under represented in the test set so we
4:07
have two types of issues here first we have a misrepresentation
4:12
in the training set and then we have an another misrepresentation depending on the training set misrepresentation
4:18
in the test set so yeah if we work with a sufficiently large data set this is usually less of an
4:24
issue this um skewing of the distributions however i think it's always a good idea
4:29
to do something called stratified splitting so stratified splitting means splitting
stratified splitting
4:37
by maintaining the class
4:45
distribution or proportion proportions
4:50
in the subsets so how we can do that in cycle learn is as follows so here we
4:56
are using the train test split function from the model selection sub-module in scikit-learn and what this
5:03
train test split function does it's splitting a data set into through subsets
5:08
so here my data set is x and this is the features the one let's say 150 flowers
5:14
well the features corresponding to the 150 flowers and then my 150
5:20
labels say let's call them instances 150 features
5:27
the corresponding to the floor instances and 150 corresponding label labels and then we will split that into
5:34
20 as a test data set and then the remainder will be a temporary data set
5:41
so what we will do here is we will define x temp and x test so if um the test set size is
5:49
20 percent then we will have the 150 divided into
5:56
30 tests um cases and the remainder the 120 will be
6:04
for let's say the temporary array i will show you in a moment why we
6:10
do the temporary array um some other things to observe here we are shuffling the data set before we
6:16
split that that is useful because you know that in iris the class labels are sorted so you have
6:22
first the 50 setoza then the 50 versicolor and then the 50 virginica flowers
6:28
if you don't shuffle then the setoza flowers will all be in one dataset for example so we shuffle to have a shuffle data set
6:35
and then we also set the random state for the shuffling so we can reproduce these results later if we need to
6:42
and here via the stratify parameter we define the stratification so here for
6:48
stratify we actually provide the labels that we want to use for this stratification
6:53
and then as a result you can see here based on the bin count output which gives you um the counts for
7:01
the zero one and two values where zero means um surtosa
7:08
one is versicolor two is originica so the class labels
7:17
so this is the number of satoshi flowers the number of versicolor flowers in the second index
7:23
and the third index index two corresponds to reginica so you can see here that the
7:29
distribution from the original data set which was 50 50 50 flowers is maintained so we have a 30
7:37
3 proportion of each class in our new temp data set and if you would check
7:46
why test you would find the same thing that there's a 33 chance of each flower in the test set
7:53
now we are going to repeat this one more time because we are now dividing the temporary one the 120 ones
8:02
into a training set and a validation set so that is why i do two splits here
8:09
first we are creating the test set so we are um we use a different color we have the
8:14
test set first and then in the second one we are creating the training the actual
8:21
training set and the actual yeah validation set that we will be using for model tuning
8:26
so we usually use a model a validation set for model tuning and then the test set only for the final
8:32
evaluation but we will talk more about that in the future when we talk about model evaluation in more detail so as a
8:40
result now here i'm using now white temp the class labels here again for stratification
8:46
and then i will get 96 training examples and if i have 96 training examples 120
8:55
minus on the 96 this would be 24 so i have 24 in my validation
9:04
set so 24 validation instances and uh here this is just illustrating
9:11
the slide that we can do the stratified split using a train test split function and specifying the
9:18
stratify argument the next topic is data normalization
minmax scaling
9:25
in particular here we are talking about min max scaling so min max scaling is a way of
9:32
scaling a feature such that all the values will be within the range 0 to 1.
9:40
so consider the case of the sepal length so here x represents one feature so x
9:47
could be for example the sepal length feature in the iris data set
9:56
and what we are doing is we are normalizing the sepal length such that it falls within the range zero
10:01
and one so we take a current observation of a training example
10:07
so i is the index over the training examples and then we subtract the feature
10:13
minimum value so it's the smallest
10:19
the smallest sapper length for example in our data set
10:30
and then we also here use the maximum feature value so it's the largest feature value in our
10:35
data set so we essentially for each value in the feature column in our training set
10:40
we subtract the x min the minimum feature value and then divide by x max minus x min
10:49
and then we get the normalized feature value so here's a simple example of how that looks like in practice
10:55
so imagine our original feature values are the values between 0 and 5 so let's say
11:02
this is our feature column here so what we do is we subtract the minimum value
11:07
and divide by the maximum minus the minimum value and then you will see afterwards the
11:12
feature column will be in the range 0
11:17
to 1. so that is one way of normalizing
standardization
11:25
yeah another common data normalization approach is standardization you probably have seen
11:31
something like that in the other statistics classes you took before so here um this looks kind of like the
11:38
z-score computation right when we have a normal distribution and we want to convert
11:44
from a normal distribution into a standard normal distribution so that's the same concept here we have
11:50
a feature value and we subtract the feature
11:57
mean and then divide by the standard deviation of the feature
12:04
and afterwards so after that the distribution oh sorry not the distribution
12:10
the the mean of this feature column will be uh zero so we have zero mean
12:16
and the variance will be one so we have unit variance after standardization and consequently the
12:23
standard division will also be one note that however these are only the
12:29
properties of that feature so the parameters of a normal distribution or standard normal distribution
12:35
but if the feature doesn't have or doesn't follow a normal distribution
12:40
it will also not have a normal distribution afterwards it's just one way of affecting the mean so it's
12:48
centering um at mean zero and then
12:55
scaling such that the on standard deviation or variance is
13:01
one however if the distribu like i said if the distribution of the feature is not normal
13:07
then after standardization it will also not be normal it's not important um whether we have a standard normal
13:13
distribution or normal distribution for the feature here for most algorithms the point is
13:19
more about having zero mean and standard deviation of one yeah so the rationale behind
13:26
standardization is that zero mean and unit variance are properties that help certain optimization algorithms
13:33
such as stochastic gradient descent however we will not be discussing stochastic gradient descent
13:39
in this class it's a thing i cover in 453
13:44
um so but in general standardization is much more popular for example than
13:51
min max scaling so in machine learning most people use standardization rather than min max scaling and it's for
13:59
these applications it's fine to do either way uh either or so if we have a k-nearest neighbor
14:04
algorithm doesn't make a big difference whether we normalize all the features or standardize all the features
14:09
what's more important is that the features are all on the same scale if we use distance metrics such as euclidean
14:15
distance and also in the next lecture we will be talking about decision trees and
14:22
decision trees don't need any feature scaling at all in essence they will be immune to feature
14:29
scaling so um sterilization though is still a useful and important concept in other
14:36
machine learning algorithms so it's usually not a bad idea to just do it
14:41
so here's how standardization would look like in practice again i have my toy feature column the 0
14:48
1 2 3 4 5 as possible feature values and then i'm subtracting the feature
14:53
mean and divide by the standard deviation so as a consequence i will get a new
15:00
feature that is centered at 0 with a unit variance
sample standard deviation
15:05
yes you may recall from previous classes the sample standard deviation has n minus 1 in the
15:11
denominator that's the bezel's correction term to make this an unbiased estimate
15:16
of the population standard deviation so in that case that's the difference between the
15:21
population and the sample standard deviation
population standard deviation
15:27
now if you wanted to get a population standard deviation via pandas you would have to replace
15:32
this by um delta degrees of freedom equals zero
15:38
or if you wanted to get the sample
15:43
standard deviation by a numpy you would add delta degrees of freedom 1
15:49
here that's basically the minus 1 here in the std function in machine learning
15:55
by the way it doesn't really matter whether you use the standard deviation
16:00
corresponding to the sample standard deviation or the population in machining all that matters is that
16:07
the feature is centered and has approximately unit variance so whether you use the sample or
16:13
population variance or standard deviation doesn't really matter at all so you can use either or
16:19
personally and just use the population standard deviation because there's no advantage of using the sample standard
16:25
deviation when we standardize the variables so yeah because i personally usually use
16:30
numpy when i work in machine learning i would just use the population stand
16:36
evasion because it's just easier to type than just putting the ddof equals one here and in practice it does
16:43
not really matter whether we compute the standard deviation for the sample or the population in machine learning when we
16:50
standardize the features what's more important though than talking about
training set parameters
16:56
sample and population standard deviation is that we use the parameters of the
17:01
training set when scaling the validation and test sets so we use the training
17:07
parameters for that so for example when you standardize features you would get the mean and the third deviation
17:16
from the training set from x train right so you get the feature mean and the feature
17:22
standard deviation from the training set and then you use that to standardize the training set here
17:27
right and note that we also use the same
17:34
mu and sigma the same mean and star deviation for scaling the validation set and also
17:42
for scaling the test set we do not recompute the mean or standard deviation from the
17:48
validation and test set so why is that the intuition behind it is basically that
17:54
the validation and test sets are unseen data sets so at the point when you do the model
18:01
training you only know the training set you don't know the validation in the test set so if you would use the parameters or
18:08
the validation and tested to scale these two sets you would in a way have too much information
18:15
you would kind of cheat or leak information i know it may seem a
18:22
little bit unintuitive however i try to make a very simple example in the next couple of slides to
18:28
illustrate why we reuse the training set parameters
18:34
and a potential pitfall that can happen if we don't do that
18:40
so consider the simple case where we are given three training examples these three training
18:47
examples and we have some measurements for these training examples like 10 centimeters 20 and 30 centimeters
18:53
and on the first two training examples belong to class two and the last training example the
19:00
third one belongs to class one now if we would compute the mean of that data set
19:07
it would be twenty and the standard deviation would be 8.2 centimeters
19:12
so that's just our training dataset how it looks like very simple so again here's the training set from
19:19
the previous slide as a reference and then let's now standardize the
19:24
training set so to standardize the first training example we would have 10 minus 20 centimeters
19:32
divided by the standard deviation which is 8.2 right so this one would be our first
19:39
one which is uh minus 1.21 it's from here right and then i repeat
19:46
the same thing for example two in example three so what i get as the new feature values is
19:52
0 here and 1.21 here of course this does not affect the class labels at
19:57
all it shouldn't it's just scaling the features so the class labels are just as this
20:03
as the class labels as before now this one again is from the previous slide just for reference now assume we
20:10
have a classification rule um that is saying if z where z equals the standardized feature
20:17
so let's call it standardized
20:24
feature i just call that z-score here so if our standardized feature is smaller or equal to 0.6 we classified
20:32
as class 2 and otherwise we classified as class 1. now let's apply the rule so if we take
20:40
this rule here and check between example 1 then this one would be correctly classified right
20:46
because this one is smaller than 0.6 so we assign
20:54
class 2 just like here then for the second one
21:01
0 is also smaller than 0.6 so we also assign class 2. now the other case where z is greater
21:09
than 0.6 that's what we have here 1.21 is greater than 0.6
21:15
so we assign class 1 here so this is our classification rule that we learned from
21:21
the training set we just assume we have some classifier that does this type of classification
standardize
21:28
now assume i have a new data set so i am giving new examples and let's say
21:34
this is our test set now we have a test set and we have the values
21:41
5 6 7 in in the data set so what would the prediction be before
21:47
we do the prediction we have to also standardize right because our classifier was trained on a standardized
21:54
training set so we also have to standardize any future case
21:59
now let's standardize the test set however we do the wrong
22:06
way first and the wrong way is using the mean from this new data set and the
22:12
standard deviation from this new data set so we estimate the new mean and standard deviation
22:18
and what happens is if we do that for these three cases we will get again the values minus
22:25
1.1 0 and 1.21 and then if we would use these so if
22:31
this is a standardized version of this one if we do that and then if we
22:37
use our classification rule we would get exactly the same
22:42
as for our training set before however note that now in the
22:49
in this new data set the values are very different than the values before so
22:55
this doesn't look right right so it's really not a good idea to use
trainingset parameters
23:02
the new data set mean and standard deviation for standardizing the new data set what would be better is to use the
23:09
training set parameters so if we use the training set parameters these ones here
23:14
what we get for the standardized months are these values and they make much much
23:20
more sense because if you look at these um these here there are values that are
23:27
much smaller than these ones right so the values are way way smaller
23:32
than these values so it's kind of intuitive that all the values the standardized
23:37
z-scores are lower than this case because this one this one here was the lowest value
23:45
in my training set right 10 centimeters and all of these are actually smaller
23:52
than the 10 so and consequently they should the z-scores should be smaller than my one
23:58
point minus 1.21 right so if i would actually then use these values i will get these smaller values and this
24:05
one is really not a good idea so here hopefully this example illustrates
24:11
why re-estimating the mean and third deviation for each data set when we do the prediction
24:17
is not a good idea and we in fact should use the training set parameters
Transformer API
24:24
yeah talking about normalization like min max scaling and standardization brings us to
24:29
the next topic circuit learned transformers or in particular the scikit-learn transformer
24:35
api so this transformer api or the transformer the term here is not to be confused with the
24:41
transformers in deep learning which are a type of neural network architecture based on the attention
24:47
mechanism so here we are talking about a transformer api and transformer is more like for
24:53
a technique for transforming your data such as like min max scaling or standardization
25:00
so scikit-learn has an api for all kinds of different transformers such as standardization and
25:07
min max scaling transformers which i will show you in the next slide so here i'm just outlining the general
25:14
concept behind transformer types in second learn so similar to the estimators what we
25:22
have is a fit method so we have a training data set typically and then we call fit on this training
25:29
data set here and then we get a model or you can also think of it as an
25:34
object a transformer object and then using this model we can transform
25:40
the training data to get transformed training data so in that way you can if we talk about a normalization
25:46
procedure we can think of it as a normalizer some some object that normalizes the
25:52
training set and then transformed is basically normalized
25:58
like standardized or mixed scaled and so forth and so after doing that for the training
26:03
set so after fitting the transformer object or model then we can also use it on the test set
26:10
on any new data set so we have a new data set here and then we would call transform
26:16
similar to the training set but note that what's important here is that we only call fit on the training set we don't call
26:22
fit again on the test data and so forth now here's how that would look like in
Standardizing
26:28
practice i'm using the standard scalar so the standard scalar is for standardization so recall we previously
26:36
have done the standardization manually where i did something like this where i had
26:42
let's say for one feature column i just computed the mean using numpy
26:48
and the standard deviation like so and if we would have a design matrix
26:54
with basically a matrix and training examples times m features so like multiple features
26:59
we can then uh just put the axis in there right so we would
27:05
say x's should be a zero because we compute the column means
27:10
and the same way here so that would work
27:18
for design matrices then after that after we obtain these
27:23
parameters we can standardize the training set so let's say x train
27:31
st or something like that for standardized we would call um or we would use the x train
27:38
data set minus mu divided by the standard deviation oops
27:46
just jumping back and forth here by the standard deviation and then we can do the same thing
27:52
for the test set so we would have test sd equals x test
27:59
minus the same mu divided by the standard deviation
28:06
so instead of doing that by hand like i just showed you we can also use this standard scalar
28:12
transformer that's like what circuit learn refers to the
28:18
transformer because it has like the transformer api and then we can
28:24
achieve the same thing um by first initializing a new scalar object or transformer object so i
28:30
call that scalar because it's a standard scalar for standardization then i fit the standard scalar and
28:36
really what happens here we use a different color what happens in this step is essentially inferring the mean
28:44
and the standard deviation from the training set from the data set provided here to the fit method
28:49
so the scalar will then have a mean and standard deviation from the training set that it can then use to
28:57
transform or standardize the training set so then in the next step like i've outlined
29:02
above it's equivalent to what i have here in red this step would be scaling or
29:09
standardizing the training set and then if we have a new data set like the test data set or
29:15
validation data set we can then also scale that one but note that we are not calling fit
29:21
again so here the fit method is only called on the training set and that is similar to not inferring the
29:29
mean and standard deviation from the test set but using the parameters from the training set
29:34
yeah one burning question now might be why are we not sticking to this approach for standardization why
29:41
do we need to use the second learn transformer api why do we have to use the standard scalar because
29:47
it doesn't seem to be too much work to do it ourselves right so in the case of sonisation i agree
29:53
it's a very simple procedure so we can do it by hand we don't need really separate classrooms i could learn from
29:58
that there are some more sophisticated transformation techniques that we will cover later on
30:04
some are related to feature selection and feature dimensionality reduction as feature
30:10
extraction and stuff like that it is more complicated to implement and there the transformer api will
30:15
become more handy however also the standard scalar is a very useful thing to have as we will see
30:22
later in the next video when we talk about second loan pipelines because the stellar scala allows us to
30:29
yeah use a second one pipeline where we can chain together a bunch of things to be executed
30:36
on a given data set so in the next video it becomes also hopefully a little bit more clear
30:41
why it's useful to use the standard scala instead of doing it ourselves okay but to move forward now in the
Categorical
30:47
previous slides i spent a lot of time explaining how we can deal with continuous feature columns like standardizing
30:53
features now let's talk about how we deal with categorical data for that i have a very
30:59
simple toy data set here which consists of yeah three training instances and four
31:06
columns it's a very small data set it's just like for illustration purposes here so we have three feature columns and one
31:13
label column first note that we have two categorical columns here so
31:19
these are these two are categorical
31:25
and this one here is a continuous one like before
31:31
now let's talk about the size here first so note that color and size are two
31:37
different types of categorical variables i will explain to you in a few moments how they are different now
31:43
let's just start with the size and you can think of it as something like a t-shirt size
31:51
and you know if you have t-shirt sizes these letters really just you know represent an order where you
31:57
can say a t-shirt of size l is bigger than a t-shirt of size m right
32:03
and similarly a t-shirt of size x x l or just xxl
32:10
is bigger than a t-shirt than of size l right so there's an order here so we have m smaller than
32:18
l smaller than x xl and so forth so this is a so-called
32:25
ordinal variable
32:33
so how can we deal with that ordinal variable yeah the problem with ordinal variables
Ordinal variables
32:39
is that we can't just have an algorithm guessing what that means what what m means what l means and stuff like
32:44
that because it can be just an arbitrary letter right so it could be a license plate uh number or
32:50
a letter or something like that so how shall or how can the computer know that this is indeed an order
32:57
variable there's actually no way this is where we as a human have to provide some guidance to the computer
33:02
so i would say the best way for dealing with such order data is really just doing our map approach using the
33:10
pandas data frame so where we define our mapping dictionary and then transform this feature
33:19
so in this case i was assigning the number 2 to m there might be for example an s
33:26
it could be a 1 or something like that i was assigning a 3 to the l and a 5 to the x xl maybe there's an
33:34
xl with size 4. but this is really arbitrary i could also choose numbers
33:40
um like 2 5 and 13 or something like that
33:47
because maybe the size or the difference between m and l is less than the difference between l
33:54
and x l or of course also l and x xl so what i mean is the interval
33:59
between those two and what if we have let's say do ml xl the interval between those two
34:05
doesn't have to be the uh like the interval between l and xl could be a different size
34:10
um so that is something that really depends on the application or on the data set so there's no way
34:17
really um that there can be an automatic way for assigning these numbers and that is
34:22
actually then where a domain expert who knows about the data would come in handy next let's take a
Class labels
34:29
look at the class labels which are another type of categorical data
34:34
namely nominal data so class labels as you know don't have any order even if we
34:40
sometimes have integers like 0 1 2 3 4 5 there is no order implied between the
34:45
class enabled so for class labels we can't say 0 is smaller than 1 and smaller than
34:51
label 2 and so forth there is really no order in the class labels
34:56
so for class labels like categorical data that is nominal that is not ordinal we can use
35:02
the label encoder so the label encoder one thing i forgot
35:07
to mention previously is that for the transformer api
35:16
there's a fit and a transform method however there is also one way you can do
35:21
that in one step and that is calling fit transform so calling fit transform is
35:29
the same as calling fit on let's say on x calling fit on x
35:36
and then immediately afterwards calling transform so fit transform is just a combination
35:44
of fitting and transforming in one step
35:50
so here that is what i'm doing i'm fitting and transforming the class label column so fitting will
36:00
just yeah take a look at what values are present in this column and then it will create its own
36:05
dictionary where the order doesn't matter for example it might it may do that alphabetically
36:12
where class 1 will be mapped to 0 and class 2 will be mapped to 1
36:19
just alphabetically and then i will memorize this mapping this happens when we call fit and in transform it will then transform
36:27
these string labels to integer labels here and uh yeah the label encoder is just
36:32
fine for working with nominal data where there is no order implied
Feature columns
36:38
yes on the previous slide we talked about the class labels as nominal categorical data and we can use
36:43
the label encoder for that because for class labels there is no order implied when we use classifiers
36:50
however if we encounter feature columns that are nominal we may run into problems by just using the
36:56
label encoder so for example consider the feature column color here so for color if we have
37:03
green red and blue as possible values we can't say for example that red
37:10
is greater than green and uh yeah blue is greater than red of course there may be applications of
37:17
that if there are certain rankings that depend on colors of uniforms or something like that but in a general
37:22
case i would say colors there's no order we can't say like one color is better than the other or
37:28
bigger better something like that than the other so we have now a feature column where we don't have an order implied
37:36
if we would use the label encoder it may alphabetically assign integer values for example it may choose
37:43
the 0 for blue the one for green and the 2 for red so we would have something like
37:48
blue green and red and most machine only
37:56
classifiers would then um in for an order here because if you think back of the k nearest neighbor
38:02
classifier it's a distance metric right so if we would have a feature that is zero and a feature that is two
38:10
this distance would be bigger than this distance but why would the distance between blue and
38:15
green be smaller than blue and red for example if there's no order in the columns colors
38:21
so that would be a problem it would be kind of misleading to the machine learning classifier if we would imply an order
38:27
even though there is none
38:33
so one way of avoiding that problem of assigning an order where there is none is using an
38:39
encoding scheme called one hot encoding
38:44
so one hot encoding works as follows it will create a new feature column
38:49
for each possible value in the nominal feature column so if we have the color here there are
38:56
three distinct values so it will create three new feature columns so we have
39:03
blue green and red now as a separate feature column and then it will use the values zeros
39:09
and ones to assign whether the color is present or not so for example in the first training
39:15
example we have the color green so it will assign a one here and a zero to blue and a zero to red
39:21
for let's say the second one here for red this is this one here it would then
39:28
assign a one to red and a zero here and a zero here
39:33
and then lastly for the blue one the blue one um this one here right
39:41
and then zero and zero for these two so when we are using the get dummies
Drop feature columns
39:46
method like on the previous slide by default it would create one feature column for each
39:51
categorical value in the nominal categorical feature column however this creates some redundancy
39:57
right because if i know that the color is not blue
40:03
and it is green i know that it can't be red right or similarly if i know it's not blue and
40:08
not green then it must be red so in that way one column is redundant so we can
40:13
drop one column here for example we can drop this column and we would retain the same
40:19
information because based on the information of these two columns we can infer the other column
40:27
so what we can do then is we can define drop first or we there's also on drop last i think so you can also say
40:33
drop last it doesn't really matter but we can drop one of these feature columns so here this is the same as above without the
40:40
blue column because it's like i said redundant to include blue here
40:46
some machine learning classifiers would also run into problems if we don't drop the columns for example if we would
40:52
use a logistic regression classifier without constraints then we would have a
40:58
problem because we would have a perfect correlation between features and then we would have a
41:04
singular matrix and run into problems with optimization procedure and stuff like that however in this class
41:10
the classifiers we use for example k nearest neighbors decision trees and stuff like that they don't have a problem with
41:16
including an additional column so this one would be just fine however if you think about it that
41:22
way it would just unnecessarily make the computation more expensive if you think
41:27
of k nearest neighbors it would just add another dimension to the distance computation so that way it doesn't hurt to drop one
41:34
feature column right now we may also encounter a scenario where we have missing data which is
41:40
another problem so there's also the missing data problem for example consider this very simple
41:45
toy data set where i have two nands here and then by the way
41:51
it stands for not a number
41:56
and data may be missing for many different reasons so it's usually hard to tell
42:01
what's going on if we don't have further information about how the data was collected so it could be missing for example
42:06
because the measurement was not obtained or there was a mistake in the measurement or there could be other reasons why
42:12
this is not available so that makes it usually very hard to deal with missing data compared to
42:18
other data transformations yeah so here are some naive ways of
Dealing with missing data
42:24
dealing with missing data so if we have a very large data set where for some training examples
42:31
yeah some measurements are missing or corrupted and if there are millions of data points
42:36
and only issues randomly occur with some of them then we can maybe just drop these rows
42:41
because that would be solving our problem if there's no systematic issue with missing data for example if
42:48
we have some minority class and always for this one class
42:53
the data is missing that would be of course unfortunate if we would remove it because then the classifier would never see data
42:59
like that and then if it encounters data from this class in real life
43:04
then yeah weird things might happen however assuming data is just corrupted
43:10
for a small number of instances because there was some data corruption or data loss going on
43:16
then we can maybe just remove those training rules so imagine we have a million training instances and for two
43:23
of them we have some lands here some missing values so why not just removing those so we can do that using
43:30
the drop in a method in pandas so we specify the x's here as zeros over the rows so if there's a
43:37
missing data point it would just remove the rows
43:42
and similarly if we have millions of features and for some of the features um missing
43:50
values occur so let's say we have a very high resolution image like thousands of pixels or millions of
43:57
pixels and for some reason the camera has an issue in one position so there's one or two pixel values that
44:04
are corrupted if you have a large image one or two pixel values usually don't matter that much so in
44:10
that case we can maybe just remove the whole column in in this case so we can do that also using
44:16
pandas the drop n a method and panda so here we specify x is one so it will drop the
44:21
corresponding columns depending on the application and if we
Imputing missing data
44:27
maybe don't want to remove data there's also a way we can impute missing data of course this is always
44:33
like also be taken with a grain of salt you may introduce more harm than doing any
44:38
good by keeping these data points so it has to be decided on a case-by-case basis however just mentioning that things like
44:46
that exist you can for example impute the missing data you can say this is just the average of
44:51
over all the other feature values so you can from cyclic learn use this transformer method called simple imputer and it will
44:59
then impute the missing values that we can specify for example in this case
45:05
the missing values are nands and then we can say which strategy like the mean or median and
45:10
stuff like that so that way it will impute these missing data points
45:17
another technique i can spontaneously think of is just predicting the missing values for example you can
45:23
consider this as a supervised learning problem so what you could do is for example you could regard
45:30
the column with a missing feature as your label column your targets and then
45:38
you can use let's say all the rows for which you don't have missing data
45:43
so you would use these now let me do this differently so this
45:49
one and this one if you combine them this would be your training data of course you would have
45:56
in real life many many more rows so let's say this is your training data and then you can fit
46:02
a regression model on this training data together of course
46:09
with these labels here during training and then after training you have a model
46:15
and then you can use that model that given these features here
46:20
to predict this target value right so you can also train models to predict
46:26
the target values there would be another approach of dealing with that it's probably a better way than just
46:31
doing the average oh yeah i see that is actually it for this video it was already pretty long
46:37
so in the next video we are going to take a look at circuit learn pipelines which combines multiple aspects that we
46:43
talked about so scikit-learn pipelines let us connect on transformers like data scaling methods and
46:50
transformation methods with the classifier and stuff like that so circuit learned pipelines are super
46:56
useful in practice and that is something we will be talking about in the next video

##v31:



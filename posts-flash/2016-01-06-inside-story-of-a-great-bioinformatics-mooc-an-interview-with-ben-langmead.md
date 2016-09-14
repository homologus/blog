---
title: Inside story of a great bioinformatics MOOC (an interview with Ben Langmead)
tags: []
categories:
- blog
---
<!--more-->

Ben Langmead, Computer Science professor at Johns Hopkins University and the
author of popular Bowtie aligner, [developed a bioinformatics MOOC](https://ww
w.youtube.com/watch?v=IzXQVwWYFv4&index=9&list=PL2mpR0RYFQsBiCWVJSvVAO3OJ2t7Dz
oHA) at Coursera that ranked very highly among all online courses (http://www
.langmead-lab.org/online-course-in-top-10/) and got overwhelmingly positive
reviews from the students (https://www.class-central.com/mooc/3433/coursera-
algorithms-for-dna-sequencing). Some of those reviews are listed below.

<iframe width="560" height="315" src="http://www.youtube.com/embed/IzXQVwWYFv4" frameborder="0"> </iframe>

"This course was organized excellently. For a course with a duration of just 4
weeks it covers an amazing amount of required DNA sequencing background
material and algorithms. Lectures were great and practicals were amazing since
they covered coding of algorithms. Course offers plenty of scope for future
learning."

"I have taken six other courses in this JHU Genomics series on Coursera and
many others in Data Science @ JHU, Cybersecurity @ the U of Maryland etc on
Coursera. I think this module is one of the very best I have taken."

"The Python HW programming assignments have all been challenging and fun. The
final one is terrific and getting the virus back from BLAST was a blast -
giving one a taste of the excitement of scientific discovery."

Creating such a successful course is no easy task and requires a lot more work
than just standing in front of a camera and uploading videos in youtube.
Moreover, MOOCs are a bit different from classroom teaching, because all
lectures have to be recorded well before the class, and the professor needs to
anticipate potential sources of confusion before recording the lectures. In
the following interview, professor Langmead provides insight into the entire
process and tells our readers about his future plans.

\-----------------------------------------------------

**What inspired you to do it? Did you get encouragement from your university and colleagues?**

**Langmead:** I have colleagues at Johns Hopkins University (JHU) -- Jeff Leek, Brian Caffo and Roger Peng in particular with extremely popular MOOCs. They were great role models from whom I learned a lot. Jeff Leek in particular was the driving force behind the Coursera specialization in Genomic Data Science (https://www.coursera.org/specializations/genomics) of which my course (https://www.coursera.org/course/ads1) is part. The Computer Science department was also very supportive, allowing me to take time away from classroom teaching to develop the course. 

\-----------------------------------------------------

**Why did you choose Coursera vs EdX?**

**Langmead:** I know little about the relative merits of the platforms. They're probably all fine for my course's content. I use Coursera because that's what JHU professors and staff are most familiar with. 

\-----------------------------------------------------

**How much time did you need to spend to prepare the module? Was it necessary to get other's help regarding technology, etc.?**

**Langmead:** JHU has excellent staff who handle videography and editing. They also do ongoing course maintenance, like rolling the course over each month, recruiting community teaching assistants, etc. That is a huge relief, and I probably would not have attempted the course without that help. 

I estimate 15 minutes of course video content took about 3 hours to prepare on
average. Not very efficient, I admit. I worked from scripts that I prepared
and rehearsed beforehand, which is time consuming. Many other instructors go
into shooting with a coarse outline and then let the words come spontaneously.

The practical sessions were different. For background: some of the videos show
brief pair-programming sessions with my co-instructor and PhD student Jacob
Pritt.

For these, Jacob would already have prepared the code. I might have prepared a
question or two to ask while he's coding, but otherwise those were
spontaneous. In fact, a couple of on-the-fly debugging moments are preserved
in the final videos. Other mistakes were so bad we had to re-do the video. We
favored having some spontaneity to break up the rigidity of the other recorded
lectures.

\-----------------------------------------------------

**How is the experience of teaching remotely?**

**Langmead:** It is highly rewarding. I am impressed with how committed and engaged the online students are. For each class session we create a forum where students can introduce themselves and explain why they're taking the course. The results are fascinating -- they come from all over the world with incredibly diverse backgrounds and diverse reasons for taking the course. It's a very different group of people from the folks I normally see in JHU classrooms. 

\-----------------------------------------------------

**How much was the time commitment to teach the actual course? Did you save time compared to regular classroom?**

**Langmead:** It's hard to compare because the online course covers a fraction of the material covered in the Computational Genomics course I teach at JHU each Fall. But once the online course had run for a few months and we had the chance to iron out kinks and recruit community teaching assistants, it became very little work on an ongoing basis. 

\-----------------------------------------------------

**In a regular classroom, the teacher can see the faces of the students and adjust message accordingly, but there is no such feedback loop for MOOCs. Did you feel that disadvantage? How was the communication with the students in general?**

**Langmead:** When I teach in person, I definitely notice the reactions on students faces. Seeing just one student nodding in agreement gives me a confidence boost. When a student comes to my office hour and explains what they don't understand, that is hugely valuable and usually leads me to change my approach and lecture notes a little. 

Online it is a different story. Not as much information comes across in a
forum post as when talking to a student face to face. But while fidelity may
be lower, throughput is way higher. Even just one or two days after the start
of a session of my MOOC, online students are using the forums to ask great
questions about quizzes and homeworks that are due days or even weeks later.
When I make a mistake (e.g. incorrect numbers in an edit-distance matrix),
students find it! Usually very quickly. The online students benefit a lot from
having these sharp, fast-working students the cohort. I benefit too; I have
thousands of code testers and proofreaders.

\-----------------------------------------------------

**There has been a lot of positive and negative comments on MOOCs. What are your thoughts after going through the entire exercise? 

Specific question in this context -

i) Do you find MOOCs economic from the point of view of teacher, or his
institution?

ii) if MOOCs are so effective, why not replace the classroom lectures with
TVs?**

**Langmead:** I'm skeptical that MOOCs can be a substitute for in-person education. I'm no expert, but I feel that the University environment (e.g. being surrounded by other excellent students, high expectations in the classroom) and incentive structure (e.g. grades that go on a permanent record, the possibility of doing research with professors) is a successful regime for getting a broad range of students to perform at or near their best. Some, but not all, of these things can be recreated in a current-day MOOC. Coursera and the other platforms have done a great job so far; e.g. Coursera has fixed class sessions, which keep the cohort experience mostly intact. But if the goal is to offer an experience comparable to, say, the JHU student experience, that's not something MOOCs can do currently. 

\-----------------------------------------------------

**Specific question in this context - do you think the teaching world will be left with only 15 or 20 super-professors for each subject?**

**Langmead:** Replacing or supplementing classroom lectures with clear videos recorded by other professors can be beneficial. Textbooks are a helpful analogy. Some people are really good at standing in front of a classroom or a camera and explaining concepts clearly; likewise, some textbooks are clearer and more widely used than others. 

I'm excited by the proliferation of recorded lectures and seminars online.
When I need to review a technical concept that is taught at the undergrad
level, I now try youtube first, before picking up a textbook -- even if the
book is on my shelf. There are excellent teachers who post their materials,
including their videos. Some of my recent favorites are Erik Demaine (MIT),
Tim Roughgarden (Stanford), Kayvon Fatahalian (Carnegie Mellon University) and
Yaser Abu-Mostafa (Cal Tech). In Computational Biology, Pavel Pevzner and
Phillip Compeau have excellent videos and MOOCs on Coursera.

\-----------------------------------------------------

**What is next? You can comment on both your own plan and the future of MOOC-based teaching in general.**

**Langmead:** I am considering doing more MOOCs along the lines of "Algorithms for DNA Sequencing". If people have any ideas for what material they would like to see turned into a 4-week online course, please let me know.


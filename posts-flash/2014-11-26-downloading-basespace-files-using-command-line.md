---
title: Downloading Basespace Files using Command Line
tags: []
categories:
- blog
---
Here are the solutions.
<!--more-->

1\. [Heng Li](https://gist.github.com/lh3/54f535b11a9ee5d3be8e) \-

>

References:

<https://support.basespace.illumina.com/knowledgebase/articles/403618-python-
run-downloader>

<https://developer.basespace.illumina.com/docs/content/documentation/rest-api
/api-reference>

Steps:

Follow steps 1-5 in the first link above to acquire access_token. This will
take a while, but you only need to do this once. Never share this token!!

Find the file you want to download. Copy the link, which looks something like:
https://basespace.illumina.com/sample/9804795/files/tree/NA12878-L1_S1_L001_R1
_001.fastq.gz?id=515013503. The "id" is the unique file identifier.

Download the file with: wget -O filename 'https://api.basespace.illumina.com/v
1pre3/files/{id}/content?access_token={token}', where {token} is from step 1
and {id} from step 2.

A final note on security. It seems that the token acquired at step 1 does not
automatically expire (in that case, this really needs improvement), so it is
VERY IMPORTANT NOT to share this token, or others will gain access to all your
data. Step 3 is not secure as others may see your download link with ps -f.

Related seqanswers thread is
[here](http://seqanswers.com/forums/showthread.php?t=47633).

2\. Dariober at the same thread -

> I've used BaseSpaceR to get fastq files via R. (This was while ago).

If I correctly remember and things haven't changed, it's a bit long winded to
get started as you need to get a token. Also it's not enough to have a run
shared with you, the owner of the project has to share the entire project (I
think...). Then something on these lines should work:

`Code:

library(BaseSpaceR)

ACCESS_TOKEN<\- 'dd9...mytoken...43'

PROJECT_ID<\- '123456' ## Get proj ID from url of the project

aAuth<\- AppAuth(access_token = ACCESS_TOKEN)

selProj <\- Projects(aAuth, id = PROJECT_ID, simplify = TRUE)

sampl <\- listSamples(selProj, limit= 1000)

inSample <\- Samples(aAuth, id = Id(sampl), simplify = TRUE)

for(s in inSample){

f <\- listFiles(s, Extensions = ".gz")

print(Name(f))

getFiles(aAuth, id= Id(f), destDir = 'outdir/', verbose = TRUE)

}`

3\. Sbastien Boisvert

[Fetching data from Illumina BaseSpace](http://dskernel.blogspot.com/2012/11
/fetching-data-from-illumina-basespace.html)

4\. Use Illumina API -

Check [here ](http://stackoverflow.com/questions/24144065/download-data-from-
illumina-basespace)and [here](https://github.com/basespace/basespace-python-
sdk).

\---------------------------------------

We tried Heng Li's method and it worked. However, the security concern
mentioned by him is extremely important, because your commands are stored in
the server logs for ever.


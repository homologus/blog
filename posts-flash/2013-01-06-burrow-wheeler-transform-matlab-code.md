---
title: Burrow Wheeler Transform - Matlab Code, Animation
tags: []
categories:
- blog
---
A [very helpful Matlab code](http://schatzlab.cshl.edu/teaching/2012/BWT.m)
written by Michael Schatz got buried within [our daily compilation of
bioinformatics news](http://www.homolog.us/blogs/2012/12/12/twelve-
developments-on-121212/), even though it deserved a full commentary.
<!--more-->

Several months back, we wrote a number of commentaries explaining how Burrows
Wheeler Transform works, and how it was being used in very fast nucleotide
search algorithms (Bowtie, BWT, etc.). You can check them here -

[Finding us in homolog.us](http://www.homolog.us/blogs/2011/10/03/finding-us-
in-homolog-us/)

[Finding us in homolog.us part II](http://www.homolog.us/blogs/2011/10/05
/finding-us-in-homolog-us-part-ii/)

[Finding us in homolog.us III (Search Algorithm and
Indexing)](http://www.homolog.us/blogs/2011/10/17/search-algorithm-and-
indexing/)

We also developed simple animations to show the transform process -

[Burrows Wheeler Transform in
Animation](http://www.homolog.us/blogs/2012/04/03/burrows-wheeler-transform-
in-animation/)

The only missing part was a simple code and [Michael Schatz's Matlab
code](http://schatzlab.cshl.edu/teaching/2012/BWT.m) fits in very well. We
modified his code to work for two examples in our earlier commentaries -
'finding US in HOMOLOG.US' and 'finding TAT in TATATATATA'. If you do not have
Matlab, you can download [open-source
Octave](http://www.gnu.org/software/octave/) to run the following codes.

**Matlab/Octave code for finding US in HOMOLOG.US**

* * *

`

%% BWT construction and exact match

%% Michael Schatz (mschatz@cshl.edu)

%%

%% Here is my most basic / easiest to understand solution. It requires O(n^2)
space,

%% O(n lg n) time to construct the BWT by sorting the strings with sort(), and
O(nm)

%% time to match a query of length m. It is relatively slow and verbose but
shows how

%% the algorithm basically works.

%%

%% (minor modification by homolog.us)

%%

clear all

%% We should find a match of qry in genome at 3 and 4

genome='HOMOLOG.US';

qry='US'

%% initialize a few helper variables

genomedollar=strcat(genome, '$');

l=length(genomedollar);

%% create a table of all cyclic permutations

permutations={};

for i=1:l

permutations{i} = strcat(genomedollar(i:l),genomedollar(1:i-1));

end

%% uncomment to print the permutations

%% permutations

%% sort the cyclic permutations to form the bwm

bwm = sort(permutations);

bwm

%disp('BWM');

%for i=1:l

% disp(bwm(i));

%end

%% initialize the bwt, and extract the last column of the bwm

bwt = zeros(1,1);

for i=1:l

s=bwm{i};

bwt(1,i) = s(l:l);

end

bwt=char(bwt);

%% print the bwt

bwt

%% Before we can search the BWT, count occurrences of each character

%% First create a lookup table so that we can quickly jump from

%% a character ($ACGT) to a position in the table (12345)

bases='$.GHLMOSU';

char2baseidx=zeros(1,255);

blen=length(bases);

for i=1:blen

c=bases(i:i);

char2baseidx(c)=i;

end

%% now count occurences

basecnt=zeros(1,blen);

for i=1:l

c=bwt(i:i);

ci=char2baseidx(c);

basecnt(ci) = basecnt(ci)+1;

end

rowstart=zeros(1,blen)+1;

for i=2:blen

rowstart(i)=rowstart(i-1)+basecnt(i-1);

end

bases

basecnt

rowstart

%% Note we can reconstruct the first column of the BWM from basecnt

%% And we have the last column from the BWT

p=1;

for i=1:blen

for j = 1:basecnt(i)

disp([bases(i), '...', bwt(p:p)]);

p = p+1;

end

end

%% Now look for a query match using LFc

qlen=length(qry);

%% Initialize that the query can be located anywhere in the genome

top=1;

bot=l+1;

%% process the query in reverse order

for i=qlen:-1:1

qc=qry(i);

disp(['Processing i=', num2str(i), ' qc=', qc, ' top=', num2str(top), ' bot=',
num2str(bot)]);

%% if bwt(top) was qc, what would be its rank?

ranktop=1;

for j=1:top-1

if(bwt(j:j)==qc)

ranktop = ranktop+1;

end

end

%% if bwt(bot) was qc, what would be its rank?

rankbot = 1;

for j=1:bot-1

if(bwt(j:j)==qc)

rankbot = rankbot+1;

end

end

disp([' ranktop=', num2str(ranktop), ' rankbot=', num2str(rankbot)])

%% shift the top and bottom pointers

top=rowstart(char2baseidx(qc))+ranktop-1;

bot=rowstart(char2baseidx(qc))+rankbot-1;

disp(['top=', num2str(top), ' bot=', num2str(bot)]);

end

disp(['found exact matches at top=', num2str(top), ' bot=', num2str(bot)]);

%% Now print the coordinate in the original genome

%% For each row in the range,

%% iteratively apply the LF until we reach

%% the beginning of the string ($)

for row=top:bot-1

pos = 1;

currow = row;

qc = bwt(currow:currow);

disp(['looking for occurrence at row=', num2str(currow), ' qc=', qc]);

while(qc ~= '$')

pos = pos+1;

%% count the rank of qc in the row

rowrank=1;

for j=1:currow-1

if (bwt(j)==qc)

rowrank=rowrank+1

end

end

%% now jump to that row

currow=rowstart(char2baseidx(qc))+rowrank-1;

qc = bwt(currow:currow);

disp([' jumping to currow=', num2str(currow), ' rowrank=', num2str(rowrank), '
qc=', qc]);

end

disp(['The occurrence at row=', num2str(row), ' is at pos=', num2str(pos)]);

end

`

* * *

**Matlab/Octave code for finding TAT in TATATATATA**

* * *

`

%% BWT construction and exact match

%% Michael Schatz (mschatz@cshl.edu)

%%

%% Here is my most basic / easiest to understand solution. It requires O(n^2)
space,

%% O(n lg n) time to construct the BWT by sorting the strings with sort(), and
O(nm)

%% time to match a query of length m. It is relatively slow and verbose but
shows how

%% the algorithm basically works.

%%

%% (minor modification by homolog.us)

%%

clear all

%% We should find a match of qry in genome at 3 and 4

genome='TATATATATA';

qry='TAT'

%% initialize a few helper variables

genomedollar=strcat(genome, '$');

l=length(genomedollar);

%% create a table of all cyclic permutations

permutations={};

for i=1:l

permutations{i} = strcat(genomedollar(i:l),genomedollar(1:i-1));

end

%% uncomment to print the permutations

%% permutations

%% sort the cyclic permutations to form the bwm

bwm = sort(permutations);

bwm

%disp('BWM');

%for i=1:l

% disp(bwm(i));

%end

%% initialize the bwt, and extract the last column of the bwm

bwt = zeros(1,1);

for i=1:l

s=bwm{i};

bwt(1,i) = s(l:l);

end

bwt=char(bwt);

%% print the bwt

bwt

%% Before we can search the BWT, count occurrences of each character

%% First create a lookup table so that we can quickly jump from

%% a character ($ACGT) to a position in the table (12345)

bases='$ACGT';

char2baseidx=zeros(1,255);

blen=length(bases);

for i=1:blen

c=bases(i:i);

char2baseidx(c)=i;

end

%% now count occurences

basecnt=zeros(1,blen);

for i=1:l

c=bwt(i:i);

ci=char2baseidx(c);

basecnt(ci) = basecnt(ci)+1;

end

rowstart=zeros(1,blen)+1;

for i=2:blen

rowstart(i)=rowstart(i-1)+basecnt(i-1);

end

bases

basecnt

rowstart

%% Note we can reconstruct the first column of the BWM from basecnt

%% And we have the last column from the BWT

p=1;

for i=1:blen

for j = 1:basecnt(i)

disp([bases(i), '...', bwt(p:p)]);

p = p+1;

end

end

%% Now look for a query match using LFc

qlen=length(qry);

%% Initialize that the query can be located anywhere in the genome

top=1;

bot=l+1;

%% process the query in reverse order

for i=qlen:-1:1

qc=qry(i);

disp(['Processing i=', num2str(i), ' qc=', qc, ' top=', num2str(top), ' bot=',
num2str(bot)]);

%% if bwt(top) was qc, what would be its rank?

ranktop=1;

for j=1:top-1

if(bwt(j:j)==qc)

ranktop = ranktop+1;

end

end

%% if bwt(bot) was qc, what would be its rank?

rankbot = 1;

for j=1:bot-1

if(bwt(j:j)==qc)

rankbot = rankbot+1;

end

end

disp([' ranktop=', num2str(ranktop), ' rankbot=', num2str(rankbot)])

%% shift the top and bottom pointers

top=rowstart(char2baseidx(qc))+ranktop-1;

bot=rowstart(char2baseidx(qc))+rankbot-1;

disp(['top=', num2str(top), ' bot=', num2str(bot)]);

end

disp(['found exact matches at top=', num2str(top), ' bot=', num2str(bot)]);

%% Now print the coordinate in the original genome

%% For each row in the range,

%% iteratively apply the LF until we reach

%% the beginning of the string ($)

for row=top:bot-1

pos = 1;

currow = row;

qc = bwt(currow:currow);

disp(['looking for occurrence at row=', num2str(currow), ' qc=', qc]);

while(qc ~= '$')

pos = pos+1;

%% count the rank of qc in the row

rowrank=1;

for j=1:currow-1

if (bwt(j)==qc)

rowrank=rowrank+1;

end

end

%% now jump to that row

currow=rowstart(char2baseidx(qc))+rowrank-1;

qc = bwt(currow:currow);

%disp([' jumping to currow=', num2str(currow), ' rowrank=', num2str(rowrank),
' qc=', qc]);

end

disp(['The occurrence at row=', num2str(row), ' is at pos=', num2str(pos)]);

end

`

* * *

Enjoy !!


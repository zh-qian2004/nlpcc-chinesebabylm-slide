# P1
Good afternoon, I am Zhiheng Qian, from Shanghai Jiao Tong University. I am here to introduce the first ChineseBabyLM Challenge on behalf of the shared task organisers.
# P2
Modern language models are trained on trillions of words. However, children acquire language from far less input. By early adolescence, a child has been exposed to fewer than 100 million words.
BabyLM aims focus on data efficiency. However, itfocus on English language, and there is no Chinese shared task so far.
# P3
Chinese is a distinct case for data-efficient language modeling. 
It uses a logographic writing system, where characters carry visual, semantic, and phonological information. It has no explicit word boundaries, so models must learn semantic segmentations. It makes extensive use of compounding, so models must learn how characters form words. It also allows relatively flexible word order, so models must capture grammatical relations rather than rely only on fixed surface patterns.
Therefore, we organized the first ChineseBabyLM challenge, a shared task with controlled training data and evaluation across multiple tracks.
# P4
Our challenge evaluates models along three complementary tracks. 

The NLU track measures Chinese syntactic and semantic understanding.

The Cognitive Modeling track asks whether model representations resemble human language representations in the brain. 

The Hanzi track focuses on knowledge specific to the Chinese writing system. 

The challenge consists of open released during development, and hidden tasks released after the model submission deadline. The submitted models will be evaluated on both open and hidden tasks.
# P5
The NLU track consists of zero-shot tasks and supervised fine-tuning tasks.

The open zero-shot tasks is ZhoBLiMP. and the hidden zero-shot task is XCOMPS-ZH.

The open fine-tuning tasks are selected from CLUE; The hidden fine-tuning tasks are C3, a multiple-choice reading-comprehension benchmark, and Diagnostic NLI. 

The Bolded tasks are selected from our works.
# P6
The Cognitive Modeling track contains two human-model alignment tasks from MulCogBench. 
For both tasks, we fit a ridge-regression from model representations to fMRI responses to evaluate the correlation between model representation and brain signal.
The word-level task uses brain responses from 11 participants reading 672 isolated words, while the discourse-level task uses data from 12 participants listening to 60 stories containing more than 52,000 words.
# P7
Hanzi track composes of  Chinese structure and pinyin knowledge tasks, which come from our unpublished work. Both are minimal pair tasks.
In the structure task, the model should understand the radical composition. For example, for example, the outer component of 阁 is 门, not 包. 
In the pinyin task, the model should understand the pronunciation of a Chinese character. For example, it should recognize that 欲 and 芋 have the same initial, final, and tone, while 欲 and 于 differ in tone. 
# P8
There are two key constraints for model training. first, the model should be trained from scratch. Second, there are two options for the training data. The option 1 is, the participant can use the official 102M word training corpus, which is sampled from BabyBabelLM. Or the participants could use a self-compiled corpus with not more than 102M words.
# P9
The table shows the composition of our official training corpus. It mainly consists of child-oriented data and other conversational or speech-like text.
We received 28 models subimissions from 18 teams from 4 different regions. 

Among teams, BabyDragon from University of Chinese Academy of Sciences ranked first overall with 61.49. 
OK的老大 from Fudan University ranked second, while TUM Campus Heilbronn ranked third.

For track winners, YNU-HPCC is the winner of NLU track.
Deepscientist is the winner of cognitive modeling track
BabyDragon is the winner of HANZI track
# P10
We received 28 models subimissions from 18 teams. 
Among teams, BabyDragon from University of Chinese Academy of Sciences ranked first overall with 61.49. 
OK的老大 from Fudan University ranked second, while TUM Campus Heilbronn ranked third.
For track winners, YNU-HPCC is the winner of NLU track.
Deepscientist is the winner of cognitive modeling track
BabyDragon is the winner of HANZI track

# P11
Finally, let me share a few statistics of the submitted models. 

Encoder-only model accounted for 72% of the submissions, while the rest were decoder-only. 

Among the teams that reported parameter counts, six fell between 100 and 150M, while the range extended from 12 million to 800 million. 

In terms of the variance, Hanzi separated systems much more strongly, while Cognitive Modeling scores were tightly compressed
# P12
Thank you for listenining. You can scan the QR codes to reach the shared task homepage and github repository.

# Pre-training and Fine-tuning for Speaker Identification in Novel Dialogue

## Abstract

Identifying the speaker of the dialogue in novels is very important to assign corresponding speakers/voices for audiobook content creation through text-to-speech (TTS), which could largely improve the listening engagement and user experience. However, it is challenging to automatically extract and identify speakers from dialogue context, since the scenario in novel is complicated with many different characters. In this paper, we propose an effective pre-training and fine-tuning pipeline to improve the accuracy of speaker identification in novel dialogue. Specifically, we design several novel pre-training tasks to learn better representations on speaker, dialogue, and their relationships on a large-scale novel dataset, and conduct speaker identification with a cascaded speaker recall and selection model by fine-tuning the pre-trained model respectively. Due to lack of public evaluation set on speaker identification in novel dialogue, we build and release an evaluation set with 41 different Chinese novel chapters to benchmark this task. Experiments show that our method achieves 85.38\% accuracy on this evaluation set, significantly outperforming previous methods. Our evaluation set and TTS demo based on our identified speakers are available at this page.

## Demo Video

The video below is used to show the final effect of our speaker identification system. We used a text-to-speech (TTS) model for speech synthesis, accompanied by sentiment prediction for dialogues. Our main contribution lies in the speaker identification for different dialogues.


       
金粉世家 (Diamond Dust Aristocratic Family)

<audio src="waves/金粉世家.wav" controls="controls">wav</audio>

红楼梦 (The Dream of the Red Chamber) 

<audio src="waves/红楼梦.wav" controls="controls">wav</audio>

水浒传 (Water Margin) 

<audio src="waves/水浒传.wav" controls="controls">wav</audio>


张恨水小说 (Zhang Henshui's Novel) 

<audio src="waves/张恨水小说.wav" controls="controls">wav</audio>

## Test Dataset
Since there is no open-source multi-domain Chinese speaker identification dataset, we select 41 Chinese novel chapters and label them as our evaluation dataset. We provide two kinds of speaker indentification data, namely chapter text and speaker indentification test data, which can be downloaded in the link below:

[chapter text](https://drive.google.com/file/d/1rRVCXCour8DBstN_FxVWR7ZmEsLSwSAi/view?usp=sharing)

[speaker indentification test data](https://drive.google.com/file/d/1MuqeTzu89wmtNwH7i7CebQlp7cvl3OQv/view?usp=sharing)

The speaker identification test data is the annotation data including 2296 pieces of data of 41 Chinese novel chapters. Since a character may have multiple appellations/aliases in the novel, we label two kinds of speaker names, namely primary speaker name and context speaker name. In fine-tuning models, we use context speaker name as label for evaluation and training. Each piece of data consists of the following seven parts:

* dialogue id
* book id
* book name
* dialogue ：target dialogue
* context ： dialogue context
* primary speaker name ： a formal and unique appellation of a character in the novel
* context speaker name ： a appellation or alias of a character that appears in dialogue context

Chapter text contains the text of 41 Chinese novel chapters, and we have used tools to segment the novel text. The dialogue and context from the speaker identification test data can be found in chapter text.

### Part of English test data
       id	text	primary speaker name	context speaker name
       0000000000000	Title: Peter Pan Chapter I. PETER BREAKS THROUGH All children, except one, grow up.	Narration	Narration
       0000000000001	They soon know that they will grow up, and the way Wendy knew was this.	Narration	Narration
       0000000000002	One day when she was two years old she was playing in a garden, and she plucked another flower and ran with it to her mother.	Narration	Narration
       0000000000003	I suppose she must have looked rather delightful, for Mrs. Darling put her hand to her heart and cried,	Narration	Narration
       0000000000004	“Oh, why can’t you remain like this for ever!”	Mrs. Darling	Female
       0000000000005	This was all that passed between them on the subject, but henceforth Wendy knew that she must grow up.	Narration	Narration
       0000000000006	You always know after you are two.	Narration	Narration
       0000000000007	Two is the beginning of the end.	Narration	Narration
       0000000000008	Of course they lived at 14, and until Wendy came her mother was the chief one.	Narration	Narration
       0000000000009	She was a lovely lady, with a romantic mind and such a sweet mocking mouth.	Narration	Narration
       0000000000010	Her romantic mind was like the tiny boxes, one within the other, that come from the puzzling East, however many you discover there is always one more; and her sweet mocking mouth had one kiss on it that Wendy could never get, though there it was, perfectly conspicuous in the right-hand corner.	Narration	Narration
       0000000000011	The way Mr. Darling won her was this: the many gentlemen who had been boys when she was a girl discovered simultaneously that they loved her, and they all ran to her house to propose to her except Mr. Darling, who took a cab and nipped in first, and so he got her.	Narration	Narration
       0000000000012	He got all of her, except the innermost box and the kiss.	Narration	Narration
       0000000000013	He never knew about the box, and in time he gave up trying for the kiss.	Narration	Narration
       0000000000014	Wendy thought Napoleon could have got it, but I can picture him trying, and then going off in a passion, slamming the door.	Narration	Narration
       0000000000015	Mr. Darling used to boast to Wendy that her mother not only loved him but respected him.	Narration	Narration
       0000000000016	He was one of those deep ones who know about stocks and shares.	Narration	Narration
       0000000000017	Of course no one really knows, but he quite seemed to know, and he often said stocks were up and shares were down in a way that would have made any woman respect him.	Narration	Narration
       0000000000018	Mrs. Darling was married in white, and at first she kept the books perfectly, almost gleefully, as if it were a game, not so much as a Brussels sprout was missing; but by and by whole cauliflowers dropped out, and instead of them there were pictures of babies without faces.	Narration	Narration
       0000000000019	She drew them when she should have been totting up.	Narration	Narration
       0000000000020	They were Mrs. Darling’s guesses.	Narration	Narration
       0000000000021	Wendy came first, then John, then Michael.	Narration	Narration
       0000000000022	For a week or two after Wendy came it was doubtful whether they would be able to keep her, as she was another mouth to feed.	Narration	Narration
       0000000000023	Mr. Darling was frightfully proud of her, but he was very honourable, and he sat on the edge of Mrs. Darling’s bed, holding her hand and calculating expenses, while she looked at him imploringly.	Narration	Narration
       0000000000024	She wanted to risk it, come what might, but that was not his way; his way was with a pencil and a piece of paper, and if she confused him with suggestions he had to begin at the beginning again.	Narration	Narration
       0000000000025	“Now don’t interrupt,”	Mr. Darling	Male
       0000000000026	he would beg of her.	Narration	Narration
       0000000000027	“I have one pound seventeen here, and two and six at the office; I can cut off my coffee at the office, say ten shillings, making two nine and six, with your eighteen and three makes three nine seven, with five naught naught in my cheque-book makes eight nine seven—who is that moving?—eight nine seven, dot and carry seven—don’t speak, my own—and the pound you lent to that man who came to the door—quiet, child—dot and carry child—there, you’ve done it!—did I say nine nine seven?	Mr. Darling	Mr. Darling
       0000000000028	yes, I said nine nine seven; the question is, can we try it for a year on nine nine seven?”	Mr. Darling	Mr. Darling
       0000000000029	“Of course we can, George,”	Mrs. Darling	Mrs. Darling
       0000000000030	she cried.	Narration	Narration
       0000000000031	But she was prejudiced in Wendy’s favour, and he was really the grander character of the two.	Narration	Narration

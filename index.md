# Pre-training and Fine-tuning for Speaker Identification in Novel Dialogue

## Abstract

Identifying the speaker of the dialogue in novels is very important to assign corresponding speakers/voices for audiobook content creation through text-to-speech (TTS), which could largely improve the listening engagement and user experience. However, it is challenging to automatically extract and identify speakers from dialogue context, since the scenario in novel is complicated with many different characters. In this paper, we propose an effective pre-training and fine-tuning pipeline to improve the accuracy of speaker identification in novel dialogue. Specifically, we design several novel pre-training tasks to learn better representations on speaker, dialogue, and their relationships on a large-scale novel dataset, and conduct speaker identification with a cascaded speaker recall and selection model by fine-tuning the pre-trained model respectively. Due to lack of public evaluation set on speaker identification in novel dialogue, we build and release an evaluation set with 41 different Chinese novel chapters to benchmark this task. Experiments show that our method achieves 85.38\% accuracy on this evaluation set, significantly outperforming previous methods. Our evaluation set and TTS demo based on our identified speakers are available at this page.

## Demo Video

The video below is used to show the final effect of our speaker identification system. We used a text-to-speech (TTS) model for speech synthesis, accompanied by sentiment prediction for dialogues. Our main contribution lies in the speaker identification for different dialogues.

<audio loop="loop" controls="controls">
       <source src="https://github.com/NovelSpkIdentify/NovelSpkIdentify.github.io/blob/main/waves/%E6%9C%89%E9%97%B4%E6%96%87%E5%BA%93%EF%BC%9A%E9%87%91%E7%B2%89%E4%B8%96%E5%AE%B6%20%E7%AC%AC49%E5%9B%9E.wav" type="audio/mp3"></source></audio>
       
<audio src="waves/有间文库：金粉世家 第49回.wav" controls="controls">wav</audio>
       

## Test Dataset
We provide two kinds of speaker indentification data, namely chapter text and speaker indentification test data, which can be downloaded in the link below:

[chapter text](https://drive.google.com/file/d/1rRVCXCour8DBstN_FxVWR7ZmEsLSwSAi/view?usp=sharing)

[speaker indentification test data](https://drive.google.com/file/d/1MuqeTzu89wmtNwH7i7CebQlp7cvl3OQv/view?usp=sharing)

The speaker identification test data is the annotation data including 2296 pieces of data of 41 Chinese novel chapters. Each piece of data consists of the following seven parts:

* dialogue id
* book id
* book name
* dialogue ：target dialogue
* context ： dialogue context
* primary speaker name ： a formal and unique appellation of a character in the novel
* context speaker name ： a appellation or alias that appears in dialogue context

Chapter text contains the text of 41 Chinese novel chapters, and we have used tools to segment the novel text.

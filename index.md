# Pre-training and Fine-tuning for Speaker Identification in Novel Dialogue

## Abstract

Identifying the speaker of the dialogue in novels is very important to assign corresponding speakers/voices for audiobook content creation through text-to-speech (TTS), which could largely improve the listening engagement and user experience. However, it is challenging to automatically extract and identify speakers from dialogue context, since the scenario in novel is complicated with many different characters. In this paper, we propose an effective pre-training and fine-tuning pipeline to improve the accuracy of speaker identification in novel dialogue. Specifically, we design several novel pre-training tasks to learn better representations on speaker, dialogue, and their relationships on a large-scale novel dataset, and conduct speaker identification with a cascaded speaker recall and selection model by fine-tuning the pre-trained model respectively. Due to lack of public evaluation set on speaker identification in novel dialogue, we build and release an evaluation set with 41 different Chinese novel chapters to benchmark this task. Experiments show that our method achieves 85.38\% accuracy on this evaluation set, significantly outperforming previous methods. Our evaluation set and TTS demo based on our identified speakers are available at this page.

##Demo Video

The video below is used to show the final effect of our speaker identification system. We used a text-to-speech (TTS) model for speech synthesis, accompanied by sentiment prediction for dialogues. Our main contribution lies in the speaker identification for different dialogues.

<iframe name="music" src="http://music.163.com/song/media/outer/url?id=1382359170.mp3" marginwidth="1px" marginheight="20px" width=100% height="80px" frameborder=1 　scrolling="yes">
</iframe>

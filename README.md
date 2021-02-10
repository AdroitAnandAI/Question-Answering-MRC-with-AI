# Machine Reading Comprehension with BIDAF 

## Enabling Question Answering Capability for Chatbots


<p align="center">
    <img src="https://github.com/AdroitAnandAI/Question-Answering-MRC-with-AI/blob/main/mcBot.gif">
</p>

This is an easy-to-use repository extended from [here](https://github.com/priya-dwivedi/cs224n-Squad-Project) for below:

1) The **Reading Comprehension capability of the model is channelled as a chatbot module.**
2) All the **dependancies are solved & the image is pushed in Docker Hub.** You can download the image and easily run the code in this repo.
3) Some **modifications and bug fixes** in the handling of input and output is also done.


### How to use?


* Run ```./get_started.sh```  to download SQuAD dataset and GloVE Vectors (glove.6B.100d.txt)

* **Download from the model checkpoint files** from [here](https://drive.google.com/file/d/1E_vMoBNA77a2vVbCKB3K-n5TY80aJtAv/view?usp=sharing) and extract to this folder: experiments/bidaf_best/best_checkpoint. 


* **Pull the docker from Docker Hub** using the command below.
```
sudo docker pull 06021981/mrc-factoid:latest
```
* Change directory to the root github directory and **execute the command below** to trigger bot.
```
sudo docker run -it -v $PWD:/tmp -w /tmp 06021981/mrc-factoid:latest python code/mcBot.py --experiment_name=bidaf_best --dropout=0.15 --batch_size=60 --hidden_size_encoder=150 --embedding_size=100 --do_char_embed=False --add_highway_layer=True --rnet_attention=False --bidaf_attention=True --answer_pointer_RNET=False --smart_span=True --hidden_size_modeling=150 --mode=official_eval --json_in_path=data/qns.json --ckpt_load_dir=experiments/bidaf_best/best_checkpoint
```



## References

https://github.com/priya-dwivedi/cs224n-Squad-Project
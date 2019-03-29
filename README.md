# MARS: Motion-Augmented RGB Stream for Action Recognition

By Nieves Crasto, Philippe Weinzaepfel, Karteek Alahari and Cordelia Schmid

MARS is a strategy to learn a stream that takes only RGB frames as input
but leverages both appearance and motion information from them. This is
achieved by training a network to minimize the loss between its features and
the Flow stream, along with the cross entropy loss for recognition.
For more details, please refer to our [CVPR 2019 paper]() and our [website]().

We release the testing code along trained models. We will release the training code 
in due course of time.

#### Performance on Kinetics400

Method 												| Stream   | Pretrain | Acc   |
:------												|:-----   :|:-----   :|:-----:|
[I3D](https://arxiv.org/pdf/1705.07750.pdf)			| RGB      |ImageNet  | 71.1  |
[ResNext101](https://arxiv.org/pdf/1711.09577.pdf)	| RGB      |none      | 65.1  |
[R(2+1)D](https://arxiv.org/pdf/1711.11248.pdf)	    | RGB      |Sport-1M  | 74.3  |
[S3D-G](https://arxiv.org/pdf/1712.04851.pdf)		| RGB      |ImageNet  | 74.7  | 
[NL-I3D](https://arxiv.org/pdf/1711.07971.pdf)		| RGB      |ImageNet  |**77.7**|
**MARS**                   							| RGB      | none     |  72.7 |
**MARS+RGB**               							| RGB      | none     |  74.8 |
[I3D](https://arxiv.org/pdf/1705.07750.pdf)			| RGB+Flow | ImageNet |  74.2 |     
[R(2+1)D](https://arxiv.org/pdf/1711.11248.pdf)		| RGB+Flow | Sports-1M| 75.4  |
[S3D-G](https://arxiv.org/pdf/1712.04851.pdf)		| RGB+Flow | ImageNet | 77.2  |
**MARS+RGB+Flow**		          					| RGB+Flow |  none    | 74.9  |

#### Performance om HMDB51, UCF101 and SomethingSomethingv1

|Method 													| Streams | Pretrain | UCF101 | HMDB51 | Something Somethingv1|
:------													   :|:-----   |:-----   :|:----- :|:----- :|:-----                |
[TRN](https://arxiv.org/pdf/1711.08496.pdf)                 |RGB      |none      | ---    | ---    | 34.4                 |
[MFNet](https://arxiv.org/pdf/1807.10037.pdf)   			|RGB      |none      | ---    | ---    | 43.9       |
[I3D](https://arxiv.org/pdf/1705.07750.pdf)					|RGB      |ImNet+Kin | 95.6   | 74.8   | ---        |
[ResNext101](https://arxiv.org/pdf/1711.09577.pdf)			|RGB      |Kinetics  | 94.5   | 70.1   | ---    	|
[S3D-G](https://arxiv.org/pdf/1712.04851.pdf)         		|RGB      |ImNet+Kin | 96.8   | 75.9   | 48.2		|
[R(2+1)D](https://arxiv.org/pdf/1711.11248.pdf)       		|RGB      |Kinetics  | 96.8   | 74.5   | ---        |
**MARS**                      								|RGB      |Kinetics  | 97.4   | 79.3   | 48.7		|
**MARS+RGB**                  								|RGB      |Kinetics  |**97.6**|**79.5**|**51.7**	|
[2-stream](https://arxiv.org/pdf/1406.2199.pdf)				|RGB+Flow |ImageNet  | 88.0   | 59.4   | --- 		|
[TRN](https://arxiv.org/pdf/1711.08496.pdf)					|RGB+Flow |none      | ---    | ---    | 42.0		|
[I3D](https://arxiv.org/pdf/1705.07750.pdf)             	|RGB+Flow |ImNet+Kin |**98.0**|**80.7**| ---		|
[R(2+1)D](https://arxiv.org/pdf/1711.11248.pdf)				|RGB+Flow |Kinetics  |  97.3  | 78.7   | --- 		|
[OFF](https://arxiv.org/pdf/1711.11152.pdf)					|RGB+Flow |none      | 96.0   | 74.2   | --- 		|
**MARS+RGB+Flow**            								|RGB+Flow |Kinetics  |**98.1**|**80.9**|**53.0**	|

## Citing MARS

## Contents
1. [Requirements](#requirements)
2. [Datasets](#datasets)
3. [Models](#models)
4. [Testing](#testing)

## Requirements
* Python3

* [Pytorch 1.0](https://pytorch.org/get-started/locally/)

```
conda install pytorch torchvision cudatoolkit=9.0 -c pytorch
```



## Datasets
### Kinetics400

* The datsets and splits can be downloaded from [here]().

* To extract frames from videos 

```
python 
```

* The list of videos used for training and validation can be found here

* To extract optical flows from frames (coming soon ...)

### UCF101

* The datsets and splits can be downloaded from [here](https://www.crcv.ucf.edu/data/UCF101.php).

* To extract frames from videos 

```
python utils1/extract_frames.py path_to_video_files path_to_extracted_frames 
```

* To extract optical flows from frames (coming soon ...)

### HMDB51

* The datsets and splits can be downloaded from [here](http://serre-lab.clps.brown.edu/resource/hmdb-a-large-human-motion-database/#Downloads).

* To extract frames from videos 

```
python utils1/extract_frames.py path_to_video_files path_to_extracted_frames 
```

* To extract optical flows from frames (coming soon ...)

### SomethingSomethingv1

* The datsets and splits can be downloaded from [here](https://20bn.com/datasets/something-something/v1).

* To extract optical flows from frames (coming soon ...)

## Models

Trained models can be found here. The names of the models are in the form of 

```
stream_dataset_frames.pth     

RGB_Kinetics_16f.pth indicates --modality RGB --dataset Kinetics --sample_duration 16
```
## Testing script




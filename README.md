# TinyTiny Multimodal

a tiny vision language model

## project goals

Build a high-quality, low-hallucination vision language model small enough to
run on an edge device without a GPU.

## moondream0

Initial prototype built using SigLIP, Phi-1.5, and the LLaVa training dataset.
The model is for research purposes only, and is subject to the Phi and LLaVa
license restrictions.

**Examples**

| Image | Examples |
| --- | --- |
| ![](assets/demo-1.jpg) | **What is the title of this book?**<br>The Little Book of Deep Learning<br>Author: Francois Flaubert<br><br>**What can you tell me about this book?**<br>The book in question is a small paperback titled "The Little Book of Deep Learning." It appears to be a guide or reference for those interested in deep learning, as the title suggests. The book is likely to be helpful for individuals who are new to the field or looking to expand their knowledge in this area. The image shows the book being held by a person, possibly a reader or a professional in the field.<br><br>**What is the person holding?**<br> The person is holding a book, which is titled "The Little Book of Deep Learning." |
| ![](assets/demo-2.jpg) | **What type of food is the girl holding?**<br>The girl is holding a sandwich.<br><br>**What color is the woman's hair?**<br>The woman's hair is white.<br><br>**What is the girl doing in the image?**<br>The girl in the image is eating a sandwich, specifically a hamburger, while sitting at a table. |
| ![](assets/demo-3.jpg) | **What color is the train?**<br>The train is red.<br><br>**What is the bus doing in the image?**<br>The bus in the image is traveling down a city street, passing by tall buildings and driving under a street light.<br><br>**What kind of public transportation is in the image?**<br>The image features a red light-rail train, which is a type of public transportation. |
| ![](assets/demo-4.jpg) | **What is the girl looking at?**<br>The girl is looking at her reflection in a mirror.<br><br>**What color is the woman's hair?**<br>The woman has black hair.<br><br>**What is the woman doing in the mirror?**<br>The woman is looking at herself in the mirror, possibly adjusting her hair or makeup. |
| ![](assets/demo-5.jpg) | **What might be the reason for the dog's aggressive behavior?**<br>The dog's aggressive behavior could be attributed to the fact that it is being bitten by a person, which is a form of animal abuse. The dog's eyes are red, and it appears to be growling, which are signs of fear or pain. The aggressive behavior might be a result of the dog's attempt to protect itself or its owner from the perceived threat. It is essential to address such behavior in dogs to ensure their well-being and prevent potential harm to both the dog and the person involved.<br><br>**What kind of dog is in the picture?**<br>The dog in the picture is a Chihuahua.<br><br>**What color is the dog?**<br>The dog is black and white. |
|

 **Usage**
Clone this repository and install the dependencies:

```bash 
git clone https://github.com/vikhyat/moondream.git
cd moondream 
```

```bash
pip install -r requirements.txt
```

Use the `engine.py` script to run the model on CPU:

```bash
python engine.py --image [IMAGE_PATH] [--interactive]
```

When the `--interactive` flag is not set, the script will predict three questions and try
to answer them.

```yaml
--2024-01-04 14:06:31--  https://raw.githubusercontent.com/vikhyat/moondream/main/assets/demo-1.jpg
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.109.133, 185.199.108.133, 185.199.110.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.109.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 284680 (278K) [image/jpeg]
Saving to: ‘demo-1.jpg’

demo-1.jpg          100%[===================>] 278.01K  --.-KB/s    in 0.003s  

2024-01-04 14:06:32 (81.8 MB/s) - ‘demo-1.jpg’ saved [284680/284680]

Fetching 12 files: 100% 12/12 [00:00<00:00, 26786.40it/s]
> what is this ?
The image features a person holding a book titled "The Little Book of Deep Learning" on a balcony. The balcony is located outside, with a view of a building in the background. The person appears to be enjoying the outdoor setting while reading the book.

> what does that book entail?
The book is titled "The Little Book of Deep Learning" and is written by French author Franco Florits. It is a comprehensive guide to deep learning, covering various aspects and techniques of machine learning and artificial intelligence. The book is designed to be accessible to both beginners and experienced professionals, providing practical insights and examples to help readers understand and apply deep learning concepts in their work.
```

**Limitations**

* The model may generate inaccurate statements.
* It may struggle to adhere to intricate or nuanced instructions.
* It is primarily designed to understand English. Informal English, slang, and
  non-English languages may not work well.
* The model may not be free from societal biases. Users should be aware of this
  and exercise caution and critical thinking when using the model.
* The model may generate offensive, inappropriate, or hurtful content if it is
  prompted to do so.

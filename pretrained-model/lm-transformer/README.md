# Seq2Seq-Bahasa

Provide T5-like using Tensor2Tensor framework.

**This directory is very lack of comments, understand Tensorflow, Tensorflow estimator, Tensorflow Dataset really helpful**.

## Table of contents
  * [Objective](#objective)
  * [Acknowledgement](#acknowledgement)
  * [Download](#download)
  * [Test](#test)
  * [Citation](#citation)
  * [Donation](#donation)

## Objective

1. Provide alternative Seq2Seq model like T5. We use Tensor2Tensor transformer model.

## Acknowledgement

Thanks to [Im Big](https://www.facebook.com/imbigofficial/), [LigBlou](https://www.facebook.com/ligblou), [Mesolitica](https://mesolitica.com/), [KeyReply](https://www.keyreply.com/) and [TensorFlow Research Cloud](https://www.tensorflow.org/tfrc) for sponsoring AWS, Google and GPU clouds to train XLNET for Bahasa.

## How-to

1. Download [sp10m.cased.t5.model](../preprocess/sp10m.cased.t5.model) and [sp10m.cased.t5.vocab](../preprocess/sp10m.cased.t5.vocab).

2. Run all prepare notebooks in [prepare](prepare).

3. Generate tfrecords,

```bash
cd prepare
python3 t2t-gcs-dumping.py
python3 t2t-gcs.py
```

4. Upload to GCS if use TPU, [prepare/upload-gcs.ipynb](prepare/upload-gcs.ipynb).

5. Run training session,

**If multiGPUs,**

BASE model,
```bash
python3 b2b-base.py
```

SMALL model,
```bash
python3 t2t-small.py
```

**If TPU**,

BASE model,
```bash
python3 b2b-base-tpu.py
```

SMALL model,
```bash
python3 t2t-small-tpu.py
```

## Download

1. **BASE**, last update 9th September 2020, [seq2seq-base-500k-09-09-2020.tar.gz](https://f000.backblazeb2.com/file/malaya-model/bert-bahasa/seq2seq-base-500k-09-09-2020.tar.gz)

Tensorboard, https://tensorboard.dev/experiment/vZgJmvPXTVGDkWLx8hEk7Q/

2. **SMALL**, last update 15th September 2020, [seq2seq-small-500k-15-09-2020.tar.gz](https://f000.backblazeb2.com/file/malaya-model/bert-bahasa/seq2seq-base-500k-15-09-2020.tar.gz)

Tensorboard, https://tensorboard.dev/experiment/QpojYycdQNevKJeVfzF2XQ/

## Test

BASE model, run [t2t-base.ipynb](t2t-base.ipynb).

## Citation

1. Please citate the repository if use these checkpoints.

```
@misc{Malaya, Natural-Language-Toolkit library for bahasa Malaysia, powered by Deep Learning Tensorflow,
  author = {Husein, Zolkepli},
  title = {Malaya},
  year = {2018},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/huseinzol05/malaya}}
}
```

2. Please at least email us first before distributing these checkpoints. Remember all these hard workings we want to give it for free.
3. What do you see just the checkpoints, but nobody can see how much we spent our cost to make it public.

## Donation

<a href="https://www.patreon.com/bePatron?u=7291337"><img src="https://static1.squarespace.com/static/54a1b506e4b097c5f153486a/t/58a722ec893fc0a0b7745b45/1487348853811/patreon+art.jpeg" width="40%"></a>

Or, One time donation without credit card hustle, **7053174643, CIMB Bank, Husein Zolkepli**
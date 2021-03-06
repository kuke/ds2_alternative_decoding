# ds2_alternative_decoding

Alternative way of CTC decoding: don't use external scoring function during beam search, instead using the external score in reranking candidate results.

**How to Run**

Replace the same files in [Deep Speech 2 Project](https://github.com/PaddlePaddle/models/tree/develop/deep_speech_2) with these two files, then run like 
```
python infer.py --use_gpu=False --alpha=1 --beta=1 --num_results_per_sample=5
```

**Output example**

```
Target Transcription:	yet these thoughts affected hester prynne less with hope than apprehension
-61.860616 -14.303021 -57.557594  10.000000 :	yet these thoughtsoftected hester prin less with hope than aprehenchen
-62.019461 -14.461867 -57.557594  10.000000 :	yet these thoughtsoftected hester prin less with hope than aprehencien
-62.160614 -14.603020 -57.557594  10.000000 :	yet these thoughtsoftected hester prin less with hope than aprehencen
-62.173969 -14.616374 -57.557594  10.000000 :	yet these thoughtsoftected hester prin less with hope than apprehenchen
-63.441821 -13.278597 -61.163223  11.000000 :	yet these thoughts oftected hester prin less with hope than aprehenchen
```

Output schema: {total score} {log probability of beam search} {language model score} {word count} : result

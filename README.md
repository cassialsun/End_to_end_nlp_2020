# End_to_end_nlp_2020
エンドツーエンドのロングテキスト要約モデルです。

-------------------------------------

Tensorflow 1.14 + Keras 2.3.1 + Bert4keras 0.9.7

Windowsなら，Bert4keras ＞＝　0.9.8

-------------------------------------

次のコードはsnippets.pyで相関経路構成を修正してから実行されます。

-------------------------------------

トレーニングコード:

#! /bin/bash

python extract_convert.py
python extract_vectorize.py

for ((i=0; i<15; i++));
    do
        python extract_model.py $i
    done

python seq2seq_convert.py
python seq2seq_model.py

-------------------------------------

予測コード：

from final import *
summary = predict(text, topk=3)
print(summary)

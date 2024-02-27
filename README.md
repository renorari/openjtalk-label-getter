# OpenJTalk label getter
OpenJTalkで音声合成する際に得られるラベルを取得します。
音素ラベルとフルコンテキストラベルに対応しています。

## Requirements
```bash
sudo apt-get install -y open-jtalk open-jtalk-mecab-naist-jdic hts-voice-nitech-jp-atr503-m001
```

## Install
```bash
pip install git+https://github.com/renorari/openjtalk-label-getter
```

## Usage
```bash
# 音素ラベル
openjtalk_label_getter こんにちは --output_type phoneme
"""
0 1600000 sil
1600000 2400000 k
2400000 3550000 o
3550000 4200000 N
4200000 4500000 n
4500000 5650000 i
5650000 6550000 ch
6550000 7550000 i
7550000 7900000 w
7900000 10050000 a
10050000 11650000 sil
"""

# フルコンテキストラベル
python openjtalk_label_getter/__init__.py こんにちは --output_type full_context_label
"""
0 1600000 xx^xx-sil+k=o/A:xx+xx+xx/B:xx-xx_xx/C:xx_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:xx_xx#xx_xx@xx_xx|xx_xx/G:5_5%0_xx_xx/H:xx_xx/I:xx-xx@xx+xx&xx-xx|xx+xx/J:1_5/K:1+1-5
1600000 2400000 xx^sil-k+o=N/A:-4+1+5/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
2400000 3550000 sil^k-o+N=n/A:-4+1+5/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
3550000 4200000 k^o-N+n=i/A:-3+2+4/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
4200000 4500000 o^N-n+i=ch/A:-2+3+3/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
4500000 5650000 N^n-i+ch=i/A:-2+3+3/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
5650000 6550000 n^i-ch+i=w/A:-1+4+2/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
6550000 7550000 i^ch-i+w=a/A:-1+4+2/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
7550000 7900000 ch^i-w+a=sil/A:0+5+1/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
7900000 10050000 i^w-a+sil=xx/A:0+5+1/B:xx-xx_xx/C:09_xx+xx/D:xx+xx_xx/E:xx_xx!xx_xx-xx/F:5_5#0_xx@1_1|1_5/G:xx_xx%xx_xx_xx/H:xx_xx/I:1-5@1+1&1-1|1+5/J:xx_xx/K:1+1-5
10050000 11650000 w^a-sil+xx=xx/A:xx+xx+xx/B:xx-xx_xx/C:xx_xx+xx/D:xx+xx_xx/E:5_5!0_xx-xx/F:xx_xx#xx_xx@xx_xx|xx_xx/G:xx_xx%xx_xx_xx/H:1_5/I:xx-xx@xx+xx&xx-xx|xx+xx/J:xx_xx/K:1+1-5
"""
```

## LICENSE
[MIT License](./LICENSE)

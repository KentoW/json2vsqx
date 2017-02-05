# json2vsqx.py
##概要
PythonでJSON形式の何かかからVOCALOID(VSQXファイル)を作成するスクリプト．
##使い方
Python2で動作．
tickが時間(480が1拍)．
note_numが音の高さ．
lyricsにはひらがなを入れる．
```python
# Sample code.
data = {u'tracks': 1, 
    u'resolution': 480, 
    u'stream': [{u'velocity': 64, u'tick': 1920, u'sub_type': u'noteOn', u'channel': 0, u'note_num': 68}, 
    {u'velocity': 0, u'tick': 480, u'sub_type': u'noteOff', u'channel': 0, u'note_num': 68, u'lyrics': 'み'}, 
    {u'velocity': 64, u'tick': 0, u'sub_type': u'noteOn', u'channel': 0, u'note_num': 70}, 
    {u'velocity': 0, u'tick': 240, u'sub_type': u'noteOff', u'channel': 0, u'note_num': 70, u'lyrics': 'く'}, 
    {u'velocity': 64, u'tick': 0, u'sub_type': u'noteOn', u'channel': 0, u'note_num': 66}, 
    {u'velocity': 0, u'tick': 960, u'sub_type': u'noteOff', u'channel': 0, u'note_num': 66, u'lyrics': 'で'}, 
    {u'velocity': 64, u'tick': 0, u'sub_type': u'noteOn', u'channel': 0, u'note_num': 71}, 
    {u'velocity': 0, u'tick': 480, u'sub_type': u'noteOff', u'channel': 0, u'note_num': 71, u'lyrics': 'す'}, 
    ], 
    u'format': 1}

doc = json2vsqx(data)
print(doc.toprettyxml('', '', 'utf-8'))
```
コマンドライン実行例
```unix
python json2vsqx.py > sample.vsqx
```

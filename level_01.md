# このページの説明
このページでは以下のエラーの対処法を掲載中です
[syntax error](#pos1)
## <a name ="pos1">ParseError syntax error</a>
### セミコロン忘れ
```c
public function onLoad() {
  $this->getLogger()->info("起動しました")
}
```  
結果  
`
ParseError: "syntax error, unexpected '}'" (EXCEPTION) in "ChatChannel/src/famima65536/chatchannel/Main" at line 3
`

この例でいうと`unexpected '}'`となっているため、エラーの原因の文字は *}* 。  
`in "ChatChannel/src/famima65536/chatchannel/Main"`から、そのエラーがあるファイルの場所がわかります。  
最後に`line 3`と書かれているため、3行目にエラーがあることが読み取れました。  

ですが今回はこの文字が原因ではなく、セミコロン(;)がないことによってエラーが出ています。  

修正後のコード  
```c
public function onLoad() {
  $this->getLogger()->info("起動しました");
}
```
このように文法のエラーであるsyntax errorは行の前後に問題があることが多いです。  
ほかの例も見てみましょう。  

### 括弧の閉じ忘れ
```c
public function onLoad() {
  $this->getLogger()->info("起動しました";
}
```  
結果  
`ParseError: "syntax error, unexpected ';', expecting ',' or ')'" (EXCEPTION) in "ChatChannel/src/famima65536/chatchannel/Main" at line 2`  

この二回でわかった人もいるかもしれませんがsyntax errorは問題の場所の次の文字で発生することが多いです。  
この場合は括弧)を閉じ忘れています。  

修正後のコード
```c
public function onLoad() {
  $this->getLogger()->info("起動しました");
}
```  

## ParseError syntax error
### 例
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

執筆中...

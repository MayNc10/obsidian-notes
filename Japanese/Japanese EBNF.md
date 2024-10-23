```ebnf
Text ::= <Sentence>+
Sentence ::= (<Noun Phrase>　は)? <Verb Phrase> か? <Period> 
Period ::= 。
```

```ebnf
Noun Phrase ::= <Name> <Honorific>?
       | Ku(<Adjective>)* <Adjective>　<Noun Phrase>
       | Noun

where Ku(x) conjugates x to Ku form
```



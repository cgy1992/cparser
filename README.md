#PyCParser

###Copyright (c) 2016 Fedor Zaytsev

##About
The aim of this project is to create pseudo parser for C language. There are several features of this parser:

* Parser skip all preprocessor directives. As a result of this it do not build symbol table and cannot say is identificator is defined type or not.
* Parser saves all comments. Each comment appends to the parent node.
* Uses grammar for C11 (see grammar.txt for more)

##Fast start
To test program you can execute following command to generate AST tree for test file:
```
git clone https://github.com/rusphantom/cparser.git
cd cparser/
python3 ./cparser.py ./tests/bin2hex_c
```

##How to use
* lexer.py file contains lexer which transforms C code as string to list of lexer.Lexem objects.
* analyzer.py file contains Analyzer object which transform list of lexer.Lexem to AST tree. analyzer.Analyzer object takes lexer.Lexer in constructor. To generate tree call parse() method.
* Node.py file contains Node object which is element in AST tree.
* To generate full AST tree with all nodes call debug.printNode( ast_tree ). To skip garbage nodes call debug.printNodeWithSkip( ast_tree )


##TODO
* Add support of '\' symbol to lexer
* Use first sets


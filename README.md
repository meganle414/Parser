# Parser

To make your parser build an abstract-syntax tree, you must add new productions, declarations, and actions to minim.cup. You will need to decide, for each nonterminal that you add, what type its associated value should have. Then you must add the appropriate nonterminal declaration to the specification. For most nonterminals, the value will either be some kind of tree node (a subclass of ASTnode) or a LinkedList of some kind of node (use the information in ast.java to guide your decision). Note that you cannot use parameterized types for the types of nonterminals; so if the translation of a nonterminal is a LinkedList of some kind of node, you will have to declare its type as just plain LinkedList.

You must also add actions to each new grammar production that you add to minim.cup. Make sure that each action ends by assigning an appropriate value to RESULT. Note that the parser will return a Symbol whose value field contains the value assigned to RESULT in the production for the root nonterminal (nonterminal program).

Unparsing
To test your parser, you must write the unparse methods for the subclasses of ASTnode (in the file ast.java). When the unparse method of the root node of the program's abstract-syntax tree is called, it should print a nicely formatted version of the program (this is called unparsing the abstract-syntax tree). The output produced by calling unparse should be the same as the input to the parser except that:

1. There will be no comments in the output.
2. The output will be "pretty printed" (newlines and indentation will be used to make the program readable); and
3. Expressions will be fully parenthesized to reflect the order of evaluation.

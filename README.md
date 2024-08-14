# PA1-cases-Building-a-Lexical-Analyzer
In this programming assignment, you will be building a lexical analyzer for small programming language and a program to test it. This assignment will be followed by two other assignments to build a parser and interpreter to the same language. Although, we are not concerned about the syntax definitions of the language in this assignment, we intend to introduce it ahead of Programming Assignment 2 in order to show the language reserved words, constants, and operators. The syntax definitions of the small programming language are given below using EBNF notations. However, the details of the meanings (i.e. semantics) of the language constructs will be given later on.

Prog ::= PROGRAM IDENT StmtList END PROGRAM
StmtList ::= Stmt; { Stmt; }
Stmt ::= DeclStmt | ControlStmt
DeclStmt ::= ( INT | FLOAT | BOOL ) VarList
VarList ::= Var { ,Var }
ControlStmt ::= AssigStmt | IfStmt | PrintStmt
PrintStmt ::= PRINT (ExprList)
IfStmt ::= IF (Expr) THEN StmtList { ELSE StmtList } END IF
AssignStmt ::= Var = Expr
Var ::= IDENT
ExprList ::= Expr { , Expr }
Expr ::= LogORExpr ::= LogANDExpr { || LogANDRxpr }
LogANDExpr ::= EqualExpr { && EqualExpr }
EqualExpr ::= RelExpr [ == RelExpr ]
RelExpr ::= AddExpr [ ( < | > ) AddExpr ]
AddExpr :: MultExpr { ( + | - ) MultExpr }
MultExpr ::= UnaryExpr { ( * | / ) UnaryExpr }
UnaryExpr ::= ( - | + | ! ) PrimaryExpr | PrimaryExpr
PrimaryExpr ::= IDENT | ICONST | RCONST | SCONST | BCONST | (Expr)

#calulatortest
Basic logical reasoning test for an iOS developer interview candidate. 

Requires the candidate to complete a calculator app to solve BODMAS equations. 

#####The candidate only needs to edit the CTCalculate.m file & fill in:
```objective-c
-(NSString *) solveQuestion:(NSString *) question
```
**The answer is included so remove the function definations in CTCalculate.m and replace it with the following**

```objective-c
-(NSString *) solveQuestion:(NSString *) question
{
	return @"Invalid String";	
}
```

###Candidate has the following helper functions

#####NSMutableArray+Stacks.h
A category on NSMutableArray's that adds the following stack functions:

```objective-c
-(void) push:(id) obj;

-(id) pop;

-(id) peek;
```

#####NSString+EquationParser.h
A category on NSString's that has the following functions to help pass an equation string :
```objective-c
/*
	returns the first element of the equations string 
	eg. "123+45/3" returns "123". "((3+5)/9)" returns "("
*/
-(NSString *) firstElement; 

/*
	returns a string with the first element of the equations string removed.
	eg. "123+45/3" returns "+45/3". "((3+5)/9)" returns "(3+5)/9)"
*/
-(NSString *) stringByRemovingFirstElement;

/* 
	returns the elementType for this string can be one of the following:

	    1. CTElementTypeInvalid

	    2. CTElementTypeOperand

	    3. CTElementTypeOpenBracket

	    4. CTElementTypeCloseBracket

	    5. CTElementTypeNumber
*/
-(CTElementType) getElementType;

/*
	Check if self it precedes the passed operand. 
	Does not check to make sure self and operand are operators.
*/
-(BOOL) precedes:(NSString *)operand;

/*
	Calculated [aStr] [self] [bStr]
*/
-(NSString *) calculateForParamA:(NSString *) aStr paramB:(NSString *) bStr;
```
###Notes

**The UI only supports the 4" iPhones/iPods**

Things to add in the future:

1. Validate equation before passing it to solveQuestion.

2. Rebuild storyboard using autolayout.

3. Add default test cases.

This is still a work in progress. Please feel free to contribute & fix bugs.

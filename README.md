1.Try to write a code for printing sequence of numbers from 1 to 50 with the differences of 3, 5, 10

Printing sequence of numbers from 1 to 50
Print(seq(1,50))
 

Printing sequence of numbers from 1 to 50 with a difference of 3
Print(seq(1,50,3))
 
Printing sequence of numbers from 1 to 50 with a difference of 5
Print(seq(1,50,5))
 

Printing sequence of numbers from 1 to 50 with a difference of 10
Print(seq(1,50,10))
 





2. What are the different data objects in R? and write syntax and example for each and every object.

In contrast to other programming languages like C and java in R, the variables are not declared as some data type. The variables are assigned with R-Objects and the data type of the R-object becomes the data type of the variable. There are many types of R-objects. The frequently used ones are −
•	Vectors
•	Lists
•	Matrices
•	Arrays
•	Factors
•	Data Frames
The simplest of these objects is the vector object and there are six data types of these atomic vectors, also termed as six classes of vectors. The other R-Objects are built upon the atomic vectors.

Data Type	Example	Verify
Logical	TRUE, FALSE	v <- TRUE 
print(class(v))
it produces the following result −
[1] "logical"

Numeric	12.3, 5, 999	v <- 23.5
print(class(v))
it produces the following result −
[1] "numeric"

Integer	2L, 34L, 0L	v <- 2L
print(class(v))
it produces the following result −
[1] "integer"

Complex	3 + 2i	v <- 2+5i
print(class(v))
it produces the following result −
[1] "complex"

Character	'a' , '"good", "TRUE", '23.4'	v <- "TRUE"
print(class(v))
it produces the following result −
[1] "character"

Raw	"Hello" is stored as 48 65 6c 6c 6f	v <- charToRaw("Hello")
print(class(v))
it produces the following result −
[1] "raw" 



In R programming, the very basic data types are the R-objects called vectors which hold elements of different classes as shown above. Please note in R the number of classes is not confined to only the above six types. For example, we can use many atomic vectors and create an array whose class will become array.

Vectors
When you want to create vector with more than one element, you should use c() function which means to combine the elements into a vector.

# Create a vector.
apple <- c('red','green',"yellow")
print(apple)
# Get the class of the vector.
print(class(apple))

When we execute the above code, it produces the following result –

[1] "red"    "green"  "yellow"
[1] "character"

Lists
A list is an R-object which can contain many different types of elements inside it like vectors, functions and even another list inside it.

# Create a list.
list1 <- list(c(2,5,3),21.3,sin)

# Print the list.
print(list1)

When we execute the above code, it produces the following result –

[[1]]
[1] 2 5 3

[[2]]
[1] 21.3

[[3]]
function (x)  .Primitive("sin")

Matrices
A matrix is a two-dimensional rectangular data set. It can be created using a vector input to the matrix function.

# Create a matrix.
M = matrix( c('a','a','b','c','b','a'), nrow = 2, ncol = 3, byrow = TRUE)
print(M)

When we execute the above code, it produces the following result –

       [,1] [,2] [,3]
[1,] "a"  "a"  "b" 
[2,] "c"  "b"  "a"

Arrays
While matrices are confined to two dimensions, arrays can be of any number of dimensions. The array function takes a dim attribute which creates the required number of dimension. In the below example we create an array with two elements which are 3x3 matrices each.

# Create an array.
a <- array(c('green','yellow'),dim = c(3,3,2))
print(a)

When we execute the above code, it produces the following result –

, , 1

            [,1]         [,2]     [,3]    
[1,] "green"  "yellow" "green" 
[2,] "yellow" "green"  "yellow"
[3,] "green"  "yellow" "green" 

, , 2

            [,1]         [,2]     [,3]    
[1,] "yellow" "green"  "yellow"
[2,] "green"  "yellow" "green" 
[3,] "yellow" "green"  "yellow"


Factors
Factors are the r-objects which are created using a vector. It stores the vector along with the distinct values of the elements in the vector as labels. The labels are always character irrespective of whether it is numeric or character or Boolean etc. in the input vector. They are useful in statistical modeling.
Factors are created using the factor() function. The nlevels functions gives the count of levels.

# Create a vector.
apple_colors <- c('green','green','yellow','red','red','red','green')

# Create a factor object.
factor_apple <- factor(apple_colors)

# Print the factor.
print(factor_apple)
print(nlevels(factor_apple))

When we execute the above code, it produces the following result –

[1] green  green  yellow red    red    red    green 
Levels: green red yellow
[1] 3

Data Frames
Data frames are tabular data objects. Unlike a matrix in data frame each column can contain different modes of data. The first column can be numeric while the second column can be character and third column can be logical. It is a list of vectors of equal length.

Data Frames are created using the data.frame() function.

# Create the data frame.
BMI <- data.frame(
   gender = c("Male", "Male","Female"), 
   height = c(152, 171.5, 165), 
   weight = c(81,93, 78),
   Age = c(42,38,26)
)
print(BMI)

When we execute the above code, it produces the following result –

       Gender        height           weight             Age
1        Male         152.0                81                 42
2        Male         171.5                93                 38
3      Female       165.0                78                  26



3. Create Data frame with 3 columns and 5 rows and write a code to fetch and delete row and a column using index and add new column and row to the existed data frame.

Creating a data frame with 3 columns and 5 rows

id<-c(1,2,3,4,5)
b<-c('book','pen','textbook','pencilcase','eraser')
p<-c(10,20,30,40,50)
df<-data.frame(id,b,p)
df
 

 

Renaming the column names of the data frame
names(df)<-c('ID','Item','Price')
df
 

 



Extracting a row from the data frame
df[1:1,]
 
Extracting the 3rd column
df[3:3]
 




Extracting 1st 3 rows
df[1:3,]
 
Extracting the 2nd column of 1st 3 rows
df[1:3,2]
 





Appending a column to the data frame
col<-c('red','blue','green','yellow','pink')
df$color<-col
df
 

 


Displaying a column
df$Item
 

Deleting the column called color
df$color=NULL
df
 


Deleting a row from the data frame
df[-c(5),]
 
Adding a row to the data frame
row<-c(5,'sharpner',5)
rbind(df,row)
 




4.Write nested if else statements to print whether the given number is negative, positive or Zero

x<-7
if(x>0){
  print("Positive Number")
}else if(x<0){
  print("Negative Number")
}else
  print("Zero")

 

5.write a program to input any value and check whether it is character, numeric or special character.

c<-'#'
if((c>='a' && c<='z')||(c>='A' && c<='Z')){
  print("Character")
}else if(c>=0 && c<=9){
  print("Digit")
}else
  print("Special Symbol")

 

6. write difference between break and next also write examples for both.

break statement
A break statement is used inside a loop (repeat, for, while) to stop the iterations and flow the control outside of the loop.
In a nested looping situation, where there is a loop inside another loop, this statement exits from the innermost loop that is being evaluated.
The syntax of break statement is:

if (test_expression) {
break
}
Note: the break statement can also be used inside the  else branch of if...else statement.
Flowchart of break statement
 

  x <- 1:5
  for (val in x) {
    if (val == 3){
      break
    }
    print(val)
  }  
 

next statement
A next statement is useful when we want to skip the current iteration of a loop without terminating it. On encountering next, the R parser skips further evaluation and starts next iteration of the loop.
The syntax of next statement is:
if (test_condition) {
next
}

Flowchart of next statement
 
x <- 1:5
for (val in x) {
  if (val == 3){
    next
  }
  print(val)
}
 

7.write a program to print a given vector in reverse format  x= c(1,5.6,3,10,3.5,5)
vec<-c(1,5.6,3,10,3.5,5)
vec
print(rev(vec))
 

8.write a program to get the mode value of the given vector (‘a’,’b’,’c’,’t’,’a’,’c’,’r’,’a’,’c’,’t’,’z’,’r’,’v’,’t’,’u’,’e’,’t’)
getmode <- function(v) {
  uniqv <- unique(v)
  uniqv[which.max(tabulate(match(v, uniqv)))]
}
v=c('a','b','c','t','a','c','r','a','c','t','z','r','v','t','u','e','t')
print(getmode(v))
 

9.Write a function to filter only data belongs to ‘setosa’ in species of Iris dataset.( using dplyr package)
library(dplyr)
iris
 
set=filter(iris,Species=='setosa')
set
 

10.Create a new column for iris dataset with the name of Means_of_obs, which contains mean value of each row.( using dplyr package)
iris1=data.frame(iris)
iris1=mutate(iris1,mean_obs=rowMeans(iris1[,1:4]))
iris1
 
11.Filter data for the “versicolor” and get only ‘sepel_length’ and Sepel _width’ columns.( using dplyr package)
vir=filter(iris,Species=='versicolor')
vir
 

vir1=select(vir,Sepal.Length,Sepal.Width,Species)
vir1
 

12.create below plots for the mtcars also write your inferences for each and every plot (use ggplot package) Use Different ( Size , Colour )
•	scatter plot
•	boxplot
•	histogram
•	line graph
•	bar graph

Reading “mtcars” dataset
mt=read.csv("D:\\mtcars.csv")
mt
mt=data.frame(mtcars)
mt
 
 

scatter plot
library(dplyr)
mt=read.csv("D:\\mtcars.csv")

mysubdata=select(mt,cyl,mpg)
plot(mysubdata$cyl,mysubdata$mpg,xlab='cyl',ylab='mpg',main='cyl vs mpg',col='red',pch=20)

 

 


boxplot

library(dplyr)
mt=read.csv("D:\\mtcars.csv")
mysubdata=select(mt,disp,hp)
boxplot(mysubdata$disp~mysubdata$hp,xlab='disp',ylab='hp',main='disp vs hp',col='blue',border='red',notch=TRUE)
 


 

Histogram


library(dplyr)
mt=read.csv("D:\\mtcars.csv")
mysubdata=select(mt,drat,wt)
hist(mysubdata$drat,xlab='drat',main='drat',col='blue',border='red',breaks=10)
 
 

line graph
library(dplyr)
mt=read.csv("D:\\mtcars.csv")
mysubdata=select(mt,drat,wt)
plot(mysubdata$drat,type='l',xlab='drat',ylab='wt',main='drat vs wt',col='blue')
 



 

bar graph

library(dplyr)
mt=read.csv("D:\\mtcars.csv")
mysubdata=select(mt,model,drat,wt)
barplot(mysubdata$drat,xlab='model',ylab='drat',main='model vs drat',col='blue',names.arg=mysubdata$model)
 
 



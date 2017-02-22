# Sum-only-numerics-in-a-DataFrame
#This is a very much beginner logic based structure which can easily be done using l/s apply
Browse[1]> students
  name age.yrs height.cm weight.kg grade
1 John      25       177        90    67
2 Mary      45       165        69    85
3 Jack      33       180        85    70
4 Jane      28       171        68    88

#Create a function that:
#Takes one argument and Checks if it is a data frame
#If it is not, stops and gives an error message

check_num_sum <- function(df)
{
  if(is.data.frame(df)==T)
    {
    total=0 #Initializing the accumulator 'total' to zero
    
    #using the 'for' loop to check each variable (i) in the df 
    #and add to total if it's a numeric one
    
    for (i in 1:length(df))
      {
      if((is.numeric(df[,i]))==T)
        {
        total=total+sum(df[,i])
        }
      }
    print(total)
    }   #print is outside the 'for' loop so that the whole total is shown
  else
    {#if the tested is not a dataframe, print error message
      print ('Error Message: This is NOT a data frame')
    }
}

Browse[1]> check_num_sum(students)
[1] 1446

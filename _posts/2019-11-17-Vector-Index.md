---
layout: post
title: Index of multi-dimensional vectors in range based for loops.
---
Example on how to find the index of a vector inside a vector using range based for loops.
Example of range based for loop.
{% highlight cpp %}
std::vector<int> result {1,2,3,4,5,6};
for(auto& it : result){
	Int index = &it - &result[0];
	Std::cout << This element is: " << it <<"\n";
	
}

{% endhighlight %}

This code snippet here is pretty self explanatory. To find the index of the vector we are referencing the iterator to get the memory address location and then referencing the first element of the vector. By subtracting these 2, we will get the index that the iterator is on. 

Now lets say that you have a multidimensional vector and you want to iterate through each vector in the main vector, and know the index of that element.


{% highlight cpp %}
std::vector<std::vector<int>> result { {1,3,5,7,9}
						   {2,4,6,8,10}} 
for(auto& it: result){
	//we are iterating through each sub vector (first the odd ones then the even ones)
	for(auto& jt : it){
		//now we are iterating inside each sub vector. What is the index?
		//to get the index just take the current memory location of the internal iterator and subtract
		
		//from it the memory location of the first element of initial iterator.
		int index = &jt - &it[0];
		
	}

}

{% endhighlight %}






--

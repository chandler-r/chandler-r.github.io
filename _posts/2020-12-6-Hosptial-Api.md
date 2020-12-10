---
layout: post
title: Hospital Bed Round-Up
cover-img: /assets/img/hospitalbed.jpeg
thumbnail-img: /assets/img/Doctor.jpg
subtitle: by Chandler Reyes
---

# Checking Out The Beds: The Final Tally

## The County With The Most Beds
The county that turned out to have the most beds was  
New York. Finding this was really difficult because  
I was really lost on how to find the total bed count.  
Then I found out that I could just siphon the total  
values into a separate dictionary assigned to different  
keys which were the counties.

## The Process Behind It All

### Finding The Data
Figuring out how to get the data and then sorting it out  
to find what I was looking for was definitely the toughest  
process of the whole lab. The code for finding the info from  
the api was a bit different from the basic structure we learned.  
The most difficult part about it was having to go through multiple  
ids when i didnt know what they were. Regardless, Anthony, Jake, and  
I, with the guidance of Mr. Lee were able to find out exactly how to  
go through the ids, even without knowing them. The key was to use a  
loop until you hit an error. That way you get all of the data you need  
without actually having to know all the different ids. The loop was  
simple, it look like this:
```javascript
while x not in [400, 401, 404]:
    query(index)
    index += 1
```
Here I just set x to zero, and while x does not equal one of the 3  
html error codes, the loop would keep going through the ids.

### Sorting The Data
The next toughest part was figuring out how exactly I should go about  
standardizing and organizing the the data. I was stuck because I was  
confusing myself with what XHAB meant. Once I figured out that all I had  
to do was either multiply or divide the number of beds, I managed to write  
the code. It turned out to be a series of if/else with a similar structure:
```javascript
if "500HAB" in row[4]:

      row[4] = "1000HAB"
      beds = float(row[5])*2
      bed_count = (float(row[6])/1000)*beds
      counties[county]['bed-count'].append(int(bed_count))
```
The blocks were similar with the main differences being the numbers being used  
to find the actual bed count.

## Final Takeaways
This lab was interesting because it made me put together skills from previous  
works as well as new techniques. It also forced me to think more simple rather  
than trying to be complex and extravagant, which would result in me confusing  
myself even more.

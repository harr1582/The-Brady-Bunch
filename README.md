# The-Brady-Bunch
Thinkful assignment
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import statistics as stat
%matplotlib inline

#Greg was 14, Marcia was 12, Peter was 11, Jan was 10, Bobby was 8, and Cindy was 6 when they started playing the 
#Brady kids on The Brady Bunch. Cousin Oliver was 8 years old when he joined the show. 
#What are the mean, median, and mode of the kids' ages when they first appeared on the show? What are the variance, 
#standard deviation, and standard error?

df=pd.DataFrame()
df['Bradys'] = [14,12,11,10,8,6,8]
print ('Mean:', np.mean(df['Bradys']))
print ('Median:', np.median(df['Bradys']))
print ('Mode:', stat.mode(df['Bradys']))
print ('Variance:', df['Bradys'].var())
print ('Standard Dev:', np.std(df['Bradys'], ddof = 1))
print ('Standard Error:', np.std (df['Bradys'], ddof = 1) / np.sqrt(len(df['Bradys'])))

#Using these estimates, if you had to choose only one estimate of central tendency 
#and one estimate of variance to describe the data, 
#which would you pick and why?

#It really depends on whom you are describing the data to. 
#If there is going to be an article about the average age of child stars and a lot more data is going to be analyzed, 
#I would give the mean age for precision. 
#However, if you are having a conversation about the Brady bunch, you would probably just use the median age of 10 
#to highlight approximately the middle of the group. 
#As for an estimate of variance, I might describe it using standard deviation 
#to demonstrate that the whole group was fairly close in age.

#Next, Cindy has a birthday. Update your estimates- what changed, and what didn't?

df['Bradys'] = [14,12,11,10,8,7,8]
print ('Mean:', np.mean(df['Bradys']))
print ('Median:', np.median(df['Bradys']))
print ('Mode:', stat.mode(df['Bradys']))
print ('Variance:', df['Bradys'].var())
print ('Standard Dev:', np.std(df['Bradys'], ddof = 1))
print ('Standard Error:', np.std (df['Bradys'], ddof = 1) / np.sqrt(len(df['Bradys'])))

#Median and mode stayed the same but everything else changed.

#Nobody likes Cousin Oliver. Maybe the network should have used an even younger actor. 
#Replace Cousin Oliver with 1-year-old Jessica, then recalculate again. 
#Does this change your choice of central tendency or variance estimation methods?

df['Bradys'] = [14,12,11,10,8,7,1]
print ('Mean:', np.mean(df['Bradys']))
print ('Median:', np.median(df['Bradys']))
#print ('Mode:', (values, counts) = np.unique(df['Bradys'], return_counts = True)
print ('Variance:', df['Bradys'].var())
print ('Standard Dev:', np.std(df['Bradys'], ddof = 1))
print ('Standard Error:', np.std (df['Bradys'], ddof = 1) / np.sqrt(len(df['Bradys'])))

#I probably would stick with median since the average gets dragged down by the infant. 
#As variance more strongly affected by extreme plot points, this number would not really be useful 
#in this instance with such a large range in the data set so I would also stick with standard deviation.

#On the 50th anniversary of The Brady Bunch, four different magazines asked their readers 
#whether they were fans of the show. The answers were: 
          #TV Guide 20% fans Entertainment Weekly 23% fans Pop Culture Today 17% fans SciPhi Phanatic 5% fans

#Based on these numbers, what percentage of adult Americans would you estimate were Brady Bunch fans on the 
#50th anniversary of the show?

df = pd.DataFrame()
df ['reader_poll'] = [20, 23, 17, 5]
print ('Mean:', np.mean(df['reader_poll']))
print ('Median:', np.median(df['reader_poll']))
print ('Variance:', df['reader_poll'].var())
print ('Standard Dev:', np.std(df['reader_poll'], ddof = 1))
print ('Standard Error:', np.std (df['reader_poll'], ddof = 1) / np.sqrt(len(df['reader_poll'])))

mean = np.mean(df['reader_poll'])
st_er = np.std (df['reader_poll'], ddof = 1) / np.sqrt(len(df['reader_poll']))
print ('Between {}% and {}% of Americans were fans of the Brady Bunch at their 50th anniversary.'.format(mean - st_er, mean + st_er))

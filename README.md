# Python-Challenge
Homework#3
#PyBank
# -*- coding: utf-8 -*-
import os
import csv
months=[]
total=[]
budget_data=os.path.join("..","Resources","budget_data.csv")

with open(budget_data, newline="",encoding="utf-8") as csvfile:
    csv_reader = csv.reader(csvfile, delimiter= ",")
    csv_header = next(csvfile)
    for row in csv_reader:
         months.append(row[0])
         total.append(int(row[1]))
    months_sum= len(months)
    
    x=1
    y=0
    total_change=(total[1]-total[0])
    changes=[]
    
    for month in range(months_sum-1):
        total_change=(total[x]-total[y])
        changes.append(int(total_change))
        x+=1
        y+=1
    av_mon_chng=round(sum(changes)/(months_sum-1),2)
    min_change=min(changes)
    max_change=max(changes)
    change_max=changes.index(max_change)
    change_min=changes.index(min_change)
    
    max_change_month=months[change_min+1]
    min_change_month=months[change_max+1]
    
print("Financial Analysis")
print(f"Months:{len(months)}")
print(f"Total:${sum(total)}")
print(f"Average Monthly Change: {av_mon_chng}")
print(f"Greatest Increase in Profits: {max_change_month} (${max_change})")
print(f"Greatest Decrease in Profits: {min_change_month} (${min_change})")


fin_analysis = open("Financial_Analysis.txt","w")
 
fin_analysis.write("Financial Analysis\n")

fin_analysis.write(f"Months: {len(months)}\n")
fin_analysis.write(f"Total: ${sum(total)}\n")
fin_analysis.write(f"Average Monthly Change: {av_mon_chng}\n")
fin_analysis.write(f"Greatest Increase in Profits: {max_change_month} (${max_change})\n")
fin_analysis.write(f"Greatest Decrease in Profits: {min_change_month} (${min_change})\n")
 
  
fin_analysis.close() 
 
 
#PyPoll 

import os
import csv

election_data= os.path.join('..','PyPoll','election_data.csv')
with open(election_data, newline="",encoding="utf-8") as csvfile:
    csv_reader = csv.reader(csvfile, delimiter= ",")
    csv_header = next(csvfile) 
    
    votes_cast=[]
    most_vote=[]
    candidate=[]
    for row in csv_reader:
        votes_cast=votes_cast+1
        candidate=row[2]
        if candidate in candidate:
            candidate=candidate.index(candidate)
            votes_cast[candidate]=votes_cast[candidate]
        else:
            candidate.append(candidate)
            votes_cast.append(1)
    percentages=[]
    max_votes=votes_cast[0]
    max_index=0
    
    for count in range(len(candidate)):
        vote_percentage= votes_cast[count]/votes_cast*100
        percentages.append(vote_percentage)
        if votes_cast[count]>max_votes:
            max_votes=votes_cast[count]
            print(max_votes)
            max_index=count
    winner= candidate[max_index]
    percentages = [round(i,2) for i in percentages]
    


    print('election Results')
    print(f"Total Votes: {votes_cast}")
    for count in range(len(candidate)):
      
        print(f"{candidates[count]}: {percentages[count]}% ({vote_counts[count]})"

    



    
    

    


    

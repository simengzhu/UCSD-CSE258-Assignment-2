# ucsd-cse258-a2  
This is the repo for UCSD CSE258 Assignment 2.

## Info  
Team members:  
  Qian Zhang, Simeng Zhu, Feng Jiang, He Qin  
Due:  
  Dec. 4, 2017(Mon, W10)  
Submission:  
  Written report, 4 pages(double column, 11pt), 2.5-3k words, figures, tables, equations   
Slack Chat:  
  https://cse-258-assignment-2.slack.com/messages/C8976PWQ7/  
Dateset(currently):
  https://www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236  
Work Log:  
  Nov/26 Sun(7:30 p.m. - 11:00 p.m.): First meet. Discussed datasets and topics.  
  Nov/30 Thu(2:00 p.m. - 10:00 p.m.): Decided to use  

## Tasks  
Report should have five components, each worth 5 percent of grade.  
1. Identify a **dataset** to study, perform an exploratory analysis of the data. **Describe** the dataset, including its **basic statistics and properties**, and report any **interesting findings**. This exploratory analysis should motivate the design of your model in the following sections. Datasets should be **reasonably large**(e.g. more than 50000 samples).

1) Month/Day_of_week to Delay   
2) Airline to Delay   
3) Top 5 airports counts   
4) Time distribution  


2. Identify a **predictive task** that can be studied on this dataset. Describe **how you will evaluate** your model at this predictive task, what relevant **baselines** can be used for comparison, and how you will **assess the validity** of your model's predictions. It's fine to use models that were described in class here (i.e, you **don't have to invent anything new** (though you may!)), though you should **explain and justify which model was appropriate** for the task. It's also important in this section to carefully describe what features you will use and how you had to process the data to obtain them.  

  - Task: Classification of delay severity.  
    Features -> 1)Airline(one hot) 2)Departure_time(one hot 2h) 3)Month(one hot) 4)Day_of_week(one hot) 5)origin_airport 6)destination_airport 7)distance
    Prediction -> Arrival_delay class(one-hot labelling)  
    ontime [1,0,0,0,0,0] 0  
    (0,10] [0,1,0,0,0,0] 1  
    (10,30] [0,0,1,0,0,0] 2  
    (30,60] [0,0,0,1,0,0] 3  
    (60, Infty) [0,0,0,0,1,0] 4  
    cancellation [0,0,0,0,0,1] 5
    Top busiest 5 airports

  - Evaluation: 1) Confusion matrix. 2) Overall accuracy
  - Baselines: 1)Airline mean over origin destination   
  - Models: 1) SVM(Multi-class) 2) KNN 3) Logistic Regression(Multi-class) 4)Neural Network?  

3. Describe your **model**. Explain and justify your **decision to use the model** you proposed. How will you **optimize** it? Did you run into any **issues due to scalability, overfitting,** etc.? What **other models** did you consider for comparison? What were your **unsuccessful attempts** along the way? What are the **strengths and weaknesses** of the different models being compared?

4. Describe **literature** related to the problem you are studying. If you are using an **existing dataset**, **where did it come from** and **how was it used**? What **other similar datasets** have been studied in the past and how? What are the **state-of-the-art methods** currently employed to study **this type of data**? Are the conclusions from existing work **similar to or different** from your **own findings**?

5. Describe your **results** and conclusions. **How well** does your model perform **compared to alternatives**, and what is the **significance** of the results? **Which feature representations worked well** and which do not? What is the **interpretation of your model’s parameters**? **Why did the proposed model succeed** why others failed (or if it failed, why did it fail)?

## Timeline  
Nov. 26  
First meet. Pick Youtube dataset. Discuss basic tasks.   

## Other Resources  

## Appendix
### Git Workflow
1. Synchronize code from remote repo  
  `git pull origin master`
2. Make some changes  
3. Check status of all changes  
  `git status`  
4. Add changes to local buffer  
  `git add --all`  
5. Commit changes  
  `git commit -m "[qinacme]: Something done."`
6. Synchronize before push(When conflicts comes, contact qinacme)  
  `git pull origin master`  
7. Push to remote(Finish today's work)  
  `git push origin master`  

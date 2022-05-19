# Assignment-spottable
Data Engineer

Q1 - The total experience, the candidate has (based on their previous experiences)
Approache - Run a for loop from 0 to lenght of data set (len(d)) take a variable as exp which will we 0 initially as passes it runs another for loor form 0 to length size of lest of dict of experience and put the difference of enddate and startdate in exp and keep on adding for each loop until it reaches the end of size of list of dict of experiences then append the value in a list names rows with its id and name 
            Repeat the same process from i=0 to i=lenght of data set
Code - 
exp=0
rows=[]
for i in range(len(d)):
    exp=0
    if(len(d[i]["Experience"])==1):
        exp=exp+((d[i]["Experience"][0]['endDate'])-(d[i]["Experience"][0]['startDate']))
    elif(i==6):
        for j in range(len(d[i]["Experience"])):
            exp=exp+((d[i]["Experience"][j]['endDate'])-(d[i]["Experience"][j]['startDate']))
    else:
        for j in range(len(d[i]["Experience"])-1):
            exp=exp+((d[i]["Experience"][j]['endDate'])-(d[i]["Experience"][j]['startDate']))
#     print("exp of ",i,exp)
    if(i==10):
            rows.append([d[i]['_id'],d[i]['Profile']['firstName'],exp])
    else:
        rows.append([d[i]['_id'],d[i]['FirstName']+" "+d[i]['LastName'],exp])
#     rows.append([d[i]["_id"], exp])
#     fn=pd.DataFrame({" Id ":d[i]["_id"],"exp_year":exp},)
q1=pd.DataFrame(rows, columns=["ID  ","Name", "Year of Experience"])
q1

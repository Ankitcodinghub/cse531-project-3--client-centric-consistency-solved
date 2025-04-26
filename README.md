# cse531-project-3--client-centric-consistency-solved
**TO GET THIS SOLUTION VISIT:** [CSE531 Project 3- Client-Centric Consistency Solved](https://www.ankitcodinghub.com/product/cse531-solved-3/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;121948&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSE531 Project 3- Client-Centric Consistency Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
&nbsp;

1. Summary

The goal of this project is to implement the client-centric consistency model on top of Project 1. Your job is to implement the essential functions that enforce a client-centric consistency model, read-your-writes, of the replicated data in the bank.

Major tasks:

1. Track read and write events by the same customer across different branch processes

2. Implement read-your-writes consistency among the branch processes

Diagram A: The customer changes branches while submitting requests to the Bank.

2. Description

In this project, the same customer process performs operations on the bank account through different branches. For example, as shown in Diagram A, Customer 1 performs the following operations on a bank account with initially $0 balance: deposits $100 to the bank account at Branch 1 and query the balance at Branch 2. The query should return $100.

To achieve this, you are tasked to implement the read-your-writes consistency model that we have learned in class. A data store (the distributed bank system) is said to provide readyour-writes consistency if the effect of a write operation (deposit or withdraw) by a process on data item x (balance) will always be seen by a successive read operation (query) on x by the same process.

3. Input and Output

The input file contains one Customer and multiple Branch processes. The format of the input file follows Project 1, with the addition of a branch parameter that indicates the target branch for each event.

[ // array of processes

{ // Customer process #1

“id” : {a unique identifier of a customer},

“type” : “customer”,

“events” : [{“id“ : {unique identifier of an event}, “interface” : {query | deposit | withdraw},

“money” : {an integer value}, “branch” : {a unique identifier of the branch} }]} { // Branch process #1

“id” : {a unique identifier of a branch},

“type” : “branch”

“balance” : {the initial amount of money stored in the branch}

}

{ … } // Branch process #2

{ … } // Branch process #3

{ … } // Branch process #N

]

Output file format for the read-your-writes.

[ // array of customers

{ // Customer process #1

“id” : { a unique identifier of a customer }

“recv” : [a list of successful returns of the events from the customer process]

}

]

Below is the example input file and the expected output file.

Example input file

[

{

“id” : 1,

“type” : “customer”,

“events” : [{“id”:1, “interface”:”deposit”, “money”:400, “branch”:1 }, {“id”: 2, “interface”:”query”, “branch”: 1} , {“id”: 3, “interface”:”query”, “branch”: 2}]

},

{

“id” : 1,

“type” : “branch”,

“balance” : 0

},

{

“id” : 2,

“type” : “branch”,

“balance” : 0

} ]

Expected output file:

[

{“id”:1,”recv”:[{“interface”:”deposit”,”branch”:1,”result”:”success”}]},

{“id”:1,”recv”:[{“interface”:”query”,”branch”:1,”balance”:400}]},

{“id”:1,”recv”:[{“interface”:”query”,”branch”:2,”balance”:400}]}

]

4. Submission Directions for Project Deliverables

1. Client-Centric Consistency Project Written Report: Your written report must be a single PDF with the correct naming convention: Your Name_Client-Centric Consistency_Written Report.

2. Client-Centric Consistency Project Code: The project code must be submitted as a .zip file of your source code.

Final submissions missing either of the deliverables will be graded based on what was submitted against the rubric criteria. Please review the rubric for how your Client-Centric Consistency Project will be graded.

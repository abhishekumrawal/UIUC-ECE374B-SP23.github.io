---
layout: default
title: Homeworks
---

<table id="customers">
  <tr>
    <th> # </th>
    <th>Topic</th>
    <th>|Problems|</th>
    <th>Assigned</th>
    <th>Due</th>
    <th>Questions</th>
    <th>Solutions</th>
  </tr>
  {% for iteml in site.data.homework %}  
    {% assign item = iteml[1] %}
    <tr>
        <td>{{ item.num }}</td>
        <td> {{ item.topic }} </td>
        <td> {{ item.num-problems }} </td>
        <td> {{ item.assigned-date | date: "%b %d" }} </td>
        <td> {{ item.due-date | date: "%b %d" }} </td>
        <td> 
            {% if item.questions-link %}
            <a href="{{ site.base }}{{ item.questions-link }}"
                style="text-decoration: none">
                <img class="homework-icon"
                    alt="Homework {{ item.num }} Questions"
                    title="Homework {{ item.num }} Questions"
                    src="{{ site.base }}/img/icons/lab_questions.png" />
            </a>
            {% endif %}
        </td>
        <td> 
            {% if item.solutions-link %}
            <a href="{{ site.base }}{{ item.solutions-link }}"
                style="text-decoration: none">
                <img class="homework-icon"
                    alt="Homework {{ item.num }} Questions"
                    title="Homework {{ item.num }} Questions"
                    src="{{ site.base }}/img/icons/lab_solutions.png" />
            </a>
            {% endif %}
        </td>
    </tr>        


  {% endfor %}

</table>

&nbsp;

Couple things to note about homeworks:
- Each homework is assigned when you have all (or atleast most) of the required knowledge to complete it. In two cases, because of scheduling constraints, one or two problems may require knowledge from the lecture/discussion right after assignment. Either way you'll have the knowledge for those problems by Wednesday. This is a long-winded way of saying: **There is zero reason not to start the homework early**
- Each homework will consist of 3 novel problems and 1-2 problems you've seen in the labs. All the problems counts equally toward your final course grade.
- The homework average consists 24% of your final course grade. We will use the highest 34 scores to calculate your final course grade. Since there are expected to be 43 problems, this means that 9 problems will be dropped (~2 homeworks).
- It's a bad idea to skip homeowrks. Homeworks and labs are where I get inspiration for exam problems. 

### Homework Logistics: How to submit

- All homework solutions must be submitted electronically via Gradescope. Submit one PDF file for each numbered homework problem. Gradescope will not accept other file formats such as plain text, HTML, LaTeX source, or Microsoft Word (.doc or .docx).
- **Homeworks are due by noon** of their due date. 
- You **should not** use Canvas to keep track of homeworks or any other course policies and logistics. **Canvas is a gradebook, that's all.**  
- You will be registered with Gradescope using your university email address. If you can't access Gradescope let the course staff know. 
- Homework solutions may be submitted by groups of at **most three** students. Students are responsible for forming their own homework groups. Groups may be different for each numbered homework problem. 
    - **For group solutions, exactly one member of each group submits the solution to each problem.** Even if the groups are identical, the submitter may be different for each numbered homework problem. This is important to realize since gradescope will overwrite other members' submissions if you submit on behalf of your group.
    - Whoever submits any group solution must also submit the names of the other group members via Gradescope. Gradescope will then automatically apply the grade for that submission to all group members. If this information is not entered correctly, the other group members' grades will be delayed or possibly lost entirely.
    - If you discover that your name was omitted from a group homework submission, please submit a regrade request.
- As error correction, each submitted homework solution should **include the following information in large friendly letters at the top of every page/problem**. 
    - The homework number
    - The problem number
    - Group names+netids
- **We will not accept late homework for any reason.** To offset this rather draconian policy, we have a very generous number of homework drops (compare to other sections/courses). Also remember you can always resubmit a problem to gradescope. There is zero reason to wait until the last minute to submit your work.  

### Homework Grading Policies: 

- **Homeworks** are graded by the entire course staff, within Gradescope. All numbered homework problems are worth the same amount. Under normal circumstances, all homework should be graded within two weeks of submission.
- Partial credit is given for work that is very close to being correct. 
- **We will give zero points for long and tedious solutions** (i.e., solutions that are longer than the official solutions by a significant amount). We reserve the right of not even reading your solution if it exceedingly and unnecessarily long. If your solutions seems too long - rewrite it to be short and precise. 
- This semester I am limiting solutions text to be **300 words long max** per problem. It is incredibly important to be able to convey complex idea as concisely as possible and I think this is good practice. I highly suggest using figures(flowcharts, graphics)/equations(useful for recurrences) to cut down on the word vomit. 
>If I had more time, I would have written a shorter letter. 
><cite> - [Unknown](https://www.lb7.uscourts.gov/documents/314-cv-921.pdf) <cite>


### Regrades

Regrades requests would be open for a week once grades are released (except for final exam). Regrade requests are not intended for arguing about point allocation, or whether or not the grading scale is fair.

Unfortunately, certain students think that they can tire us into giving them point that they did not earn, by keep asking for unjustified regrade requests. As such, superfluous, argumentative and repetitive regrade requests, after an appropriate warning, would results in a zero on the relevant questions - please do not waste our time.
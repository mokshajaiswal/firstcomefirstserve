 Two types of people can enter into a library-students and teachers. After entering the library, the visitor searches for the required books and get them. In ordr to get them issued, he goes to the single CPU which is there to process the issuing of books. Two types of queues are there at the counter-one for students and one for teachers.A student goes and stands at the tail of the queue for students and simliarly the teacher goes and stands at the tail of the queue for teaches (FIFO).If a student is being served and a teacher arrives at the counter, he would be the next person to get service (PRIORITY - non preemtive). If two teachers arrive at the same time, they will stand in their queue to get service (FIFO). Write a program to ensure that the system works in a non-chaotic manner.
•	If a teacher is being served and during the period when he is being served, another teacher comes, then that teacher would get the service next. This process might continue leading to increase in waiting time of students. Ensure in your program that the waiting time of students is minimized.
Sample Input:
2
3
1 1 0
2 1 0
3 1 0
Expected Output:
Person[1]: Time: 1 To 2
Person[2]: Time: 2 To 3
Person[3]: Time: 3 To 4
Explanation:
The above problem can be solved by using multi level scheduling for both the teacher queue and the student queue. However starvation occurs when new teacher comes before the current student is addressed the student have to wait, if this continues then the student will have longer waiting time; so to minimise this, I have coded this using "Multilevel Feedback Queue Scheduling" which enables process switching during runtime. This incorporates both the first come first serve technique along with shortest job first. However we have the process time of issuing book of teacher and student same. The code minimises the student waiting time also maintains the priority allocated for both of them at the same time.

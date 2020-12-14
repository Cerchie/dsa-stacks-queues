# dsa-stacks-queues
Solution code had no challenges, but 
I decided to try one to solidify my knowledge:

Browser Back/Forward
Design how you could design a browser back/forward system using two stacks, so that you can visit a series of sites (Google, Yahoo, EBay, go back to Yahoo, then forward again to EBay, then onto Apple, and so on).

Write pseudo-code for this.


1. Read the problem. Can I restate the problem in my own words?
Basically, a stack is a list (if I create it that way, which I will because array-stacks are less desirable) of chained-together-nodes where you can remove from the top and add to the top. If I'm to be able to go back and forward in the browser, I think I'll want .prev defined. 

2. What are the inputs? What data types can I expect here?
Nodes which are  = sites. 

3. What is my expected output and its data type?
Two (?) stacks. 

4. Do I have enough information to solve the problem? Do I need to ask any more clarifying questions?
I don't know why we need two stacks. Update: I googled it: 
Simplest solution would be to use two stacks (back, forward).
Clicking the back button will pop from the back stack and push the current page on the forward stack (and go to the popped value on the back stack).
Clicking on any link on a page (following a link) will clear the forward stack and push the current page on the back stack.
Clicking on the forward button will pop from the forward stack and push the current page on the back stack (and go to the popped value on the forward stack).
The back and forward buttons are disabled when the appropriate stack is empty.

5. How am I going to label the important pieces of data that go into the problem?
site-node, .first, .last, 

6. Can I run though a simple example of the problem in my own words?
The user has visited Google, Yahoo, and Bing in that order, filling the stack with the corresponding nodes. The user clicks the back button, triggering the back function. It pops Yahoo from the top of the back stack and pushes Bing's val on the forward stack. It returns the popped val of Yahoo.
 The user then want to go forward, so he clicks the forward button which triggers the forward function. It pops Bing from the forward stack, returns its val, and pushes Yahoo onto the back stack. 

7. How about a more complex example?
Say the user clicks Google -> Yahoo -> Bing, then Bing -> Yahoo. Now he clicks a link on the Yahoo page. The link function is triggered, which clears the forward stack and pushes Yahoo onto the back stack. 

8. How am I going to handle empty/invalid inputs?
Error-handle, using a msg like "must enter site-list"

9. Write my pseudocode. Does this reveal anything else I don't understand about the problem?
Given: We've got Node and Stack classes with push(), pop(), peek() and isEmpty() methods defined on Stack. 




const browser = (sites) =>
{ 

    if (!sites){
        return new Error "must enter site-list"
    }
let backStack = New Stack;

let forwardStack = New Stack;

let siteNodes = sites.map(site => new Node(site =val));

backStack.push(siteNodes); 

forwardStack.push(siteNodes);
link = () => {
    function that checks for link
}
function browser-back(sites) {
if (!link){
backStack.pop(this.first)
forwardStack.push(this.first.next)
return this.first.val}
else {
    forwardStack.clear()
    backStack.push(this.first)}

}}
function browser-forward(sites) {
if (!link){
forwardStack.pop(this.first)
backwardStack.push(this.first.next)
return this.first.val}
else {
    forwardStack.clear()
    backStack.push(this.first)}

}}
}

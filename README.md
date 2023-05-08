Download Link: https://assignmentchef.com/product/solved-prog1385-assignment-6-ultimate-carradio
<br>
In this assignment, you will be (once again) modifying your Assign-05 code to use <strong><em>more inheritance</em></strong>.  As well, in this assignment, you will be asked to use <strong>new</strong> and <strong>delete</strong>, throw and catch <strong>exceptions</strong> and also create / use <strong>virtual functions</strong>.

<h1>More Types of Radios</h1>

<ul>

 <li>Create a new class called <strong>PioneerAM</strong>. This class will inherit from PioneerCarRadio. o     PioneerAM behaves like PioneerCarRadio except that it <strong>operates in the AM band <u>only</u></strong>! o    There is no ability to change to the FM band – they shouldn’t even display the FM band o     Do this by overriding the appropriate methods that are in the parent class or grandparent class.</li>

 <li>Create a new class called <strong>PioneerWorld</strong>. This class will inherit from PioneerAM.

  <ul>

   <li>PioneerWorld behaves like PioneerAM

    <ul>

     <li>Except that the AM band range is 531 kHz to 1602 kHz</li>

     <li>And the interval between frequencies is 9 kHz, not 10 kHz</li>

     <li>So scanning up from 531 would bring you to 540, then 549, etc. Wrapping from 1602 brings you to 531.</li>

    </ul></li>

   <li>Do this by overriding the appropriate methods that are in the parent class or grandparent class.</li>

  </ul></li>

</ul>

<h1>New/Delete and Exceptions</h1>

<ul>

 <li>Create a new testHarness (i.e. your main())  and put it in a file called <strong>cpp.  </strong>In thi<strong>s </strong>main o Change your PioneerCarRadio variable to be a pointer

  <ul>

   <li>Give it an initial value of NULL o Call this variable pRadio.</li>

  </ul></li>

 <li>When your program starts o You will need to create and call a function named <strong><em>createRadio()</em></strong>  that takes a string (or char pointer … your choice) to determine which type of radio you want to start with and returns a pointer to that radio back to main() and into the pRadio pointer.

  <ul>

   <li>Your program will need to get this string (or char pointer) from the command line arguments of the program</li>

   <li>This means you needs to take in and parse command-line arguments</li>

   <li>This function will exist in the ultimateRadio.cpp file and when passed the string (or char pointer) will …</li>

   <li>If the program is started with the runtime switch of <strong>–car</strong> then instantiate a <strong><em>new</em></strong> PioneerCarRadio object and return it to assign it to pRadio.</li>

   <li>If the program is started with the runtime switch of <strong>–am</strong> then instantiate a <strong><em>new</em></strong> PioneerAM object and return it to assign it to pRadio.</li>

   <li>If the program is started with the runtime switch of <strong>–world </strong>then instantiate a <strong><em>new</em></strong> PioneerWorld object and return it to assign it to pRadio.</li>

   <li>Otherwise, throw an exception.</li>

   <li>Remember you will need to write this createRadio() function</li>

  </ul></li>

 <li>Since it will be throwing exception(s), remember to put the call to <em>createRadio()</em> in a try block o Remember that you will initially be getting this function’s parameter from a command line argument  o       In the catch clause, print an error message and quit the program o    Make sure to instantiate each radio in an <em><u>off</u></em> state</li>

</ul>

<ul>

 <li>Whenever you use new, use the principles discussed in class to handle this correctly. o             You are required to use the “new” new in this assignment o      Use exception handling to detect out-of-memory situations</li>

</ul>

<h1>Virtual Functions</h1>

<ul>

 <li>In order to implement these 2 new children classes, you will once again need to override some methods</li>

 <li>Make any overridden methods virtual <strong><em>in the parent class</em></strong> o       Recommendations: ToggleFrequency(), ScanUp(), ScanDown().</li>

 <li>Since we are using virtual functions, remember best practices and make all destructors virtual</li>

</ul>

<h1>Switching Radios and Quitting the Program</h1>

<ul>

 <li>Each specialized radio class needs to tell the user who they are … o The PioneerCarRadio already does with the Pioneer XS440 that appears in its output o Make the PioneerAM class say   Pioneer XS440-AM

  <ul>

   <li>And the PioneerWorld class say                               Pioneer XS440-WRLD</li>

  </ul></li>

 <li>Create a destructor for each new class o In each destructor, simply print a message stating which radio is being destroyed</li>

</ul>

&#x25aa;   e.g. “Destroying Pioneer XS440-WRLD Radio” o The only message that should be seen from any destructor is the one from the actual data-type of the instance being destroyed

<ul>

 <li>The output from PioneerCarRadio, PioneerAM and PioneerWorld is <em>somewhat</em> the same … except for the difference in its name (i.e. the first line of output) and the presence/absence of the FM band … o Try to think of a clever way to implement this “radio name” idea …

  <ul>

   <li>Perhaps by adding a data member to one of the classes to hold the name … hmmm…</li>

  </ul></li>

 <li>Each radio instance that is created, will run until the ‘x’ key is pressed within that instance o This means that each of the “Pioneer” classes shares the same input processing

  <ul>

   <li>As developed in Assign-05 o Once an ‘x’ key is pressed, the radio object is destroyed in the ultimateRadio.cpp source o           And do nothing until the user presses one of the following keys</li>

   <li><strong>c</strong> — to create and run a new PioneerCarRadio radio</li>

   <li><strong>a</strong> — to create and run a new PioneerAM radio</li>

   <li><strong>w</strong> — to create and run a new PioneerWorld radio</li>

   <li><strong>x</strong> –  to quit the program</li>

   <li>Note that these keystrokes will need to be captured and processed within your testHarness</li>

  </ul></li>

</ul>

(where the new radio would be created)

<h1>In Case It Makes Things Easier</h1>

<ul>

 <li>You can create mutators and accessors for whatever private data members you need to from the AmFmRadio class</li>

</ul>

<h1>What Not To Do</h1>

<ul>

 <li>Don’t put excessive amounts of the parent class’s functionality (PioneerCarRadio) in the child classes</li>

</ul>

(PioneerAM, PioneerWorld) unnecessarily o This is duplicating functionality and code – a definite no-no
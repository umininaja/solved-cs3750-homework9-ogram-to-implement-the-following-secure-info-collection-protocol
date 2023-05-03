Download Link: https://assignmentchef.com/product/solved-cs3750-homework9-ogram-to-implement-the-following-secure-info-collection-protocol
<br>
<strong>Task I </strong>: Write a client Java program and a server Java program to implement the following secure Info Collection protocol on top of <strong>SSL/TLS</strong> service. TCP or UDP service <strong><em>cannot</em></strong> be used directly in your programs, i.e., any TCP/UDP class such as Socket and ServerSocket <strong><em>cannot</em></strong> be used in your source code although the ssl sockets used in your source code will certainly use the TCP service.

<ul>

 <li><strong>InfoCollection Server</strong> Program:

  <ol>

   <li>Take <strong>one argument, which specifies the port number that the server listens to,</strong> and create the SSL Server Socket.</li>

   <li>Listen to the given port and wait for a connection request from an InfoCollection Client.</li>

   <li>Create a new thread and an SSL socket for every incoming SSL connection from an InfoCollection client. While the original thread goes back to Step 2, the new thread continues with the following steps.</li>

   <li>Get the <strong>session</strong> of this SSL socket and display the following information (hint: use the <strong>get…()</strong> methods of this session.)</li>

  </ol></li>

</ul>

Peer host is ……

Cypher suite is …… Protocol is ……

Session ID is ……

The creation time of this session is ……

The last accessed time of this session is ……

<ol start="5">

 <li>Send questions to and collect information from the InfoCollection client

  <ol>

   <li>Send “User Name: ” to client, read the response from client, create a txt file named as &lt;this user ID&gt;.txt, and write</li>

  </ol></li>

</ol>

“User Name: &lt;response from client&gt;” as the first line in this file.

<ol start="5">

 <li>Send “Full Name: ” to client, read the response from client, and add a line, “Full Name: &lt;response from client&gt;”, to the file created in Step 5.a.</li>

 <li>Send “Address: ” to client, read the response from client, and add a line, “Address: &lt;response from client&gt;”, to the file created in Step 5.a.</li>

 <li>Send “Phone number: ” to client, read the response from client, and add a line, “Phone number: &lt;response from client&gt;”, to the file created in Step 5.a.</li>

 <li>Send “Email address: ” to client, read the response from client, and add a line, “Email address: &lt;response from client&gt;”, to the file created in Step 5.a.</li>

 <li>Close the file created in Step 5.a.</li>

 <li>Send “Add more users? (yes or any for no)” to client, read the response from client. If the client responds “yes”, go back to Step 5.a and repeat.  Otherwise, close the SSL connection and terminate this new thread (and loop back to Step 2 if the server is single-threaded).</li>

</ol>

<ul>

 <li><strong>InfoCollection Client</strong> Program:

  <ol>

   <li>Take <strong>two arguments, which specify the <em>ip/dns</em> and the <em>port</em> number of the remote InfoCollection Server.</strong></li>

   <li>Create a SSL socket to connect to your InfoCollection server. Catch the exception, terminate the program, and display error messages on the standard output if any.</li>

   <li>Get the session of this SSL socket and display all the information as what is listed in Server program’s Step 4.</li>

   <li>Read <strong><em>each</em></strong> question from the Info Collection server, one at a time, and display each question on the standard output to ask the user to input the answer. Read the user’s answer from the standard input and send it to the server.

    <ol start="5">

     <li>If the user answers any except for “yes” to the InfoCollection Server’s Step 5.g, close the SSL connection and terminate this program AFTER sending the user’s answer to the InfoCollection Server. b. Otherwise, repeat Step 4.</li>

    </ol></li>

  </ol></li>

</ul>




<strong>Task II</strong>: Generate keys and test your program on <strong>cs3750a</strong> and <strong>cs3750b</strong>.

<table width="64">

 <tbody>

  <tr>

   <td width="64">  <strong>Warning</strong>:</td>

  </tr>

 </tbody>

</table>

to complete this part, especially when you work at home, you must first (1) <strong>connect to the MSUDenver VPN</strong> via <strong>GlobalProtect</strong>; then (2) <strong>connect to </strong>the virtual servers<strong> cs3750a.msudenver.edu</strong> and <strong>cs3750b.msudenver.edu</strong> using <strong><em>sftp</em></strong> and <strong><em>ssh</em></strong> command on MAC/Linux or <strong><em>PUTTY</em></strong> and <strong><em>PSFTP</em></strong> on Windows.  For details, you may refer to <strong>Lab 1. </strong>

The server program always has to start BEFORE the client program in your test.




<ol>

 <li>Create a directory “<strong>HW09</strong>” under your home directory on cs3750a and cs3750b. Create a subdirectory “<strong>server</strong>” on <strong>cs3750a</strong> for the <strong><em>server</em></strong> program and your <strong><em>keystore</em></strong>. Make a subdirectory “<strong>client</strong>” on <strong>cs3750b</strong> for the <strong><em>client</em></strong> program and your <strong><em>truststore</em></strong></li>

 <li>Use <strong><em>keytool </em></strong>to create a simple JKS keystore suitable for use with JSSE. Make a PrivateKeyEntry in your keystore in <strong>HW09/server</strong>, then make a corresponding trustedCertEntry in your truststore in <strong>HW09/client</strong>.</li>

 <li>In a file named “keyinfo.txt” under <strong>HW09/server on cs3750a</strong>, list the names and passwords of your keystore and truststore, and the alias and password of your PrivateKeyEntry and trustedCertEntry.</li>

 <li>RUN and TEST your <strong>server</strong> program in <strong>HW09/server</strong> on cs3750a. You must use the <strong><em>port number</em></strong> assigned to you in the file named “<strong><em>pdf</em></strong>”, which is posted Blackboard under “Lab03 SSL”, in your <strong>server</strong> program as the local port number to create a SSL Server Socket, which will wait for a connection request from any client.</li>

 <li>RUN and TEST your <strong>client</strong> program in <strong>HW09/client</strong> on cs3750b, copy &amp; paste the outputs of this client program during your test to a file named “<strong><em>txt</em></strong>”. (Hint: in your <strong>client</strong> program, your need to use <strong>cs3750a.msudenver.edu</strong> as the <em>remote DNS/IP</em> and the <strong>port number</strong> assigned to you as the <em>remote port number</em> to create a SSL socket that is connected to your server program.)</li>

 <li>(This step can be done simultaneously with the above step if your server program supports multithreading.) RUN and TEST your <strong>client</strong> program on your local computer, while the <strong>server</strong> program is running on cs3750a. You may either copy the truststore to your local computer or import the key certificate to a local truststore on your local computer.</li>

</ol>



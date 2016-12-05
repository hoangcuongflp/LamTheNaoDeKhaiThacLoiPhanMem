# LamTheNaoDeKhaiThacLoiPhanMem
Note HVA - Làm thế nào để khai thác lỗi phần mềm
http://www.hvaonline.net/hvaonline/posts/list/38052.hva


Đã từ lâu, kỹ thuật tận dụng các lỗi phần mềm được coi như là ma thuật của các hacker. Làm thế nào mà họ có thể tìm ra lỗi của một chương trình và khai thác nó? Bài viết này sẽ giúp cho các bạn có thể biết được: cần chuẩn bị những kiến thức gì để có thể tìm và khai thác lỗi phần mềm. Đồng thời bài viết được xem như là một bộ khung của giáo trình “tìm và tận dụng lỗi phần mềm”. 

Bài viết được dựa trên nội dung của bài “From 0x90 to 0x4c454554, a journey into exploitation” tại địa chỉ: http://myne-us.blogspot.com/2010/08/from-0x90-to-0x4c454554-journey-into.html 

Cấu trúc của bài viết được chia nhỏ ra các phần một cách rõ ràng để mọi người có thể dễ dàng hơn trong quá trình học và nghiên cứu về khai thác lỗi phần mềm. Để thuận tiện cho quá trình nghiên cứu và học tập, Các bạn phải hoàn thành từng “chỉ mục” trước khi bước qua “chỉ mục” tiếp theo. 

Để quá trình học tập và thực hành việc tận dụng lỗi phần mềm dễ dàng hơn các bạn có thể tải các Cheatsheet về làm hình nền cho máy tính. Link: http://redmine.corelan.be:8800/projects/corelanart/files 

Ngoài ra còn một vài bài viết tiếng anh quan trọng khác các bạn nên đọc: 
- Lịch sử của quá trình khai thác lỗi phần mềm - http://www.abysssec.com/blog/2010/05/past-present-future-of-windows-exploitation/ 
- Làm thế nào để phá vỡ stack - http://5d4a.wordpress.com/2010/08/02/smashing-the-stack-in-2010/ 
- Các dự án tổng hợp tài liệu về bảo mật - https://code.google.com/p/it-sec-catalog/ 

Phần 1: Kiến thức lập trình (Programming) 

Chỉ mục 1: Hoàn thành quá trình này trước khi đọc cuốn sách "Hacking Art of exploitation" 

Khi bước chân vào con đường IT môn học tiên quyết bao giờ cũng là lập trình! Trong bảo mật nói chung và việc khai thác lỗi phần mềm nói riêng thì việc biết lập trình trở nên rất quan trọng bởi vì nếu bạn không có kiến thức về lập trình thì làm sao bạn có thể biết điểm yếu của một chương trình thường xuất hiện ở đâu? Nếu không có kiến thức lập trình thì làm sao bạn có thể đọc hiểu code để mà khai thác lỗi? ... 
Ngoài ra lập trình còn giúp bạn viết một số tool cho nhu cầu của riêng bạn, hay viết các đoạn mã khai thác lỗi … Dưới đây là một số ngôn ngữ lập trình phổ biến và hữu ích: 

Python: Đây là một ngôn ngữ mạnh mẽ, dễ dùng và rất nhiều tài liệu hướng dẫn. Đặc biệt đây còn là ngôn ngữ lập trình mà các hacker rất yêu thích và nó thường được sử dụng để khai thác lỗi phần mềm. 

Tài liệu tiếng anh:

-	Learn Python the hard way - http://learnpythonthehardway.org/static/LearnPythonTheHardWay.pdf 
-	Wikibooks Python - http://en.wikibooks.org/wiki/Subjectsmilieython_programming_language 
-	http://docs.python.org/ 
-	Một vài ebook miễn phí - http://www.onlinecomputerbooks.com/free-python-books.php 
-	Grey hat Python - http://oreilly.com/catalog/9781593271923 
 

Tài liệu tiếng Việt:

-	http://www.vithon.org/ 
 


Ruby: Đây là ngôn ngữ chủ yếu được dùng để viết các Exploit cho Công cụ Metasploit. Cho nên đây cũng là một ngôn ngữ rất tốt để bắt đầu học khai thác lỗi phần mềm. 

Tài liệu:

-	Wikibooks Ruby - http://en.wikibooks.org/wiki/Subject:Ruby_programming_language 
-	Little Book Of Ruby - http://www.sapphiresteel.com/IMG/pdf/LittleBookOfRuby.pdf 
-	Ruby Programmers Guide - http://www.ruby-doc.org/docs/ProgrammingRuby/ 
-	Một vài ebook miễn phí - http://www.onlinecomputerbooks.com/free-ruby-books.php 
 


Perl: Đây là một ngôn ngữ lâu đời nhưng vẫn còn rất nhiều người sử dụng, Nó là một trong những ngôn ngữ kịch bản (scripting languages) hữu dụng nhất và có rất nhiều exploit dùng đến nó. 

Tài liệu:

-	O'Reilly Learning Perl - http://www.amazon.com/Learning-Perl-5th-Randal-Schwartz/dp/0596520107/ref=sr_1_1?ie=UTF8&s=books&qid=1280901933&sr=8-1 
-	Một vài tài liệu miễn phí - http://www.onlinecomputerbooks.com/free-perl-books.php 
 


C/C++: Đây là một ngôn ngữ lập trình cực kỳ quan trọng, nó giúp cho bạn hiểu được bạn khai thác cái gì? Và bắt đầu khai như thế nào? Bạn không cần hiểu hết tất cả, nhưng khi hoàn thành phần này bạn có kiến thức tốt về lập trình C/C++. Đây cũng là ngôn ngữ lập trình được giảng dạy trong hầu hết các trường đại học ở Việt Nam hiện nay, vì thế tài liệu tiếng Việt rất đa dạng và phong phú. Dưới đây là một vài tài liệu cơ bản cần nắm vững. 

Tài liệu:

-	Cprogramming.com - http://cprogramming.com/ 
-	C Tutorial - http://www.java2s.com/Tutorial/C/CatalogC.htm 
-	Beej's Guide to C Programming - http://beej.us/guide/bgc/ 
-	Một vài ebook miễn phí - http://www.onlinecomputerbooks.com/free-c-books.php 
 


X86 Assembly: Tiếp theo chúng ta phải hiểu được máy tính đọc cái gì khi ta biên dịch C/C++. Chúng ta nên tập trung vào ngôn ngữ Assembly IA-32 (x86). Một vài tài liệu dưới đây được trình bày khá hay. 

Tài Liệu:

-	Skullsecurity: Assembly - http://www.skullsecurity.org/wiki/index.php/Fundamentals 
-	Windows Assembly Programming Tutorial - http://www.acm.uiuc.edu/sigwin/old/workshops/winasmtut.pdf 
-	http://en.wikibooks.org/wiki/X86_Assembly 
-	The Art of Assembly - http://homepage.mac.com/randyhyde/webster.cs.ucr.edu/index.html 
-	Assembly primer for hackers - http://www.securitytube.net/Assembly-Primer-for-Hackers-%28Part-1%29-System-Organization-video.aspx 
-	PC Assembly Language - http://www.drpaulcarter.com/pcasm/ 
 


Windows Programming: Lập trình windows giúp cho chúng ta hiểu được chương trình của chúng ta và cấu trúc của các thư viện hoạt động với hệ điều hành như thế nào. Những kiến thức này cực kỳ quan trọng về sau khi ta tiến hành khai thác lỗi phần mềm trên Windows. 

Tài liệu:

-	Windows Programming - http://en.wikibooks.org/wiki/Windows_Programming 
-	Windows API Tutorial - http://www.relisoft.com/win32/index.htm 
-	Windows Sysinternals - http://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Dstripbooks&field-keywords=windows+sysinternals&x=0&y=0 
-	Windows Internals 4 - http://www.amazon.com/Microsoft-Windows-Internals-4th-Server/dp/0735619174 
 


Disassembly: Disassembly không hẳn là lập trình, Nó trình bày những gì máy tính hiểu và tính toán thông qua CPU và bộ nhớ . Đây là một kỹ năng mà chúng ta cần nắm vững. 

Tài liệu:

-	http://en.wikibooks.org/wiki/X86_Disassembly 
-	The Art of Disassembly - http://tuts4you.com/download.php?view.187 
 

Ngoài các kiến thức lập trình trên bạn còn phải sử dụng thành thạo Windows cũng như Linux, nó giúp ích rất nhiều cho quá trình nghiên cứu và tận dụng lỗi phần mềm. 

Phần 2: Bắt đầu quá trình tìm và khai thác lỗi 

Sau khi tìm hiểu phần 1, bạn đã có nắm vững kiến thức về lập trình và những gì máy đang thực hiện mà chúng ta có thể can thiệp trực tiếp vào – Khai thác lỗi 

Phần này gồm rất nhiều bài học được tổng hợp dưới các link sau: 

Smash the stack for fun and profit (Phrack 49) - http://www.phrack.org/issues.html?issue=49&id=14#article
C function call conventions and the stack - http://cs.umbc.edu/~chang/cs313.s02/stack.shtml
Anatomy of a program in memory - http://duartes.org/gustavo/blog/post/anatomy-of-a-program-in-memory
Function Calls, Part 1 (the Basics) - http://www.codeguru.com/cpp/misc/misc/assemblylanguage/article.php/c14641
IA-32 Architecture - http://www.sandpile.org/ia32/index.htm
Video Code Audit - http://pentest.cryptocity.net/code-audits/

(Chỉ mục 1 - Đã hoàn thành: Sau khi hoàn thành chỉ mục một bạn phải nắm vững một trong các ngôn ngữ lập trình đã kể trên. Đồng thời có kiến thức tốt về stack và cách gọi hàm ) 

Hacking art of exploitation [Chapter 1&2] - http://www.amazon.com/Hacking-Art-Exploitation-Jon-Erickson/dp/1593271441/ref=sr_1_fkmr1_1?ie=UTF8&qid=1280905635&sr=1-1-fkmr1
Exploit writing tutorial part 1 : Stack Based Overflows - http://www.corelan.be/index.php/2009/07/19/exploit-writing-tutorial-part-1-stack-based-overflows/
Exploit writing tutorial part 2 : Stack Based Overflows – jumping to shellcode - http://www.corelan.be/index.php/2009/07/23/writing-buffer-overflow-exploits-a-quick-and-basic-tutorial-part-2/

Chỉ mục 2 – Hoàn thành việc chuẩn bị kiến thức các phần sau trước khi kết thúc phần 2 

Đọc một vài bài viết đầu tiên tại Blog http://blog.ksplice.com/2010/03/ có nhiều thông tin hữu ích. 
Một vài bài viết tại blog http://www.nullthreat.net/ giúp ích rất nhiều cho quá trình trở thành một người kiểm tra lỗi phần mềm. 
The Stack-based Buffer Overflow Vulnerability and Exploit Experimental Demonstration - http://www.tenouk.com/Bufferoverflowc/stackbasedbufferoverflow.html
The Tao of Windows Buffer Overflow - http://www.cultdeadcow.com/cDc_files/cDc-351/index.html
How do buffer overflow attacks work? - http://nsfsecurity.pr.erau.edu/bom/index.html
Buffer Overflows - http://www.hackerscenter.com/index.php?/Downloads/Library/Application-Security/View-category.html
Video Buffer overflow Primer - http://www.securitytube.net/Buffer-Overflow-Primer-Part-1-%28Smashing-the-Stack%29-video.aspx
Shellcoder's Handbook Ch1&2 - http://www.amazon.com/Shellcoders-Handbook-Discovering-Exploiting-Security/dp/047008023X/ref=sr_1_1?ie=UTF8&s=books&qid=1282450549&sr=8-1
Hacking art of exploitation [Chapter 3] - http://www.amazon.com/Hacking-Art-Exploitation-Jon-Erickson/dp/1593271441/ref=sr_1_fkmr1_1?ie=UTF8&qid=1280905635&sr=1-1-fkmr1
Exploit writing tutorial part 3 : SEH Based Exploits - http://www.corelan.be/index.php/2009/07/25/writing-buffer-overflow-exploits-a-quick-and-basic-tutorial-part-3-seh/
Exploit writing tutorial part 3b : SEH Based Exploits – just another example - http://www.corelan.be/index.php/2009/07/28/seh-based-exploit-writing-tutorial-continued-just-another-example-part-3b/
Tutorial: SEH Based Exploits and the Development Process - http://www.ethicalhacker.net/content/view/309/2/
SEH Overwrites Simplified - http://www.shell-storm.org/papers/files/405.pdf

Tiện đây mình xin giới thiệu một tài liệu hiếm hoi về khai thác lỗi phần mềm bằng tiếng việt, đó là cuốn “Nghệ thuật tận dụng lỗi phần mềm” – Nguyễn Thành Nam. Nơi mua có thể tham khảo tại topic http://www.hvaonline.net/hvaonline/posts/list/80/31846.hva. Theo mình đây là một tài liệu rất hữu ích cho những người mới bắt đầu tìm hiểu về khai thác lỗi phần mềm. 
(Chỉ mục 2 – Đã hoàn thành) 

Phần 3 – Các công cụ cần thiết 

Đây là danh sách các công cụ cần thiết và rất hữu dụng: 
Immunity Debugger - http://www.immunityinc.com/products-immdbg.shtml
Ollydbg - http://www.ollydbg.de/
Windbg - http://msdn.microsoft.com/en-us/windows/hardware/gg463016.aspx
IDA Pro - http://www.hex-rays.com/idapro/
Sysinternals - http://technet.microsoft.com/en-us/sysinternals/bb795533.aspx
Explorer Suite - http://www.ntcore.com/exsuite.php

Và dưới đây là những bài viết của Corelan về cách sử dụng chúng trong việc khai thác lỗi. Các bài viết sẽ được cập nhật thêm sau: 
Exploit writing tutorial part 5 : How debugger modules & plugins can speed up basic exploit development - http://www.corelan.be/index.php/2009/09/05/exploit-writing-tutorial-part-5-how-debugger-modules-plugins-can-speed-up-basic-exploit-development/
Corelan: Immunity debugger cheatsheet - http://www.corelan.be/index.php/2010/01/26/starting-to-write-immunity-debugger-pycommands-my-cheatsheet/

Ngoài ra các bạn cũng có thể tìm đọc một vài tài liệu hướng dẫn sử dụng các chương trình trên internet 

Phần 4 – Kiến thức về mạng và Metasploit 

Kiến thức về mạng là một phần rất quan trọng trong việc khai thác lỗi phần mềm, nếu có kiến thức tốt về mạng và lập trình mạng bạn có thể khai thác lỗi thông qua mạng LAN hay internet và có thể chiếm quyền và điều khiển máy tính từ xa. 
Beej's Guide to Network Programming - http://beej.us/guide/bgnet/output/html/multipage/index.html
Hacking art of exploitation [Chapter 4] - http://www.amazon.com/Hacking-Art-Exploitation-Jon-Erickson/dp/1593271441/ref=sr_1_fkmr1_1?ie=UTF8&qid=1280905635&sr=1-1-fkmr1
Socket Programming in Ruby - https://www6.software.ibm.com/developerworks/education/l-rubysocks/l-rubysocks-a4.pdf

Metasploit là một công cụ tìm và khai thác lỗi phần mềm phổ biến nhất hiện nay. Các link bài viết dưới đây sẽ giúp các bạn biết sử dụng hiệu quả công cụ này. 
Video Security Tube: Metasploit Megaprimer - http://www.securitytube.net/video/1175
http://www.metasploit.com/
Metasploit Unleashed - http://www.offensive-security.com/metasploit-unleashed/Metasploit_Unleashed_Information_Security_Training
Video Metasploit Louisville Class - http://www.irongeek.com/i.php?page=videos/metasploit-class
Metasploitable (a target) - http://blog.metasploit.com/2010/05/introducing-metasploitable.html
Exploit writing tutorial part 4 : From Exploit to Metasploit – The basics - http://www.corelan.be/index.php/2009/08/12/exploit-writing-tutorials-part-4-from-exploit-to-metasploit-the-basics/
Video Developing my first exploit - http://guides.intern0t.net/msf2.php
Exploit Creation in Metasploit - http://www.youtube.com/user/DHAtEnclaveForensics#p/u/9/rGlvgeeU0vQ
Wikibooks Metasploit/Writing Windows Exploit - http://en.wikibooks.org/wiki/Metasploit/WritingWindowsExploit

Phần 5 – Shellcode 

Phần này chúng ta sẽ tìm hiểu cách viết shellcode để khai thác lỗi 
Exploit writing tutorial part 9 : Introduction to Win32 shellcoding - http://www.corelan.be/index.php/2010/02/25/exploit-writing-tutorial-part-9-introduction-to-win32-shellcoding/
Shellcode Tutorials - http://projectshellcode.com/?q=node/12
Shellcoder's Handbook Ch3 - http://www.amazon.com/Shellcoders-Handbook-Discovering-Exploiting-Security/dp/047008023X/ref=sr_1_1?ie=UTF8&s=books&qid=1282450549&sr=8-1
Hacking art of exploitation [Chapter 5] - http://www.amazon.com/Hacking-Art-Exploitation-Jon-Erickson/dp/1593271441/ref=sr_1_fkmr1_1?ie=UTF8&qid=1280905635&sr=1-1-fkmr1
Writing small shellcode - http://www.shell-storm.org/papers/files/440.pdf
Shell-storm Shellcode database - http://www.shell-storm.org/shellcode/
Advanced shellcode - http://www.vividmachines.com/shellcode/shellcode.html#as

Phần 6 - Kỹ thuật Reverse 

Chỉ mục 3: Cần ghi nhớ phần này để tham khảo và sử dụng trong quá trình reverse 
Understanding Code - http://www.reteam.org/papers/e57.pdf
Reverse Engineering the World - http://mattoh.wordpress.com/
Reversing for Newbies - http://tuts4you.com/download.php?list.17
Intro to Reverse Engineering - http://www.ethicalhacker.net/content/view/152/2/
Introduction to Reverse Engineering Software - http://www.acm.uiuc.edu/sigmil/RevEng/
Reversing blog post - http://www.room362.com/blog/2009/6/12/getting-your-fill-of-reverse-engineering-and-malware-analysi.html
Reversing: secrets of reverse engineering - http://www.amazon.com/Reversing-Secrets-Engineering-Eldad-Eilam/dp/0764574817/ref=sr_1_1?s=books&ie=UTF8&qid=1280937813&sr=1-1
Video Reverse Engineering - http://pentest.cryptocity.net/reverse-engineering/
CrackZ's Reverse Engineering Page - http://www.woodmann.com/crackz/
Video Reverse engineering techniques - http://www.securitytube.net/video/572
History of Packing Technology - http://securitylabs.websense.com/content/Assets/HistoryofPackingTechnology.pdf
Windows PE Header - http://marcoramilli.blogspot.com/2010/12/windows-pe-header.html
OpenRCE Articles - http://www.openrce.org/articles/

Và một diễn đàn về Reverse engineering lớn và có uy tín nhất Việt Nam đó là http://reaonline.net/ 
Để tăng kiến thức và kỹ năng reverse engineering bạn phải thường xuyên luyện tập và đúc rút kinh nghiệm cho bản thân. Một trang web cung cấp crackme để bạn thực hành là http://crackmes.de/ 

Phần 7 – Bắt đầu tìm hiểu sâu hơn về tràn bộ đệm (Buffer overflow) 

Để nắm vững phần này các bạn nên thực hành nhiều để hiểu rõ vấn đề, Các bạn hãy tìm một vài exploit cũ tại http://www.exploit-db.com/ tải về thực hành, nắm vững cách thức hoạt động của nó, và viết lại nó theo cách của bạn. 

A – Ngăn chặn lỗi tràn bộ đệm 
Buffer overflow protection - http://en.wikipedia.org/wiki/Buffer_overflow_protection
Video The evolution of Microsoft's Mitigations - http://technet.microsoft.com/en-us/security/dd285253.aspx
Canary Bit - http://www.cs.purdue.edu/homes/mkirkpat/papers/canbit.pdf
Preventing the Exploitation of Structured Exception Handler (SEH) Overwrites with SEHOP - http://blogs.technet.com/b/srd/archive/2009/02/02/preventing-the-exploitation-of-seh-overwrites-with-sehop.aspx
Bypassing SEHOP - http://www.sysdream.com/articles/sehop_en.pdf
Executable space protextion - http://en.wikipedia.org/wiki/Executable_space_protection
Data Execution Prevention - http://en.wikipedia.org/wiki/Data_Execution_Prevention
Bypassing Hardware based Data Execution Prevention - http://www.securestate.com/Downloadables/Documents/Whitepapers/Bypassing_Hardware_based_Data_Execution_Prevention.pdf
Address space layout randomization - http://en.wikipedia.org/wiki/ASLR
An Analysis of Address Space Layout Randomization on Windows Vista - http://www.symantec.com/avcenter/reference/Address_Space_Layout_Randomization.pdf
Defeating the Stack Based Buffer Overflow Prevention - http://dl.packetstormsecurity.net/papers/bypass/defeating-w2k3-stack-protection.pdf
Exploit writing tutorial part 6 : Bypassing Stack Cookies, SafeSeh, SEHOP, HW DEP and ASLR - http://www.corelan.be/index.php/2009/09/21/exploit-writing-tutorial-part-6-bypassing-stack-cookies-safeseh-hw-dep-and-aslr/
Return-to-libc attack - https://secure.wikimedia.org/wikipedia/en/wiki/Return-to-libc_attack
Video Microsoft protections video - http://technet.microsoft.com/en-us/security/dd285253.aspx

B – Tràn bộ đệm nâng cao 
Video Exploitation - http://pentest.cryptocity.net/exploitation/
Exploit writing tutorial part 7 : Unicode – from 0×00410041 to calc - http://www.corelan.be/index.php/2009/11/06/exploit-writing-tutorial-part-7-unicode-from-0x00410041-to-calc/
Exploit writing tutorial part 8 : Win32 Egg Hunting - http://www.corelan.be/index.php/2010/01/09/exploit-writing-tutorial-part-8-win32-egg-hunting/
Exploit writing tutorial part 10 : Chaining DEP with ROP – the Rubik’s[TM] Cube - http://www.corelan.be/index.php/2010/06/16/exploit-writing-tutorial-part-10-chaining-dep-with-rop-the-rubikstm-cube/
Video Virtual Worlds - Real Exploits - http://www.youtube.com/watch?v=UIKy1Shxd6Q

Ngoài ra các bạn cũng có thể thực hành làm quen với các bài tập tìm và khai thác lỗi lập trình tại http://community.corest.com/~gera/InsecureProgramming/ một vài bài tập tại đây đã được giải thích rất rõ trong cuốn sách “Nghệ thuật tận dụng lỗi phần mềm”. 
Và một trang wargame khá hay nữa đó là http://www.smashthestack.org/ 
Các bạn cũng nên xem qua topic của bạn choc_ http://www.hvaonline.net/hvaonline/posts/list/27801.hva 
Trên HVA cũng có một topic bàn về các wargame về khai thác lỗi phần mềm trên trang http://www.overthewire.org/wargames/ . Các bạn có thể xem tại http://www.hvaonline.net/hvaonline/posts/list/23615.hva 

Phần 8 – Heap Overflow 
Heap Overflows for Humans - http://www.exploit-db.com/download_pdf/15982
rm -rf / on heap overflow - http://pthreads.blogspot.com/2007/04/heap-overflow.html
Shellcoder's Handbook Ch4&5 - http://www.amazon.com/Shellcoders-Handbook-Discovering-Exploiting-Security/dp/047008023X/ref=sr_1_1?ie=UTF8&s=books&qid=1282450549&sr=8-1
A heap of risk - http://www.h-online.com/security/features/A-Heap-of-Risk-747161.html
Video Defcon 15 remedial Heap Overflows - http://video.google.com/videoplay?docid=1985155227368288256#
Heap overflow: ancient art of unlink seduction - http://www.thehackerslibrary.com/?p=872
Memory corruptions part II – heap - http://advancedwindowsdebugging.com/ch06.pdf

Và đọc những phần còn lại của cuốn sách Shellcoder's Handbook 

Phần 9 – Danh sách các trang web cung cấp exploit 

Hãy thường xuyên truy cập vào các trang web dưới đây để tìm kiếm và tải về các exploit mới nhất để nghiên cứu 
http://www.exploit-db.com/
http://www.cvedetails.com/
http://packetstormsecurity.org/files/tags/exploit/
http://www.us-cert.gov/cas/techalerts/
http://cve.mitre.org/cve/index.html
http://web.nvd.nist.gov/view/vuln/search?cid=3
http://cwe.mitre.org/index.html

Phần 10 – Rèn luyện -- updating 

Để trở thành một chuyên gia khai thác lỗi phần mềm bạn phải thường xuyên tìm kiếm và khai thác lỗi phần mềm, có thể là một wargame hay là một ứng dụng nào đó trên máy tính của bạn. Trong quá trình luyện tập bạn sẽ đúc rút ra được những kinh nghiệm quý giá cho bản thân. 

Do tài liệu về mảng này trên mạng cũng không nhiều và khá rời rạc, cho nên bài viết trên tổng hợp lại những tài liệu và địa chỉ hữu ích cho các bạn có thể tham khảo. Chính vì tài liệu có từ rất nhiều nguồn khác nhau nên, nếu chỉ tổng hợp các bài viết thành một file pdf thì không thể đảm bảo được sự liền mạch và khoa học của một tài liệu. Để tổng hợp và viết lại thành một giáo trình hoàn chỉnh đòi hỏi thời gian và kiến thức sâu về từng mục. 

Một số cuốn sách không có link download mình sẽ đưa lên sau, hoặc các bạn có thể tự tìm trên internet 

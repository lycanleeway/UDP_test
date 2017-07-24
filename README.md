# UDP_test
UDP_test for VLP-16 PS: no message description
written by liwei  2017.07.24 in Hangzhou

following this web:
http://blog.csdn.net/qingzai_/article/details/50834146

A Win32 Console Appliacation (not empty)

Tip1:
siLocal.sin_addr.s_addr = htonl(0xC0A80A21);                 //IP changeable             使用htonl 代替编译总是出错的 inet_addr
//	siLocal.sin_addr.s_addr = inet_addr("192.168.10.33");

Tip2:
	//		cout << inet_ntoa(siRemote.sin_addr) << endl
	//		<< pszRecv << endl;
			char sendBuf[20] = { '\0' };
			cout << inet_ntop(AF_INET, (void*)&siRemote.sin_addr, sendBuf, 16) << endl
				<< pszRecv << endl;
        
Tip3:
int nPort = 2368;                                                  ///port changeable
//int nPort = 1234;  

Tip4:
//申请内存  
	pszRecv = new char[4096];                          /// 4096  changeable
  

not ending...

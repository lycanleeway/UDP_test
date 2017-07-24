# UDP_test
UDP_test for VLP-16 PS: no message description
written by liwei in Hangzhou
// UDP_test.cpp : Defines the entry point for the console application.
//
 /* Item:UDP_Velodyne test
    Author: liwei33
    Date: 2017.07.21
    Version 1.0          */

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
-------------------------------------------------------------------------------------------------------------------------
2017.07.24
#Addition#

printf("length,%d\n", nRet);

printf("1208: %x\n", unsigned char(pszRecv[1208]));

printf("Factory Bytes: %x%x\n", unsigned char(pszRecv[1204]), unsigned char( pszRecv[1205]));

printf("Time stamp: %x;%x;%x;%x\n", unsigned char(pszRecv[1200]), unsigned char(pszRecv[1201]), unsigned char(pszRecv[1202]), unsigned char(pszRecv[1203]));

printf("First Flag: %x%x\n", unsigned char( pszRecv[0]), unsigned char(pszRecv[1]));
printf("Second Flag: %x%x\n", unsigned char( pszRecv[100]), unsigned char( pszRecv[101]));

printf("\n");

###这只是循环接收30次
可加入 esc 判定接收结束  ###
注：usigned char 是为了 解决 printf 对有/无符号判定 造成ffffff的问题

---------------------------------------------------------------------------------------------------------------------------------
 




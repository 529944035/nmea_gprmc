C/C++ ʹ��ChinaMapShift�� ���Ի�ת: ����WGS-84 ����GCJ-02 �ٶ�BD-09


**�ص�����**��Ӧ-�й���ͼ ���õ��ǻ�������
http://cn.bing.com/ditu/
	
	**�ص�����**NMEA Tools �ɼ��Ķȷָ�ʽҪ��ת��С����ʽ
	**�ص�����**��ת�ɻ������꣬�������й���ͼ�϶�Ӧ��
�㷨��ֻ���Լ�������	
https://github.com/Dronaldo17/ChinaMapShift
	Algorithm for the map offset problem in China. 
	**�ص�����**����й���ͼƫ��������㷨��
	
![��Ӧ-�й���ͼ ���õ��ǻ�������](https://github.com/hongwenjun/nmea_gprmc/blob/master/WGS2GCJ/WGS2GCJ.png) 

***
���Դ���
```
#include <iostream>
#include <string>
#include <stdio.h>
#include "china_shift.h"
#include <iomanip>

// Transform WGS-84 to GCJ-02 (Chinese encrypted coordination system)

//    typedef struct {
//        double lng;
//        double lat;
//    } Location;
//
//    Location transformFromWGSToGCJ(Location wgLoc);
//    Location transformFromGCJToWGS(Location gcLoc);
//    Location bd_encrypt(Location gcLoc);
//    Location bd_decrypt(Location bdLoc);


using namespace std;

int main()
{

    puts("����WGS-84 ת ����GCJ-02 ת  �ٶ�BD-09");

    Location gps = { 119.465265, 29.1934702};
    cout << setprecision(9) << "����WGS-84: "  << gps.lat << "  " << gps.lng << endl;

    gps = transformFromWGSToGCJ(gps);
    cout << "����GCJ-02: "  << gps.lat << "  " << gps.lng << endl;

    gps = bd_encrypt(gps);
    cout << "�ٶ� BD-09: "  << gps.lat << "  " << gps.lng << endl;

    cout << endl << endl;



    puts("�ٶ�BD-09  ת ����GCJ-02 ת  ����WGS-84");

    gps = { 119.476936, 29.196518};
    cout << "�ٶ� BD-09: "  << gps.lat << "  " << gps.lng << endl;

    gps = bd_decrypt(gps);
    cout << "����GCJ-02: "  << gps.lat << "  " << gps.lng << endl;

    gps = transformFromGCJToWGS(gps);
    cout << "����WGS-84: "  << gps.lat << "  " << gps.lng << endl;

    return 0;
}


```
***
```
����WGS-84 ת ����GCJ-02 ת  �ٶ�BD-09
����WGS-84: 29.1934702  119.465265
����GCJ-02: 29.1908196  119.470341
�ٶ� BD-09: 29.1965172  119.476936


�ٶ�BD-09  ת ����GCJ-02 ת  ����WGS-84
�ٶ� BD-09: 29.196518  119.476936
����GCJ-02: 29.1908195  119.470342
����WGS-84: 29.1934702  119.465265

��������������ʹ�ðٶ�API��ͼȡ�ĵ㣬��ת��WGS-84���꣬�� maps.google.com�ϵ�ͼ��Ӧ�� 
Google��ͼ�й��棬��������뼸���������꣬ͨ�����·�ʽ����������%09��ת���
http://www.google.cn/maps/dir/29.1934702%09119.465265/29.1908196%09119.470341/29.1965172%09119.476936/

```
�������
https://github.com/hongwenjun/nmea_gprmc
https://github.com/hongwenjun/TrajectoryCombine

 

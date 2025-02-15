---
title: 'base64 encode & decode'
author: openmicrolab
type: post
date: 2011-09-15T11:55:01+00:00
url: /base64-encode-decode/
dsq_thread_id:
  - "1261936051"
categories:
  - Infomation
  - Development
tags:
  - BASE64
  - base64 decode
  - base64 encode

---
base64란 64진수라는 뜻.  
즉 2진수 데이터를 64진수 데이터로 변경하는 것.  
예를&nbsp;들면 a, b, c의 경우 ASCII값은 0x61, 0x62, 0x63이고, 2진수로 01100001, 01100010, 01100011이다  
이것을 6bit씩 끊으면&#8230;. 011000&nbsp; 010110&nbsp; 001001 100011 가 되고, 각각 값은 0x18(24), 0x16(22), 0x09(9), 0x23(35)가 된다.

base64의 문자셋은 다음과 같으므로,  
A~Z : 0 ~25  
a~z : 26 ~51  
0~9 : 52 ~ 61  
+&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; : 62  
/&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; : 63  
위 abc는 YWJj가 된다.

만약 딱 떨어지지 않는 경우 남는 비트의 경우 6 bit 문자를&nbsp;0으로 padding하고 그래도 남는 6 bit 문자는 = 으로 치환한다.

C코드  


  
<DIV style="BORDER-BOTTOM: #eeeeee 1px solid; BORDER-LEFT: #eeeeee 1px solid; PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #eeeeee; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; BORDER-TOP: #eeeeee 1px solid; BORDER-RIGHT: #eeeeee 1px solid; PADDING-TOP: 10px" class=txc-textbox>#include ＜stdio.h>  
#include ＜stdlib.h>  
#include ＜time.h>  
#include ＜endian.h>  
&nbsp;  
static const char MimeBase64[] = {  
&nbsp;&nbsp;&nbsp; &#8216;A&#8217;, &#8216;B&#8217;, &#8216;C&#8217;, &#8216;D&#8217;, &#8216;E&#8217;, &#8216;F&#8217;, &#8216;G&#8217;, &#8216;H&#8217;,  
&nbsp;&nbsp;&nbsp; &#8216;I&#8217;, &#8216;J&#8217;, &#8216;K&#8217;, &#8216;L&#8217;, &#8216;M&#8217;, &#8216;N&#8217;, &#8216;O&#8217;, &#8216;P&#8217;,  
&nbsp;&nbsp;&nbsp; &#8216;Q&#8217;, &#8216;R&#8217;, &#8216;S&#8217;, &#8216;T&#8217;, &#8216;U&#8217;, &#8216;V&#8217;, &#8216;W&#8217;, &#8216;X&#8217;,  
&nbsp;&nbsp;&nbsp; &#8216;Y&#8217;, &#8216;Z&#8217;, &#8216;a&#8217;, &#8216;b&#8217;, &#8216;c&#8217;, &#8216;d&#8217;, &#8216;e&#8217;, &#8216;f&#8217;,  
&nbsp;&nbsp;&nbsp; &#8216;g&#8217;, &#8216;h&#8217;, &#8216;i&#8217;, &#8216;j&#8217;, &#8216;k&#8217;, &#8216;l&#8217;, &#8216;m&#8217;, &#8216;n&#8217;,  
&nbsp;&nbsp;&nbsp; &#8216;o&#8217;, &#8216;p&#8217;, &#8216;q&#8217;, &#8216;r&#8217;, &#8216;s&#8217;, &#8216;t&#8217;, &#8216;u&#8217;, &#8216;v&#8217;,  
&nbsp;&nbsp;&nbsp; &#8216;w&#8217;, &#8216;x&#8217;, &#8216;y&#8217;, &#8216;z&#8217;, &#8216;0&#8217;, &#8216;1&#8217;, &#8216;2&#8217;, &#8216;3&#8217;,  
&nbsp;&nbsp;&nbsp; &#8216;4&#8217;, &#8216;5&#8217;, &#8216;6&#8217;, &#8216;7&#8217;, &#8216;8&#8217;, &#8216;9&#8217;, &#8216;+&#8217;, &#8216;/&#8217;  
};  
&nbsp;  
static int DecodeMimeBase64[256] = {  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* 00-0F \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* 10-1F \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,62,-1,-1,-1,63,&nbsp; /\* 20-2F \*/  
&nbsp;&nbsp;&nbsp; 52,53,54,55,56,57,58,59,60,61,-1,-1,-1,-1,-1,-1,&nbsp; /\* 30-3F \*/  
&nbsp;&nbsp;&nbsp; -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9,10,11,12,13,14,&nbsp; /\* 40-4F \*/  
&nbsp;&nbsp;&nbsp; 15,16,17,18,19,20,21,22,23,24,25,-1,-1,-1,-1,-1,&nbsp; /\* 50-5F \*/  
&nbsp;&nbsp;&nbsp; -1,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,&nbsp; /\* 60-6F \*/  
&nbsp;&nbsp;&nbsp; 41,42,43,44,45,46,47,48,49,50,51,-1,-1,-1,-1,-1,&nbsp; /\* 70-7F \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* 80-8F \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* 90-9F \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* A0-AF \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* B0-BF \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* C0-CF \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* D0-DF \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,&nbsp; /\* E0-EF \*/  
&nbsp;&nbsp;&nbsp; -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1,-1&nbsp;&nbsp; /\* F0-FF \*/  
};  
&nbsp;  
typedef union{  
&nbsp;&nbsp;&nbsp; struct{  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; unsigned char c1,c2,c3;  
&nbsp;&nbsp;&nbsp; };  
&nbsp;&nbsp;&nbsp; struct{  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; unsigned int e1:6,e2:6,e3:6,e4:6;  
&nbsp;&nbsp;&nbsp; };  
} BF;  
&nbsp;  
int endian = 0; // little : 0, big : 1  
&nbsp;  
void base64e(char \*src, char \*result, int length){  
&nbsp;&nbsp;&nbsp; int i, j = 0;  
&nbsp;&nbsp;&nbsp; BF temp;  
&nbsp;  
&nbsp;&nbsp;&nbsp; if(endian == 0){ // little endian(intel)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; for(i = 0 ; i < length ; i = i+3, j = j+4){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.c3 = src[i];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+1) > length) temp.c2 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; else temp.c2 = src[i+1];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+2) > length) temp.c1 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; else temp.c1 = src[i+2];  
&nbsp;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j]&nbsp;&nbsp; = MimeBase64[temp.e4];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+1] = MimeBase64[temp.e3];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+2] = MimeBase64[temp.e2];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+3] = MimeBase64[temp.e1];  
&nbsp;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+2) > length) result[j+2] = &#8216;=&#8217;;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+3) > length) result[j+3] = &#8216;=&#8217;;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }  
&nbsp;&nbsp;&nbsp; } else { // big endian(sun)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; for(i = 0 ; i < length ; i = i+3, j = j+4){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.c1 = src[i];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+1) > length) temp.c2 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; else temp.c2 = src[i+1];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+2) > length) temp.c3 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; else temp.c3 = src[i+2];  
&nbsp;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j]&nbsp;&nbsp; = MimeBase64[temp.e4];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+1] = MimeBase64[temp.e3];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+2] = MimeBase64[temp.e2];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+3] = MimeBase64[temp.e1];  
&nbsp;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+2) > length) result[j+2] = &#8216;=&#8217;;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if((i+3) > length) result[j+3] = &#8216;=&#8217;;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }  
&nbsp;&nbsp;&nbsp; }  
}  
&nbsp;  
void base64d(char \*src, char \*result, int *length){  
&nbsp;&nbsp;&nbsp; int i, j = 0, src_length, blank = 0;  
&nbsp;&nbsp;&nbsp; BF temp;  
&nbsp;  
&nbsp;&nbsp;&nbsp; src_length = strlen(src);  
&nbsp;  
&nbsp;&nbsp;&nbsp; if(endian == 0){ // little endian(intel)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; for(i = 0 ; i < src_length ; i = i+4, j = j+3){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e4 = DecodeMimeBase64[src[i]];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e3 = DecodeMimeBase64[src[i+1]];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if(src[i+2] == &#8216;=&#8217;){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e2 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; blank++;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; } else temp.e2 = DecodeMimeBase64[src[i+2]];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if(src[i+3] == &#8216;=&#8217;){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e1 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; blank++;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; } else temp.e1 = DecodeMimeBase64[src[i+3]];  
&nbsp;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j]&nbsp;&nbsp; = temp.c3;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+1] = temp.c2;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+2] = temp.c1;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }  
&nbsp;&nbsp;&nbsp; } else { // big endian(sun)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; for(i = 0 ; i < src_length ; i = i+4, j = j+3){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e4 = DecodeMimeBase64[src[i]];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e3 = DecodeMimeBase64[src[i+1]];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if(src[i+2] == &#8216;=&#8217;){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e2 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; blank++;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; } else temp.e2 = DecodeMimeBase64[src[i+2]];  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if(src[i+3] == &#8216;=&#8217;){  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; temp.e1 = 0x00;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; blank++;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; } else temp.e1 = DecodeMimeBase64[src[i+3]];  
&nbsp;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j]&nbsp;&nbsp; = temp.c1;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+1] = temp.c2;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; result[j+2] = temp.c3;  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }  
&nbsp;&nbsp;&nbsp; }  
&nbsp;&nbsp;&nbsp; *length = j-blank;  
}  
&nbsp;  
int main(void){  
&nbsp;&nbsp;&nbsp; char str1[]=&#8221;테스트문자열입니다.ABCabc123,./&#8221;;  
&nbsp;&nbsp;&nbsp; char str2[]=&#8221;7YWM7Iqk7Yq466y47J6Q7Je07J6F64uI64ukLkFCQ2FiYzEyMywuLw==&#8221;;  
&nbsp;&nbsp;&nbsp; char *result;  
&nbsp;&nbsp;&nbsp; int src_size;  
&nbsp;&nbsp;&nbsp; struct timespec start,end;  
&nbsp;  
&nbsp;&nbsp;&nbsp; if (_\_LITTLE\_ENDIAN == BYTE_ORDER) endian == 0;  
&nbsp;&nbsp;&nbsp; else endian == 1;  
&nbsp;  
&nbsp;&nbsp;&nbsp; src_size = strlen(str1);  
&nbsp;&nbsp;&nbsp; result = (char \*)malloc((4 \* (src\_size / 3)) + (src\_size % 3 ? 4 : 0) + 1);  
&nbsp;&nbsp;&nbsp; clock\_gettime(CLOCK\_REALTIME, &start);  
&nbsp;&nbsp;&nbsp; base64e(str1, result, src_size);  
&nbsp;&nbsp;&nbsp; clock\_gettime(CLOCK\_REALTIME, &end);  
&nbsp;&nbsp;&nbsp; float time\_dif = (end.tv\_sec &#8211; start.tv\_sec) + ((end.tv\_nsec &#8211; start.tv_nsec) );  
&nbsp;&nbsp;&nbsp; printf(&#8220;함수 수행 시간: %f\n&#8221;, time_dif);  
&nbsp;&nbsp;&nbsp; printf(&#8220;%s\n%s\n&#8221;,str1,result);  
&nbsp;&nbsp;&nbsp; free(result);  
&nbsp;  
&nbsp;&nbsp;&nbsp; src_size = strlen(str2);  
&nbsp;&nbsp;&nbsp; result = (char \*)malloc(3 \* (src_size / 4));  
&nbsp;&nbsp;&nbsp; base64d(str2,result,&src_size);  
&nbsp;&nbsp;&nbsp; printf(&#8220;%s\n%s\n길이:%d\n&#8221;,str2,result,src_size);  
&nbsp;&nbsp;&nbsp; free(result);  
}  
</DIV>  




온라인에서 base64를 테스트 할 수 있는 사이트 : <http://ostermiller.org/calc/encode.html>

&nbsp;
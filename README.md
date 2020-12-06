
# Linux Shell Types
 - sh (Bourne shell) : By Unix Shell, Super shell
 - bash (Bourne-agin shell) : Super shell in Linux
 - csh (C shell) : C like syntax
 - tcsh (Enhanced-C shell): c
 - ksh (korn shell) : by David Korn, Powerful Script Language
 - zch (Z shell) : Unix/GNU shell script, Powerful Script Language
 
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# Linux File System Directories
/bin : 기본 명령어
/boot : for booting
/dev : device file, cd-rom
/etc : config, passwd, rc.d
/home : user home dir
/lib : shared library
/media : ssd
/opt : application software package
/proc : process info	 / /proc/cpuinfo : cpu에 대한 정보
/root : root home dir
/sbin : 관리자용, ifconfig
/srv : system data
/tmp : temporary dir
/usr : source or programs
/usr/local
/var : logs, ftp, spool, mail
/lost+found => 트리의 index 

cf. inode  (ls -il)

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# linux ports
20  FTP (data)
21  FTP (Control)
22  SSH / rsync / rcp
23  Telnet
25  SMTP (Simple Mail Transfer)
465 SMTPS
43  whois
53  DNS
80   HTTP
443  HTTPS
110  POP3 => 메일서버 구성시 필요
995  POP3S => 메일서버 구성시 필요
123  NTP (Network Time Protocol)
143  IMAP2/4
993  IMAPS
514  SysLog

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# linux 기본 명령어
touch : reload 기능 or 파일 생성
cat :  전체 내용 가져오기
head : 윗부분 내용/ tail : 뒷부분 내용
which : 파일 위치 / clear : 화면 clear / echo : 커맨드 창에 print
cd : 디렉토리 이동/ cd - : 이전 디렉토리 이동 
mkdir : 디렉토리 생성 / rmdir : 디렉토리 삭제 (아무것도 없을 시 가능)
find : 파일 위치 찾기
passwd : 패스워드 변경
df : 전체 디바이스 
du : 디렉토리 사용량
free : 메모리
top : 작업관리자
vmstat : cpu 사용량
ps -ef | grep ~ : 프로세스 확인
chmod : 사용권한
chown : 사용자 변경
ln : 링크 

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# linux 사용자 설정
$> useradd -g <group> <userid> : user 생성
#> groupadd <group> : 유저들의 group 생성
$> passwd <account-name> :  패스워드 변경
$> cat /etc/shadow : 전체 user 정보
$> deluser <account-name> : 유저 삭제
cf. chage -d 0 <acount-name> : 유저 상세 정보
 
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# linux 검색
grep <찾을단어> <file-name> [-io] : 파일 찾기 
echo "I love $ hh" | grep \$ :  파일 찾기 
cf. egrep <찾을단어> *.gz : 압축파일에서 파일 찾기 

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# Shell Script => vi .vimrc 설정하기
set tabstop=4 
set shiftwidth=4 
set expandtab 
set smartindent 
set autoindent 
set number 
set showmatch

# 1 ~ 100 loop
for i in {1..100}; do ~ done 

# infinite loop
while true; do ~; done

# 변수 선언
echo "$0 $1 $#"  : # => 총 변수 개수
STR="abc"
echo $STR

i=100
ii=$(( $i + 100 ))
echo "i=${i}, ii=${ii}"

문자: ==    !=
숫자: -gt, eq, lt, ne, le, ge
파일: -f, -d, -r, -w, -x

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# 날짜 
DATE=`date +%Y-%m-%d`
echo $DATE
DATE=`date +%Y-%m-%d --date=yesterday`
DATE=`date +%Y-%m-%d --date='1 day ago'`
DATE=`date +%Y-%m-%d --date='2 day ago'`
DATE=`date +%Y-%m-%d --date='2 day'`
DT=`date +%Y-%m-%d --date='1 week ago'`
DT=`date +%Y-%m-%d --date='1 month ago'`
DT=`date +%Y-%m-%d --date='1 month'`

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# 배열
declare -a arr
arr=("aaa" "bbb" "ccc" 123)

echo $arr
echo ${arr[0]}
arr[4]="6666666"

echo ${arr[@]}
echo "${#arr} : ${#arr[@]}"
for i in ${arr[@]}; do ...

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# function
echo "$0 $@ $#"
say_hello() {
	echo "Hello $0 $@ by $2!! ($#)"
}
say_hello "Jade" "Jeon"

#IFS & AWK => IFS : 필드를 분리하는 값 / AWK : 몇 번째 값을 가져오는지 설정

echo "IFS=${IFS}."

PRE_IFS=$IFS
IFS="
"
for i in `ls -al`; do
    echo $i | awk '{print $5}'
done

IFS=$PRE_IFS

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

# cron
$> crontab -l
$> crontab -e
분 시 일 월 주
* * * * * /test.sh >> /temp.log 2>&1
(2: Standard Error, 1: Standard Out) 
$> ps -ef | grep cron
  
 

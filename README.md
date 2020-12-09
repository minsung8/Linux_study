
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
  
 
#root> visudo
	# %wheel  ALL=(ALL)       ALL
	%wheel  ALL=(ALL)       NOPASSWD: ALL
#root> usermod -aG wheel <user> => user의 sudo 권한 설정 및 exit 후 재접속

$user> sudo bash
$user> sudo vi /etc/hosts	=> 수정권한 생성
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
$> gzip x.log         # x.log → x.log.gz  => 압축
$> gzip x.log.gz -d   # x.log.gz → x.log => 압축해제
$> gzip x.log.gz -l   # compress status & list 

cf. xz(xz, J), bzip2(bz2, j)  

# windows 호환 zip (원본파일은 그대로 남김)
$> zip x.log.zip x.log      <->   unzip x.log.zip
$> zip -P "암호" x.zip x/*

$> tar cvfz xxx.tar.gz *.log	=> 압축
$> tar xvfz xxx.tar.gz		=> 압축해제
cf. tar [cvfJ, cvfj] / tar [xvfJ, xvfj]
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
ftp:   21 port
sftp:  22 port (ssh)
samba: windows remote directory
ownCloud: 클라우드 파일 서버(mariadb, httpd, php, etc)

# sftp settings (ftp server)
$> useradd -s /bin/false ftpuser	=> user 만들기
$> vi /etc/ssh/sshd_config		=> ssh 환경설정
	#Subsystem sftp /usr/libexec/openssh/sftp-server
	Subsystem sftp internal-sftp
	Match Group sftp
	    ChrootDirectory /sftp_home/%u
        ForceCommand internal-sftp

$> systemctl restart sshd       => restart ssh daemon
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
# sftp 명령어
$> sftp -P 50000 ftpuser@106.10.46.114
sftp> help	=> 명령어 정리 
sftp> get <file>	=> 파일 가져오기 명령
sftp> get -r <directory>	=> 디렉토리 가져오기
sftp> put <file>           cf. put -r <directory> => 파일 업로드
# for local
sftp> lls		=> 로컬의 ls
sftp> lpwd	=> 로컬의 pwd
sftp> lcd
sftp> bye		=> 종료
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
# 지난 log 파일 정리
$> find . -name "*.gz"
$> find . -name \*.gz | sort
$> find . -name \*.gz -mtime +30	
$> find . -name \*.gz -mtime +30 -delete 	=> 30일 지난 해당파일 삭제

# sort, uniq 
$> cd /var/log/nginx
$> cat access.log | awk '{print $1}' | sort | uniq	=> 각 1번째 행을 unique, sort 적용하여 보여준다
$> cat access.log | awk '{print $1}' | sort | uniq -c
cf. cat access.log | awk '{print $1}' | uniq -c
cf. at -f /root/bin/rmoldlogs.sh 19:27
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
$> cat /etc/resolv.conf	=> 서버 정보 NCP
                                               기본 DNS 서버 : 10.250.255.11
                                               보조 DNS 서버 : 10.250.255.12

$> nslookup <domain>	=> 해당 도메인의 정보
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
	# vmstat : 모니터링 
$> vmstat
$> vmstat 1
$> vmstat 1 3
$> vmstat -a
$> vmstat -d
$> vmstat -s

* procs 프로세스(CPU)
r : runnable(실행 대기) queue에 쌓인 process 수
b : blocked(인터럽트할 수 없는 sleep된) process 수

--memory--  메모리 사용
swpd : swapped memory size
free : free(미사용) memory size
buff : buffered(사용중인 버퍼) size
cache : cached memory size

---swap--  메모리 swapping 상태
si :swapped in - 1초간 load된 size
so :swapped out -1초간 write된 size
---io---  Block I/O 
bi : block in - 1초간 디바이스로부터 read된 size 
bo : block out - 1초간 디바이스로 write된 size 

--system--  interrupt나 context switch
in : interrupt - 1초간 interrupted 횟수 
cs : context switch - 1초당 context switch 횟수

----cpu----  cpu가동 상황
us : User application 실행 비율
sy : System Kernel 실행 비율
id : CPU idle time
wa : I/O waiting time
st : stolen - 가상 머신 실행 비율

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

#sar (System Activity Reporter)
# CPU average
$> sar
$> sar -f /var/log/sa/sa20
# memory average
$> sar -r
$> sar -f /var/log/sa/sa20 -r
# load average
$> sar -q

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

#netstat (NETwork STATistics)  &  ss 
# install in docker
$> yum install net-tools -y
# netstat
$> netstat
$> netstat -an
$> netstat -anl
$> netstat -an | grep 3306
# cf. ss (more fast)
$> ss -an | grep 3306

cf. nstat

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
#NFS (Network File System) 구성하기
# install both (nfs server & client)
$> yum install net-tools -y

# server (nfs server)
$> yum install nfs-utils rpc-bind -y
$> mkdir /upload && chmod 757 /upload
$> vi /etc/exports
	/upload      <client-ip>(rw,sync)	=> ip, read, write 권한 + sync 환경설정
$> systemctl start nfs-server    # or systemctl restart nfs
$> systemctl enable nfs-server
$> exportfs -v             # 방화벽(ACG): TCP/UDP(111, 2049) 

# client (nfs client: other server)
$> mount -t nfs <server-ip>:<server-mount-path> <client-mount-path>
$> df -h              # umount <client-mount-path>


> SMTP(Simple Mail Transfer Protocol)는 e-mail을 컴퓨터에서 다른 컴퓨터로 전송할 때 사용하는 메일 서버의 기본 프로토콜이다.

이메일에 첨부파일을 넣어 전송하는 예제이다.

```
Ex)
from email.mime.text import MIMEText
from email.mime.multipart import MIMEMultipart
import smtplib
import re

SMTP_SERVER = 'smtp.gmail.com' #gmail 서버
SMTP_PORT = 465 #gmail 포트
SMTP_USER = 'kimkh940930@gmail.com'
SMTP_PASSWORD = '비밀번호'

def send_mail(name, addr, subject, contents, attachment=None): #attachment는 첨부파일을 의미 =None은 없을 수도 있음을 의미(기본값 지정)
    #이메일 유효성 검사 코드
    if not re.match('(^[a-zA-Z0-9_.-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$)',addr): #^는 문자열의 시작을 의미 모든 알파벳과 숫자와 _.- 중의 하나로 시작하는 문자열임을 의미 +는 그 이후 하나 이상 나온다는 의미 $는 문자열의 끝을 의미
        print('Wrong email')
        return
    msg = MIMEMultipart('alternative') #텍스트를 포함하겠다는 의미

    if attachment:
        msg = MIMEMultipart('mixed') #텍스트 뿐 아니라 파일도 포함하겠다는 의미

    msg['From'] = SMTP_USER
    msg['To'] = addr
    msg['Subject'] = name + '님, ' + subject
    
    text = MIMEText(contents, _charset='utf-8')
    msg.attach(text) #내용을 붙여나가는 함수

    if attachment:
        from email.mime.base import MIMEBase #파일전송에 필요한 클래스
        from email import encoders #파일을 형식에 맞춰 인코딩하는 클래스

        file_data = MIMEBase('application', 'octect-stream') #일반적인 파일을 의미
        file_data.set_payload(open(attachment, 'rb').read()) #rb의 b는 binary로 컴퓨터가 인식하는 형태로 열겠다는 의미
        encoders.encode_base64(file_data)
        
        import os
        filename = os.path.basename(attachment) #파일경로를 찾는 기능을 제공
        file_data.add_header('Content-Disposition', 'attachment; filename="'+filename+'"' ) #헤더정보를 추가
        msg.attach(file_data)

    smtp = smtplib.SMTP_SSL(SMTP_SERVER, SMTP_PORT) #서버정보를 가진 클래스
    smtp.login(SMTP_USER, SMTP_PASSWORD)
    smtp.sendmail(SMTP_USER, addr, msg.as_string()) #as_string함수로 정해진 메일 형식으로 변환
    smtp.close()

contents = '''

자동으로 보내지는 메일 '''

send_mail('김경환','kimkh940930@gmail.com','자동화 메일',contents,'test.txt')


```

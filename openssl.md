# RSA Private/Public key
```sh
$>openssl genrsa -out private.key 2048       
Generating RSA private key, 2048 bit long modulus
.......................................................................................................+++++
......+++++
e is 65537 (0x10001)
$>openssl rsa -in private.key -pubout -out public.key
writing RSA key
```

# Self signed certificate
## db.cfg
```
[ req ]
default_bits = 4096
default_keyfile = db.key
distinguished_name = req_distinguished_name
req_extensions = v3_req
prompt = no
[ req_distinguished_name ]
C = SE
ST = Stockholm
L = Stockholm
O = foo.bar
OU = foo.bar
CN= db.foo.bar
emailAddress = postmaster@foo.bar
[v3_ca]
subjectKeyIdentifier=hash
authorityKeyIdentifier=keyid:always,issuer:always
basicConstraints = CA:true
[v3_req]
# Extensions to add to a certificate request
basicConstraints = CA:FALSE
keyUsage = nonRepudiation, digitalSignature, keyEncipherment
```

Then, begin by generating a self-signing certificate authority key:
```sh
openssl genrsa -out cadb.key 4096
```

And using this, a certificate signing authority:

```sh
openssl req -x509 -new -nodes -key cadb.key -days 3650 -config db.cfg -out cadb.pem
```

Now, generate a private key for our certificate:

```sh
openssl genrsa -out db.key 4096
```

And from this, a signing request:

```sh
openssl req -new -key db.key -out db.csr -config db.cfg
```

Then we can finally create and sign our certificate:

```sh
openssl x509 -req -in db.csr -CA cadb.pem -CAkey cadb.key -CAcreateserial  -out db.crt -days 365 -sha256
```

# .pfx
A .pfx file (Personal Information Exchange) is a binary format for storing a server certificate, intermediate certificates, and private key into a single encryptable file. This format is commonly used to export and import certificates and private keys on Windows systems.

The .pfx file format is also known as PKCS #12 (Public Key Cryptography Standards #12) and is typically used to bundle all the necessary cryptographic information for SSL/TLS configurations.

PKCS#12 바이너리 포맷의 인증서 스토어 이며, Personal Information Exchange Format 를 의미한다. 주로 Windows IIS 기반에서  인증서 적용/이동시 활용된다. 주요 장점으로는 개인키,서버인증서,루트인증서,체인인증서를 모두 담을수 있어서 SSL 인증서 적용이나 또는 이전시 상당히 유용하고 편리하다. Tomcat 등 요즘에는 pfx 설정을 지원하는 서버가 많아지고 있다. (예, sslcert.co.kr_xxx.pfx) (바이너리 이진 파일) (pfx/p12 등은 인증서라기 보다는 인증서를 모아 놓은 저장소,스토어,바구니 용도 파일)

# .pem  

PEM (Privacy Enhanced Mail)은 Base64 인코딩된 ASCII 텍스트 이다. 파일 구분 확장자로 .pem 을 주로 사용한다.  노트패드에서 열기/수정도 가능하다. 개인키, 서버인증서, 루트인증서, 체인인증서 및 CSR 등 SSL 관련 모든 과정에서 사용되는 기본 포맷이며, Base64 포맷은 가장 광범위하고 거의 99% 시스템에 호환되는 산업 표준 포맷이다. (대부분 Base64 Text 파일) (예, sslcert.co.kr_xxx.crt.pem)


# .crt 
인증서 파일이다 라는 의미로 붙이며, 거의 대부분 Base64 PEM 포맷이며, 주로 유닉스/리눅스 기반 시스템에서 통용되는 확장자 이다. cer 확장자를 붙이기도 한다. 파일을 노트패드 등으로 열어 보면 PEM 포맷인지 바이너리 포맷인지 알수 있지만, 99% 는 Base64 PEM 포맷이라고 봐도 무방하다. (.crt 확장자 보다는 파일 포맷이 명확하도록 .pem 또는 .der 붙이는걸 권장) (예, sslcert.co.kr_xxx.crt.pem)


# .cer

대부분 Base64 PEM 포맷이며, 종종 바이너리 포맷일때도 있다. 주로 Windows 기반에서 인증서 파일임을 구분하기 위해서 사용되는 확장자 이다. crt 확장자와 거의 동일한 의미이며, cer 이나 crt 확장자 모두 윈도우에서는 기본 인식되는 확장자이다. 저장할때 어떤 포맷으로 했는지에 따라 다르며, 파일 생성을 했던 사람이 자기 마음대로 붙이기 나름이다. 


# .csr

Certificate Signing Request 의 약자이며 거의 대부분 Base64 PEM 포맷이다. SSL 발급 신청을 위해서 본 파일 내용을 인증기관 CA 에 제출하는 요청서 파일임을 구분하기 위해서 붙이는 확장자 이다. (Base64 Text 파일)


# .der

Distinguished Encoding Representation (DER) 의 약자이며, 바이너리 포맷이다. 노트패드등으로 열어 봐서는 알아 볼수 없다.  바이너리 인코딩 포맷을 읽을수 있는 인증서 라이브러리를 통해서만 내용 확인이 가능하다.  사설 또는 금융등 특수 분야 및 아주 오래된 구형 시스템을 제외하고는, 최근 웹서버 SSL 작동 시스템 에서는 흔히 사용되는 포맷은 아니다. (바이너리 이진 파일)


# .p7b

PKCS#7 포맷이며, '서버인증서+루트인증서+체인인증서' 를 모두 담을수 있어서 SSL 인증서 적용이나 또는 이전시 상당히 유용하고 편리하다. Windows 에서는 자동으로 인식하며, 일부 서버에서는 p7b 포맷으로만 인증서 설정이 되는 경우가 있다.  (Base64 Text 파일) (pfx 와 달리 p7b 는 개인키가 포함되지 않음) (일부에서는 .p7c 라는 확장자를 붙이기도 함) (예, sslcert.co.kr_xxx.p7b) (p7b 등은 인증서라기 보다는 인증서를 모아 놓은 저장소,스토어,바구니 용도 파일)


# .key

주로 openssl 및 java 에서 개인키 파일임을 구분하기 위해서 사용되는 확장자이다. Base64 PEM 포맷일수도 있고 DER 바이너리 포맷일수도 있으며, 노트패드 같은 텍스트 편집기로 파일을 열어봐야 어떤 포맷인지 알수가 있다. 저장할때 어떤 포맷으로 했는지에 따라 다르며, 확장자는 이름 붙이기 나름이다. (예, sslcert.co.kr_xxx.key.pem) 


# .jks

Java Key Store 의 약자이며, Java 기반의 독자 인증서 스토어 포맷이다. pfx 와 마찮가지로 개인키+서버인증서+루트인증서+체인인증서를 모두 담을수 있어서 SSL 인증서 파일 관리시 유용하다. Java 기반의 Tomcat 서버에서 SSL 적용시 가장 많이 사용되는 포맷이다.  (예, sslcert.co.kr_xxx.jks) (바이너리 이진 파일) (jks 등은 인증서라기 보다는 인증서를 모아 놓은 저장소,스토어,바구니 용도 파일)

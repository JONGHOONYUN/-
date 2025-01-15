우분투 24.04 LTS  
php 8.1.29 (apache2handler)  
**wiki 1.39.8.**

**해볼만한거**  
**1\. (기존버전유지한채) wiki 세팅할 때. 필수 플러그인만(Abuse Filter 확인해보기)**

**2\. mediawiki 1.35= PHP 7.3.19 or later(7.4) \=SMW 4.0.x**  
[**https://www.php.net/supported-versions.php**](https://www.php.net/supported-versions.php)

[**https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/tests/README.md**](https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/tests/README.md)

**Package phpunit/php-token-stream is abandoned, you should avoid using it. No replacement was suggested.**

[**https://zetawiki.com/wiki/%EB%AF%B8%EB%94%94%EC%96%B4%EC%9C%84%ED%82%A4\_%EC%98%A4%EB%A5%98\_%EB%A9%94%EC%8B%9C%EC%A7%80\_%ED%91%9C%EC%8B%9C**](https://zetawiki.com/wiki/%EB%AF%B8%EB%94%94%EC%96%B4%EC%9C%84%ED%82%A4_%EC%98%A4%EB%A5%98_%EB%A9%94%EC%8B%9C%EC%A7%80_%ED%91%9C%EC%8B%9C)

**$wgShowExceptionDetails \= true;**  
**error\_reporting( \-1 );**  
**ini\_set( 'display\_errors', 1 );**

**Error: Class "Wikimedia\\Equivset\\Equivset" not found**

# 0.기본 환경

미디어위키 세팅에서 기본적으로 LTS 선택  
[https://www.mediawiki.org/wiki/Download/ko](https://www.mediawiki.org/wiki/Download/ko)  
MediaWiki 1.39.8 (.zip 다운로드, .tar.gz 다운로드) \- 장기 지원 (LTS)

Semantic MediaWiki 4.1.3 / 2024.07.18. 기준 최신 버전  
[https://www.semantic-mediawiki.org/wiki/Semantic\_MediaWiki\_4.1.3](https://www.semantic-mediawiki.org/wiki/Semantic_MediaWiki_4.1.3)  
최적화 지원 \= MediaWiki 1.39 and PHP 8.1

[https://www.semantic-mediawiki.org/wiki/Help:Compatibility](https://www.semantic-mediawiki.org/wiki/Help:Compatibility)  
[https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/COMPATIBILITY.md](https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/COMPATIBILITY.md)

[https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/INSTALL.md](https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/INSTALL.md)

## 참조: 린지 세팅

[http://ekch.org/wiki/index.php?title=Special:Version](http://ekch.org/wiki/index.php?title=Special:Version)

**MediaWiki	1.35.0**  
PHP	7.3.23 (fpm-fcgi)  
MariaDB	5.5.68-MariaDB

**Semantic MediaWiki	3.2.1**  
Semantic Compound Queries	2.1.0 (75e8b38) 16:34, 18 August 2019  
Semantic Drilldown	2.1 (9ef81a4) 10:37, 4 November 2020  
Semantic Result Formats	3.2.0 (ecbf369) 17:44, 27 August 2020  
Semantic Scribunto	2.1.0 (2d31857) 16:48, 18 August 2019

AWS 최대 강점은 시간당으로 비용 계산이 되고, 테스트 단계에서 무한 리셋 가능

# 1\. 서버 삭제 

# 2\. 서버 재생성

# 3\. MediaWiki 1.39.8 설치

3.1. 대응 환경 구축: [https://wikidocs.net/179453](https://wikidocs.net/179453)

3.2. 미디어위키 설치

sudo chmod 777 /var/www/html/swiki/images

sudo mv /var/www/html/swiki/images/.htaccess /var/www/html/swiki/images/.htaccess\_disabled

3.3. 미디어위키 기본 테스트

# 

# 4\. SMW 4.1.3 설치: 

[https://www.semantic-mediawiki.org/wiki/Semantic\_MediaWiki\_4.1.3](https://www.semantic-mediawiki.org/wiki/Semantic_MediaWiki_4.1.3)

4.1. 컴포저 설치  
vim composer.local.json

composer update \--no-dev \--optimize-autoloader

sudo systemctl restart apache2

4.2. 미디어위키 로컬세팅 변경 및 업데이트

로컬세팅.php  
wfLoadExtension( 'SemanticMediaWiki' );  
enableSemantics( 'dhkorea.org' );

**sudo php maintenance/update.php**

4.3. 테스트  
[https://www.semantic-mediawiki.org/wiki/Help:Verify\_the\_installation](https://www.semantic-mediawiki.org/wiki/Help:Verify_the_installation)

[**https://www.semantic-mediawiki.org/wiki/Help:Verify\_the\_installation**](https://www.semantic-mediawiki.org/wiki/Help:Verify_the_installation)

**Property test: \[\[Property name::Property value\]\]**

[**https://www.semantic-mediawiki.org/wiki/Help:Semantic\_search**](https://www.semantic-mediawiki.org/wiki/Help:Semantic_search)

[**https://www.semantic-mediawiki.org/wiki/Help:Inline\_queries\#Parser\_function\_.23ask**](https://www.semantic-mediawiki.org/wiki/Help:Inline_queries#Parser_function_.23ask)

**\[\[like::ruru\]\]**  
**\[\[like::마루\]\]**

**{{\#ask: \[\[김바로\]\] |?like}}**

**{{\#ask: \[\[김바로\]\]**   
**\[\[like::+\]\]**  
**|?like**  
**}}**

[cafe24\_semantic wiki](https://drive.google.com/drive/u/0/folders/19AbnZ-EXUz9pgoiQbAPa3bNFpssgzEFU) —\> LocalSettings.php

**ssl 접속(putty)**  
175.125.21.135 22  
cafe24\_dhkorea

**root / 암호**

[**https://www.semantic-mediawiki.org/wiki/Sites\_using\_Semantic\_MediaWiki**](https://www.semantic-mediawiki.org/wiki/Sites_using_Semantic_MediaWiki)

[**https://bookowners.online/index.php?title=Thomas\_Sheppard\_d.1763\&action=edit**](https://bookowners.online/index.php?title=Thomas_Sheppard_d.1763&action=edit)

[**https://bookowners.online/Special:Browse/Thomas\_Sheppard\_d.1763**](https://bookowners.online/Special:Browse/Thomas_Sheppard_d.1763)

[**https://bookowners.online/index.php?title=Special:ExportRDF/Thomas\_Sheppard\_d.1763\&syntax=rdf**](https://bookowners.online/index.php?title=Special:ExportRDF/Thomas_Sheppard_d.1763&syntax=rdf)

# 

# 

# 백업 세팅

**mv swiki/ swiki\_backup01/**

**mysql \-u root \-p**

**show databases;**

**drop database swiki;**

**exit**

# 미디어 위키 설치

cd /var/www/html

wget [https://releases.wikimedia.org/mediawiki/1.39/mediawiki-1.39.5.zip](https://releases.wikimedia.org/mediawiki/1.39/mediawiki-1.39.5.zip)

unzip [mediawiki-1.39.5.zip](https://releases.wikimedia.org/mediawiki/1.39/mediawiki-1.39.5.zip) 

mv [mediawiki-1.39.5](https://releases.wikimedia.org/mediawiki/1.39/mediawiki-1.39.5.zip) swiki

**sudo systemctl restart apache2**

**cd /var/www/html/**

**vim .htaccess**

**\<IfModule mod\_rewrite.c\>**  
**RewriteEngine On**  
**RewriteBase /**  
**RewriteRule ^(swiki)($|/) \- \[L\]**  
**RewriteRule ^index\\.php$ \- \[L\]**  
**RewriteCond %{REQUEST\_FILENAME} \!-f**  
**RewriteCond %{REQUEST\_FILENAME} \!-d**  
**RewriteRule . /index.php \[L\]**  
**\</IfModule\>**

**![][image1]**

**service apache2 restart**  
service apache2 status

[https://dhkorea.org/swiki/](https://dhkorea.org/swiki/)

mysql \-u root \-p  
CREATE DATABASE swiki;   
CREATE USER 'swikiadmin'@'localhost' IDENTIFIED by 'rurudao01\!';  
GRANT ALL PRIVILEGES ON swiki .\* TO 'swikiadmin'@'localhost';   
FLUSH PRIVILEGES;  
exit

swiki  
swikiadmin  
암호

cd swiki

wget \--load-cookies \~/cookies.txt "https://docs.google.com/uc?export=download\&confirm=$(wget \--quiet \--save-cookies \~/cookies.txt \--keep-session-cookies \--no-check-certificate 'https://docs.google.com/uc?export=download\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej' \-O- | sed \-rn 's/.\*confirm=(\[0-9A-Za-z\_\]+).\*/\\1\\n/p')\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej" \-O LocalSettings.php && rm \-rf \~/cookies.txt

sudo chmod 777 /var/www/html/swiki/images

sudo mv /var/www/html/swiki/images/.htaccess /var/www/html/swiki/images/.htaccess\_disabled

**\#wfLoadExtension( 'AbuseFilter' );**

[**https://dhkorea.org/swiki/**](https://dhkorea.org/swiki/)

# 시맨틱위키설치 update composer 

[**https://medium.com/techvblogs/update-composer-in-ubuntu-4138e36205eb**](https://medium.com/techvblogs/update-composer-in-ubuntu-4138e36205eb)

**sudo apt-get update**  
**sudo apt install php-xml**  
**sudo apt-get install php-mbstring**  
**sudo apt-get install php-intl**  
**sudo apt-get install php-mysql**  
**sudo apt-get install php-curl**

**sudo apt-get install** php-common php-mysql php-xml php-xmlrpc php-curl php-gd php-imagick php-cli php-dev php-imap php-mbstring php-bcmath  php-soap php-zip php-redis php-intl

**cd /var/www/html/swiki**

**COMPOSER=composer.local.json php composer.phar require \--no-update mediawiki/semantic-media-wiki**

**vim composer.local.json**

**![][image2]**

**![][image3]**

[**https://github.com/onoi/http-request**](https://github.com/onoi/http-request)

**sudo systemctl restart apache2**

**composer update \--no-dev**

**sudo systemctl restart apache2**

composer update \--prefer-source

php composer.phar update \--no-dev

php composer.phar update \--prefer-source

**wfLoadExtension( 'SemanticMediaWiki' );**  
**enableSemantics( 'dhkorea.org' );**

**cd /var/www/html/swiki**

**wget \--load-cookies \~/cookies.txt "https://docs.google.com/uc?export=download\&confirm=$(wget \--quiet \--save-cookies \~/cookies.txt \--keep-session-cookies \--no-check-certificate 'https://docs.google.com/uc?export=download\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej' \-O- | sed \-rn 's/.\*confirm=(\[0-9A-Za-z\_\]+).\*/\\1\\n/p')\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej" \-O LocalSettings.php && rm \-rf \~/cookies.txt**

**php maintenance/update.php**

php maintenance/update.php \--skip-external-dependencies

+ # 데이터 업데이트

[**https://github.com/WikiValley/RDFIO**](https://github.com/WikiValley/RDFIO)  
[**https://packagist.org/packages/rdfio/rdfio**](https://packagist.org/packages/rdfio/rdfio)

**cd /var/www/html/swiki**

**vim composer.local.json**

vim composer.lock

vim composer.json

composer require rdfio/rdfio \--update-no-dev

**sudo systemctl restart apache2**

**composer update \--no-dev**

**sudo systemctl restart apache2**

**cd /var/www/html/swiki**

**php maintenance/update.php**

[https://dhkorea.org/swiki/Special:RDFIOAdmin](https://dhkorea.org/swiki/Special:RDFIOAdmin)

**https://dhkorea.org/swiki/index.php?title=%ED%8A%B9%EC%88%98:%EB%A1%9C%EA%B7%B8%EC%9D%B8**  
[**https://github.com/rdfio/rdf2smw**](https://github.com/rdfio/rdf2smw)

**wget [https://github.com/rdfio/rdf2smw/releases/download/v0.6/rdf2smw\_v0.6\_linux64.gz](https://github.com/rdfio/rdf2smw/releases/download/v0.6/rdf2smw_v0.6_linux64.gz)**

**gzip \-d rdf…..**

**wget \--load-cookies \~/cookies.txt "https://docs.google.com/uc?export=download\&confirm=$(wget \--quiet \--save-cookies \~/cookies.txt \--keep-session-cookies \--no-check-certificate 'https://docs.google.com/uc?export=download\&id=109I7RA3SS\_ttqnFDRV9Ks4IwbwAjeRYH' \-O- | sed \-rn 's/.\*confirm=(\[0-9A-Za-z\_\]+).\*/\\1\\n/p')\&id=109I7RA3SS\_ttqnFDRV9Ks4IwbwAjeRYH" \-O test.nt && rm \-rf \~/cookies.txt**

[**https://drive.google.com/file/d/109I7RA3SS\_ttqnFDRV9Ks4IwbwAjeRYH/view?usp=sharing**](https://drive.google.com/file/d/109I7RA3SS_ttqnFDRV9Ks4IwbwAjeRYH/view?usp=sharing)

**./**

**go run rdf2smw \--in test.nt \--out smw.xml**

+ # 기본 동작 테스트

[**https://www.semantic-mediawiki.org/wiki/Help:Verify\_the\_installation**](https://www.semantic-mediawiki.org/wiki/Help:Verify_the_installation)

**Property test: \[\[Property name::Property value\]\]**

[**https://www.semantic-mediawiki.org/wiki/Help:Semantic\_search**](https://www.semantic-mediawiki.org/wiki/Help:Semantic_search)

[**https://www.semantic-mediawiki.org/wiki/Help:Inline\_queries\#Parser\_function\_.23ask**](https://www.semantic-mediawiki.org/wiki/Help:Inline_queries#Parser_function_.23ask)

**\[\[like::ruru\]\]**  
**\[\[like::마루\]\]**

**{{\#ask: \[\[김바로\]\] |?like}}**

**{{\#ask: \[\[김바로\]\]**   
**\[\[like::+\]\]**  
**|?like**  
**}}**

+ # sparql 세팅

**// 들어오는 링크 표시 안함**  
$smwgBrowseShowAll \= false;

[**https://www.semantic-mediawiki.org/wiki/Help:Using\_SPARQL\_and\_RDF\_stores\#Configuring\_SMW**](https://www.semantic-mediawiki.org/wiki/Help:Using_SPARQL_and_RDF_stores#Configuring_SMW)

**Compatibility**  
[**https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/COMPATIBILITY.md**](https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/COMPATIBILITY.md)

**cd /var/www/html/swiki**

**wget \--load-cookies \~/cookies.txt "https://docs.google.com/uc?export=download\&confirm=$(wget \--quiet \--save-cookies \~/cookies.txt \--keep-session-cookies \--no-check-certificate 'https://docs.google.com/uc?export=download\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej' \-O- | sed \-rn 's/.\*confirm=(\[0-9A-Za-z\_\]+).\*/\\1\\n/p')\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej" \-O LocalSettings.php && rm \-rf \~/cookies.txt**

**php maintenance/update.php**

[**https://dhkorea.org/swiki/**](https://dhkorea.org/swiki/)

[**http://dhkorea.org:3030**](http://dhkorea.org:3030)

[**https://github.com/gbv/fuseki.deb\#fuseki-debian-package**](https://github.com/gbv/fuseki.deb#fuseki-debian-package)

**wget https://github.com/gbv/fuseki.deb/releases/download/v4.9.0-1/fuseki\_4.9.0-1\_all.deb**

**sudo dpkg \--install ./[fuseki\_4.9.0-1\_all.deb](https://github.com/gbv/fuseki.deb/releases/download/v4.9.0-1/fuseki_4.9.0-1_all.deb) && sudo apt install \-f**

**sudo systemctl enable fuseki**

**sudo systemctl restart fuseki**

**vim /etc/systemd/system/fuseki.service**

**sudo systemctl restart apache2**

**vim  /etc/fuseki/fuseki.service**

**vim  /etc/fuseki/shiro.ini**  
**![][image4]**

[**http://dhkorea.org:3030**](http://dhkorea.org:3030)

**cd /opt/fuseki/**  
**cd /etc/fuseki/**

+ # 데이터 리셋 정제

**sudo systemctl restart apache2**

**cd /var/www/html/swiki**

**wget \--load-cookies \~/cookies.txt "https://docs.google.com/uc?export=download\&confirm=$(wget \--quiet \--save-cookies \~/cookies.txt \--keep-session-cookies \--no-check-certificate 'https://docs.google.com/uc?export=download\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej' \-O- | sed \-rn 's/.\*confirm=(\[0-9A-Za-z\_\]+).\*/\\1\\n/p')\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej" \-O LocalSettings.php && rm \-rf \~/cookies.txt**

**cd /var/www/html/swiki**

**php maintenance/update.php**

**cd /var/www/html/swiki**

**php /var/www/html/swiki/maintenance/runJobs.php \--maxjobs 1000**

**cd /var/www/html/swiki**  
**touch LocalSettings.php**

**cd /var/www/html/swiki/extensions/SemanticMediaWiki/maintenance/**

**php rebuildData.php \-v \-d 50**

**cd /var/www/html/swiki**  
**touch LocalSettings.php**

**cd /var/www/html/swiki**

**php /var/www/html/swiki/maintenance/runJobs.php \--maxjobs 1000**

**sudo systemctl restart apache2**

- # 완전 리셋

- 

**sudo systemctl restart apache2**

**cd /var/www/html/swiki**

**wget \--load-cookies \~/cookies.txt "https://docs.google.com/uc?export=download\&confirm=$(wget \--quiet \--save-cookies \~/cookies.txt \--keep-session-cookies \--no-check-certificate 'https://docs.google.com/uc?export=download\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej' \-O- | sed \-rn 's/.\*confirm=(\[0-9A-Za-z\_\]+).\*/\\1\\n/p')\&id=1978lnO--iNcAUosgUjSAGT0JldFgF3Ej" \-O LocalSettings.php && rm \-rf \~/cookies.txt**

**cd /var/www/html/swiki**

**php maintenance/update.php**

**cd /var/www/html/swiki**

**php /var/www/html/swiki/maintenance/runJobs.php \--maxjobs 1000**

**cd /var/www/html/swiki**  
**touch LocalSettings.php**

**cd /var/www/html/swiki/extensions/SemanticMediaWiki/maintenance/**

**php rebuildData.php \-fpv**  
**php rebuildData.php \-v**

**cd /var/www/html/swiki**  
**touch LocalSettings.php**

**cd /var/www/html/swiki**

**php /var/www/html/swiki/maintenance/runJobs.php \--maxjobs 1000**

**sudo systemctl restart apache2**

# sparql 테스트

**PREFIX xsd: \<http://www.w3.org/2001/XMLSchema\#\>**  
**PREFIX owl: \<http://www.w3.org/2002/07/owl\#\>**  
**PREFIX rdfs: \<http://www.w3.org/2000/01/rdf-schema\#\>**  
**PREFIX rdf: \<http://www.w3.org/1999/02/22-rdf-syntax-ns\#\>**

**SELECT ?subject ?predicate ?object**  
**WHERE {**  
  **?subject rdfs:label '정록1 0093'.**  
  **?subject ?predicate ?object.**  
**}**

**PREFIX xsd: \<http://www.w3.org/2001/XMLSchema\#\>**  
**PREFIX owl: \<http://www.w3.org/2002/07/owl\#\>**  
**PREFIX rdfs: \<http://www.w3.org/2000/01/rdf-schema\#\>**  
**PREFIX rdf: \<http://www.w3.org/1999/02/22-rdf-syntax-ns\#\>**

**SELECT ?subject ?predicate ?object ?target ?all ?allv**  
**WHERE {**  
  **?subject rdfs:label '정록1 0093'.**  
  **?subject \<http://dhkorea.org/swiki/Special:URIResolver/Property-3A정록-3AAKSPersonID\> ?object.**  
  **?target ?predicat ?object.**  
  **?target ?all ?allv**  
**}**

**PREFIX xsd: \<http://www.w3.org/2001/XMLSchema\#\>**  
**PREFIX owl: \<http://www.w3.org/2002/07/owl\#\>**  
**PREFIX rdfs: \<http://www.w3.org/2000/01/rdf-schema\#\>**  
**PREFIX rdf: \<http://www.w3.org/1999/02/22-rdf-syntax-ns\#\>**

**SELECT ?subject ?predicate ?object**  
**WHERE {**  
  **?subject rdfs:label '조선왕조실록관력'.**  
  **?subject ?predicate ?object.**  
**}**

# 윤종훈 기술(시맨틱미디어위키)

호환성  
https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/COMPATIBILITY.md

우분투 24.04 LTS  
php 8.1.29 (apache2handler)  
**wiki 1.39.8.**

**해볼만한거**  
**1\. (기존버전유지한채) wiki 세팅할 때. 필수 플러그인만(Abuse Filter 확인해보기)**

**2\. mediawiki 1.35= PHP 7.3.19 or later(7.4) \=SMW 4.0.x**  
[**https://www.php.net/supported-versions.php**](https://www.php.net/supported-versions.php)

## 0.기본 환경

미디어위키 세팅에서 기본적으로 LTS 선택  
[https://www.mediawiki.org/wiki/Download/ko](https://www.mediawiki.org/wiki/Download/ko)  
MediaWiki 1.39.8 (.zip 다운로드, .tar.gz 다운로드) \- 장기 지원 (LTS)

Semantic MediaWiki 4.1.3 / 2024.07.18. 기준 최신 버전  
[https://www.semantic-mediawiki.org/wiki/Semantic\_MediaWiki\_4.1.3](https://www.semantic-mediawiki.org/wiki/Semantic_MediaWiki_4.1.3)  
최적화 지원 \= MediaWiki 1.39 and PHP 8.1

[https://www.semantic-mediawiki.org/wiki/Help:Compatibility](https://www.semantic-mediawiki.org/wiki/Help:Compatibility)  
[https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/COMPATIBILITY.md](https://github.com/SemanticMediaWiki/SemanticMediaWiki/blob/master/docs/COMPATIBILITY.md)

## 

## 

## 1\. 기본세팅(아파치2/특정버젼 php / mysql) 설치

sudo apt-**get** **update**

sudo apt-**get** upgrade

*\#시스템 업데이트 실행*  
sudo apt update && apt upgrade \-y

*\# php8.1 레파지토리 추가*  
sudo apt install software-properties-common  
sudo add-apt-repository ppa:ondrej/php

*\# php8.1 레파지토리 업데이트*  
sudo apt update

*\#php8.1 설치*   
sudo apt-**get** install apache2 mysql-server php8.1 php8.1-mysql libapache2-mod-php8.1 php8.1-xml php8.1-mbstring

*\#버전확인*  
php \-v

\#아파치 재시작  
sudo service apache2 **start**

sudo systemctl status apache2

## 2.미디어위키 파일 다운로드/설치/압축해제

cd ../../var/www/html

sudo wget https://releases.wikimedia.org/mediawiki/1.39/mediawiki-1.39.8.tar.gz

sudo tar \-xvzf mediawiki-1.39.8.tar.gz

sudo mv mediawiki-1.39.8 wiki

sudo apt-get install php8.1-intl

sudo service apache2 restart

## 3.mysql 데이터베이스 생성

sudo mysql \-u root

CREATE DATABASE wikidb;

SHOW DATABASES;

CREATE USER wiki@localhost IDENTIFIED BY 'ehowl0821';

GRANT ALL PRIVILEGES ON wikidb.\* TO wiki@localhost WITH GRANT OPTION;

quit

## 4.미디어위키 이미지 권한 부여

sudo chmod 777 /var/www/html/wiki/images

sudo mv /var/www/html/wiki/images/.htaccess /var/www/html/wiki/images/.htaccess\_disabled

## 

## 5.웹에서 미디어위키 설치/세팅

sudo chmod \-R 777 "../../var/www/html/"

sudo chmod \-R 755 "../../var/www/html/"

\#웹에서 미디어위키 설치 과정 중 확장기능 설치하는 부분에서 왠만하면 기본적인것만 체크하기. “스팸막기”확장기능 \- “Abuse Filter” 확장기능 추가시 충돌/에러-(ex.로그인/회원가입/페이지 생성 시 error 가 뜨며 불가능해지는 사태 발생)

## 

## 6.시맨틱미디어위키 4.2.0 설치

### *\#composer 설치*

COMPOSER=composer.local.json php composer.phar require \--no-update mediawiki/semantic-media-wiki

*\#위 코드 안되면,*

cd /var/www/html/wiki

sudo vim composer.local.json 

*\#위 코드로 vim 으로 들어가서 composer.local.json 내부에 아래 내용 그대로 복사 “”사이에 있는 버전 숫자 확인 필수*

{  
	**"require"**: {  
                  **"mediawiki/semantic-media-wiki"**: "\~4.2"  
        }  
}

*\#Composer 설치*  
sudo apt-get install composer

*\#Composer version 2.7.1*

### *\#composer업데이트*

sudo composer update \--no-dev

위 코드 안되면 아래 코드

sudo composer update \--no-dev \--optimize-autoloader

*\#아파치 재시작*  
sudo systemctl restart apache2

*\#에러코드*  
Package phpunit/php-token-stream is abandoned, you should avoid using it. No replacement was suggested.

### \#미디어위키 로컬세팅 변경 및 업데이트

vim LocalSettings.php 들어가서 아래 문자열 추가

wfLoadExtension( 'SemanticMediaWiki' );  
enableSemantics( '13.209.254.53/wiki' );

**sudo php maintenance/update.php**  
안될경우 아래 코드  
sudo php maintenance/update.php \--skip-external-dependencies

**php extensions/SemanticMediaWiki/maintenance/rebuildData.php \-v**

### 

### \#시맨틱위키 테스트

[https://www.semantic-mediawiki.org/wiki/Help:Verify\_the\_installation](https://www.semantic-mediawiki.org/wiki/Help:Verify_the_installation)

**Property test: \[\[Property name::Property value\]\]**

[**https://www.semantic-mediawiki.org/wiki/Help:Semantic\_search**](https://www.semantic-mediawiki.org/wiki/Help:Semantic_search)

[**https://www.semantic-mediawiki.org/wiki/Help:Inline\_queries\#Parser\_function\_.23ask**](https://www.semantic-mediawiki.org/wiki/Help:Inline_queries#Parser_function_.23ask)

**\[\[Foaf:made::MP HIPHOP 2000 초\]\]**

**\[\[Krsc:isMasteredBy::이현숙\]\] \[\[분류:Krsc:MusicTrack\]\]**

**{{\#ask: \[\[Dcterms:alternative::+\]\] \[\[마스터플랜\]\] | ?Dcterms:alternative}}**

| 조건) | 출력 선택 |
| :---- | :---- |
| **\[\[dcterms:alternative::+\]\]** | **?Dcterms:alternative ?Krsc:birthdate** |
| **\[\[Category:foaf:Person\]\]** | **?Dcterms:alternative** |
| **\[\[분류:Krsc:MusicTrack\]\] \[\[dcterms:isPartOf::MP HIPHOP 2000 초\]\]** | **?Krsc:isMasteredBy ?Krsc:MasteringStudio ?Krsc:isMixedBy ?Krsc:RecordingStudio** |
| **\[\[foaf:knows::MC 메타\]\] \[\[분류:Foaf:Agent\]\]**  | **?Dcterms:title ?Dcterms:alternative ?Foaf:knows ?Krsc:isMemberof** |
| **\[\[foaf:knows::김반장\]\]** | **?Dcterms:title ?Dcterms:alternative ?Foaf:knows**  |
| **\[\[Krsc:isMasteredBy::이현숙\]\]** | **\[\[분류:Krsc:MusicTrack\]\]** |
| **\[\[krsc:isMemberof::BLEX\]\] \[\[krsc:isMemberof::마스터플랜\]\]** | **?Dcterms:title ?Foaf:made ?Foaf:knows**  |
|  **\[\[krsc:isMemberof::마스터플랜\]\]**  |  **?foaf:made** |
| **\[\[Category:Foaf:Group\]\] \[\[krsc:organizedBy::\<q\>\[\[Category:Foaf:Agent\]\] \[\[Krsc:isMemberof::마스터플랜\]\]\</q\>\]\]** | **?Dcterms:title ?krsc:organizedBy ?Foaf:member**  |
| **\[\[Category:Foaf:Person\]\] \[\[krsc:participate::MP HIPHOP 2000 초\]\]** | **?krsc:participate** |
| **\[\[Category:Foaf:Person\]\] \[\[krsc:mastering::\<q\>\[\[Category:Krsc:MusicTrack\]\] \[\[dcterms:isPartOf::MP HIPHOP 2000 초\]\]\</q\>\]\]** | **?krsc:participate**  |

**MP HIPHOP 2000초의 믹싱작업에 참여한 인물이 참여한 다른 곡**

**A+관계어+B**

**![][image5]**

### php unit

   
PHPUnit 9.6.17

sudo apt install phpunit  


[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,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>

[image3]: <data:image/png;base64,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>

[image4]: <data:image/png;base64,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>

[image5]: <data:image/png;base64,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>
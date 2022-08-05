---
title: WIN 10 시스템 프로세스 80 포트 점유 증상

date: 2022-08-04 16:21:00 +0900

categories: [MSSQL]

tags: [MSSQL, WINDOW]

---

# WIN 10 시스템 프로세스 80 포트 점유 증상

1. WIN 10 시스템 프로세스 80 포트 점유 증상이 있다.
2. 원인
   + IIS쪽도 확인해보았지만 IIS는 설치 자체가 안되어 문제가 아니었다.
   + 추가 확인 결과 MSSQL 설치할때 report 서버가 켜져있는데 얘가 system 프로세스에 물려서 80 포트를 점유하는 증상이 있는것으로 보인다
3. 조치내용
   + SQL 서버 구성 관리자를 들어가서 SQL Server report services를 종료하니 해결되었다
4. 관련내용 링크
   + [이틀정도 검색하다 보인 글이며 참으로 고마운 외국인 아저씨들..이었다..](https://social.technet.microsoft.com/Forums/ie/en-US/bcc1f713-1fc9-42c9-8b9e-0a172d34c1c6/microsofthttpapi20-listening-on-port-80-in-new-windows-10-installation-why?forum=win10itpronetworking)

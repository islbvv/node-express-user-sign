# node-express-user-sign

Node.js + Express 기반 회원가입 백엔드 샘플 코드입니다.  
2개월 첫 단체 프로젝트에서 작성한 코드를 업로드하였으며,  
3계층 아키텍처를 기반으로 설계하였습니다.

---

## 1. 주요 기능
- 개인/기관 회원가입  
- bcrypt 비밀번호 해싱  
- 주민등록번호 AES 암호화  
- 가입 정보 검증  
- ID 중복 검사  
- 트랜잭션 기반 개인/기관 DB 저장  
- 기관 회원가입 시 가입 승인 요청 테이블 저장  

---

## 2. 아키텍처 구조
본 프로젝트는 다음 흐름으로 구성됩니다.  
Route → Service → Mapper → DB

### i. Route
- 요청/응답 처리  
- 입력 데이터 수집  
- 에러 핸들링  

### ii. Service
- 핵심 비즈니스 로직  
- 비밀번호 해싱 / 주민등록번호 암호화  
- 유효성 검증  
- 도메인 조립(createUser, makeParams)  
- 트랜잭션 처리  

### iii. Mapper
- SQL 실행  
- DB 접근  
- 실행 결과 반환  

---

## 3. 프로젝트 구조
```
backend  
↳ src  
  ↳ routes  
    ↳ signUser.js  
  ↳ services  
    ↳ signUserService.js  
  ↳ mappers  
    ↳ signUserMapper.js  
.gitignore  
README.md

※ test/ 및 utils/는 현재 샘플 포트폴리오 범위에서 제외하였습니다.
```

---

## 4. 목적
이 프로젝트는 입문 2개월차에 진행한 첫 단체 프로젝트에서 구현한 백엔드 로직을 정리한 포트폴리오입니다.  
특히 아래의 구조적인 설계, 보안, 트랜잭션, 데이터 조립 등을 신경쓰며 작업했습니다.  
  1) 유지보수성 높은 계층 구조  
  2) 개인정보 암호화 처리  
  3) 트랜잭션 기반 로직  
  4) 도메인 조립 패턴  
  5) 명확한 코드 흐름

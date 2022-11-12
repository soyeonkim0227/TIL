# Sequelize 관계성 정의 테이블 간에 관계 정의

## 시퀄라이즈에서 모델 간에 관계를 맺는 방법

- 1 : 1(일 대 일)
- 1 : M(일 대 다)
- N : M(다 대 다)

- 관계를 맺어주는 코드는 associate라는 함수 안에 정의할 수 있다.
- 그 안에 hasOne, hasMany, belongsTo, belongsToMany 속성으로 해당 관계 방식을 정의한다.

# 1 : 1 관계 방식

- 예) “유저” 모델과 “유저 정보” 모델로 매칭을 시킬 수 있다.
- 한 유저에 대한 정보가 크다면 하나에 테이블 보다는 분리를 하는 경우가 발생하는데 두 모델을 만들고 관계성을 맺어 사용한다.

```jsx
User.hasOne(models.UserInfo, {foreignKey: "user_id", sourceKey: 'id'});
// Users 안에 있는 "id" 값을 "user_id"라는 컬럼 이름으로 UserInfo 모델에 새로운 컬럼으로 추가한다.
```

```jsx
UserInfo.belongsTo(models.Users, {foreignKey: "user_id", sourceKey: "id"});
// UserInfo 모델 안에 "user_id"라는 컬럼 이름으로 Users 모델에 있는 "id" 값을 새로운 컬럼으로 추가한다.
```

- hasOne: 관계를 맺는 대상(자식)에게 자신의 외래 키를 추가한다. (Users ⇒ UserInfo) UserInfo 외래 키가 추가된다.
- belongsTo: 관계를 맺는 대상(부모)에게 외래 키를 받아 추가한다. (UserInfo ⇒ Users) UserInfo 외래 키가 추가된다.

# 1 : M 관계 방식

- 예) “회사” 모델과 “회사 소속 유저” 모델로 매칭을 시킬 수 있다.
- 유저(1)가 게시글들(M)을 보유한다.
- 한 회사에 소속된 유저는 여러 명일 수 있다.

```jsx
CompanyInformation.hasMany(models.Users, {foreignKey: "company_id", sourceKey: "id"});
// CompanyInformation 안에 있는 "id" 값을 "company_id"라는 컬럼 이름으로 Users 모델에 새로운 컬럼으로 추가한다.
```

```jsx
Users.belongsTo(models.CompanyInformation, {foreignKey: "company_id", sourceKey: "id"});
// Users 모델 안에 "company_id"라는 컬럼 이름으로 CompanyInformation 모델에 있는 "id" 값을 새로운 컬럼으로 추가한다.
```

- hasMany: 관계를 맺는 대상(자식)에게 자신의 외래 키를 추가한다. 그리고 복수에 데이터를 추가가 가능하며 관계를 맺는다 (CompanyInfo ⇒ Users) Users 외래 키가 추가된다.
- belongsTo: 관계를 맺는 대상(부모)에게 외래 키를 받아 추가한다. (Users ⇒ CompanyInformation) Users 외래 키가 추가된다.

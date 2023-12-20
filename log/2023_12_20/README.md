# 테이블 필드 이름
```
식별자(테이블 이름, 칼럼 이름 등)를 지정할 때는 가능한 표준 SQL 예약어를 피하는 것이 좋다. 이러한 예약어를 사용하면 예상치 못한 문제가 발생할 수 있습니다.
```

# 디비 테이블 생성 코드
```
create table users (
    id number primary key not null,
    name varchar2(10) not null,
    pw varchar2(400) not null
);

create table board(
    id number primary key not null,
    title varchar2(50) not null,
    content clob not null,
    created_at date default sysdate not null,
    updated_at date default sysdate not null,
    view_count number not null,
    good_count number not null,
    
     user_id number not null,
     
     CONSTRAINT user_id_fk FOREIGN KEY(user_id)
    REFERENCES users(id) ON DELETE CASCADE
);

create table comments(
    id number primary key not null,
    content varchar2(100) not null,
    created_at date default sysdate not null,
    updated_at date default sysdate not null,
    good_count number not null,
    
    user_id number not null,
    board_id number not null,
    
    CONSTRAINT comment_user_id_fk FOREIGN KEY(user_id)
    REFERENCES users(id) ON DELETE CASCADE,
    
    CONSTRAINT comment_board_id_fk FOREIGN KEY(board_id)
    REFERENCES board(id) ON DELETE CASCADE
);

create table board_like (
     id number primary key not null,
     
     user_id number not null,
     board_id number not null,
     
     CONSTRAINT board_like_user_id_fk FOREIGN KEY(user_id)
    REFERENCES users(id) ON DELETE CASCADE,
    
    CONSTRAINT board_like_board_id_fk FOREIGN KEY(board_id)
    REFERENCES board(id) ON DELETE CASCADE
);

create table comments_like (
     id number primary key not null,
     
     user_id number not null,
     board_id number not null,
     comments_id number not null,
     
     CONSTRAINT comments_like_user_id_fk FOREIGN KEY(user_id)
    REFERENCES users(id) ON DELETE CASCADE,
    
    CONSTRAINT comments_like_board_id_fk FOREIGN KEY(board_id)
    REFERENCES board(id) ON DELETE CASCADE,
    
    CONSTRAINT comments_like_comments_id_fk FOREIGN KEY(comments_id)
    REFERENCES comments(id) ON DELETE CASCADE
);


CREATE SEQUENCE board_seq START WITH 1 INCREMENT BY 1 MAXVALUE 100 CYCLE NOCACHE;
CREATE SEQUENCE users_seq START WITH 1 INCREMENT BY 1 MAXVALUE 100 CYCLE NOCACHE;
CREATE SEQUENCE comment_seq START WITH 1 INCREMENT BY 1 MAXVALUE 100 CYCLE NOCACHE;
CREATE SEQUENCE comment_like_seq START WITH 1 INCREMENT BY 1 MAXVALUE 100 CYCLE NOCACHE;
CREATE SEQUENCE board_like_seq START WITH 1 INCREMENT BY 1 MAXVALUE 100 CYCLE NOCACHE;
```
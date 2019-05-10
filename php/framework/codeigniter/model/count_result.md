
### $this->db->count_all_results()

특정 액티브레코드 쿼리를 통해 적용될 레코드의 수를 확인하도록 해줍니다. 쿼리는 where(), or_where(), like(), or_like() 등과 같은 액티브 레코드 한정자들을 허용합니다. 예제:

```php
echo $this->db->count_all_results('my_table');  // Produces an integer, like 25
$this->db->like('title', 'match');
$this->db->from('my_table');
echo $this->db->count_all_results(); // Produces an integer, like 17
```

**실제 반영되는 쿼리**
```sql
SELECT COUNT(*) AS `numrows`
FROM (`table`)
WHERE `where_caluse` IN ('where_condition1', 'where_condition2')
```

이 함수도 select() 에 값을 전달해도 초기화되버립니다. 만약에 유지하고 싶으시다면, FALSE 값을 두 번째 파라미터로 전달해주세요:

```php
echo $this->db->count_all_results('my_table', FALSE);
```

### $this->db->count_all()
특정 테이블의 레코드수를 리턴합니다. 첫 번째 파라미터에는 테이블명이 들어갑니다 예제:

```php
echo $this->db->count_all('my_table');  // Produces an integer, like 25
```

**실제 반영되는 쿼리**
```sql
SELECT COUNT(*) AS `numrows` FROM `table`
```
[공식 문서 이동](http://www.ciboard.co.kr/user_guide/kr/database/query_builder.html)

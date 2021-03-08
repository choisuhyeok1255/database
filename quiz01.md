```sql
# 1. Sakila 데이터 베이스에서 국가가 인도 고객의 수를 출력하세요
use sakila;

select country, count(country) as count
from customer_list
where country = "india";
```

```sql
# 2. 한국 도시중에 인구가 100만이 넘어가는 도시를 조회하여 인구순으로 내림차순하세요.
use world;

select Name, Population
from city
where CountryCode = "kor" AND Population >= 1000000;
```

```sql
# 3. city 테이블에서 population이 800만 ~ 1000만 사이인 도시 데이터를 인구수순으로 내림차순 하세요.
select Name, CountryCode, Population
from city
where Population >= 8000000 AND Population < 10000000
ORDER BY Population DESC;
```

```sql
# 4. country 테이블에서 1940 ~ 1950년도 사이에 독립한 국가들을 조회하고 독립한 년도 순으로 오름차순하세요.
select Code, concat(Name,"(",IndepYear,")") as NameIndep, Continent, Population
from country
where IndepYear between 1940 AND 1950
order by IndepYear ASC;
```

```sql
# 5. countrylanguage 테이블에서 스페인어, 한국어, 영어를 95% 이상 사용하는 국가 코드를 %로 내림차순하여 아래와 같이 조회하세요.
select CountryCode, Language, Percentage
from countrylanguage
where Percentage >= 95 AND Language IN ("English", "Spanish", "Korean")
order by Percentage DESC;
```

```sql
# 6. country 테이블에서 Code가 A로 시작하고 GovernmentForm에 Republic이 포함되는 데이터를 아래와 같이 조회하세요.
select code, name, continent, governmentform, population
from country
where code LIKE "A%" AND governmentform LIKE "%republic%";
```

```sql
# 7. sakila actor 테이블에서 first_name이 DAN 인 배우의 수를 출력하세요.
use sakila;

select first_name, count(first_name) as count
from actor
# like , = 뭐가 다르지?
where first_name = "DAN";
```

```sql
# 8. sakila film_text 테이블에서 title이 ice가 들어가고 description에 drama가 들어간 데이터르 출력하세요.
select film_id, title, description
from film_text
where title like "%ice%" AND description like "%drama%";
```

```sql
# 9. sakila 데이터 베이스의 film_list 뷰에서 price가 1 ~ 4, length가 180 이상, category는 Sci-Fi과 Animation이 아닌 데이터를 출력하세요.
select title, description, category, length, price
from film_list
where price between 1 AND 4 AND length >= 180 AND category not in ("Sci-Fi", "Animation");
```
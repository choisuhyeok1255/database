# 1. Sakila 데이터 베이스에서 국가가 인도 고객의 수를 출력하세요
use sakila;

select country, count(country) as count
from customer_list
where country = "india";
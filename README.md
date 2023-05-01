# DatabaseSystems

## Homework 1

### Dragonfly

***Dragonfly*** имеет Consistency and Partition tolerance (CP), так как основан он на базе Redis, которая в свою очередь является СР базой данных. А Redis является СР из-за:

* С - так как представялет собой БД с однонодовой конфигурацией и не требует синхронизации данных между нодами.
* P - позволяет каждому отдельному инстансу БД обслуживать клиентов в силу своей однонодности.

### ScyllaDB

***ScyllaDB*** - Availability and Partition tolerance. Так как эта база данных, как и предыдущая, основана на более известной БД Cassandra. Cassandra же в свою очередь удовлетворяет AP, так как:

* A - получаем доступность в результате цикличной архитектуры, которая позволяет перенаправлять запрос на другие ноды. Таким образом мы получаем доступность, но теряем консистентность.
* P - при выходе отдельной ноды из строя, мы можем обратиться к другой ноде за данными.

### ArenadataDB

***ArenadataDB*** - основана на Greenplum. Это значит, что архитектура состит из сегментов PostgreSQL. Consistency and Availability :

* C - наличие master nodes и взаимной согласованности всех сегментов.
* A - наличие "зеркал" сегментов и резервной master ноды.

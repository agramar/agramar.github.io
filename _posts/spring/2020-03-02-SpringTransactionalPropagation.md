---
layout: post
title: Spring Transactional Propagation
category: Spring
tags:
- Spring
- Transactional
- Propagation
---

스프링 트랜젝션 전파
=================

#### REQUIRED
* Support a current transaction, create a new one if none exists.
* Analogous to EJB transaction attribute of the same name.
* This is the default setting of a transaction annotation.

#### SUPPORTS
* Support a current transaction, execute non-transactionally if none exists.
* Analogous to EJB transaction attribute of the same name.
* Note: For transaction managers with transaction synchronization,
* {@code SUPPORTS} is slightly different from no transaction at all,
* as it defines a transaction scope that synchronization will apply for.
* As a consequence, the same resources (JDBC Connection, Hibernate Session, etc)
* will be shared for the entire specified scope. Note that this depends on
* the actual synchronization configuration of the transaction manager.

#### MANDATORY
* Support a current transaction, throw an exception if none exists.
* Analogous to EJB transaction attribute of the same name.

#### REQUIRES_NEW
#### NOT_SUPPORTED
#### NEVER
#### NESTED
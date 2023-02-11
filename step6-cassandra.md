<!-- TOP -->
<div class="top">
  <img class="scenario-academy-logo" src="https://datastax-academy.github.io/katapod-shared-assets/images/ds-academy-2023.svg" />
  <div class="scenario-title-section">
    <span class="scenario-title">Inserts, Updates, Deletes and Upserts in Apache Cassandra®</span>
    <span class="scenario-subtitle">ℹ️ For technical support, please contact us via <a href="mailto:aleksandr.volochnev@datastax.com">email</a> or <a href="https://dtsx.io/aleks">LinkedIn</a>.</span>
  </div>
</div>

<!-- NAVIGATION -->
<div id="navigation-top" class="navigation-top">
 <a href='command:katapod.loadPage?[{"step":"step5-cassandra"}]'
   class="btn btn-dark navigation-top-left">⬅️ Back
 </a>
<span class="step-count"> Step 6 of 9</span>
 <a href='command:katapod.loadPage?[{"step":"step7-cassandra"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>

<!-- CONTENT -->

<div class="step-title">Deleting rows</div>

Let's delete all data from our tables.

✅ Delete one column in a row:
```
DELETE age FROM users
WHERE email = 'joe@datastax.com';

SELECT * FROM users WHERE email = 'joe@datastax.com';
```

✅ Delete a row:
```
DELETE FROM ratings_by_user
WHERE email = 'joe@datastax.com'
  AND title = 'Alice in Wonderland'
  AND year  = 2010;
  
SELECT * FROM ratings_by_user WHERE email = 'joe@datastax.com';
```

✅ Delete all rows in a partition:
```
DELETE FROM ratings_by_user
WHERE email = 'joe@datastax.com';
  
SELECT * FROM ratings_by_user WHERE email = 'joe@datastax.com';
```

✅ Delete the remaining rows in the tables:
<details>
  <summary>Solution</summary>

```
SELECT * FROM users;
SELECT * FROM ratings_by_user;

DELETE FROM users
WHERE email = 'joe@datastax.com';
DELETE FROM users
WHERE email = 'jen@datastax.com';
DELETE FROM ratings_by_user
WHERE email = 'jen@datastax.com';

SELECT * FROM users;
SELECT * FROM ratings_by_user;
```

</details>

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"step5-cassandra"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
 <a href='command:katapod.loadPage?[{"step":"step7-cassandra"}]'
    class="btn btn-dark navigation-bottom-right">Next ➡️
  </a>
</div>


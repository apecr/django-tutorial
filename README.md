# Django Tutorial

## Part 1

## Part 2

### Database setup

````shell
$ python manage.py migrate
````

### Creating models

```shell
$ python manage.py makemigrations polls
$ python manage.py sqlmigrate polls 0001
```

The last command results in something like that:

```sql
BEGIN;
--
-- Create model Question
--
CREATE TABLE "polls_question" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "question_text" varchar(200) NOT NULL, "pub_date" datetime NOT NULL);
--
-- Create model Choice
--
CREATE TABLE "polls_choice" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "choice_text" varchar(200) NOT NULL, "votes" integer NOT NULL, "question_id" bigint NOT NULL REFERENCES "polls_question" ("id") DEFERRABLE INITIALLY DEFERRED);
CREATE INDEX "polls_choice_question_id_c5b4b260" ON "polls_choice" ("question_id");
COMMIT;
```

```shell
$ python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, polls, sessions
Running migrations:
  Applying polls.0001_initial... OK
```

### Playing with the API

```shell
python manage.py shell
```

### Introducing the Django Admin

```shell
python manage.py createsuperuser

```

## PART 3


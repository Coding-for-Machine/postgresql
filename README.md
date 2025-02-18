# postgresql

```SQL
CRATE TABLE users (
  id SERIAL PRIMARY KEY,
  username VARCHAR(100) UNIQUE,
  email VARCHAR(100) UNIQUE,
  is_active BOOLEAN DEFAULT TRUE,
  is_admin BOOLEAN DEFAULT FALSE
);
```

```SQL
CERATE TABLE IF NOT EXISTS posts (
  id SERIAL PRAMARY KEY,
  title VARCHAR(100) NOT NULL,
  body TEXT NOT NULL,
  is_active BOOLEAN DEFAULT TRUE,
  user_id INT REFERENCES users(id)
);
```

```SQL
CERATE TABLE tages (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100) UNIQUE
);

```

```SQL
CREATE TABLE post_tages (
  post_id INT REFERENCES posts(id),
  tage_id INT REFERENCES tages(id),
  FOREIGN KEY (post_id, tage_id)

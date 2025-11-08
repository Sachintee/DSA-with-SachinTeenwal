--- ❤️ ---

# 🚀 _Day 312. Actors and their Movies_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/actors-and-their-movies/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <mysql/mysql.h>

using namespace std;

int main() {
    MYSQL *conn;
    MYSQL_RES *res;
    MYSQL_ROW row;

    const char *server = "localhost";
    const char *user = "root";
    const char *password = "yourpass";
    const char *database = "moviesdb";

    conn = mysql_init(nullptr);

    if (!mysql_real_connect(conn, server, user, password, database, 0, nullptr, 0)) {
        cerr << "Database connection failed: " << mysql_error(conn) << endl;
        return 1;
    }

    const char *query = R"(
        SELECT DISTINCT m.movie_title
        FROM movies m
        JOIN movies_cast mc ON m.movie_id = mc.movie_id
        WHERE mc.actor_id IN (
            SELECT actor_id
            FROM movies_cast
            GROUP BY actor_id
            HAVING COUNT(DISTINCT movie_id) >= 2
        )
        ORDER BY m.movie_title;
    )";

    if (mysql_query(conn, query)) {
        cerr << "Query failed: " << mysql_error(conn) << endl;
        mysql_close(conn);
        return 1;
    }

    res = mysql_store_result(conn);
    cout << "movie_title" << endl;
    while ((row = mysql_fetch_row(res)) != nullptr) {
        cout << row[0] << endl;
    }

    mysql_free_result(res);
    mysql_close(conn);

    return 0;
}

```

## Code (Java)

```java
import java.sql.*;

public class MoviesQuery {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/moviesdb";
        String user = "root";
        String password = "yourpass";

        String query = """
            SELECT DISTINCT m.movie_title
            FROM movies m
            JOIN movies_cast mc ON m.movie_id = mc.movie_id
            WHERE mc.actor_id IN (
                SELECT actor_id
                FROM movies_cast
                GROUP BY actor_id
                HAVING COUNT(DISTINCT movie_id) >= 2
            )
            ORDER BY m.movie_title;
        """;

        try (Connection conn = DriverManager.getConnection(url, user, password);
             Statement stmt = conn.createStatement();
             ResultSet rs = stmt.executeQuery(query)) {

            System.out.println("movie_title");
            while (rs.next()) {
                System.out.println(rs.getString("movie_title"));
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}

```

## Code (Python)

```python
import sqlite3

# Connect to the database (use your actual DB path or MySQL connector if needed)
conn = sqlite3.connect("movies.db")
cursor = conn.cursor()

query = """
SELECT DISTINCT m.movie_title
FROM movies m
JOIN movies_cast mc ON m.movie_id = mc.movie_id
WHERE mc.actor_id IN (
    SELECT actor_id
    FROM movies_cast
    GROUP BY actor_id
    HAVING COUNT(DISTINCT movie_id) >= 2
)
ORDER BY m.movie_title;
"""

cursor.execute(query)
rows = cursor.fetchall()

print("movie_title")
for row in rows:
    print(row[0])

conn.close()

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

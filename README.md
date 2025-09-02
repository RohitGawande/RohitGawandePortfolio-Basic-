

# Water Quality Monitoring System 🚰

A **Java-based Web Application** to report and track water quality issues in different locations.  
Built using **JSP, Servlets, JDBC, MySQL, and Tomcat**.

---

## 📌 Features
- User can submit water quality issues with:
  - Name
  - Location
  - Description
  - Optional Image Upload
- Issues are stored in a MySQL database.
- View all reported issues in a simple list.
- Scalable design to add more features in the future (e.g., Admin Panel, Real-time Monitoring, REST APIs).

---

## 🛠️ Tech Stack
- **Frontend:** JSP, HTML, CSS
- **Backend:** Java Servlets
- **Database:** MySQL
- **Server:** Apache Tomcat
- **Build Tool:** Maven

---

## ⚙️ Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/your-username/WaterQualityMonitoringSystem.git
cd WaterQualityMonitoringSystem
````

### 2. Configure Database

* Start MySQL server
* Create database:

```sql
CREATE DATABASE rohit;
USE rohit;
```

* Create `issue` table:

```sql
CREATE TABLE issue (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(100) NOT NULL,
  location VARCHAR(200) NOT NULL,
  description TEXT NOT NULL,
  image LONGBLOB,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 3. Configure Database Properties

Update `src/main/resources/config.properties`:

```properties
db.url=jdbc:mysql://localhost:3306/
db.username=your_mysql_username
db.password=your_mysql_password
```

### 4. Build & Deploy

* Run Maven build:

```bash
mvn clean package
```

* Deploy the generated WAR file from `target/` to **Tomcat’s webapps folder**
* Start Tomcat server:

```bash
http://localhost:9999/WaterQualityMonitoringSystem
```

---

## 🚀 Usage

1. Open `http://localhost:9999/WaterQualityMonitoringSystem/`
2. Submit an issue through the form
3. View submitted issues on the **View Issues** page

---

## 📂 Project Structure

```
WaterQualityMonitoringSystem/
│── src/main/java/com/rohitgawande/waterquality/
│   ├── controller/   # Servlets
│   ├── dao/          # Database operations
│   ├── model/        # JavaBeans/POJOs
│   └── util/         # Utility classes (DBConnection)
│
│── src/main/webapp/
│   ├── index.jsp
│   ├── success.jsp
│   ├── viewIssues.jsp
│   └── WEB-INF/
│       └── web.xml   # Servlet configuration
│
│── src/main/resources/
│   └── config.properties
│
│── pom.xml
│── README.md
│── LICENSE
```

---

## 📈 Future Enhancements

* Add **User Authentication** (Login/Register)
* Role-based access (**Admin Panel**)
* REST APIs for mobile/IoT integration
* Real-time notifications for new issues
* Data visualization (charts/maps)

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo
2. Create a new branch (`feature-xyz`)
3. Commit changes
4. Push branch and create a Pull Request

---

## 📜 License

This project is licensed under the **MIT License**.
See the [LICENSE](./LICENSE) file for details.

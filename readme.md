# Reference
- https://blog.me-idea.in.th/mongodb-docker-compose-up-%E0%B8%9B%E0%B8%B8%E0%B9%8A%E0%B8%9A%E0%B8%AA%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%87-mongo-database-%E0%B8%9B%E0%B8%B1%E0%B9%8A%E0%B8%9A-d27004a9fd78

# การขึ้น mongodb container
-  ดูจาก reference ที่ให้ไปเลยครับ เพราะลอกเขามาครับ hahaha

# การเขียน uri จากที่ได้สร้างมาจาก docker-compose-standalone.yml
- มีการสร้าง database กี่ database
    - ที่เข้าใจคือ จะสร้าง admin อยู่แล้วแต่ดเราเพิ่มใน shell script ให้สร้าง อีก database นึงตาม MONGO_INITDB_DATABASE ใน compose
    - ในที่นี้มีการสร้าง database 2 database คือ
        - admin
        - newExample

# uri admin 
    ```
        mongodb://userroot:passroot@localhost:27021/admin
    ```
  - userroot    คือ ใน compose คือ MONGO_INITDB_ROOT_USERNAME
  - userroot    คือ ใน compose คือ MONGO_INITDB_ROOT_PASSWORD
  - localhost   คือ domain ของ container ที่เราเอาไปวาง
  - 27021       คือ port ที่เราเปิดให้เข้า 
  - admin       คือ ชื่อ database ที่เราต้องการจะเข้า

# uri newExample
    ```
        mongodb://userNewExample:passNewExample@localhost:27021/newExample
    ```
  - userNewExample    คือ ใน compose คือ MONGO_INITDB_USERNAME
  - passNewExample    คือ ใน compose คือ MONGO_INITDB_PASSWORD
  - localhost         คือ domain ของ container ที่เราเอาไปวาง
  - 27021             คือ port ที่เราเปิดให้เข้า 
  - newExample        คือ ชื่อ database ที่เราต้องการจะเข้า ใน compose คือ MONGO_INITDB_DATABASE
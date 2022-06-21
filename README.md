# Django DRF Elasticsearch
Two months back, at my Tech Talk session with BRAC IT, I showed a demo of Elasticsearch from an online tutorial, but it was cumbersome to some of you because of installation issues and others. Instead, participants preferred my way of doing all things on Docker. So I am uploading all my demo code here with everything in dockerized containers. I kept the models same as it is and uploaded the exact data generation script.

## Want to use this project?

1. Fork/Clone

2. Install Docker & Docker-Compose
3. Build:

    ```sh
    $ docker-comose build
    ```

4. Run:

    ```sh
    $ docker-compose up -d
    ```

5. Open web container's bash:

    ```sh
    $ docker-compose exec web bash
    ```

6. Apply the migrations:

    ```sh
    root@container-id $ python manage.py migrate
    ```
7. Populate the database with some test data by running the following command:

    ```sh
    root@container-id $ python manage.py populate_db
    ```

8. Create and populate the Elasticsearch index and mapping:

    ```sh
    root@container-id $ python manage.py search_index --rebuild
    ```

9. Test Elasticsearch with the following queries:

    - [http://127.0.0.1:8000/search/user/mike/](http://127.0.0.1:8000/search/user/mike/) - should find the user 'mike13'
    - [http://127.0.0.1:8000/search/user/jess_/](http://127.0.0.1:8000/search/user/jess_/) - should find the user 'jess_'
    - [http://127.0.0.1:8000/search/category/seo/](http://127.0.0.1:8000/search/category/seo/) - should find the category 'SEO optimization'
    - [http://127.0.0.1:8000/search/category/progreming/](http://127.0.0.1:8000/search/category/progreming/) - should find the category 'Programming' (:warning: notice the typo)
    - [http://127.0.0.1:8000/search/article/linux/](http://127.0.0.1:8000/search/article/linux/) - should find the article 'Installing the latest version of Ubuntu'
    - [http://127.0.0.1:8000/search/article/java/](http://127.0.0.1:8000/search/article/java/) - should find the article 'Which programming language is the best?'
   

9. Or if you familiar with swagger you can play with the following URL -
    - [http://localhost:8000/doc/](http://localhost:8000/doc/)
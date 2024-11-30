
MVN:

mvn dependency:purge-local-repository
mvn dependency:resolve
mvn clean package -Dmaven.test.skip=true
mvn clean install -U  (w app/server)
mvn spring-boot:run (w master/yachtcharterpl)
mvn clean install-DskipTests
mvn -version



DOCKER:
 
docker-compose down
docker-compose up --build
docker-compose up db
docker stop $(docker ps -a -q)
docker-compose
docker volume ls
docker volume rm yacht-charter-mysql-data


BASH:

net start mysql80
net stop mysql80

MYSQL:

mysql -u root -p

GIT:

git add client
git status
git commit -m "update pom.xml"
git push
git checkout
git pull --rebase
git stash
git switch rafal-branch
git fetch origin
git branch
git rebase -i HEAD~5
git push --force-with-lease
git remote -v
del .git /F /Q


VIM:

\q  wyjscie 

ssh-keygen -t ed25519 -C "milanoitaliana@gmail.com"


07.11.2024
1. Zatrzymanie mysql
2. Uruchomienie DockerDesktop 

16.11.2024
1. Skonfigurować po SSH  VVVVV
2. Sklonować repo VVVVV
3. Uporządkować notatnik - README i puschować na repo VVVVV

19.11.2024
1. Zarchiwizować pozostałe niewykorzystane repo na GIT

23.11.2024

1. Dodać klucz prywatny do gitignore i do knonwhost   VVVV Dodałem do gitignore, ale nie do known-host
2. Rebuild działający VVVVV Restart IDE pomógł 
3. Uzupełnić zapytania do charters w odniesieniu do boats   VVVVV
4. Poprawić endpointy wg nomenklatury poniżej dla charters i innych   VVVVV
5. Sprawdzić pozostałe zapytania postman, tak aby zwracały status 200 (m.in. dodać crossorigin tak jak w boatcontroller.  VVVVV
6. 

GET /boats         - pobierz wszystkie łódki
GET /boats/{id}    - pobierz konkretną łódkę
POST /boats        - dodaj nową łódkę
PUT /boats/{id}    - aktualizuj łódkę
DELETE /boats/{id} - usuń łódkę

26.11.2024 

1. Live Coding na Visual Studio Code (ext. live share)
2. Pozmieniać zapytania na Postman w odniesieniu do AddCharter
3. Dodać do klasy User relacje ManyToOne do charteru
4. Rozpisać relacje między klasami (entities) -> wtyczka, która generuje wizualnie zależności (boats, charters, users)

CRUD dla charteru (dodawanie rezerwacji
CRUD dla łodzi (dodawanie, wyświetlanie, edycja, usuwanie).



@JsonFormat(pattern = "yyyy-MM-dd HH:mm:ss",timezone = "Europe/Warsaw")
    @Column(name="start_charter")
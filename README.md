-- Нужные библиотеки
https://github.com/BurntSushi/toml

--// миграция
megrate create -ext sql -dir migrations create_users
migrate -path migrations -database "postgres://localhost/restapi_dev?sslmode=disable&user=postgres&password=QSD73qa" up


--//--//для SoapUI
--//
http://localhost:8080/users
{
    "email": "user@example.org",
    "password":"password"
}
--//
http://localhost:8080//sessions
{
    "email": "user@example.org",
    "password":"password"
}
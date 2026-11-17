# Projekt AWS — zamówienia

Autor: Dmytro Nesvitailo, grupa 2

## Laboratorium 3

- Wariant: zamówienia.
- Region: eu-north-1 (Stockholm).
- Prefiks własnych zasobów: dmytro-nesvitailo.
- Używam własnego bucketu S3.
- Dozwolony prefiks danych: dmytro-nesvitailo/input/.
- Obiekt kontrolny: control/control.txt.
- Rola odczytująca: dmytro-nesvitailo-s3-reader.
- Rola przygotowująca dane: AccountFullAccessRole.

Bucket ma włączone wszystkie cztery ustawienia Block Public Access.
Polityka roli pozwala wyłącznie na s3:GetObject we własnym prefiksie.
Listowanie nie jest potrzebne, ponieważ znam dokładny klucz pliku.

## Wynik

Rola odczytująca pobrała zlecenia.csv. Plik jest zgodny z oryginałem
i zawiera nagłówek oraz 12 rekordów.

Ta sama rola otrzymała AccessDenied dla istniejącego obiektu
control/control.txt w tym samym buckecie. Istnienie obu obiektów
potwierdzono wcześniej rolą przygotowującą dane.

Dowód obu odczytów: dowody/03-iam-s3.txt.
Polityki IAM: iam/trust-policy.json i iam/read-policy.json.

Próbka, bucket, region i prefiks pozostają do kolejnych laboratoriów.

## Nazwa bucketu i anonimizacja

Nazwa bucketu: dmytro-nesvitailo-chmura-<ACCOUNT_ID>.
W dowodzie i politykach XXXXXXXXXXXX zastępuje numer konta AWS.
Przed ponownym wdrożeniem polityk należy zastąpić tę wartość własnym
numerem konta. Zapisane polityki są zanonimizowanymi kopiami konfiguracji.

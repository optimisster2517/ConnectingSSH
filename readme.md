# 🔐 Домашнее задание: Основы терминала и SSH

Репозиторий содержит выполненное домашнее задание по курсу "Основы терминала" от Нетологии.

## 📋 Описание проекта

В ходе выполнения задания была организована защищённая сессия подключения к виртуальному серверу хостинг-провайдера REG.RU через протокол SSH.

## 🎯 Выполненные задания

### Задание 1: Подключение к серверу через SSH

Выполнено успешное подключение к удалённому серверу с использованием SSH-клиента.

**Параметры сервера:**
- **Имя сервера:** Black Cobaltum
- **IP-адрес:** 149.33.36.99
- **ОС:** Ubuntu 24.04 LTS
- **Пользователь:** root

**Команда подключения:**
```bash
ssh root@149.33.36.99
```

<div align="center">
  <img src="https://github.com/optimisster2517/ConnectingSSH/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA1.PNG" width="700" alt="Скриншот 1: Успешное подключение к серверу"/>
  <p><i>Успешное подключение к серверу по SSH. Видно приветственное сообщение Ubuntu и командную строку сервера</i></p>
</div>

---

### Задание 2*: Настройка SSH-ключей и псевдонима (необязательное)

Реализована возможность подключения к серверу без ввода пароля с использованием SSH-ключей и настройка псевдонима для упрощения подключения.

#### Этапы выполнения:

1. **Генерация SSH-ключа**
   ```bash
   ssh-keygen -t rsa -b 4096
   ```

2. **Копирование публичного ключа на сервер**
   ```bash
   type C:\Users\Admin\.ssh\id_rsa.pub | ssh root@149.33.36.99 "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys"
   ```

3. **Создание файла конфигурации SSH**
   - Путь: `C:\Users\Admin\.ssh\config`
   - Содержимое:
   ```
   Host netology
       HostName 149.33.36.99
       User root
       IdentityFile C:\Users\Admin\.ssh\id_rsa
   ```

4. **Подключение по псевдониму**
   ```bash
   ssh netology
   ```

<div align="center">
  <img src="https://github.com/optimisster2517/ConnectingSSH/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA2.PNG" width="700" alt="Скриншот 2: Создание SSH-ключа"/>
  <p><i>Создание SSH-ключа и копирование публичного ключа на сервер. Успешное подключение без ввода пароля</i></p>
</div>

<div align="center">
  <img src="https://github.com/optimisster2517/ConnectingSSH/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA3.PNG" width="700" alt="Скриншот 3: Файл конфигурации SSH"/>
  <p><i>Содержимое файла конфигурации SSH (~/.ssh/config) с настроенным псевдонимом "netology"</i></p>
</div>

<div align="center">
  <img src="https://github.com/optimisster2517/ConnectingSSH/blob/main/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA4.PNG" width="700" alt="Скриншот 4: Подключение по псевдониму"/>
  <p><i>Успешное подключение к серверу командой `ssh netology` без запроса пароля</i></p>
</div>

---


## 👤 Автор

**Иван Фомин**

- GitHub: [@optimisster2517](https://github.com/optimisster2517)


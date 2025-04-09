# OSINT Homework 04 — Ansible Playbook для встановлення OSINT-інструментів (на Kali Linux)

## 🔧 Інструменти, що встановлюються

1. **Amass** – збір сабдоменів
2. **theHarvester** – пошук email-адрес та доменів
3. **Subfinder** – пасивний пошук сабдоменів
4. **Shodan CLI** – взаємодія з Shodan API
5. **GitDorker** – пошук секретів у GitHub (альтернатива TruffleHog)

## 📦 Особливості

- Встановлення через `apt`, `git clone`, або `pipx`
- Окрема секція для кожного інструменту з мітками `tags`
- Підтримка `become: true` для привілейованих команд
- Працює як локально, так і на віддаленому сервері через SSH


## ⚙️ Встановлення

### 1. Клонувати репозиторій
```bash
git clone https://github.com/toquzu/osint-hw04.git
cd osint-hw04
```

### 3. Запуск Playbook

#### ✅ Локально:
```bash
ansible-playbook -l local -i inventory.ini playbook.yml
```

#### 🔒 На віддаленому сервері:
Онови `inventory.ini` з IP та користувачем:
```ini
[aws]
your.server.ip ansible_user=username
```
Тоді запусти:
```bash
ansible-playbook -i inventory.ini playbook.yml
```

#### 🎯 Запуск з конкретним тегом:
```bash
ansible-playbook -i inventory.ini playbook.yml --tags "amass"
```


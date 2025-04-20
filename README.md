Цей проєкт демонструє розгортання AWS EC2 інстансу, автоматичне встановлення інструментів для OSINT за допомогою Ansible, а також приклад збору сабдоменів через amass.

OSINT-ansible/
├── OSINT.yml              # Ansible-плейбук для встановлення всіх інструментів
├── hosts.txt              # Інвентарний файл Ansible з IP-адресами інстансів
├── output.txt             # Результат роботи утиліти amass
├── README.md              # Документація проєкту
├── screenshots/           # Папка зі скріншотами
│   ├── config.png         # Параметри створення інстансу AWS
│   ├── ssh.png            # Підключення по SSH
│   ├── ansible_run.png    # Запуск Ansible playbook
│   ├── amass_version.png  # Перевірка встановлення amass
│   ├── output_result.png  # Результат виконання команди amass
│   └── instance_ui.png    # UI AWS після запуску інстансу


Запуск Ansible playbook:

ansible-playbook OSINT.yml -l L4

Після встановлення можна запускати amass:

amass enum -d nasa.gov -passive -o output.txt

Конфігурація AWS

AMI: Ubuntu Server 24.04 LTS

Тип інстансу: t3.micro (t2.micro не було доступним)

Регіон: eu-north-1

SSH-доступ: відкритий для всіх (0.0.0.0/0)

Ключ: L4.pem


Інструменти:

Amass

theHarvester

Subfinder


Shodan CLI


GitDorker

Скриншоти:
config.png - Налаштування AWS інстансу

ssh.png - Підключення до інстансу через SSH

ansible_run.png - Результат виконання Ansible playbook

amass_version.png - Перевірка встановлення amass

output_result.png - Збір сабдоменів через amass

instance_ui.png - Стан інстансу в AWS після запуску

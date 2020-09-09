# Установка Sandbox ноды

### 1. Настройка Ubuntu

Обновляем пакеты на сервере до новейших версий:

```text
sudo apt update
```

Установим Докер:

```text
sudo apt install docker.io curl -y
```

Активируем Докер:

```text
sudo systemctl start docker
sudo systemctl enable docker
```

### 2. Запуск Sandbox ноды

```text
docker run \
--publish 3085:3085 \
-d \
--name coda \
codaprotocol/coda-demo:pickles-sandbox
```

### 3. Просмотр логов

```text
docker logs --follow coda
```

Теперь переходим к Challenge \#1

### 4. Использование CLI

{% hint style="info" %}
Этот шаг нужно выполнять только начиная с пункта Challenge \#2
{% endhint %}

Для доступа к любым командам [Coda CLI](https://codaprotocol.com/docs/cli-reference):

```text
docker exec -it coda bash
```

Например проверка статуса, состояния узла:

```text
coda client status
```

![](../.gitbook/assets/image.png)

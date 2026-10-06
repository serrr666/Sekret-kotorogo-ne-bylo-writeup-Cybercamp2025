# Секрет, которого не было — разбор таска с CyberCamp 2025

Использованный софт: Git, GitHub

## Ход расследования

### 1. История репозитория

По условию секрет удалили из кода. Проверил историю [AIVulnScan](https://github.com/saleny/AIVulnScan/tree/3e257ef1c864eb284ee6ef0434fc928b9a985ba9), включая все ветки:

```bash
git clone https://github.com/saleny/AIVulnScan.git
cd AIVulnScan
git log --all -p -- tests/test_scan.py
```

### 2. Найденный секрет

В коммите `3e257ef` (`add new tests`) обнаружен флаг в комментарии файла `tests/test_scan.py`, строка 12.

Старую версию файла можно получить командой:

```bash
git show 3e257ef1c864eb284ee6ef0434fc928b9a985ba9:tests/test_scan.py
```

[Файл с флагом на GitHub](https://github.com/saleny/AIVulnScan/blob/3e257ef1c864eb284ee6ef0434fc928b9a985ba9/tests/test_scan.py#L12)

![Флаг в старой версии файла](https://github.com/user-attachments/assets/47f7a223-e653-4fbd-8319-b2878c4ac6ff)



### 3. Удаление из кода

В следующем [коммите `afe4d46`](https://github.com/saleny/AIVulnScan/commit/afe4d462b1c81b8e3faaaa882d04ee7be7829454) комментарий удалили. Однако предыдущий коммит остался доступен: обычное удаление строки не очищает историю Git.

## Ответ

```text
{y0u_f1Иd_th1$_v3Яy_$3cЯ3t_$tЯ1Иg_0И_g1t}
```

Буквы `И` и `Я` в ответе — кириллица.


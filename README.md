# ДЗ1 «Внимание своими руками»

- `dz1-attention.ipynb`: реализация split_heads, merge_heads, attention и блока трансформера
- `dz1-bughunt.ipynb`: поиск багов, мой вариант seed 42
- `REPORT.md`: отчёт с таблицей багов, графиком и генерацией
- `loss.png`, `sample.txt`: график лосса и сгенерированный текст

## Ноутбуки в Colab

- `dz1-attention.ipynb`: https://colab.research.google.com/drive/13aUCwq-ffDJmqD9blOiJFBmwuvAwIpNh
- `dz1-bughunt.ipynb`: https://colab.research.google.com/drive/11a-pqcHXKnxp_FFNMSiHKQnrgqt-mrWX

## Как запустить

Проще всего в Colab: открыть ноутбук по ссылке выше (или загрузить через File → Upload notebook) и нажать Runtime → Run all. Сначала `dz1-attention.ipynb`, потом `dz1-bughunt.ipynb`. Ставить ничего не нужно.

Локально нужны Python 3.10+ и пакеты:

```bash
pip install torch matplotlib jupyter
```

После этого открыть ноутбуки в Jupyter и выполнить все ячейки.

## Воспроизводимость

- seed 42 задаётся во второй ячейке, обучение использует `torch.manual_seed(0)` (так было в исходном ноутбуке), перед генерацией тоже стоит `manual_seed(0)`.
- Модель учится на CPU, поэтому результат одинаковый и в Colab, и локально. Я запускал два раза, числа совпали.
- Моё окружение: Python 3.12, torch 2.11, Windows 11.
- Что должно получиться: 17/17 в обоих ноутбуках, лосс 3.184 → 0.037, генерация повторяет фразу «алгоритм внимания смотрит на все позиции сразу».

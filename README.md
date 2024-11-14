
---

# Параллельное умножение матриц с использованием MPI


---

## Основные компоненты

- **Matrix A**: Первая матрица размером `rowsA x colsA`.
- **Matrix B**: Вторая матрица размером `colsA x colsB`.
- **Matrix C**: Результирующая матрица размером `rowsA x colsB`.

---

## Логика работы программы

1. **Инициализация и разбиение данных:**
   - Главный процесс инициализирует значения матриц A и B.
   - Каждый процесс получает части матриц для умножения.
   
2. **Распределение задач:**
   - Каждому процессу выделяется блок строк для обработки.
   - Процесс с рангом `i` обрабатывает строки от `startRow` до `endRow`.

3. **Умножение матриц:**
   - Каждый процесс выполняет умножение части матриц A и B.
   
4. **Сборка результатов:**
   - Результаты умножения от каждого процесса отправляются главному процессу для сборки итоговой матрицы C.
   
5. **Вывод результата:**
   - Главный процесс выводит результирующую матрицу и время выполнения.

---


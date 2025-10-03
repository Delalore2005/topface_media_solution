# TOPFACE Media Solution — Анализ пролонгаций

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg?logo=jupyter)
![Status](https://img.shields.io/badge/status-active-success.svg)

Аналитический проект для расчёта коэффициентов **C1/C2** пролонгаций по аккаунт-менеджерам и отделу.  
Формируются помесячные и годовые отчёты, визуализации и итоговый Excel-отчёт.

---

## 📊 Пример визуализации

![Динамика коэффициентов отдела](Reports/department_prolongation_coefficients.png)

---

## 📈 Методология

В проекте рассчитываются два ключевых коэффициента пролонгации:

- **C1 (первый месяц)**  
  Отношение выручки в *m* по проектам, завершённым в *(m−1)*, к выручке этих проектов в *(m−1)*.  

- **C2 (второй месяц)**  
  Отношение выручки в *m* по проектам, завершённым в *(m−2)* и **не имевшим выручки в *(m−1)***, к выручке этих проектов в *(m−2)*.  

**Правила:**
- Источник проектов и аккаунт-менеджеров — таблица `prolongations`.  
- Суммы по месяцам — из агрегата `financial_agg`.  
- Если знаменатель = 0 или отсутствует — коэффициент не рассчитывается (`NaN`).  

---

## 🚀 Возможности
- Гармонизация месяцев и данных продаж.  
- Расчёт коэффициентов **C1/C2** по каждому аккаунт-менеджеру (2023).  
- Суммирование числителей/знаменателей для корректных расчётов.  
- Агрегация по отделу и формирование годового отчёта (**ratio-of-totals**).  
- Итоговые таблицы для дашборда и Excel.  
- Экспорт графиков (**PNG**) и отчётов (**XLSX**).  

---

## 🧱 Структура репозитория

```
TOPFACE/
├─ data/                         # Исходные данные (CSV/XLSX)
├─ Reports/                      # Итоговые отчёты и графики
│   ├─ department_prolongation_coefficients.png   # Динамика показателей отдела
│   ├─ annual_prolongation_by_manager.png        # Годовое сравнение менеджеров
│   ├─ monthly_trends_by_manager.png             # Тренды по месяцам для каждого AM
│   └─ comprehensive_manager_comparison.png      # Итоговое сравнение всех менеджеров
├─ Charts/                       # Ноутбуки или скрипты для визуализаций
├─ topface_solution_code.ipynb   # Главный ноутбук с расчётами
├─ requirements.txt              # Зависимости проекта
└─ README.md                     # Документация проекта
```

---

## 📦 Установка и запуск

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/Delalore2005/topface_media_solution.git
   cd topface_media_solution
   ```

2. Создайте виртуальное окружение:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate   # macOS/Linux
   # .venv\Scripts\activate     # Windows
   ```

3. Установите зависимости:
   ```bash
   pip install -r requirements.txt
   ```

4. Запустите Jupyter:
   ```bash
   jupyter lab
   ```
   или:
   ```bash
   jupyter notebook
   ```

---

## 🗂️ Результаты работы

- **Excel-отчёт:**  
  `prolongation_analysis_report.xlsx`  
  - Вкладки: *Monthly Results*, *Annual Results*, *Department Summary*, *Summary Statistics*

- **Визуализации (PNG):**
  - `department_prolongation_coefficients.png`
  - `annual_prolongation_by_manager.png`
  - `monthly_trends_by_manager.png`
  - `comprehensive_manager_comparison.png`

- **Документация:**  
  `prolongation_analysis_code_explanation.txt`

---

## 📑 Таблицы для дашборда

- **Помесячный отчёт** — коэффициенты C1/C2 + числители/знаменатели.  
- **Годовой отчёт** — годовые коэффициенты (**ratio-of-totals**), средние показатели, суммы баз.  
- **Помесячный отчёт по отделу** — агрегированные C1dept/C2dept и базы.  
- **Сводная статистика** — контроль полноты (число валидных месяцев для каждого AM).  

---

## 📅 Roadmap

- [ ] Автоматизировать обновление отчётов (скрипт с планировщиком).  
- [ ] Добавить CI/CD через GitHub Actions для проверки ноутбуков.  
- [ ] Расширить методологию: включить **C3 (3-й месяц)**.  
- [ ] Добавить интерактивный дашборд (Streamlit/Plotly Dash).  
- [ ] Перевести документацию и визуализации на английский для международного использования.  

---

## 👤 Контакты

Автор: **@Delalore2005**  
Вопросы и предложения — через Issues в репозитории.

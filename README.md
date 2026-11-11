[![Unit Tests & JaCoCo Coverage](https://github.com/LeonidGorbunov/java-unit-testing-burger/actions/workflows/tests.yml/badge.svg)](https://github.com/LeonidGorbunov/java-unit-testing-burger/actions/workflows/tests.yml)
[![Allure Report](https://img.shields.io/badge/Allure%20Report-Live-brightgreen)](https://leonidgorbunov.github.io/java-unit-testing-burger/)
# Java Unit Testing Burger Project

**Контекст и цели проекта**: разработка изолированных модульных тестов для верификации калькуляции стоимости, структуры чеков и внутренней логики списков сборной модели данных.

**ТЗ (вид работ)**: модульное тестирование (Unit Testing), параметризация данных, Mock-изоляция (Mockito), верификация множественных условий (ErrorCollector).

**Продукт**: консольный Java-модуль «Конструктор бургеров» (калькуляция стоимости и чеков).

**Выполненные задачи**:
1. Моделирование и изоляция (Mocking): обеспечена 100% изоляция класса `Burger` от зависимостей `Bun` и `Ingredient` через генерацию гибких Mock-объектов.
2. Комплексная параметризация: спроектирована параметризованная матрица тестов (JUnit 4) для сквозной валидации формул подсчёта стоимости, включая проверку граничных значений (BVA), нулевых цен и обработки отрицательных диапазонов.
3. Верификация логики массивов: написаны тесты на методы манипуляции со списками (`addIngredient`, `removeIngredient`, `moveIngredient`).
4. Мягкие проверки (Soft Assertions): для теста перестановки элементов применён механизм `ErrorCollector`, предотвращающий досрочное падение теста при падении первого шага.
5. Строковая валидация: реализован тест метода формирования чека (`getReceipt`) с учётом системных разделителей строк `%n` и явным форматированием числовых типов под `Locale` окружения.
6. Тестовое покрытие (Code Coverage): достигнуто 100% покрытие кода (Line/Branch Coverage) с помощью плагина JaCoCo.

**Область тестирования (Scope)**: логика перестановки и удаления элементов динамических списков, строковое форматирование отчётов, математическая корректность методов калькуляции.

**Окружение**: Java (JDK 11), JUnit 4, Mockito, Maven, JaCoCo Compiler Plugin.

### Метрика тестового покрытия JaCoCo (100% Coverage Verification)
![JaCoCo Code Coverage Report](jacoco-coverage.png)

### 📊 Интерактивный отчёт о покрытии (JaCoCo) и CI/CD

* **Отчёт JaCoCo (100% покрытие):** [Открыть JaCoCo Report на GitHub Pages](https://leonidgorbunov.github.io/java-unit-testing-burger/)
* **Автоматический прогон в облаке:** в репозиторий интегрирован пайплайн [GitHub Actions](.github/workflows/tests.yml), выполняющий `mvn clean test jacoco:report` на JDK 11 с публикацией HTML-отчёта в ветку `gh-pages`.

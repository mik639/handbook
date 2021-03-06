# Handbook

## 1. Общее
#### 1.1. Чтобы смерджить pull request надо набрать минимум 2 святых и 3 обычных апрува.
#### 1.2. Для проекта GlassesUSA используем только цвета из стайл гайда в avocode и создаем переменные места использования.
#### 1.3. Используем idx для обращения к свойствам с глубокой вложенность. Удаляем после Babel 7.
#### 1.4. Создавая новый контейнер, стараемся дробить на реиспользуемые компоненты (кладем их в __helpers) компоненты которые пренадлежат только этому контейнеру кладем в папку с его именем в components (плоско, без вложенностей). Пример:

	components/
	  reviews/
        reviewsItem/
        reviewsList/
	containers/
	  reviews/
		
#### 1.5. Истиной в код стайле является Prettier.
#### 1.6. Название файлов пишем через camelCase.
	
## 2. React
#### 2.1. Используем stateless компоненты когда надо и аккуратно.
#### 2.2. Не используем default экспорт в компонентах.

## 3. Redux
#### 3.1. В законнекченных компонентых используем mapStateToProps и mapDispatchToProps.
#### 3.2. Рядом с редьюсерами создаем файл с типом.
#### 3.3. Рядом с редьюсерами создаем файл с фикстурой.
#### 3.4. Создавать InitialState в соответствии Flow type редюсера.
#### 3.5. Не сохранять полностью весь payload, а выбирать необходимые данные.
#### 3.6. Для connected компонентов используем имя ComponentNameConnected.

## 4. Тесты
#### 4.1. Каждый новый компонент должен быть покрыт тестами на 100%.
#### 4.2. Больше не используем nock, sinon для тестов экшенов.

## 5. Селекторы
#### 5.1. В селекторах созданых с помощью createSelector, мы тестируем только результирующую функцию(последний аргумент). Для этого используем метод "resultFunc()" у созданного селектора. Пример:
	test('getCartItemOptions', () => {
	  const quoteItem = {test: '100500'};
	  const result = cartSelectors.getCartItemOptions.resultFunc(quoteItem);
	  expect(result).toEqual(CustomOptionsFixture);
	});
#### 5.2. Осторожно использовать selectors with props и внимательно читать документацию.

## 6. Flow
#### 6.1. Имена для типов даем через CamelCase + Type. Пример: CriteoEventType.
	
## 7. Стили
#### 7.1. Используем react-responsive в связке с custom-media postCSS плагином для адаптивного дизайна.
		

# Как писать новую фичу

1. Создаем папку для фичи (см. в каком числе название - products или product)
2. Создаем папку для типов - types
3. Создаем типы:
- Action - не нужно создавать - они будут созданы автоматически
- Product - создать тип для сущности с которой мы работаем
- ProductsState - тип нашего централизованного состояния - 
- чаще всего - это интерфейс для объекта ключом которого является массив
```
{
  products: Product[];
} 

```
4. создаем файл api.ts - этот файл отвечает за связь с сервером - внутри него - мы будем делать фетч запросы
```
// GET - метод для получения данных
// внутри треугольных скобок пишем то, что по факту приходит с бэка
// функция возвращает промис - это не ошибка
// мы будем с этим промисом работать и в зависимости от его состояния
// будут разные сценарии действие
// fullfiled - удовлетворен - со значением
// rejected - отвергнут - с ошибкой
// pending - ожидается - пока еще не определился fullfiled | rejected
```

5. Пишем слайс productsSlice.ts
- пропишем initial state
- прописываем асинк санк - по одному на каждую функцию из файла api
- пишем слайс
- экспортируем

6. Пишем компонент и используем useAppDispatch и useAppSelector
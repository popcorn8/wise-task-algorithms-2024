# Модуль. Выделенное ребро является критическим

Выделенное ребро является критическим, то есть его удаление уменьшает k-связность графа.

Выделять ребро следует синим цветом (blue).

## Внешние зависимости

Добавьте в ваш проект следующие зависимости:

1. math-system
   - Скачайте файл `math-system-1_0-SNAPSHOT.jar` и добавьте его в ваш проект в папку `lib`.
   - При необходимости обновите путь к файлу в файле `pom.xml`.
  
   ```xml
    <project ...>
        ...
        <dependencies>
            <dependency>
                <groupId>com.example</groupId>
                <artifactId>math-system</artifactId>
                <version>1.0-SNAPSHOT</version>
                <scope>system</scope>
                <type>jar</type>
                <!-- Измените следующий путь, при обновлении пакета math-system -->
                <systemPath>${project.basedir}/libs/math-system-1_0-SNAPSHOT.jar</systemPath> 
            </dependency>
            ...
        </dependencies>
    </project>
   ```
   
## Описание алгоритма

### `execute(Graph graph)`

Этот метод выполняет алгоритм для определения изменения реберной связности графа после удаления помеченного ребра.

- Сначала он находит помеченное ребро, перебирая все ребра графа и ища среди них ребро, помеченное синим цветом.
- Затем метод определяет реберную связность исходного графа, используя функцию `findKConnectivityOfGraph(graph)`.
- После этого метод удаляет помеченное ребро из графа и снова находит реберную связность без этого ребра.
- Если реберная связность изменилась, возвращается `true`, иначе `false`.

### `getSuperSetOfEdges(List<Edge> edges)`

Этот метод генерирует надмножество всех возможных подмножеств ребер. Он используется для поиска реберной связности графа. 
- Метод перебирает все подмножества ребер, используя битовые маски, и добавляет их в список.
- После этого он сортирует полученные подмножества по размеру в порядке убывания и возвращает список всех подмножеств ребер.

### `findKConnectivityOfGraph(Graph graph)`

Этот метод находит реберную связность графа. 
- Сначала он получает список всех ребер графа и вызывает метод `getSuperSetOfEdges(graph.getEdges())` для получения всех подмножеств ребер.
- Затем метод проверяет каждое подмножество ребер, удаляя их из графа и проверяя связность графа с помощью метода `isGraphConnected(graph)`.
   - Если граф перестаёт быть связным после удаления некоторого подмножества ребер, то реберная связность равна разности количества ребер и размера этого подмножества.

### `isGraphConnected(Graph graph)`

Этот метод проверяет, является ли граф связным. Он использует поиск в глубину (DFS) для определения связности графа.
- Сначала он выбирает первую вершину графа и запускает поиск в глубину из нее.
- После этого метод проверяет, были ли посещены все вершины графа.
-  Если да, то граф связный, и метод возвращает `true`, в противном случае - `false`.

Таким образом работает модуль проверки на то, является ли выделённое ребро критическим.

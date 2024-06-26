# wise-task-algorithms-2024

## 1. Информация о модуле

| Название модуля  | Имя студента разрабатывающего модуль | Имя студента тестирующего модуль | Капитан команды   |
| ------------- | ------------- |----------------------------------|-------------------|
| Граф является 2-нечетно связным | Медведский Даниил  | Мещеряков Радомир | Тищенко Артём |



## 2. Двусвязный граф

Двусвязный граф — это связный и неделимый граф, в том смысле, что удаление любой вершины и всех инцидентных ей рёбер не приведёт к потере связности.
Теорема Уитни утверждает, в частности, что граф двусвязен тогда и только тогда, когда между любыми двумя его вершинами есть минимум два непересекающихся пути.

Таким образом, тобы проверить двусвязность, достаточно удостовериться, что при удалении любой вершины (и всех инцидентных ей рёбер) из всех оставшихся вершин во все другие оставшиеся будет хотябы один путь.

## 3. Написание модуля
Описание методов класса TwoOddCon
```java
public class TwoOddCon implements GraphProperty {
    public Map<Vertex, List<Edge>> getVerticesEdges(Graph graph) {}
    // Метод, возвращающий словарь (вершина: лист инцедентных рёбер)
    public List<UUID> getListEdges(Map<Vertex, List<Edge>> map, Vertex vertex) {}
    // Метод, возврвщвющий список всех UUID вершин, смежных с заданной.
    public Map<Vertex, List<Edge>> delete(Graph graph, Map<Vertex, List<Edge>> map, Vertex vertex) {}
    // Метод, удаляющий из словаря поданную вершину и все инцидентные ей рёбра. 
    public List<Vertex> neighbors(Graph graph, HashMap<Vertex, List<Edge>> map, Vertex vertex) {}
    // Метод, возвращающий список смежных вершин дял поданной вершины.
    public HashMap<Vertex, Double> BellmanFord(Graph graph, HashMap<Vertex, List<Edge>> map, Vertex start) {}
    // Алгоритм Беллмана-Форда.
    @Override
    public boolean execute(Graph graph) {}
    // Главный (исполняемый) метод, удаляющий поочерёдно вершины и инцедентные ей рёбра
    // и запускающий после каждого раза алгоритм Беллмана-Форда.
    // Если хоть один путь в полученном списке равен бесконечности, значит граф стал несвязным.
}
```


## 4. О разработчике
![img1.png](../priests-of-absolute-chaos.png) https://vk.com/priests_of_absolute_chaos

https://www.youtube.com/@priests-of-absolute-chaos

# Iterador
El siguiente proyecto muestra un ejemplo de Iterador en python
Desarrollado por: 
Andres Felipe Reyes García 20142020103
Camilo Ramirez Alarcon 20142020078
Daniel Camargo 20142020094
<pre><code>
import abc

class Item:
    def __init__(self, name, price):
        self.name = name
        self.price = price

    def __str__(self):
        return "{}: $ {}".format(self.name, self.price)

class MenuIterator:
    def __init__(self, items):
        self.indx = 0
        self.items = items

    def has_next(self):
        return False if self.indx >= len(self.items) else True

    def next(self):
        item = self.items[self.indx]
        self.indx += 1
        return item

    def remove(self):
        return self.items.pop()

class Menu:
    def __init__(self):
        self.items = []

    def add(self, item):
        self.items.append(item)

    def iterator(self):
        return MenuIterator(self.items)

if __name__ == '__main__':
    i1 = Item("spaghetti", 7.50)
    i2 = Item("hamburger", 6.00)
    i3 = Item("chicken sandwich", 6.50)

    menu = Menu()
    menu.add(i1)
    menu.add(i2)
    menu.add(i3)

    print("Displaying Menu:")
    iterator = menu.iterator()

    while iterator.has_next():
        item = iterator.next()
        print(item)

    print("Removing last item returned")
    iterator.remove()

    print("Displaying Menu:")
    iterator = menu.iterator()
    while iterator.has_next():
        item = iterator.next()
        print(item)
</pre></code>
## Model

![Model](ModeloIterador.png)

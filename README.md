class Jacket:
    def __init__(self, brand, size, price):
        self.brand = brand
        self.size = size
        self.price = price


class JacketStore:
    def __init__(self): 
        self.stock = []

    def add_jacket(self, brand, size, price):
        jacket = Jacket(brand, size, price)
        self.stock.append(jacket)
        print("Был добавлен :" + brand + ' ' + str(price) + ' ' + str(size))

    def display_stock(self):
        if self.stock == []:
            print("На складе нету ничего")
        else:
            print("Вот куртка:")
            for jacket in self.stock:
                print(jacket.brand, jacket.size, jacket.price)

    def buy_jacket(self, brand, size):
        for jacket in self.stock:
            if jacket.brand == brand and jacket.size == size:
                self.stock.remove(jacket)
                print("Ты купил:" + brand + ' ' + str(size))
                return
        print("Такого бренда нет в наличии")


store = JacketStore()
store.add_jacket('Nike', 'xs', 20000)
store.add_jacket('Adidas', 'l', 15000)
store.add_jacket('Supreme', 'm', 40000)

store.display_stock()

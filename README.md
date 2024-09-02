# ООП часть 2. Интерфейсы и полиморфизм

> Привет! На связи домашнее задание урока 2.2. ООП.

Ниже вам даны несколько блоков кода. Ваша задача — поправить код так, чтобы он учитывал изученные принципы ООП.
Обязательные для выполнения блоки кода

1-й блок кода. Пример с велосипедом


public class Bicycle {
    public String modelName;
    public int wheelsCount;
    public void updateTyre() {
        System.out.println("Меняем покрышку");
    }
}

2-й блок кода. Пример с машиной


public class Car {
    public String modelName;
    public int wheelsCount;
    public void updateTyre() {
        System.out.println("Меняем покрышку");
    }
    public void checkEngine() {
        System.out.println("Проверяем двигатель");
    }
}

3-й блок кода. Пример с сервисной станцией


public class ServiceStation {
    public void check(Car car, Bicycle bicycle, Truck truck) {
        if (car != null) {
            System.out.println("Обслуживаем " + car.modelName);
            for (int i = 0; i < car.wheelsCount; i++) {
                car.updateTyre();
            }
            car.checkEngine();
        } else if (truck != null) {
            System.out.println("Обслуживаем " + truck.modelName);
            for (int i = 0; i < truck.wheelsCount; i++) {
                truck.updateTyre();
            }
            truck.checkEngine();
            truck.checkTrailer();
        } else if (bicycle != null) {
            System.out.println("Обслуживаем " + bicycle.modelName);
            for (int i = 0; i < bicycle.wheelsCount; i++) {
                bicycle.updateTyre();
            }
        }
    }
}

4-й блок кода. Пример с грузовой машиной


public class Truck {
    public String modelName;
    public int wheelsCount;
    public void updateTyre() {
        System.out.println("Меняем покрышку");
    }
    public void checkEngine() {
        System.out.println("Проверяем двигатель");
    }
    public void checkTrailer() {
        System.out.println("Проверяем прицеп");
    }
}

5-й блок кода. Общий пример


public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        Car car2 = new Car();
        car.modelName = "car1";
        car2.modelName = "car2";
        car.wheelsCount = 4;
        car2.wheelsCount = 4;
        Truck truck = new Truck();
        Truck truck2 = new Truck();
        truck.modelName = "truck1";
        truck2.modelName = "truck2";
        truck.wheelsCount = 6;
        truck2.wheelsCount = 8;
        Bicycle bicycle = new Bicycle();
        Bicycle bicycle2 = new Bicycle();
        bicycle.modelName = "bicycle1";
        bicycle2.modelName = "bicycle2";
        bicycle.wheelsCount = 2;
        bicycle2.wheelsCount = 2;
        ServiceStation station = new ServiceStation();
        station.check(car, null, null);
        station.check(car2, null, null);
        station.check(null, bicycle, null);
        station.check(null, bicycle2, null);
        station.check(null, null, truck);
        station.check(null, null, truck2);
    }
}

# Критерии оценки по всем заданиям
  – В исправленном коде применен принцип полиморфизма.
  – В исправленном коде применен принцип наследования.
  – В исправленном коде применен принцип инкапсуляции.
  – В исправленном коде применена перегрузка методов.

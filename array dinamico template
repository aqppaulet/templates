#include <iostream>
#include <string>

template <typename T>
class DynamicArray {
private:
    T* data;
    int size;

public:
    DynamicArray() {
        data = new T[0];
        size = 0;
    }

    DynamicArray(int size, T arr[]) {
        data = new T[size];
        this->size = size;
        for (int i = 0; i < size; i++) {
            data[i] = arr[i];
        }
    }

    DynamicArray(const DynamicArray& o) {
        data = new T[o.size];
        size = o.size;
        for (int i = 0; i < o.size; i++) {
            data[i] = o.data[i];
        }
    }

    void print() const {
        std::cout << "[";
        for (int i = 0; i < size; i++) {
            std::cout << data[i] << " ";
        }
        std::cout << "]" << std::endl;
    }

    int count() const {
        return size;
    }

    void pushback(T v) {
        T* tmp = new T[size + 1];
        for (int i = 0; i < size; i++) {
            tmp[i] = data[i];
        }
        delete[] data;
        size++;
        data = tmp;
        data[size - 1] = v;
    }

    void insert(T v, int pos) {
        T* tmp = new T[size + 1];
        for (int i = 0; i < pos - 1; i++) {
            tmp[i] = data[i];
        }
        for (int i = pos - 1; i < size; i++) {
            tmp[i + 1] = data[i];
        }
        delete[] data;
        size++;
        data = tmp;
        data[pos - 1] = v;
    }

    void remove(int pos) {
        T* tmp = new T[size - 1];
        for (int i = 0; i < pos - 1; i++) {
            tmp[i] = data[i];
        }
        for (int i = pos; i < size; i++) {
            tmp[i - 1] = data[i];
        }
        size--;
        delete[] data;
        data = tmp;
    }

    int search(const T& value) const {
        for (int i = 0; i < size; i++) {
            if (data[i] == value) {
                return i;
            }
        }
        return -1;
    }

    T& operator[](int index) {
        return data[index];
    }

    const T& operator[](int index) const {
        return data[index];
    }

    ~DynamicArray() {
        delete[] data;
    }
};

int main() {
    int z[] = { 10, 5 };
    DynamicArray<int> a(2, z);
    a.print();
    a.pushback(6);
    a.print();
    a.insert(7, 2);
    a.print();
    a.remove(2);
    a.print();
    a.remove(2);
    a.print();

    double y[] = { 3.14, 2.718 };
    DynamicArray<double> b(2, y);
    b.print();
    b.pushback(1.618);
    b.print();
    b.insert(2.236, 2);
    b.print();
    b.remove(1);
    b.print();
    b.remove(1);
    b.print();

    char e[] = { 'A', 'B', 'C' };
    DynamicArray<char> c(3, e);
    c.print();
    c.pushback('D');
    c.print();
    c.insert('E', 2);
    c.print();
    c.remove(1);
    c.print();
    c.remove(1);
    c.print();

    std::string f[] = { "Arriba", "melgar" };
    DynamicArray<std::string> d(2, f);
    d.print();
    d.pushback("!");
    d.print();
    d.insert("Campeon", 2);
    d.print();
    d.remove(1);
    d.print();
    d.remove(1);
    d.print();

    int indexA = a.search(5);
    if (indexA != -1) {
        std::cout << "El Elemento 5 se encontro en el texto" << indexA << " en el arreglo a" << std::endl;
    } else {
        std::cout << "El Elemento 5 no se encontro en el texto "<< std::endl;
    }

    int indexD = b.search(2.718);
    if (indexD != -1) {
        std::cout << "El Elemento 2.718 se encontro en el texto con el indice" << indexD << " in array b" << std::endl;
    } else {
        std::cout << "El Elemento 2.718 no se encontro  en el arreglo b" << std::endl;
    }

    int indexF = d.search("melgar");
    if (indexF != -1) {
        std::cout << "El Elemento  \"melgar\" se encontro en el texto con el indice " << indexF << " in array d" << std::endl;
    } else {
        std::cout << "El Elemento  \"melgar\" no se encontro  en el arreglod" << std::endl;
    }

    return 0;
}

# Clases

```java
public class Bebida {
    // Atributos
    private String sabor; 
    private String color;
    private int precio;
    public String etiqueta;

    public Bebida(String color, String sabor) {
        // hemos inicializado los atributos.
        // El this sirve para referenciar atributos o métodos de la propia clase

        // this.color recibe el valor del argumento color del constructor

        this.color = color;
        this.sabor = sabor;
        this.precio = 13;
        this.etiqueta = "";

    }
    /*
    en los métodos es necesaria la visibilidad (public / private)
    Si es static o no
    el tipo de atributo que retorna
    el nombre del método seguido de paréntesis
    los argumentos que reciba el método separados por comas
    y cada uno de ellos precedidos de su tipo

    */
    public void mostrarEtiqueta() {
        System.out.println("Mi etiqueta es " + this.etiqueta);
    }

    public String toString() {
        return "Mi bebida es " + this.color + " y sabe "  + this.sabor;
    }
}


public class Programa {
    public static void main(String[] args) {
        // Construimos una variable donde almacenar nuestra bebida llamada bebida1.Para construir una variable primero ponemos su tipo, depués el nombre de la variable y si es una clase, para crear el objeto tenemos que poner new delante seguido del constructor con sus argumentos fijándonos bien que sean del mismo tipo definidos en la clase. 
        Bebida bebida1 = new Bebida("rojo", "dulce");

        // Siempre podemos acceder a los elementos públicos definidos en la clase, ya sean atributos o métodos. Nos referiremos a ellos poniendo la variable que almacena el objeto seguido de un punto y el nombre del atributo o método
        bebida1.etiqueta = "cuadrada";
        bebida1.mostrarEtiqueta();
        System.out.println(bebida)

    }
}
```
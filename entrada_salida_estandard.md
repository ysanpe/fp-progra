# Salida estándar de sistema
```
System.out.println
```

System es una clase a la que se puede llamar sin importar su paquete ya que pertenece al java Standard
out.println son atributos estáticos de la clase System 
println imprime por salida estándar un String

## Ejemplo salida estándar de sistema
```java
System.out.println("Hola, mundo!"); 
```


# Entrada estándar de sistema

Para leer datos de la entrada estándar de sistema (normalmente el teclado) java usa tambien la clase System, pero en este caso en vez de usar System.out utilizará System.in (flujo de entrada estándar).
Para leer de este flujo, es necesario utilizar la clase Scanner.

Scanner recibe en el constructor un stream, podría ser de teclado o de otros tipos. Estos streams tienen que ser de tipo InputStream.

## Ejemplo entrada estándar de sistema

```java
// importamos la clase Scanner del paquete java.util. Java es un paquete y util otro paquete dentro de java
import java.util.Scanner;

public class EntradaDeTeclado {
    // variable de tipo string que almacenara la entrada de texto que se lea de teclado
    private String entradaTexto;
        
    // variable de tipo entero que almacenara la entarda de texto que se lea de teclado OJO pero la convertira a int asi que tiene que ser un entero
    private int entradaNumero;
    
    // variable de tipo scaner que nos ayuda a buscar en un stream (flujo) de texto
    private Scanner entradaEscaner;
        
    // constructor de la clase entrada de teclado se inicializan las variables privadas propias de la clase
    // fijate que uso "this" para referirme a las variables de esta clase no otras cualquiera
    public EntradaDeTeclado() {
        // inicializo la entrada de texto a string vacio ("")
        this.entradaTexto = "";
           
        // inicializo la entrada para numeros a cero (0)
        this.entradaNumero = 0;
            
        // inicializo un scanner para leer de teclado
        this.reInicializarEscaner();
        }

    public void reInicializarEscaner() {
        this.entradaEscaner = new Scanner(System.in);
    }
    
    public void pedirEntradaTexto() {
        // uso el scanner para leer de la entrada estándar de sistema un string y lo almaceno en entradaTexto
        this.reInicializarEscaner();
        this.entradaTexto = this.entradaEscaner.nextLine();
    }
    
    public void pedirEntradaNumero() {
        // uso el scanner para leer de la entrada estándar de sistema un entero y lo almaceno en entradaNumero
        this.reInicializarEscaner();
        this.entradaNumero = this.entradaEscaner.nextInt();
    }
    
    
    public String getEntradaTexto() {
        // metodo que devuelve la entrada de tipo texto
        return this.entradaTexto;
        }
    
    public int getEntradaNumero() {
        // metodo que devuelve la entrada de tipo numero
        return this.entradaNumero;
    }
}



public class Principal { 
    
    public static void main (String[] args) { 
        // creo mi lector de teclado
        EntradaDeTeclado teclado = new EntradaDeTeclado() ;
        
        // creo las variables que van a almacenar las entradas de teclado
        // de tipo entero y de tipo texto
        int numero1;
        String numero2; 
        
        // leo la primera entrada y la leo de tipo numerico asi que la almaceno en una variable numerica
        System.out.println("Introduce un número");
        teclado.pedirEntradaNumero();
        numero1 = teclado.getEntradaNumero();
        
        // leo la segunda entrada y la leo de tipo texto asi que la almaceno en una variable tipo string
        System.out.println("Introduce otro número");
        teclado.pedirEntradaTexto();    
        numero2 = teclado.getEntradaTexto();

        // muestro las entradas
        System.out.println("La variable numero1 vale " + numero1);
        System.out.println("La variable numero2 vale " + numero2);
    }
       
}
```
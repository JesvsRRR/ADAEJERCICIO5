# 1. Formulación del problema

<p align="center">
  <img src="image.png" alt="Imagen del ejercicio n°5" />
</p>

# 2. Resolución

> I) Entrada del valor de la variable "dimension"

- Se importa la clase `Scanner` del paquete `java.util` para poder leer datos desde la entrada estándar y darle valor a la variable `"d"`.

```bash
import java.util.Scanner;
```

```bash
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Ingresar dimension [d]: ");
        int d = sc.nextInt();
        
        if(d <= 0){
           d = sc.nextInt();;
        }
```

> II) Ingreso de numeros a la matriz cuadrada

- Se llama a la función `Verificar_Simetria(d)` que utilizara la variable `"d"`.
- Se inicializa la matriz cuadratica `Matriz[d][d]` y una variable contadora `Sino`.
- Se procede a ingresar el valor numerico a cada matriz cuadratica. 

```bash
    Verificar_Simetria(d);
```

```bash
public class Main {
    public static void Verificar_Simetria(int d){
    Scanner sc = new Scanner(System.in);
    int[][] Matriz = new int[d][d];
    int SiNo = 0;
    
    for(int i=0; i < d; i++){
        
        for(int j=0; j < d;j++){
            System.out.print("["+i+"]"+"[" + j+"]");
            Matriz[i][j] = sc.nextInt();           
        }
    }
```
> III) Comprobación de la existencia de la matriz simetrica, impresión de la matriz cuadratica y la verificación de la simetria como dato de salida

- En algebra, podemos definir una matriz como simetrica si entre la diagonal principal que envuelve lados de izquierda y derecha tiene valores igual como si se tratase de un espejo. En ese caso se realiza otro recorrido donde se imprime y se compara estos lados que se presumen iguales de la matriz `"Matriz[d][d]"`, si fuese el caso se suma 1 a la variable `SiNo`.
- Si despues del recorrido la variable `SiNo` es igual a `"d"` al cuadrado, entonces la matriz es simetrica y se imprime,igualmente si fuera el caso contrario.

```bash
    for(int i=0; i < d;i++){
        for(int j=0; j < d;j++){
           System.out.print("["+Matriz[i][j]+"]");
           if(Matriz[j][i] == Matriz[i][j]){
           SiNo++;   
           }
        }
        System.out.println(""); 
    }
    if(SiNo == d*d){
    System.out.println("ES SIMETRICO");    
    }
    else{
    System.out.println("NO ES SIMETRICO");   
    }
    
    }
```

### Codigo completo
```bash
import java.util.Scanner;

public class Main {
    public static void Verificar_Simetria(int d){
    Scanner sc = new Scanner(System.in);
    int[][] Matriz = new int[d][d];
    int SiNo = 0;
    
    for(int i=0; i < d; i++){
        
        for(int j=0; j < d;j++){
            System.out.print("["+i+"]"+"[" + j+"]");
            Matriz[i][j] = sc.nextInt();           
        }
    }    
    
    for(int i=0; i < d;i++){
        for(int j=0; j < d;j++){
           System.out.print("["+Matriz[i][j]+"]");
           if(Matriz[j][i] == Matriz[i][j]){
           SiNo++;   
           }
        }
        System.out.println(""); 
    }
    if(SiNo == d*d){
    System.out.println("ES SIMETRICO");    
    }
    else{
    System.out.println("NO ES SIMETRICO");   
    }
    
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Ingresar dimension [d]: ");
        int d = sc.nextInt();
        
        if(d <= 0){
           d = sc.nextInt();;
        }
        Verificar_Simetria(d);        
    }
}
```

# 3. Complejidad

> I) Entrada del valor de la variable "dimension"

- Complejidad de tiempo: 𝑂(1) (Porque se realiza una lectura simple, en el peor caso seria 𝑂(k) si se ingresan multiples valores incorrectos)
- Complejidad de espacio: 𝑂(1) (Porque solo estamos utilizando una variable escalar)

> II) Ingreso de numeros a la matriz cuadrada

- Complejidad de tiempo: 𝑂(d²) (Debido a que se realiza un recorrido en bucle doble más de una vez)
- Complejidad de espacio: 𝑂(d²) (Debido a la implementación de una estructura de datos bidimensional)

> III) Comprobación de la existencia de la matriz simetrica, impresión de la matriz cuadratica y la verificación de la simetria como dato de salida

- Complejidad de tiempo: 𝑂(d²) (La complejidad total es la suma de las dos partes 𝑂(d²) + 𝑂(d²) = 𝑂(d²) )
- Complejidad de espacio: 𝑂(d²) (Ya que solo almacenamos una matriz de tamaño d x d, osea una estructura bidimensional)

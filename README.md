class Platillo {
    protected String nombre;
    protected double precio;
    protected String descripcion;

    // Constructor
    public Platillo(String nombre, double precio, String descripcion) {
        this.nombre = nombre;
        this.precio = precio;
        this.descripcion = descripcion;
    }

    // Método para mostrar información del platillo
    public void mostrarInformacion() {
        System.out.println("Platillo: " + nombre);
        System.out.println("Precio: $" + precio);
        System.out.println("Descripción: " + descripcion);
    }
}

// Subclase Entrada
class Entrada extends Platillo {
    private boolean esFria;

    public Entrada(String nombre, double precio, String descripcion, boolean esFria) {
        super(nombre, precio, descripcion);
        this.esFria = esFria;
    }

    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("Tipo: " + (esFria ? "Fría" : "Caliente"));class PlatoFuerte extends Platillo {
    private int nivelPicante;

    public PlatoFuerte(String nombre, double precio, String descripcion, int nivelPicante) {
        super(nombre, precio, descripcion);
        this.nivelPicante = nivelPicante;
    }

    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("Nivel de Picante: " + nivelPicante + "/5");
    }
}
    }
}

// Subclase PlatoFuerte
class PlatoFuerte extends Platillo {
    private int nivelPicante;

    public PlatoFuerte(String nombre, double precio, String descripcion, int nivelPicante) {
        super(nombre, precio, descripcion);
        this.nivelPicante = nivelPicante;
    }

    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("Nivel de Picante: " + nivelPicante + "/5");
    }
}

// Subclase Postre
class Postre extends Platillo {
    private boolean contieneAzucar;

    public Postre(String nombre, double precio, String descripcion, boolean contieneAzucar) {
        super(nombre, precio, descripcion);
        this.contieneAzucar = contieneAzucar;
    }

    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion();
        System.out.println("Contiene Azúcar: " + (contieneAzucar ? "Sí" : "No"));
    }
}

// Clase principal para probar la herencia
public class Restaurante {
    public static void main(String[] args) {
        Entrada entrada = new Entrada("Bruschetta", 5.99, "Pan tostado con tomate y albahaca", true);
        PlatoFuerte platoFuerte = new PlatoFuerte("Tacos al Pastor", 12.99, "Tacos de cerdo con piña y salsa", 3);
        Postre postre = new Postre("Pastel de Chocolate", 6.50, "Bizcocho de chocolate con crema", true);

        System.out.println("--- Menú del Restaurante ---");
        entrada.mostrarInformacion();
        System.out.println();
        platoFuerte.mostrarInformacion();
        System.out.println();
        postre.mostrarInformacion();
    }
}

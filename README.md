package proyecto_programacion;

public class personajes {
	 private String nombre;
	 private int nivelActual;
	 private int saludActual;
	 
	 public personajes (String nombre, int nivelActual,int saludActual) {
		this.nombre=nombre;
		this.nivelActual=nivelActual;
		this.saludActual=saludActual;
	 }

	    public String getNombre() {
	        return nombre;
	    }
	 
	    public int getSaludActual() {
	        return saludActual;
	    }
	 
	    public int getNivel() {
	        return nivel;
	    }
	 
	    public boolean estaInhabilitado() {
	        return saludActual <= 0;
	    }
	 
	    /**
	     * Calcula el valor del ataque según el nivel del personaje.
	     * Si la salud es cero, el personaje está inhabilitado y el ataque vale cero.
	     */
	    public int generaAtaque() {
	        if (estaInhabilitado()) {
	            return 0;
	        }
	        return nivel * 10;
	    }
	 
	    /**
	     * Calcula el daño recibido y reduce la salud actual.
	     * Si la salud llega a cero, el personaje queda inhabilitado.
	     */
	    public void recibeAtaque(int ataque) {
	        if (estaInhabilitado()) {
	            return;
	        }
	        int dano = Math.max(0, ataque);
	        reducirSalud(dano);
	    }
	 
	    protected void reducirSalud(int dano) {
	        saludActual = Math.max(0, saludActual - dano);
	    }
	 
	    @Override
	    public String toString() {
	        return nombre + " (Nivel " + nivelActual + ", Salud " + saludActual + ")";
	    }
	}
	 
	

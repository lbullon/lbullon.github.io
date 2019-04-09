## Bienvenidos a un tutorial sobre inyección de Dependencias

Para ello en primer lugar crearemos un proyecto con dos clases:
```markdown
public class Disco {
	public Disco() {
		
	}
	private Autor autor;
	private String titulo;
	private String fechaLanzamiento;
	public String getNombre() {
		return titulo;
	}
	public void setNombre(String nombre) {
		this.titulo = nombre;
	}
	public String getFechaLanzamiento() {
		return fechaLanzamiento;
	}
	public void setFechaLanzamiento(String fechaLanzamiento) {
		this.fechaLanzamiento = fechaLanzamiento;
	}
	public Autor getAutor() {
		return autor;
	}
	public void setAutor(Autor autor) {
		this.autor = autor;
	}


}

public class Autor {
	private String nombre;
	private String nacionalidad;

public Autor() {
	
};
public String getNombre() {
	return nombre;
}
public void setNombre(String nombre) {
	this.nombre = nombre;
}
public String getNacionalidad() {
	return nacionalidad;
}
public void setNacionalidad(String nacionalidad) {
	this.nacionalidad = nacionalidad;
}

}

```


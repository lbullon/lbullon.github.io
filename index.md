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
## Explicación

Como vemos hemos desarrollado dos clases, una sobre disco y otra sobre autor. Vemos que en la clase de Disco , que a su vez
tiene dentro una clase Autor.

Pero para crear la inyección de dependencia vamos a realizar un xml
En el que vamos a inyectar la dependencia en este caso de nombres de los atributos que componen los objetos.

```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
 xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
  http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.0.xsd">

    <bean id="Disco" class="">
        <property name="titulo" value="Lobos"/>
        <property name="autor" ref="autor"/>
        <property name="fechaLanzamiento" value="23/04/2018"/>

    </bean>

    <bean id="autor" class="">
        <property name="nombre" value="Leiva" />
        <property name="nacionalidad" value="Española" />
    </bean>
</beans>
```
Con esto ya crearíamos una dependencia de un tipo muy básico para que el autor sea uno concreto y el del autor sería tal.
Eso lo hacemos con los bean,

En el primer bean dentro del id tenemos que incrustar el nombre de la clase, en este caso Disco. Mientras que en la class, tendremos que poner la dirección donde está la clase.
Con esto ya habríamos creado una dependendencia.

<h1> Amigo Secreto</h1>


  let amigos = []; 
      Se inicializa un array vacío llamado amigos. Aquí se almacenarán todos los nombres que se agreguen.

Función agregarAmigo():
  let nombreAmigo = document.getElementById('amigo').value.trim(); 
      Obtiene el valor del campo de texto (el input) con el id="amigo" y usa .trim() para eliminar cualquier espacio en blanco al inicio o al final.

  if (nombreAmigo === '') { ... }
      Esta es la validación. Si el nombre está vacío (''), muestra una alerta con el mensaje "Por favor, ingrese un nombre válido" y detiene la ejecución de la función con return.

  if (amigos.includes(nombreAmigo)) { ... }
      Verifica si el nombre ya existe en la lista para evitar duplicados. Si es así, muestra una alerta y se detiene.

  amigos.push(nombreAmigo); 
      Si el nombre es válido, lo añade al final del array amigos.

  document.getElementById('amigo').value = '';
      Limpia el campo de texto después de agregar el nombre, dejándolo listo para el siguiente.

  mostrarListaAmigos();
      Llama a una función para actualizar la lista visualmente en la página.

Función mostrarListaAmigos():
    Esta función actualiza el <ul> con id="listaAmigos" para que muestre los nombres que se han agregado.

  amigos.map(amigo => <li>${amigo}</li>).join('')
      Itera sobre el array amigos, crea un elemento de lista (<li>) para cada nombre y luego los une en una sola cadena de texto.

  document.getElementById('listaAmigos').innerHTML = listaHTML;
      Inserta la cadena de HTML generada dentro del elemento <ul>.

Función sortearAmigo():
  
  if (amigos.length < 2) { ... }
      Valida que haya al menos dos nombres en la lista para poder hacer el sorteo. Si no, muestra una alerta.

  let indiceAleatorio = Math.floor(Math.random() * amigos.length);
      Genera un número entero aleatorio.

  Math.random() 
      Genera un número decimal entre 0 y 1.

  * amigos.length
      Lo escala para que esté entre 0 y el número total de amigos.

  Math.floor() 
      Redondea el resultado hacia abajo, asegurando que sea un número de índice válido para el array.

  let amigoSorteado = amigos[indiceAleatorio];
      Usa el índice aleatorio para seleccionar un nombre del array amigos.

  document.getElementById('resultado').innerHTML = ...
      Muestra el nombre del amigo sorteado dentro del <ul> con id="resultado", usando un formato de párrafo para que se vea claro en la página.
      

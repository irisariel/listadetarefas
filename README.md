# listadetarefas

# HTML


<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Minha Lista de tarefas</title>
<link rel="stylesheet" href="css_01.css">
  <script src="js.01.js" defer></script>

</head>

<body>
<div class="contador">
  <h1>Minha lista de tarefas</h1>
  <p>Não procrastine!</p>
<form id="form-tarefa">
  <input type="text" id="campo-tarefa" placeholder="Digite uma tarefa...">
<button type="submit">Adicionar
</button>
</form>
<ul id="lista-tarefas"></ul>

</div>
</body>
</html>


# CSS

body{
  font-family: Arial, Helvetica, sans-serif;
  background-color: #fff4e8;
  margin: 0;
  padding: 40px 20px;
}

.contador {
  background-color: white;
  max-width: 450px;
  margin: 0 auto;
  padding: 25px;
  border-radius: 12px;
  box-shadow: 0 4px 12px #00000015;
}

h1{
  color: #d96b27;
  text-align: center;
}

p{
  text-align: center;
  color: #666;
}

form{
  display: flex;
  gap: 8px;
}

input {
  flex: 1;
  min-width: 0;
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 6px;
  
}

button {
  background-color: #e87932;
  color: white;
  border: none;
  padding: 12px;
  border-radius: 6px;
  
}

#JS

const formulario = document.getElementById("form-tarefa");
const campo = document.getElementById("campo-tarefa");
const lista = document.getElementById("lista-tarefas");

formulario.addEventListener("submit", function(evento) {
    evento.preventDefault();

    if (campo.value === "") {
        return;
    }

    const tarefa = document.createElement("li");
    tarefa.textContent = campo.value;

    
    tarefa.addEventListener("click", function() {
        tarefa.classList.toggle("concluida");
    });

    tarefa.addEventListener("dblclick", function() {
        tarefa.remove();
    });

  
    lista.appendChild(tarefa);


    campo.value = "";
});

// to do: localstorage




# humberto1

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>lista de tarefas</h1>

    <input type="text"      id="nomeTarefa" placeholder="Digite a tarefa"><br><br>
    <input type="number"    id="prioridadeTarefa" placeholder="Prioridade da tarefa"><br><br>
    <input type="date"      id="dataTarefa"><br><br>
    
    <button onclick="cadastrarTarefas()">Cadastrar tarefa</button><br><br>
    <button onclick="ordenarNome()">ordenação nome </button><br><br>
    <button onclick="ordenarPrioridade()">ordenação prioridade</button><br><br>
    <button onclick="ordemDescendente()">Ordem alfabetica descendente</button><br><br>
    <button onclick="ordemPDescendente()">Ordem prioridade descendente</button><br><br>


    
    <script>


        var listaTarefas = [];

        function cadastrarTarefas(){


            let nomeTarefa = document.getElementById("nomeTarefa").value;
            let prioridadeTarefa = parseInt(document.getElementById("prioridadeTarefa").value);
            let dataTarefa =document.getElementById("dataTarefa").value;

            let novaTarefa = { nomeTarefa, prioridadeTarefa, dataTarefa};

            listaTarefas.push(novaTarefa);
            console.log(listaTarefas)
        }
    

        function ordenacaoNumerica(tarefaA, Tarefab){

            if(tarefaA.prioridadeTarefa > Tarefab.prioridadeTarefa)
                return 1; 
            if(tarefaA.prioridadeTarefa < Tarefab.prioridadeTarefa)
                return -1;
            return 0;
            }
        
    
        function ordenarPrioridade(){
            console.log(listaTarefas.sort(ordenacaoNumerica));

            

        }
    

        function ordenacaoString(tarefaA, Tarefab){

            if(tarefaA.nomeTarefa > Tarefab.nomeTarefa)
                return 1;
                if(tarefaA.nomeTarefa < Tarefab.nomeTarefa)
                    return -1;
                    return 0;
            }
            

        function ordenarNome(tarefaA, Tarefab){
           console.log(listaTarefas.sort(ordenacaoString));

        }
    

        function ordenacaoStringDesc(tarefaA, Tarefab){
            
            if(tarefaA.nomeTarefa < Tarefab.nomeTarefa)
                return 1;
                if(tarefaA.nomeTarefa > Tarefab.nomeTarefa)
                    return -1;
                    return 0;
            }

        
        function ordemDescendente(tarefaA, Tarefab){
            console.log(listaTarefas.sort(ordenacaoStringDesc));


        }

        function ordenacaoNumericaDesc(tarefaA, Tarefab){
            if(tarefaA.prioridadeTarefa < Tarefab.prioridadeTarefa)
                return 1; 
            if(tarefaA.prioridadeTarefa > Tarefab.prioridadeTarefa)
                return -1;
            return 0;
            }


        
        function ordemPDescendente(tarefaA, Tarefab) {
            console.log(listaTarefas.sort(ordenacaoNumericaDesc));
        }
    
    
    </script>
</body>
</html>

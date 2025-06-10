# AED
#include <stdio.h>
#include <stdlib.h>

typedef struct { // struct agrupa diferentes tipos de variaveis declaradas, como int, flt, db.
    
char titulo[100];
char categoria[100];
int prioridade;
int ativa;

} tarefa; // como struct cria diferentes tipos de variáveis, aqui a "tarefa" virou um "tipo de variável"

tarefa tarefas[10];
int total = 0;

void adicionartarefa() {

char titulo[100];
char categoria[100];
int prioridade;
int ativa;
    
printf("Digite o titulo da tarefa:\n");
scanf("%s", tarefas[total].titulo);
printf("Digite a categoria da tarefa:\n");
scanf("%s", tarefas[total].categoria);
printf("Digite a prioridade da tarefa:\n");
scanf("%d", &tarefas[total].prioridade);
tarefas[total].ativa = 1;
total++;
printf("Tarefa adicionada com sucesso!\n");

}

void listartarefas() { // void é usado p nao retornar nenhum valor

printf("Lista de tarefas:\n");
for(int i = 0; i < total; i++) {
    
printf("Tarefa(%d)\n",i);
printf("Titulo:%s\n",tarefas[i].titulo);
printf("Categoria:%s\n",tarefas[i].titulo);   
printf("Prioridade:%d",tarefas[i].prioridade);    

}
}

void editartarefas() {

int editar;
    
printf("Digite o numero da tarefa que deseja editar:\n");    
scanf("%d", &editar);

printf("Novo titulo:\n");
scanf("%s", tarefas[editar].titulo);
printf("Nova categoria:\n");
scanf("%s", tarefas[editar].categoria);

}

void excluirtarefa() {
    
int a;
    
printf("Qual tarefa deseja exlcuir?\n");    
scanf("%d", &a);
    
tarefas[a].ativa = 0;    

}


int main() {

int opcao;
    
do {
        printf("1. Adicionar tarefa\n");
        printf("2. Listar tarefas\n");
        printf("3. Editar tarefa\n");
        printf("4. Excluir tarefa\n");
        printf("0. Sair\n");
        printf("Escolha uma opção: ");
        scanf("%d", &opcao);
        switch (opcao) {
            case 1:
                adicionartarefa();
                break;
            case 2:
                listartarefas();
                break;
            case 3:
                editartarefas();
                break;
            case 4:
                excluirtarefa();
                break;
            case 0:
                break;
                
        }
        
    } while (opcao != 0);

    return 0;
    
}
